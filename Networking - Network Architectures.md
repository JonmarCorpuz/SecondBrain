# Two-Tier Network Architecture

## Access Layer 

The Access layer is the point at which end devices connect to the local network

* Provides physical network connectivity to the network infrastructure for end devices
* Enforces network policies and security (Ex: *Port security*, *VLANs*, *ACLs*, *Firewall rules*, *etc.*)
* Has a lot of ports for end hosts to connect to
* QoS marking is typically done here

## Distribution Layer

The Distribution layer serves as an intermediary between the Access Layer and the Core Layer

* Aggregates traffic from multiple Access layer switches or segment before forwarding it to a WAN to help reduce the number of connections required between the Access and Core layers and optimize network bandwidth usage
* The border between Layer 2 and Layer 3
* Make routing decisions to determine the best path for traffic within the network (Ex: *Static routes*, *OSPF*, *EIGRP*, *etc.*)
* Responsible for enforcing network policies and access control mechanisms (Ex: *ACLs*, *QoS policies*, *VLANs*, *etc.*)
* Typically implements redundancy and high availability features to ensure network resilience and minimize downtime (Ex: *EtherChannels*, *HSRP*, *VRRP*, *etc.*)
* Distribution switches can connect to other distribution switches from other LANs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Three-Tier Network Architecture

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/03fig03.jpg)

## Access Layer

* The layer that end hosts connect to
* Typically have lots of ports for end hosts to connect to
* QoS marking is typically done here
* Security services are performed here (Ex: *Port security*, *DAI*, *etc.*)

## Distribution Layer

* Aggregates connections from the Access Layer switches
* Typically is the border between Layer 2 and Layer 3

## Core Layer

* Helps scale large LAN networks by connecting distribution layers together in large LAN networks (Recommended to use if there are more than three Distribution Layers in a single location)
* Connections are all Layer 3
* Focuses on speed
* CPU-intensive operations should be avoided at this layer (Ex: *QoS marking*, *Port security*, *etc.*)
* Should remain connectivity throughout the LAN even if devices fail

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Enterprise Network Architecture

An enterprise network refers to the interconnected IT infrastructure and networking components used by an organization to facilitate communciation, collaboration, and data exchange among its employees, departments, and external stakeholders

* Typically designed to meet the specific needs and requirements of large-scale organizations
* Designed to be scalable

## Enterprise Network Architecture Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/A-Typical-Enterprise-Network-Source.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/01fig20_alt.jpg)

### Enterprise Edge

The Enterprise Edge refers to the part of the network that interfaces with external networks and services (Ex: *Internet*, *Extranets*, *Remote branch offices*, *etc.*)

* Acts as a boundary between the internal network of an organization and the outside world
* Includes various networking devices (Ex: *Firewalls*, *Routers*, *VPN concentrators*, *etc.*)
* Critical for ensuring the security, availability, and performance of network services for an organization

### Service Provider Edge

The Service Provider Edge refers to the part of the network that sits between an organization's internal network and their service provider's network

* Enables and facilitates the interconnection of the SP's network with the organization's internal network
* Responsible for managing and directing traffic within the provider's network to ensure efficient use of network resources and optimal performance for customers (Ex: *Traffic prioritization*, *Traffic shaping*, *Traffic engineering*, *etc.*)
* The Service Provider Edge is where various services offered by the SP are delivered to customers (Ex: *VPNs*, *Internet access*, *etc.*)
* Serves as the entry point to the Sp's network

### Server Farm

A Server Farm, also known as a data center or a server cluster, is a centralized facility used to house and manage a large number of servers and associated equipment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Spine-Leaf Architecture

* Two-tier network architecture that's designed for data centers
* Traditional three-tier architecture led to bottlenecks in bandwidth as well as variability in the server-to-server latency depending on the path the traffic takes
* The path taken by traffic is randomly chosen to balance the traffic load among the Spine switches
* Provides consistent latency for East-West traffic (Traffic between the servers) since each server is separated by the same number of hops, except those connected to the same Leaf switch

## Spine-Leaf Architecture Components

### Spine Switches

* Spine switches don't connect to other Spine switches

### Leaf Switches

* Every Leaf switch is connected to every Spine switch and vice versa
* Leaf switches don't connect to other Leaf switches
* End hosts only connect to Leaf switches

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Split-MAC Wireless Architecture

* Scalable
* The WLC can automatically select which channel each AP should use
* The WLC can automatically set the appropriate transmit power for each AP to provide sufficient coverage without interfering with other APs
* The WLC can provide self-healing coverage, meaning that when an AP stops functioning, the WLC can increase the transmit power of nearby APs to avoid coverage holes
* Provides seamless roaming, meaning that wireless clients can roam between APs with no noticeable delay
* Provides client load balancing, meaning that if a wireless client is in range of two APs, the WLC can associate the client with the least-used AP to balance the load among APs
* Provides central management of security and QoS policies to ensure consistency across the network
