# VXLAN Overview

A Virtual Extensible Local Area Nnetwork is a network virtualization technology and encapsulation method that addresses the scalability limitations of traditional VLANs 

* Widely used in data center environments to enable the creation of logical networks that span across physical network boundaries
* Changes the way VLANs transit a network by taking an Ethernet frame and encapsulating it in an IP packet using UDP as its transport (Also known as MAC-in-IP encapsulation because the layer 2 frame is untouched and wrapped in a normal IP/UDP packet)

# VXLAN Components

## Original Ethernet Frame

The original Ethernet frame is the actual Layer 2 Ethernet frame that needs to be transported across the network

* Includes the MAC addresses, EtherType field, payload, and the FCS

## VXLAN Header

VXLAN header encapsulates Layer 2 Ethernet frames within Layer 3 UDP packets

* VXLAN headers are 64 bits (8 bytes), which contain:
	* VNI (VXLAN Network Identifier), which uses 24 bits of that header
	* Flags
	* Reserved bits

# VTEP

VXLAN introduces the concept of VXLAN Tunnel Endpoint, which is any device that can process VXLAN packets

* VTEP includes encapsulating VXLAN packets for routing or bridging, or removing the encapsulation to natively route or bridge
* When a VTEP receives a packet that's destined to a local host, it removes the encapsulation leaving only the original Layer 2 Ethernet frame behind
