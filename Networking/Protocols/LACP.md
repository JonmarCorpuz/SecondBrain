# LACP Overview

LACP allows network devices to automatically negotiate and manage the bundling of multiple physical Ethernet links into a single logical links

* Ensures that only compatible ports are aggregated and that they share the same configuration parameters
* Used to configure EtherChannels

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# LACP Process

## LACP Initialization

## LACP Negotiation

When LACP is enabled on network devices they'll first exchange LACP packets to negotiate the formation of an EtherChannel

* Each device will send out LACP frames containing its system information (Ex: *System ID*, *Port ID*, *etc.*) and LACP capabilities (Ex: *Supported LACP modes*, *The maximum number of ports*, *etc.*)
* Based on the exchanged information, the devices will determine the appropriate configuration for forming the EtherChannel (Ex: *The ports to be aggregated*, *LACP operation mode*, *etc.*

## LACP Aggregation

Based on the LACP negotiation, the devices form the EtherChannel by determining which ports should be included in the EtherChannel

## LACP Dynamic Management

After the EtherChannel is formed, the devices continue to exchange LACP frames periodically to monitor the status of the EtherChannel and the individual member ports

* In response to detected changes, LACP dynamically adjusts the configuration of the EtherChannel (Ex: *LACP can dynamically incorporate a newly added port to an EtherChannel into the bundle without disrupting network traffic*, *etc.*)
* Ensures network continuity and resilience by reverting an EtherChannel port bundle back to individual port operation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# LACP Operation Modes

## Active

* The network device will actively send LACP frames to initiate and negotiate the formation of an EtherChannel with a neighboring device
* The network device will actively seek to form EtherChannels with compatible devices that support LACP (Neighboring devices supporting LACP will respond to the LACP frames by the active device and proceed with the LACP negotiation)
* Typically used on interfaces that you want to actively participate in forming EtherChannels

## Passive

* A network device will only respond to LACP frames sent by the neighboring devices instead of actively sending LACP frames to initiate the negotiating process
* The network will wait for LACP frames from the neighboring device before proceeding with EtherChannel negotiation
* Used on interfaces that you want to passively participate in EtherChannel negotiation without actively initiating it
