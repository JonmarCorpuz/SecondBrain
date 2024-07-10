A Campus Area Network is a type of network that interconnects multiple LANs within a campus, which is a physical area where a group of buildings or facilities belong to an organization (Ex: *University campus*, *Corporate campus*, *Military base*, *etc.*)

* Provides high-speed connectivity
* Facilitates the exchange of data and resources among different departments, buildings, or area within the campus

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Enterprise CAN Network Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/03fig03.jpg)

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

## Core Layer

The Core layer serves as the backbone of the network
