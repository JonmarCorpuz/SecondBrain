The Network Address Translation is a process used in routers to modify the source and/or destination IP addresses of packets

* Allows multiple devices within a local network to share a single public IP address for accessing the internet
* Allows hosts with private IP addresses to communicate with other hosts over the Internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Components

## Inside Network

An inside network refers to a router's internal network

### Inside Local Address

An inside local address is the IP address of an inside host from the perspective of the local network

* An inside local IP address is mapped to an inside global IP address
* Usually a private IP address

### Inside Global Address

An inside global address is the IP address of an inside host after NAT from the perspective of the external network

* Usually a public IP address

## Outside Network

An outside network refers to a router's external network

### Outside Local Address

An outside local address is the IP address of an outside host from the perspective of the local network

### Outside Global Address

An outside global address is the IP address of the outside host from the perspective of the outside network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Types

## Source NAT

Source NAT is a type of NAT that translates the source IP address of a packet

* Allows devices with private IP addresses to communicate over the Internet

### Static Source NAT

* Involves statically configuring one-to-one mappings of private IP addresses to public IP addresses
* Each host in the internal network would need to be mapped to their own public IP address (You won't be able to map two hosts to the same inside global address and an inside global address will remain mapped to the first inside local address that was mapped to it)
* Doesn't help preserve IP addresses since it requires a one-to-one mapping
* Port numbers are preserved and aren't translated

## Destination NAT

## PAT

Port Address Translation is a type of NAT that allows multiple devices within a private network to share a single public IP address

### PAT Components

#### Translation Table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

### Outbound PAT Traffic

1. **Packet Creation**: When an internal device sends a packet to an external destination, it constructs the packet with its own private IP address as the source IP and a random source port number
2. **Translation Table Lookup**: The router or firewall performing PAT will check its translation table to determine the appropriate public IP address to use for the translation
3. **Source Address Translation**: The router or firewall performing PAT will replace the source IP address in the packet header with its own public IP address, as well as the source port number with a unique port number allocated from a pool of available ports
4. **Packet Forwarding**: The router or firewall performing PAT will forward the modified packet towards the external destination

### Inbound PAT Traffic

1. **Packet Arrival**: A packet arrives at the router or firewall performing the PAT
2. **Translation Table Lookup**: The router or firewall performing PAT checks its translation table to find the corresponding entry for the destination IP address and port number in the incoming packet
