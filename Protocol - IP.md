The Internet Protocol is responsible for routing packets of data across networks

* Operates at the Network layer of the OSI model and adds an IP header to the data packet to include additional information (Ex: *Source IP address*, *Destination IP address*, *Packet length*, *etc.*)
* Doesn't guarantee delivery or provide mechanisms for error recovery or flow control since it's connectionless

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPv4

Internet Protocol version 4 addresses are 32-bit binary numbers that are represented in dotted-decimal notation

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

### Interface Identifier (Client ID)

The Interface ID, also know as the host portion, typically consists of the last 64 bits of the IPv6 address 

* Uniquely identifies a device within its network
