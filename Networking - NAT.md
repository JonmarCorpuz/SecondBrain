The Network Address Translation is a process used in routers to modify network address information in packet headers while in transit across a traffic routing device

* Allows multiple devices within a local network to share a single public IP address for accessing the internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Types

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
