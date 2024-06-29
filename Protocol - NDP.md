The Neighbor Discovery Protocol is protocol that's used in IPv6 communication

* An essential part of IPv6 routing and replaces IPv4's ARP
* Uses ICMPv6 and solicited-node multicast addresses to learn the MAC address of other hosts
* Much more efficient than ARP since it uses solicited-node multicast addresses
* Allows hosts to automatically discover routers on the local network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NDP Router Discovery

## Router Solicitation

The RS message (ICMPv6 Type 133) 

* Sent to the multicast address on all the routers in the local network
* Asks all routers on the local llink to identify themselves
* Sent when an interface is enabled or when a host connects to a network

## Router Advertisement

The RA message (ICMPv6 Type 134)

* Sent to the multicast address of all the nodes in the local network
* The router announces its presence and provides information about their link (Ex: *Default gateway*, *Prefix length*, *etc.*)
* Are sent in response to RS messages and periodically sent even if a router hasn't received an RS message

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NDP MAC Address Discovery

## Neighbor Solicitation 

The NS message (ICMPv6 Type 135) is used to determine the link-layer address (MAC address) of a neighbor node on the same local link

* The equivalent of IPv4's ARP Request message except that it's a multicast message
* A router can automatically calculate a neighboring router's solicted-node mutlicast address by using their unicast address (Prefix length + Last 6 hexadecimal digits)

## Neighbor Advertisement 

The NA message (ICMPv6 Type 136) provides information about a node's link-layer address (MAC address)

* The equivalent of IPv4's ARP Reply message
* A response message to a NDP NS message or to advertise changes in link-layer addresses

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
