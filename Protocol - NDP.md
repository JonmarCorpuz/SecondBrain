The Neighbor Discovery Protocol is protocol that's used in IPv6 communication

* An essential part of IPv6 routing and replaces IPv4's ARP
* Uses ICMPv6 and solicited-node multicast addresses to learn the MAC address of other hosts
* Much more efficient than ARP since it uses solicited-node multicast addresses

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NDP Messages

## Neighbor Solicitation 

The NS message (ICMPv6 Type 135) is used to determine the link-layer address (MAC address) of a neighbor node on the same local link

* The equivalent of IPv4's ARP Request message except that it's a multicast message
* A router can automatically calculate a neighboring router's solicted-node mutlicast address by using their unicast address (Prefix length + Last 6 hexadecimal digits)

## Neighbor Advertisement 

The NA message (ICMPv6 Type 136) provides information about a node's link-layer address (MAC address)

* The equivalent of IPv4's ARP Reply message
* A response message to a NDP NS message or to advertise changes in link-layer addresses

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
