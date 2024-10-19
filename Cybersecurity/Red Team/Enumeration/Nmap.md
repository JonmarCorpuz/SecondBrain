# Nmap Overview

Network Mapper is an open-source tool that's used for network discovery and security auditing

* Provides host discovery by identifying live hosts on a network
* Provides a list of open, closed, and filtered ports on a host, as well as the services that are running on them
* Can detect which OS is running on a host
* Can map out the path that packets take to reach their destination

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Port States

| Nmap Port State | Description | 
| --- | --- |
| Open | Indicates that a service is listening on the specified port |
| Closed | Indicates that no service is listening on the specified port (The port can still be accessible) |
| Filtered | Nmap cannot determine if the port is open or closed because the port isn't accessible (Usually due to a firewall preventing Nmap from reaching that port or that the responses are blocked from reaching Nmap's host |
| Unfiltered | Nmap cannot determine if the port is open or closed, although the port is accessible |
| Open/Filtered | Nmap cannot determine whether the port is open or filtered |
| Closed/Filtered | Nmap cannot decide whether a port is closed or filtered |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scanning Techniques

## ARP Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f0ce4cd34b827f529255c5c73bb909d1.png)

* If a host sends back an ARP Reply, then the host is active

## ICMP Ping Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/25fb5fd5d2009cf69d7aae40e8fde2ec.png)

* If a host sends back an ICMP Reply, then the host is active

## TCP SYN Ping Scan

### Privileged TCP SYN Nmap Ping Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/168d48701c5f872cf1930e08b32bcd6f.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fe642b2fafb70cbaa2531d2c41d6cddb1.png)

* If a port replies back with a SYN/ACK, then the port is open
* If a port replies back with a RST, then the port is closed
* Privileged users don't need to complete the TCP Three-Way Handshake even if the port is open
* Nmap tears down the connection once it receives a response from the host, which decreases the chances of the scan being logged since it didn't establish a TCP connection

### Unprivileged TCP SYN Nmap Ping Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/23e7f481f78de8d3e89ef845b747002d.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fe642b2fafb70cbaa2531d2c41d6cddb2.png)

* Unprivileged users have to complete the TCP Three-Way Handshake even if the port is open

## TCP ACK Ping Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/db5ab44a8c700c4ab0603e85e456040d.png)

* Must be a privileged user to accomplish this scan (Attempting this with an unprivileged user will result in an attempt for the TCP Three-Way Handshake)
* An active target will respond with a RST flag because the TCP packet with the ACK flag isn't part of any ongoing connection
* Useful to help map out firewall rules

## TCP Connect Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>} -sT
```

TCP Connect scan works by completing the TCP Three-Way Handshake in order to determine if a TCP port is open and then tearing that connection down right away

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/514972cd54b3f58c83f951978ea9183e.png)

* The only scan that's possible for non privileged users to discover open TCP ports

## TCP Null Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/04b178a9cf7048c21256988b8b2343e3.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/224e01a913a1ce7b0fb2b9290ff5e1c8.png)

* Requires root privileges
* A TCP packet with no flags set won't trigger any response when it reaches an open port, which means that a lack of reply in a Null scan indicates that either the port is open or a firewall is blocking the packet
* If a port is closed, it'll reply to a Null flag with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP FIN Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/78eb3d6ba158542f2b3223184b032e64.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/74dc07da7351a5a7f258948ec59efccc.png)

* If a port is closed, it'll reply to a FIN flag with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP Xmas Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/7d28b756aed3b6eb72faf98d6974776c.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/4304eacbc3db1af21657f285bc16ebce.png)

* If a port is closed, it'll reply to a Xmas scan with a RST packet, which indicates that the port is closed (Note that some firewalls may drop the traffic without sending an RST reply)
* Can be efficient when scanning a target behind a stateless firewall, since it'll usually check if the incoming packet has the SYN flag set to detect a connection attempt

## TCP Maimon Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8ca5e5e0f6e0a1843cebe11b5b0785b3.png)

* The FIN and ACK bits are set
* Most target systems respond with an RST regardless of whether the TCP port is open

## TCP Window Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/5118dcb424d429376f09bf2f85db5bce.png)

* Almost the same as the ACK scan but it examines the TCP Window field of the RST packets returned, which can reveal an open port on specific systems
* Sometimes you have to repeat a TCP Window scan against a target that's behind a firewall in order to get more information
* Useful to help map out firewall rules

## UDP Ping Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>} -sU
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1b827ef60c39619e281c4ca51a6d57b6.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f927563f4778092ced3ef7afa67cece3.png)

* Open UDP ports aren't expected to send a reply
* Closed UDP ports are expected to send back an ICMP Port Unreachable packet reply, which reveals that the host is online

## Spoofed Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/45b982d501fd26deb2b381059b16f80c.png)

* The target will respond to the incoming packets by sending the replies to the destination IP address that we spoofed
* To figure out which ports are open, the attacker needs to monitor the network traffic to analyze the replies that are sent back to the destination address
* In general, you expect to specify the network interface using **-e** and to explicitly disable ping scan using **-Pn**
* You can also spoof you MAC address if you're in the same Ethernet (802.3) network or WiFi (802.11)
* Spoofing only works in a minimal number of cases where certain conditions are met

## Decoy Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/754fc455556a424ca83f512665beaf7d.png)

* Decoy scanning involves making the scan appear to be coming from many IP addresses so that the attacker's IP address would be lost among them

## Idle Scan

```Bash
#
nmap {<TARGET_IP>|<TARGET_NETWORK>}
```

* Requires an idle system to be connected to the network that you can use to communicate with (If the idle host is busy, then all the returned IP IDs would be useless)
* Nmap will make each probe appear as if it's coming from the idle host, then it'll check for indicators whether the idle host received any response to the spoofed probe, which can be accomplished by checking the IP ID value in the IP header of the packets

1. Trigger the idle host to respond so that you can record the current IP ID on the idle host
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/a93e181f0effe000554a8b307448bbb2.png)

2. Send a spoofed SYN packet to a TCP port on the target to make it appear as if it was coming from the idle host
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8e28bf940936ddbc2367b193ea3550b8.png)
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2b0de492e2154a30760852e07cebae0e.png)

3. Trigger the idle machine again to respond so that you can compare the new IP ID with the one received earlier (If the difference is 1, it means the port on the target is closed or filtered, but if the difference is two, it means that the port on the target is open)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Scan Timing

| Nmap Scan Timing | Meaning | Description |
| --- | --- | --- |
| 0 | Paranoid | |
| 1 | Sneaky | |
| 2 | Polite | |
| 3 | Normal | |
| 4 | Aggressive | |
| 5 | Insane | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Nmap Service Detection Scan Intensity Levels

| Nmap Scan Intensity Level | Description |
| --- | --- |
| 0 | Quick but may miss some services and only includes the most likely probes |
| 1 | Includes slightly more probes than level 0 |
| 2 | Includes more probes to provide a better balance between speed and accuracy |
| 3 | Good balance between thoroughness and time consumption (The default level) |
| 4 | More probes than the default and is more likely to identify obscure services but takes more time |
| 5 | Further increases the number of probes to provide a more comprehensive version detection | 
| 6 | Adds even more probes to the scan but is more time-consuming |
| 7 | Very thorough since it uses almost all available probes but can be very slow |
| 8 | Uses all probes to provide maximum thoroughness | 
| 9 | All probes are used to ensure the most comprehensive detection but at the cost of scan time and potential false positives |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

