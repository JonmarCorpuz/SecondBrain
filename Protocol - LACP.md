LACP allows network devices to automatically negotiate and manage the bundling of multiple physical Ethernet links into a single logical links

* Ensures that only compatible ports are aggregated and that they share the same configuration parameters

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# LACP Process

## LACP Initialization

## LACP Negotiation

When LACP is enabled on network devices they'll first exchange LACP packets to negotiate the formation of an EtherChannel

* Each device will send out LACP frames containing its system information (Ex: *System ID*, *Port ID*, *etc.*) and LACP capabilities (Ex: *Supported LACP modes*, *The maximum number of ports*, *etc.*)
* Based on the exchanged information, the devices will determine the appropriate configuration for forming the EtherChannel (Ex: *The ports to be aggregated*, *LACP operation mode*, *etc.*

## LACP Aggregation

Based on the LACP negotiation, the devices determine which ports should be included in the EtherChannel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# LACP Operation Modes

## Active

## Passive
