# Types of VMWare vSwitches

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vSwitches.png)

## vSwitch

The vSphere Standard vSwitch is a basic virtual switch in VMWare vSphere that enables and facilitates network communication for VMs running on a specific ESXi host and the physical network

* Created on each ESXi host to handle network traffic for VMs and other network-related services
* Operates at the data link layer (Layer 2) of the OSI model 
* Managed on a per-host basis, meaning that each host in the vSphere environment has its own independent vSwitch configuration
* Configuration and management of the vSwitch are done through the vSphere Web Client or vSphere Client
* Supports NIC teaming, which involves the use of multiple physical network adapters (NICs) for redundancy and load balancing in order to ensure network connectivity in case of a NIC failure and optimize network performance
* Allows administrators to configure traffic shaping policies (A set of rules or configurations applied to control the rate of data transmission or reception for network traffic) on the vSwitch in order to control and prioritize network traffic based on specific requirements
* Virtual switches can have one or more network adapters (uplinks) associated with them, which all provide connectivity to the physical network

## Distributed vSwitch

The vSphere Distributed Switch is an advanced virtual switch in VMWare's vSphere virtualization platform that provides a centralized management and configuration of networking settings for multiple ESXi hosts within a vSphere cluster

* Part of the vSphere Enterprise Plus edition
* Designed to simplify network administration in larger and more complex virtualized environments
* Organizes virtual networks into port groups, where each port group can have its own specific configuration settings (Ex: *VLAN assignments*, *Security policies*, *etc.*)
* Supports load-based teaming in order to allow for dynamic distribution of network traffic across multiple physical network adapters based on load conditions
* Supports Network I/O Control (NIOC) in order to provide QoS by allocating network bandwidth to different traffic types to ensure that critical workloads receive the necessary resources
* Supports traffic shaping
* Supports port mirroring (A network feature that allows the traffic passing through one network port or group of ports to be duplicated and sent to another port for analysis or monitoring purposes), which allows administrators to monitor and analyze network traffic by redirecting selected network traffic to a designated port for inspection
* Allows configurations to be backed up and restored when needed, simplifying the process of recovering from configuration changes or hardware failures
* Supports DvSwitches to be spanned across multiple vCenter Server Instances, making it easier to manage networking in a distributed environment

## Distributed Port Group (DVPortGroup)
