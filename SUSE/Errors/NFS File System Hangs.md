# Issue Overview

An [NFS mount appears to be hung or stalled indefinitely](https://www.suse.com/support/kb/doc/?id=000019722#:~:text=An%20NFS%20mount%20appears%20to%20be%20hung%20or%20stalled%20indefinitely.%20%C2%A0New%20NFS%20mount%20attempts%2C%20pointing%20to%20the%20same%20server%2C%20may%20also%20hang.) (New NFS mount attempts, pointing to the same server, may also hang)

* Network packet captures show that the NFS client is sending out packets destined to the NFS Server's port 2049, but no responses are seen (Often, but not always, this will take the form of a TCP SYN packet being sent but getting no reply)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Error Observations

## Connection Observations

* Evidence of the connection attempt may be seen on the NFS client machine with the `netstat -nt | grep :2049` and `ss -nt | grep :2049` commands
* If one or more connection show the status "SYN_SENT" for an extended period of time, then something is blocking these attempts (Normally, a connection will only be in this status for a fraction of a second, because the other side of the connection will reply and this status will change

## Log Observations

* There might also be occurences of `nfs: server <NFS_SERVER> not responding` messages in the NFS client machine's /var/log/messages
* However, packets on other connections (both new and old) between the same client machine and server machine may be having no problems (This is what sets this scenario apart from most other cases of "nfs: server not responding":  There is not a global problem effecting all communication between the two devices)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Potential Solutions

* If the problem has already occurred, reboot of the NFS client machine will likely be necessary (This could potentially solve the issue for NFSv3 and below, since some firewalls and smart routers will detect and block TCP [connection reuse](https://www.haproxy.com/glossary/what-is-connection-reuse#:~:text=Connection%20reuse%20is%20the%20process%20of%20using%20the%20same%20TCP%20connection%20to%20send%20and%20receive%20multiple%20HTTP%20requests%20and%20responses.%20Alternatively%2C%20a%20new%20connection%20is%20subsequently%20opened%20to%20handle%20each%20pair%20of%20new%20messages.%C2%A0), even though connection reuse is a practice which NFS has traditionally relied upon it)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Potential Causes

## Connection Reuse Being Blocked

Something is blocking the NFS client's individual communication attempts with the NFS Server, which often comes from a smart router, frontend device, firewall, or some other kind of network security device or policy 
* The connection being blocked is usually a repeat of a previous connection, also known as "connection reuse", which the NFS client was using before it ran into some temporary trouble


Addtionally, an NFS mount will initially use a somewhat randomly chosen connection definition which, for any number of reasons, may eventually be interrupted and when the NFS client code attempts to re-establish the connection, the same connection definition will be used (Connection reuse)
* Some devices have a **smart connection reuse** feature, which can detect connection reuse and may treat it with suspicion if it happens within a short time frame


Furthermore, NFS traditionally needs precisely the same connection definition it was using before a problem came up, because of the way NFS recovery works in NFSv2, NFSv3, and NFSv4
