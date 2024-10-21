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

* All VLANs are allowed on a trunk port by default
* If a VLAN doesn't exist, even if it's allowed on the trunk it won't appear in the VLANs allowed and active list

### Inter-Switch Link

The ISL is a Cisco proprietary VLAN trunking protocol that encapsulates the entire Ethernet frame with an ISL header and trailer

* Created before the industry standard IEEE 802.1Q

### IEEE 802.1Q

The IEEE 802.1Q is a industry standard trunking protocol that inserts a 4-byte (32 bits) between the source and length/type fields of the Ethernet frame header

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dsfdfdgsgdfsgfdsgdfsfdsfdsfdsfddfsdfsfdsdsfdsg.png)

* VLANs are configured on a switch by adding a 802.1q or dot1q tag to a frame, which will designate the VLAN that the traffic originated from
* The 802.1q tag provides a standard between vendors that'll always define the VLAN of a frame
* Provides a native VLAN for trunk ports, which is used for untagged traffic and used the VID 1 on all trunks by default

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

ROAS is a networking technique that's used to route traffic between multiple VLANs by creating multiple subinterfaces on an interface for each VLAN

* Each subinterface is configured with a unique VLAN tag and an IP address in order to allow the router to distinguish and route traffic between VLANs over a single physical connection
* The router will behave as if frames arriving with a certain VLAN tag have arrived on the subinterface configured with that VLAN tag
* The router will tag frames sent out of each subinterface with the VLAN tag configured on the subinterface

## SVI Routing

A switch virtual interface is a virtual interface on a Layer 3 switch that represents a VLAN interface for routing and management purposes

* Used for inter-VLAN routing within the switch itself
* Can route traffic between SVIs without the need of an external router
* Typically have an IP address assigned to it and functions similarly to physical interfaces but within the context of a VLAN on the switch
* Configured as a VLAN's default gateway
* SVIs get added to the Layer 3 switch's routing table
* Must have at least one access or trunk port in the VLAN to be in an up/up state in order for it to be up/up itself (If not, it'll remain down/down)
* SVIs are shutdown by default

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VLAN Types

## Data VLAN

A data VLAN handles the regular data traffic network

* Data traffic uses the IP network (Ex: *Enterprise WAN*, *Internet*, *etc.*)

## Voice VLAN

A voice VLAN handles VoIP traffic generate

* Ensures that voice traffic gets the necessary priorirty and bandwidth to avoid delays and jitter
* Voice traffic uses the PSTN

## Management VLAN

A management VLAN is used to access and manage network devices

* Having a dedicated virtual network for management traffic reduces the risk of unauthorized access to critical network infrastructure

## Native VLAN

A native VLAN is the network traffic that carries untagged traffic on trunk ports

* Allows devices that don't support VLAN tagging to still be able to receive and understand the traffic that belongs to the native VLAN
* Not available in ISL
* Each switch in the network must have the same native VLAN
* Expects all traffic in the Native VLAN to be untagged, meaning that it doesn't have a dot1q tag (If a frame does happen to have a dot1q tag, the switch will consider this as an error and will not forward it)
* Assigned to an unused VLAN
* Each frame is smaller since they're not tagged, which allows the device to send more frames per second
* Networking devices will understand that untagged traffic belongs to the native VLAN, so there's no need to encapsulate them with dot1q tag

## Private VLAN

A private VLAN is a sub-VLAN of another VLAN

* Allows for isolation between hosts in the same VLAN without using multiple VLANs and IP subnets
* Conserves IP addresses
* Simplifies IP management

## Guest VLAN

A guest VLAN provides network access to guests without granting them access to the organization's internal network resources
