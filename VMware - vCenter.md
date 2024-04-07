vCenter is a centralized management platform that provides administrators with a unified interface for managing and monitoring virtualized environments

* Designed to streamline and enhance the management of VMWare vSphere environments, which are widely used for server virtualization

# vCenter Features

## vSphere High Availability

vSphere HA ensures the availability of VMs by automatically detecting host failures and restarting the VMs from that failed host on an alternate host within the cluster

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/vSphere%20HA.jpg)

## vMotion

vMotion allows for the live migration of VMs from one host to another without any interruption to the VM's operation

* Can be used to dynamically balance the workload across a cluster of ESXi hosts by migrating VMs to hosts with lower resource utilization (Load Balancing)
* Ensures that a VM's transition is seamless and without downtime, which is achieved by transferring the entire state of the VM (Ex: *Memory*, *CPU*, *Device states*, *etc.*)
* Facilitates the relocation of VMs between different datacenters (Datacenter Migration)

### Storage vMotion

Storage vMotion enables the live migration of VM storage from one datastore to another without any interruption to the VM's operation

* Allows administrators to move the VMDK files associated with a running VM from one datastore to another with zero downtime (Live Storage Migration)
* Ensures a seamless transition without service interruption (Zero Downtime)
* Allows administrators to balance storage loads across datastores, optimize resource utilization, and adapt to changing storage requirements
* Facilitates maintenance activities by allowing administrators to migrate VMs off a datastore that needs maintenance, upgrades, or decommissioning (Maintenance Operations)
