traceroute is a network diagnostic tool used to track the path that packets take from one network host to another

* Commonly used to identify the path and measure transit delays of packets across an IP network
* Provides the IP addresses of the routers or hops that a packet traverses as it goes from your system to a target host, as well as the number of routers between the two
* Can help diagnose routing issues, identify network bottlenecks, and understand the structure of a network
* Relies on using ICMP to trick the routers into revealing their IP address by manipulating the TTL field (When a router receives a packet with a TTL of 0, it'll discard that packet and then send an ICMP TTL exceeded message back to the source)

# Traceroute on Windows

```PowerShell
tracert <target_ip>
```

# Traceroute on Linux and MacOS

```Bash
traceroute <target_ip>
```
