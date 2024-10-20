# Identify Live Hosts on a Network

## ping

```Bash
for i in {1..255} ;do (ping -c 1 <NETWORK_PORTION>.$i | grep "bytes from"|cut -d ' ' -f4|tr -d ':' &);done
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Identify Live Networking Devices on a Network

## traceroute

traceroute is a network diagnostic tool used to track the path that packets take from one network host to another

```Bash
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
cat ~/.bash_history
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Enumerate Files Owned by Root

## find

```Bash
find / -perm -4000 2> /dev/null
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Query DNS Information

## dig

Domain Information Groper is a CLI tool that's used for querying DNS servers to retrieve information about DNS records

```Bash
dig [<DNS_SERVER_IP>] <DOMAIN> {<RECORD_TYPE>}
```
