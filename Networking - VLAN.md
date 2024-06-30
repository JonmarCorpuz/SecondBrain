A Virtual Local Area Network is a method of logically dividing a physical network into multiple virtual networks

* Logically segments traffic within a network at the Layer 2 of the OSI model without requiring a physical separation of devices
* Switches don't forward traffic directly between hosts in different VLANs
* Automatically created when assigned to an interface

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/922c8b652a916ec056dcc5ebc65fee00.png)

* VLANs are configured on a switch by adding a 802.1q or dot1q tag to a frame, which will designate the VLAN that the traffic originated from
* The 802.1q tag provides a standard between vendors that'll always define the VLAN of a frame

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Types

## Data VLAN

A data VLAN handles the regular data traffic network

## Voice VLAN

A voice VLAN handles VoIP traffic generate

* Ensures that voice traffic gets the necessary priorirty and bandwidth to avoid delays and jitter

## Management VLAN

A management VLAN is used to access and manage network devices

* Having a dedicated virtual network for management traffic reduces the risk of unauthorized access to critical network infrastructure

## Native VLAN

A native VLAN is the network traffic that's carried untagged on trunk ports

* Allows devices that don't support VLAN tagging to still be able to receive and understand the traffic that belongs to the native VLAN

## Private VLAN

A private VLAN is a sub-VLAN of another VLAN

* Allows for isolation between hosts in the same VLAN without using multiple VLANs and IP subnets
* Conserves IP addresses
* Simplifies IP management

## Guest VLAN

A guest VLAN provides network access to guests without granting them access to the organization's internal network resources
