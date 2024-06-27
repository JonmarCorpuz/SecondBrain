The Internet Protocol is responsible for routing packets of data across networks

* Operates at the Network layer of the OSI model and adds an IP header to the data packet to include additional information (Ex: *Source IP address*, *Destination IP address*, *Packet length*, *etc.*)
* Doesn't guarantee delivery or provide mechanisms for error recovery or flow control since it's connectionless
* Internet Protocol version 6 addresses are 128-bit that are represented as eight groups of four hexadecimal digits separated by colons
* Includes built-in support for IPsec and features that simplify routing and network configuration
* Allows devices to automatically configure their IP addresses without the need for DHCP

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/6560b502fd983ecbcc9f0be1_177.%20Different%20Classes%20of%20IT%20Security%20Policies-min.jpg)

## Network Prefix

The network prefix defines the network portion of the IPv6 address

* Expressed as a number of bits, which indicates how many bits of the address are reserved for the network prefix

## Subnet ID

The subnet ID in an IPv6 address identifies a specific subnet within a network

* Two subnets within the same network cannot have the same IPv6 network address and client ID combination

## Interface Identifier (Client ID)

The Interface ID, also know as the host portion, typically consists of the last 64 bits of the IPv6 address 

* Uniquely identifies a device within its network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Address Types

## Unicast 

An IPv6 unicast address identifies a single network interface and are used for one-to-one communication between devices on a network

## Multicast

An IPv6 multicast address is an address that starts with the prefix **ff00::/8** and is used to deliver packets to multiple recipients efficiently

* Devices interested in receiving multicast traffic subscribe to specific multicast addresses

## Anycast

An IPv6 anycast address is an address that's assigned to multiple interfaces

* Packets destined to an anycast address is sent to the nearest interface that hols that address
* Often used for load balancing and service redundancy
* Assigned from the unicast space

## Loopback

An IPv6 loopback address is an address that's used to send packets to the same device

* Often used for testing and troubleshooting

## Link-Local

An IPv6 link-local address is an address that's always within the **fe80::/64** range and are automatically assigned to interfaces on a local network segment

* Used primarily for communication between devices on the same link
* Not routable beyond the local network segment

## Unique Local Address

An IPv6 ULA address is a private address that starts with the **fc00::/7** prefix and is used for communication within a site or organization

* Not globally routable
* Intended for local use only

## Global Unicast Address

An IPv6 global unicast address is a public address that starts with the **2000::/3** prefix and is used for communication between devices across different networks

* Globally routable on the internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2-Figure2-1.png)

## Version (4 bits)

The version section indicates the IP version that's being used, which in this case is set to 6 for IPv6

## Traffic Class (8 bits)

The Traffic Class field is used to prioritize packets and specify QoS parameters

* Similar to IPv4's ToS field

## Flow Label (20 bits)

The Flow Label field is used to identify packets belonging to the same flow

* Allows for special handling of those packets within routers

## Payload Length (16 bits)

The Payload Length field indicates the length of the IPv6 payload in octets, excluding the header

## Next Header (16 bits)

The Next Header field specifies that type of the next header in the packet

* Indicates the protocol or extension header following the IPv6 header

## Hop Limit (8 bits)

The Hop Limit field specifies the maximum number of router hops that the packet can traverse before being discarded

* Similar to IPv4's TTL field

## Source Address (128 bits)

The Source Address field specifies the IPv6 address of the packet's source

## Destination IPv6 Address (128 bits)

The Destination Address field specifies the IPv6 address of the packet's intended destination
