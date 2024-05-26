The Internet Protocol is responsible for routing packets of data across networks

* Operates at the Network layer of the OSI model and adds an IP header to the data packet to include additional information (Ex: *Source IP address*, *Destination IP address*, *Packet length*, *etc.*)
* Doesn't guarantee delivery or provide mechanisms for error recovery or flow control since it's connectionless

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4

Internet Protocol version 4 addresses are 32-bit binary numbers that are represented in dotted-decimal notation

## IPv4 Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vpc-ip-anatomy.6b178b63cc72849678ddaddc133b6acf233c87b67a938a20a057a2601beaa91c.png)

### Network Address

The network address portion of an IPv4 address identifies the network to which the device belongs to

* Determined by the subnet mask
* Devices within the same network share the same network portion of their IPv4 address

### Host Address

The host portion of an IPv4 address identifies a specific device within a network

* Determined by the remaining bit of the address after the network portion
* The host portion must be unique in every network

### Subnet Mask

The subnet mask specifies how many bits of an IPv4 address represent the network portion

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPv4 Address Types

### Unicast

An IPv4 unicast address is an address that identifies a single interface on a network

* Used for one-to-one communication between devices on a network

### Broadcast

An IPv4 broadcast address is an address that's used to send packets to all devices on a specific network segment

* Has all host bits set to 1
* Used for broadcasting information or messages to multiple devices simultaneously within a local network

### Multicast

An IPv4 multicast address is an address that's used to deliver packets to multiple recipients efficiently

* Devices interested in receiving multicast traffic subscribe to specific multicast addresses
* Used for one-to-many or many-to-many communication
* Commonly used in multimedia streaming, network discovery, and routing protocols

### Loopback

An IPv4 loopback address is a special address that's used by a device to send traffic to itself

### Private

### Public

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPv4 Address Classes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/4hdOm.png)

### Class A

Class A addresses range from 1.0.0.0 to 126.0.0.0

### Class B

Class B addresses range from 128.0.0.0 to 192.255.0.0

### Class C

Class C addresses range from 192.0.0.0 to 223.255.255.0

### Class D

Class D addresses range from 224.0.0.0 to 239.255.255.255 and are reserved for multicast addresses

* Used for multicasting data to multiple recipients simultaneously

### Class E

Class E addresses range from 240.0.0.0 to 255.255.255.255 and are reserved for experimental and future use

* Not intended for general use on the internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6

Internet Protocol version 6 addresses are 128-bit that are represented as eight groups of four hexadecimal digits separated by colons

* Includes built-in support for IPsec and features that simplify routing and network configuration
* Allows devices to automatically configure their IP addresses without the need for DHCP

## IPv6 Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/6560b502fd983ecbcc9f0be1_177.%20Different%20Classes%20of%20IT%20Security%20Policies-min.jpg)

### Network Prefix

The network prefix defines the network portion of the IPv6 address

* Expressed as a number of bits, which indicates how many bits of the address are reserved for the network prefix

### Subnet ID

The subnet ID in an IPv6 address identifies a specific subnet within a network

* Two subnets within the same network cannot have the same IPv6 network address and client ID combination

### Interface Identifier (Client ID)

The Interface ID, also know as the host portion, typically consists of the last 64 bits of the IPv6 address 

* Uniquely identifies a device within its network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPv6 Address Types

### Unicast 

An IPv6 unicast address identifies a single network interface and are used for one-to-one communication between devices on a network

### Multicast

An IPv6 multicast address is an address that starts with the prefix **ff00::/8** and is used to deliver packets to multiple recipients efficiently

* Devices interested in receiving multicast traffic subscribe to specific multicast addresses

### Anycast

An IPv6 anycast address is an address that's assigned to multiple interfaces

* Packets destined to an anycast address is sent to the nearest interface that hols that address
* Often used for load balancing and service redundancy
* Assigned from the unicast space

### Loopback

An IPv6 loopback address is an address that's used to send packets to the same device

* Often used for testing and troubleshooting

### Link-Local

An IPv6 link-local address is an address that's always within the **fe80::/64** range and are automatically assigned to interfaces on a local network segment

* Used primarily for communication between devices on the same link
* Not routable beyond the local network segment

### Unique Local Address

An IPv6 ULA address is a private address that starts with the **fc00::/7** prefix and is used for communication within a site or organization

* Not globally routable
* Intended for local use only

### Global Unicast Address

An IPv6 global unicast address is a public address that starts with the **2000::/3** prefix and is used for communication between devices across different networks

* Globally routable on the internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IP Headers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/technologies_white_paper0900aecd8054d37d-03.avif)

## IPv4 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1_-ZrMtI_V4FqPYeATVL5PSw.png)

### Version (4 bits)

The Version field indicates the IP version that's being used, which in this case is set to 4 for IPv4

### Header Length (4 bits)

The Header Lengt field specifies the length of the IPv4 header in 32-bit words

* With 4 bits, the Header Length fiel can represent values from 0 to 15, where each value corresponds to a header length ranging from 0 (no header present) to 60 byes (the maximum header length)
* Since the header length is specified in 32-bit words, the actual header length in bytes is calculated by multiplying the value in the Header Length field by 4

### Type of Service (8 bits)

### Total Length (16 bits)

The Total Length field indicates the total length of the IPv4 packet, including the header and payload

* The maximum value is 65 535 bytes (524 280 bits)

### Identification (16 bits)

The Identification field is used for uniquely identifying fragments of an original IP datagram

* Primarily used in fragmentation and reassembly of IP packets

### Flags (3 bits)

The Flags field contains control flags that are used for fragmentation and reassembly

* Reserved (bit **0**), which indicates that the bit is reserved for potential future use
* Don't Fragment (bit **1**), which indicates that the packet should not be fragmented
* More Fragments (bit **2**), which indicated that there are more fragments following this one

### Fragment Offset (13 bits)

The Fragment Offset field indicated in what portion of a fragmented packet that it belongs to

* Specifies where the fragment fits in the original datagram

### Time to Live (8 bits)

The Time to Live field represents that maximum number of hops that the packet can traverse before being discarded

* Decrements by one at each router and if it reaches zero, then the packet is discarded

### Protocol (8 bits)

The Protocol field indicates the protocol used in the data portion of the packet (Ex: *TCP*, *UDP*, *ICMP*, *etc.*)

### Header Checksum (16 bits)

The Header Checksum field provides error-checking for the header only

* Calculated based on the header contents and is recomputed at each router

### Source Address (32 bits)

The Source Address field specifies the IPv4 address of the packet's source

### Destination Address (32 bits)

The Source Address field specifies the IPv4 address of the packet's destination

### Options (Variable length)

The Options field may include various additional information (Ex: *Record route*, *Timestamp*, *etc.*)

* The presence and format of options are indicated by the header length field

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPv6 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2-Figure2-1.png)

### Version (4 bits)

The version section indicates the IP version that's being used, which in this case is set to 6 for IPv6

### Traffic Class (8 bits)

The Traffic Class field is used to prioritize packets and specify QoS parameters

* Similar to IPv4's ToS field

### Flow Label (20 bits)

The Flow Label field is used to identify packets belonging to the same flow

* Allows for special handling of those packets within routers

### Payload Length (16 bits)

The Payload Length field indicates the length of the IPv6 payload in octets, excluding the header

### Next Header (16 bits)

The Next Header field specifies that type of the next header in the packet

* Indicates the protocol or extension header following the IPv6 header

### Hop Limit (8 bits)

The Hop Limit field specifies the maximum number of router hops that the packet can traverse before being discarded

* Similar to IPv4's TTL field

### Source Address (128 bits)

The Source Address field specifies the IPv6 address of the packet's source

### Destination IPv6 Address (128 bits)

The Destination Address field specifies the IPv6 address of the packet's intended destination
