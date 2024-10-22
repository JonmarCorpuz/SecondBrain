# EtherChannel Overview

An EtherChannel, also known as a port channel or link aggregation group (LAG), is a technology that's used to combine multiple physical Ethernet links into a single logical link

* Operates on Layers 2 and 3 of the OSI model
* Provides higher bandwidth and increased redundancy by grouping multiple interfaces together and having them act as a single interface
* Provides load balancing across the member links by distributing traffic across multiple links
* Prevents oversubscription, which is when the bandwidth of the interfaces connected to end hosts is greater than the bandwidth of the connection to the distribution switches
* Solves the problem of having only one link active while there's multiple links connected between two switches that aren't grouped together into a single logical link because of STP
* Only eight interfaces can be formed into a single EtherChannel (LACP allows up to 16, but ony 8 will be active while the rest will be in stanbdy mode)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EtherChannel Configuration Methods

## PAgP

* Cisco proprietary protocol
* Dynamically negotiates the creation and maintenance of the EtherChannel
* PAgP EtherChannel configuration modes include **auto** and **desirable**

| Link Configuration | EtherChannel Formation |
| --- | --- |
| auto + auto | No |
| desirable + auto | Yes |
| desirable + desirable | Yes |

## LACP

* Industry standard protocol (IEEE 802.3ad)
* Dynamically negotiates the creation and maintenance of the EtherChannel
* LACP EtherChannel configuration modes include **active** and **passive**

| Link Configuration | EtherChannel Formation |
| --- | --- |
| passive + passive | No |
| active + passive | Yes |
| active + active | Yes |

## Static EtherChannel

* A protocol isn't used to determine if an EtherChannel should be formed
* Interfaces are statically configured to form an EtherChannel
* Doesn't allow switches to dynamically maintain the EtherChannel
* Static EtherChannel configuration modes include **on** and will only form an EtherChannel if the other switch's EtherChannel is configured in **on** mode as well

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EtherChannel Components

## Channel Group Number

* Has to match for member interfaces on the same switch
* Doesn't have to match the channel group number on the adjacent switch (Ex: *Channel group 1 on switch 1 can form an EtherChannel with channel group on switch 2*)
* Each member interface must have matching configurations (Ex: *Duplex*, *Speed*, *Switchport mode*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EtherChannel Negotiation

EtherChannel negotiation refers to the process where network devices dynamically form EtherChannels by bundling multiple physical links into a single logical link

* Involves the exchange of messages between the devices to determine which ports should be included in the EtherChannel and to configure the channel settings

## Link Aggregation Control Protocol

LACP is a dynamic negotiation protocol that allows network devices to automatically negotiate and manage the bundling of multiple physical Ethernet links into a single logical links

* LACP negotiation modes include Active (The device will actively initiate LACP negotiation) and Passive (The device will wait for the other end to initiate negotiation)
* Exchanges control messages between the participating devices to negotiate the formation of the EtherChannel

## Port Aggregation Protocol
 
PAgP is a Cisco proprietary protocol that's used to automatically negotiate and manage the formation of EtherChannels between Cisco switches

* PAgP negotiation modes include Active (The device will actively initiate LACP negotiation) and Passive (The device will wait for the other end to initiate negotiation)
* Exchanges control messages between Cisco switches to negotiate the bundling of ports into an EtherChannel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EtherChannel Load Balancing

* Load balances based on **flows**, which is a communication between two nodes in a network, meaning that frames in the same flow will be forwarded using the same physical interface (If some frames in the same flow were forwarded using different physical interfaces, some frames may arrive at the destination out of order)
* Load balacing is configured based on inputs (Ex: *Source MAC addresses*, *Destination MAC addresses*, *Source IP addresses*, *Destination IP addresses*, *etc.*)
