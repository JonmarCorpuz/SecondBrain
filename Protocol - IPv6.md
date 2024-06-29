The Internet Protocol is responsible for routing packets of data across networks

* Operates at the Network layer of the OSI model and adds an IP header to the data packet to include additional information (Ex: *Source IP address*, *Destination IP address*, *Packet length*, *etc.*)
* Doesn't guarantee delivery or provide mechanisms for error recovery or flow control since it's connectionless
* Provides more usable IP addresses than IPv4
* 128-bit (16 bytes) that are represented as eight groups of four hexadecimal digits separated by colons
* Only uses slash notation to indicate the prefix length
* Includes built-in support for IPsec and features that simplify routing and network configuration
* Allows devices to automatically configure their IP addresses without the need for DHCP
* A router can be assigned an IPv6 address of each IPv6 type

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Address Shortening

* Leading zeroes must be removed (Ex: *2001:0db8:0000:0001:0f2a:4fff:fea3:00b1 becomes 2001:db8:0:1:f2a:4fff:fea3:b1*)
* A **::** must be used to shorten the longest string of multiple all zero quartets and a **0** for a single all zero quartets (Ex: *2001:0000:0000:0000:0f2a:4fff:fea3:00b1 becomes 2001::f2a:0:0:b1*)
* If there are two equal-length choices for the **::**, then shortent the left one (Ex: *2001:0db8:0000:0000:0f2a:0000:0000:00b1 becomes 2001:db8::f2a:0:0:b1*)
* Hexadecimal characters must be written using lowercase

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/6560b502fd983ecbcc9f0be1_177.%20Different%20Classes%20of%20IT%20Security%20Policies-min.jpg)

## Network Prefix

The network prefix defines the network portion of the IPv6 address (48-bits)

* Expressed as a number of bits, which indicates how many bits of the address are reserved for the network prefix

### Global Routing Prefix

* The first three quartet
* Usually assigned by the ISP

### Subnet ID 

The subnet ID in an IPv6 address identifies a specific subnet within a network (16-bits)

* Two subnets within the same network cannot have the same IPv6 network address and client ID combination
* The fourth quartet

## Client ID (Interface Identifier)

The Client ID uniquely identifies a device within a network (64-bits)

* Typically consists of the last 64 bits of the IPv6 address 
* The last four quartets

### EUI-64

The Extended Unique Identifier-64 is a standard for creating a 64-bit unique identifier

* Allows a host to assign itself a unique 64-bit IPv6 interface identifier by expanding its 48-bit MAC address into a 64-bit interface identifier by dividing it in half, inserting the **fffe** hexadecimal in the middle, and then invert the seventh bit
* If the U/L bit was flipped to 0, that means that the MAC address the EUI-64 interface ID was made from an LAA MAC address
* If the U/L bit was flipped to 1, that means that the MAC address the EUI-64 interface ID was made from a UAA MAC address

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Address Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dsdsfjoododogohihodoihiohiihhihihohiohio.jpg)

## Unicast 

An IPv6 unicast address identifies a single network interface 

* Used for one-to-one communication between devices on a network (One source to one destination)

## Multicast

An IPv6 multicast address is an address that 

* Uses the **ff00::/8** address block, which ranges from **ff00::** to **ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff**
* Used to deliver packets to multiple recipients that are part of a specific multicast group
* Devices interested in receiving multicast traffic subscribe to specific multicast addresses
* Defines multiple multicast scopes which indicate how far the packet should be forwarded, which needs to be defined by the network engineer

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/sddsfgfgfgfserwerewrewtrtretwrwewewqewr.png)

| Multicast Scope | IPv6 Scope | Description |
| --- | --- | --- |
| Interface-local | FF01 | The packet doesn't leave the local device |
| Link-local | FF02 | The packet remains in the local subnet |
| Site-local | FF05 | The packet can be forwarded by routers within a single location (Can't be forwarded over a WAN) |
| Organization-local | FF08 | The packet can be forwarded by routers between multiple physical locations |
| Global | FF0E | The packet can be routed over the Internet (No boundaries) |

| Multicast Group | IPv6 Address | IPv4 Address |
| --- | --- | --- |
| All nodes/hosts | <multicast_scope>::1 | 224.0.0.1 |
| All routers | <multicast_scope>::2 | 224.0.0.2 |
| All OSPF routers | <multicast_scope>::5 | 224.0.0.5
| All OSPF DRs/BDRs | <multicast_scope>::6 | 224.0.0.6 |
| All RIP routers | <multicast_scope>::9 | 224.0.0.9 |
| All EIGRP routers | <multicast_scope>::A | 224.0.0.10 |

## Anycast

An IPv6 anycast address is an address that's assigned to multiple interfaces

* One-to-one-of-many (Multiple routers are configured with the same IPv6 address)
* Packets destined to an anycast address is sent to the nearest interface that holds that address (When a host sends packets to an anycast address, the routers will forward it to the nearest router with the smallest routing protocol metric that's configured with that IP address)
* Often used for load balancing and service redundancy
* Assigned from the unicast space
* There's no specific address range for anycast addresses, meaning that you can use a regular unicast address and specify it as an anycast address

## Loopback

An IPv6 loopback address is an address that's used to send packets to the same device

* Uses the **::1** address (127 bits of 0s and one 1 bit)
* Often used for testing and troubleshooting (Ex: *Testing the protocol stack on the local device*, *etc.*)
* Messages sent to this address are processed within the local device, but not sent to other devices

## Link-Local

An IPv6 link-local address is an address that's automatically generated on IPv6-enabled interfaces

* Uses the **fe80::/64** address block, which ranges from **fe80** to **febf:ffff:ffff:ffff:ffff:ffff:ffff:ffff** (The standard states that the 54 bits after FE80/10 should be all 0s, which means that you'll only see link local addresses beginning with FE8)
* Automatically assigned to interfaces on a local network segment
* Used primarily for communication between devices on the same link
* Not routable beyond the local network segment
* The interface ID is generated using EUI-64 rules
* Can be used for routing protocol peerings, next-hop addresses for static routes, NDP, etc.

## Unique Local Address

An IPv6 ULA address is a private address that can't be used over the Internet

* Uses the **fd00::/7** address block, which ranges from **fd00::** to **fdff:ffff:ffff:ffff:ffff:ffff:ffff:ffff** (Requires the 8th bit to be set to 1, so the first two digits must be FD)
* Used for communication within a site or organization
* Not globally routable and intended for local use only
* Doesn't need to be registered in order for them to be used within internal networks

## Global Unicast Address

An IPv6 global unicast address is a public address that can be used over the Internet

* Uses the **2000::/3** address block, which ranges from **2000::** to **3fff:ffff:ffff:ffff:ffff:ffff:ffff:ffff**
* Must be registered and globally unique
* Used for communication between devices across different networks

## Unspecified Address

* Represent using only **::**
* Used when a device doesn't yet know its IPv6 address
* Default routes can be configured to **::/0**

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv6 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/2-Figure2-1.png)

* The IPv6 header has a fixed size of 40 bytes

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
