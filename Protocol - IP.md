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

### Header Length (4 bits)

### Type of Service (8 bits)

### Total Length (16 bits)

### Identification (16 bits)

### Flags (3 bits)

### Fragment Offset (13 bits)

### Time to Live (8 bits)

### Protocol (8 bits)

### Header Checksum (16 bits)

### Source IPv4 Address (32 bits)

### Destination IPv4 Address (32 bits)

### Options (Variable length)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPv6 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2-Figure2-1.png)

### Version (4 bits)

### Traffic Class (8 bits)

### Flow Label (20 bits)

### Payload Length (16 bits)

### Next Header (16 bits)

### Hop Limit (8 bits)

### Source IPv6 Address (128 bits)

### Destination IPv6 Address (128 bits)
