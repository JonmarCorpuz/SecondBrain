The Network Address Translation is a process used in routers to modify the source and/or destination IP addresses of packets

* Allows multiple devices within a local network to share a single public IP address for accessing the internet
* Allows hosts with private IP addresses to communicate with other hosts over the Internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Components

## Inside Network

An inside network refers to a router's internal network

| Inside Network Address | Description | 
| --- | --- |
| Inside Local Address | The IP address of an inside host from the perspective of the local network (Usually a private IP address that's mapped to an inside global IP address) |
| Inside Global Address | The IP address of an inside host after NAT from the perspective of the external network (Usually a public IP address that allows external hosts to access the internal hosts via their inside global address) |

## Outside Network

An outside network refers to a router's external network

| Outside Network Address | Description |
| --- | --- |
| Outside Local Address | The IP address of an outside host from the perspective of the local network |
| Outside Global Address | The IP address of the outside host from the perspective of the outside network |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Types

## Static NAT

### Static Source NAT

* Involves statically configuring one-to-one mappings of private IP addresses to public IP addresses
* Translates the source IP address of a packet
* Each host in the internal network would need to be mapped to their own public IP address (You won't be able to map two hosts to the same inside global address and an inside global address will remain mapped to the first inside local address that was mapped to it)
* Doesn't help preserve IP addresses since it requires a one-to-one mapping
* Port numbers are preserved and aren't translated
* Static dynamic entries are permanent

### Static Destination NAT

## Dynamic NAT

Dynamic NAT dynamically maps inside local addresses to inside global addresses as needed and clears them when they're no longer needed

* Dynamic mappings are still one-to-one (One inside local IP address per inside global IP address)
* Uses ACLs to identify which traffic should be translated (Ex: *If a source IP is permitted by the ACL, the source IP will be translated, otherwise it'll not be translated*, *etc.*)
* If a source IP isn't permitted by the ACL, it won't be dropped but instead it just won't be translated
* Uses a NAT pool to define the available inside global addresses
* NAT pool exhaustion happens when there aren't enough global IP addresses available and will drop a packet that needs NAT
* Dynamic NAT entries are temporary and will time out automatically if not used (Default timer of 24 hours and each time a translation is made, the timer resets)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PAT

Port Address Translation translates both the IP address and the port number if necessary

* Using a unique port number for each communication flow, a single public IP address cam be used by many different internal hosts at the same time
* The router performing PAT will keep track of which inside local address is using which inside global address and port, as well as each communication flows by using a unique port number for each flow
* Useful for preserving public IP addresses
* Uses many-to-one mapping (Many inside local addresses to one inside global address)

## PAT Components

### Translation Table

## Static PAT

Static PAT maps a specific private IP address and port number to a specific public IP address and port number

* Unidirectional
* Used for allowing external access to internal services, such as web servers, FTP servers, or gaming servers
* When traffic arrives at the public IP address on the specified port, the router forwards it to the corresponding internal IP address and port

## Dynamic PAT

Dynamic PAT maps multiple private IP addresses to a single public IP address (or a pool of public IP addresses) by using different port numbers

* Commonly used in scenarios where many devices need to access the internet simultaneously using a single public IP address
* When an internal device initiates a connection to the internet, the router assigns a unique port number to the session, allowing it to distinguish between different internal devices

## PAT Traffic

### Outbound PAT Traffic

1. **Packet Creation**: When an internal device sends a packet to an external destination, it constructs the packet with its own private IP address as the source IP and a random source port number
2. **Translation Table Lookup**: The router or firewall performing PAT will check its translation table to determine the appropriate public IP address to use for the translation
3. **Source Address Translation**: The router or firewall performing PAT will replace the source IP address in the packet header with its own public IP address, as well as the source port number with a unique port number allocated from a pool of available ports
4. **Packet Forwarding**: The router or firewall performing PAT will forward the modified packet towards the external destination

### Inbound PAT Traffic

1. **Packet Arrival**: A packet arrives at the router or firewall performing the PAT
2. **Translation Table Lookup**: The router or firewall performing PAT checks its translation table to find the corresponding entry for the destination IP address and port number in the incoming packet
