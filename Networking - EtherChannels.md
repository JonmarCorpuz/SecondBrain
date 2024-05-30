An EtherChannel, also known as a port channel or link aggregation group (LAG), is a technology that's used to combine multiple physical Ethernet links into a single logical link

* Primarily operates at the Data Link layer of the OSI model (Layer 2)
* Provides higher bandwidth and increased redundancy
* Provides load balancing across the member links by distributing traffic across multiple links

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
