The Internet Protocol is responsible for routing packets of data across networks

* Operates at the Network layer of the OSI model and adds an IP header to the data packet to include additional information (Ex: *Source IP address*, *Destination IP address*, *Packet length*, *etc.*)
* Doesn't guarantee delivery or provide mechanisms for error recovery or flow control since it's connectionless
* 32-bit (4 bytes) binary numbers that are represented in dotted-decimal notation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4 Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vpc-ip-anatomy.6b178b63cc72849678ddaddc133b6acf233c87b67a938a20a057a2601beaa91c.png)

## Network Address

The network address portion of an IPv4 address identifies the network to which the device belongs to

* Determined by the subnet mask
* The host portion is all 0
* Devices within the same network share the same network portion of their IPv4 address
* The first address of a network
* Can't be assigned to a host

## Host Address

The host portion of an IPv4 address identifies a specific device within a network

* Determined by the remaining bit of the address after the network portion
* The host portion must be unique in every network

## Subnet Mask

The subnet mask specifies how many bits of an IPv4 address represent the network portion

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4 Address Types

## Unicast

An IPv4 unicast address is an address that identifies a single interface on a network

* Used for one-to-one communication between devices on a network

## Broadcast

An IPv4 broadcast address is an address that's used to send packets to all devices on a specific network segment

* Has all host bits set to 1
* Used for broadcasting information or messages to multiple devices simultaneously within a local network
* The last address in a network

## Multicast

An IPv4 multicast address is an address that's used to deliver packets to multiple recipients efficiently

* Devices interested in receiving multicast traffic subscribe to specific multicast addresses
* Used for one-to-many or many-to-many communication
* Commonly used in multimedia streaming, network discovery, and routing protocols

## Loopback

An IPv4 loopback address is a special address that's used by a device to send traffic to itself

* Address range is from 127.0.0.0 to 127.255.255.255
* Used to test the network stack on the local device, which refers to the set of software layers that handle network communication tasks of the TCP/IP model
* Devices that send traffic to a loopback address, it's simply processed back up the TCP/IP stack as if it were traffic received from another device

## Private

## Public

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4 Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1_-ZrMtI_V4FqPYeATVL5PSw.png)

## Version (4 bits)

The Version field indicates the IP version that's being used, which in this case is set to 4 for IPv4

## Header Length (4 bits)

The Header Lengt field specifies the length of the IPv4 header in 32-bit words

* With 4 bits, the Header Length fiel can represent values from 0 to 15, where each value corresponds to a header length ranging from 0 (no header present) to 60 byes (the maximum header length)
* Since the header length is specified in 32-bit words, the actual header length in bytes is calculated by multiplying the value in the Header Length field by 4

## Type of Service (8 bits)

## Total Length (16 bits)

The Total Length field indicates the total length of the IPv4 packet, including the header and payload

* The maximum value is 65 535 bytes (524 280 bits)

## Identification (16 bits)

The Identification field is used for uniquely identifying fragments of an original IP datagram

* Primarily used in fragmentation and reassembly of IP packets

## Flags (3 bits)

The Flags field contains control flags that are used for fragmentation and reassembly

* Reserved (bit **0**), which indicates that the bit is reserved for potential future use
* Don't Fragment (bit **1**), which indicates that the packet should not be fragmented
* More Fragments (bit **2**), which indicated that there are more fragments following this one

## Fragment Offset (13 bits)

The Fragment Offset field indicated in what portion of a fragmented packet that it belongs to

* Specifies where the fragment fits in the original datagram

## Time to Live (8 bits)

The Time to Live field represents that maximum number of hops that the packet can traverse before being discarded

* Decrements by one at each router and if it reaches zero, then the packet is discarded

## Protocol (8 bits)

The Protocol field indicates the protocol used in the data portion of the packet (Ex: *TCP*, *UDP*, *ICMP*, *etc.*)

## Header Checksum (16 bits)

The Header Checksum field provides error-checking for the header only

* Calculated based on the header contents and is recomputed at each router

## Source Address (32 bits)

The Source Address field specifies the IPv4 address of the packet's source

## Destination Address (32 bits)

The Source Address field specifies the IPv4 address of the packet's destination

## Options (Variable length)

The Options field may include various additional information (Ex: *Record route*, *Timestamp*, *etc.*)

* The presence and format of options are indicated by the header length field

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4 Address Classes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/4hdOm.png)

## Class A

Class A addresses range from 1.0.0.0 to 126.0.0.0

| Class | First Octet | First Octet Numeric Range | Prefix Length |
| --- | --- | --- | --- |
| A | 0------- | 0-127 | /8 |

## Class B

Class B addresses range from 128.0.0.0 to 192.255.0.0

| Class | First Octet | First Octet Numeric Range | Prefix Length |
| --- | --- | --- | --- |
| B | 10------ | 0-128-191 | /16 |

## Class C

Class C addresses range from 192.0.0.0 to 223.255.255.0

| Class | First Octet | First Octet Numeric Range | Prefix Length |
| --- | --- | --- | --- |
| C | 110----- | 192-223 | /24 |

## Class D

Class D addresses range from 224.0.0.0 to 239.255.255.255

* Reserved for multicast addresses
* Used for multicasting data to multiple recipients simultaneously

## Class E

Class E addresses range from 240.0.0.0 to 255.255.255.255

* Reserved for experimental and future use
* Not intended for general use on the internet
