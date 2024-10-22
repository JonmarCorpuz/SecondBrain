# LLDP Overview

The Link Layer Discovery Protocol (IEEE 802.1AB) is a vendor-neutral Layer 2 protocol that's used to advertise and discover information about networking devices that are directly connected to each other

* Allows devices to announce their identity, capabilities, and information about their neighbors on the network (Ex: *Device type*, *Device name*, *Port Identifier*, *VLAN information*, *System capabilities*, *etc.*)
* Considered as a security risk since they share information about the devices in the network
* Interface Tx and Rx operations are enabled separately

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# LLDP Messages

* Periodically sent to the 0180.C200.000E multicast MAC address
* Devices don't forward LLDP messages to other devices, meaning that a device can only become a LLDP neighbor with other directly connected devices (When a device receives a LLDP message, it'll process and then discard it)
* Sent once every 30 seconds
* If a LLDP message from a neighbor isn't sent for 120 seconds, the LLDP neighbor is removed from the LLDP neighbor table, which ensures that that LLDP neighbor table doesn't have entries from old LLDP neighbors that are no longer connected
* LLDP has a reinitialization delay timer of 2 seconds by default, which delays the actual initialization of LLDP and prevents devices from sending LLDP messages immediately when LLDP is enabled

