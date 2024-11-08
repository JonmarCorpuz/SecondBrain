# Identify Live Hosts on a Network

## ping

Ping is a CLI tool that's used to test the reachability of a host on an IP network

* Allows to determine whether a specific IP address or hostname is reachable
* Measures the round-trip time for messages sent from the originating host to a destination computer
* Can identify if any packets are lost during transmission
* Displays the TTL value, which can help identify routing loops or excessively long paths
* Uses ICMP type 8 (ICMP Echo) and ICMP type 0 (ICMP Reply) messages


```Bash
for i in {1..255} ;do (ping -c 1 <NETWORK_PORTION>.$i | grep "bytes from"|cut -d ' ' -f4|tr -d ':' &);done
```

## arp-scan

```Bash
#
arp-scan -l
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Identify Live Networking Devices on a Network

## traceroute

traceroute is a network diagnostic tool used to track the path that packets take from one network host to another

```Bash
#
traceroute <TARGET_IP>
```

* Commonly used to identify the path and measure transit delays of packets across an IP network
* Provides the IP addresses of the routers or hops that a packet traverses as it goes from your system to a target host, as well as the number of routers between the two
* Can help diagnose routing issues, identify network bottlenecks, and understand the structure of a network
* Relies on using ICMP to trick the routers into revealing their IP address by manipulating the TTL field (When a router receives a packet with a TTL of 0, it'll discard that packet and then send an ICMP TTL exceeded message back to the source)
* Starts by sending UDP datagrams within IP packets of TTL being 1, which causes the first router to encounter a TTL of 0 and send an ICMP TTL exceed back to the source revealing its IP address, traceroute will then send another UDP datagram within an incremented TTL and so on, until it manages to reach its destination (Some routers may not send back an ICMP TTL exceed message and reveal their public IP address)
* Don't expect the route to remain fixed when the packets need to go via other routers outside our network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Expose Possible Sensitive Information

## .bash_history

```Bash
#
cat ~/.bash_history
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Enumerate Permissions

## sudo

List all commands that the user can run with sudo
```Bash
sudo -l
```

## find


```Bash
find / -perm -4000 2> /dev/null
```

Find all directories or files containing the specified string
```Bash
find / -type {d|f} -name <string> 2>/dev/null
```

Find all directories or files containing the specified file permissions
```Bash
find / -type {d|f} -perm {<file_permissions>|<subject>=<permission>} 2>/dev/null
```

Find all directories or files owned by the specified user
```Bash
find / -type {d|f} -user <username> 2>/dev/null
```

Find all directories or files that were modified in the last specified time period
```Bash
find / -type {d|f} -mtime <days> 2>/dev/null
```

Find all directories or files that were accessed in the last specified days
```Bash
find / -type {d|f} -atime <days> 2>/dev/null
```

Find all directories or files that were changed within the specified time
```Bash
find / -type {d|f} -cmin -<minutes> 2>/dev/null
```

Find all directories or files that were accessed within the specified time
```Bash
find / -type {d|f} -amin -<minutes> 2>/dev/null
```

Find all directories or files with the specified size
```Bash
find / -type {d|f} -size {[+]|[-]}<size> 2>/dev/null
```


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Query DNS Information

## dig

Domain Information Groper is a CLI tool that's used for querying DNS servers to retrieve information about DNS records

```Bash
dig [<DNS_SERVER_IP>] <DOMAIN> {<RECORD_TYPE>}
```

## nslookup

Name Server Lookup is a network administration CLI tool that's used to query the DNS to obtain domain name or IP address mapping information

Return all the IPv4 and/or IPv6 addresses used by the target domain
```Bash
nslookup -type={A|AAAA} <DOMAIN> [TARGET_DNS_ADDRESS]
```

Return all the mail servers used by the target domain
```Bash
nslookup -type=MX <DOMAIN> [TARGET_DNS_ADDRESS]
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# View System Information

## uname

```Bash
# Print system information
uname -a
```

## env

```Bash
# Display all environmental variables and their values
env
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# View Process Information

## ps

```Bash
# View all running processes
ps -A
```

```Bash
# View process tree
ps axjf
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# View Listening Ports and Established Connections

## netstat

```Bash
# Show all listening ports and established connections
netstat -a
```

```Bash
# Show all listening ports and TCP established connections
netstat -at
```

```Bash
# Show all listening ports and UDP established connections
netstat -au
```

```Bash
# Show all ports that are open and ready to accept incoming connections (Listening mode)
netstat -l
```

```Bash
# List network usage statistics by protocol
netstat -s
```

```Bash
# List connections with the service name and PID information
netstat -tp
```

```Bash
# Display interface statistics
netstat -i
```

```Bash
#
netstat -ano
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Interesting Files

* /etc/issue
* /etc/passwd
* /etc/crontab

* /proc/version
