A Local Area Network is a network of devices that are interconnected within a limited geographical area 

* Also referred to as a single broadcast domain, which is a group of devices that'll receive a broadcast frame that has the destination MAC address set to FFFF.FFFF.FFFF and that was sent by one of the members
* Commonly used for sharing resources and internet connections among locally connected devices
* Lost of unnecessary broadcast traffic, which can reduce network performance
* Without VLANs configured, even if there are different subnets connected to the switch, broadcast frames will still be sent out of all interfaces since switches operate on Layer 2 of the OSI model and all the subnets are considered to be part of the same broadcast domain
