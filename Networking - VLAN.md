A Virtual Local Area Network is a method of logically dividing a physical network into multiple virtual networks

* Logically segments traffic within a network at the Layer 2 of the OSI model without requiring a physical separation of devices
* Switches don't forward traffic directly between hosts in different VLANs
* Automatically created when assigned to an interface

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Ports

## Access Ports

An access port (Untagged port) is a switchport that's assigned to a single VLAN and carries traffic for that VLAN only

* Frames sent over an access port aren't tagged because the interface belongs only to a single VLAN

## Trunk Ports

A trunk port (Tagged port) is a switch port that carries traffic for multiple VLANs 

### Inter-Switch Link

The ISL is a Cisco proprietary VLAN trunking protocol that encapsulates the entire Ethernet frame with an ISL header and trailer

* Created before the industry standard IEEE 802.1Q

### IEEE 802.1Q

The IEEE 802.1Q is a industry standard trunking protocol that inserts a 4-byte (32 bits) between the source and length/type fields of the Ethernet frame header

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dsfdfdgsgdfsgfdsgdfsfdsfdsfdsfddfsdfsfdsdsfdsg.png)

* VLANs are configured on a switch by adding a 802.1q or dot1q tag to a frame, which will designate the VLAN that the traffic originated from
* The 802.1q tag provides a standard between vendors that'll always define the VLAN of a frame

#### TPID 

* 16 bits (2 bytes) in length
* Always set to a value of 0x8100 to indicate that the frame is 802.1Q-tagged
* 

#### PCP

* 3 bits in length
* Used for Class of Service, which prioritizes important traffic in congested networks

#### DEI

* 1 bit in length
* Used to indicate frames that can be dropped if the network is congested, which makes sure that more important traffic gets through

#### VID

* 12 bits in length, which means that there are 4096 total VLANs
* Identifies the VLAN that the frame belongs to
* VLANs 0 and 4095 are reserved, meaning that the actual range of VLANs is 1 to 4094

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Ranges

## Normal VLANs



## Extended VLANs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Routing

## Router on a Stick

## SVI Routing

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
* Not available in ISL

## Private VLAN

A private VLAN is a sub-VLAN of another VLAN

* Allows for isolation between hosts in the same VLAN without using multiple VLANs and IP subnets
* Conserves IP addresses
* Simplifies IP management

## Guest VLAN

A guest VLAN provides network access to guests without granting them access to the organization's internal network resources
