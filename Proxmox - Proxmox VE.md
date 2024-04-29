Proxmox is an open-source server virtualization management platform that allows users to deploy and manage VMs and containers on a single host or across multiple hosts in a cluster

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dshdoiasiffdsgfafgea.png)

* Based on Debian Linux
* Utilizes KVM for virtualization

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxmox Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Opera%20Snapshot_2024-04-25_223038_getlabsdone.com.png)

## Virtual Machine Bridge

The vmbr is a virtual network interface that's used to connect VMs and containers to the physical network

* Allows communication between the virtualized environment and external networks by serving as a brdige between the virtual network inside Proxmox and the physical network infrastructure

## Bond

A bond is a network bonding configuration used to combine multiple physical network interfaces into a single logical interface

* Provides increased bandwidth and can improve network throughput

## Quick Emulator

QEMU is the open-source virtualization technology that's used to emulate and run VMs and containers within Proxmox

* Serves as the hypervisor
* Responsible for creating and managing virtual machines and containers
* Emulates hardware components (Ex: *CPU*, *RAM*, *etc.*)

## Quick Emulator Agent

A QEMU Agent enhances the communication and interaction between the Proxmox host and the virtual machine running on it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxmox Cluster Components

## Resource Pool

A resource pool is a logical grouping of physical or virtual resources (Ex: *CPU*, *RAM*, *etc.*)

## Ceph

Ceph is a distributed storage system solution that's used in a Proxmox cluster by deploying it alongside Proxmox hosts

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/28519913-b1429d2a-706d-11e7-83cf-e1369b5e923f.gif)

* Provides a scalable and high-performant storage by distributing data across a cluster of storage nodes (Object Storage Devices)
* Allows administrators to easily provision and manage storage resources for VMs and containers
* Allows administrators to add more OSDs and storage nodes to the cluster to scale out when needed
* Provides fault tolerance and ensures data availability by replicating data across multiple OSDs and storage nodes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxmox Features

## Kernel-based Virtual Machine

KVM enables Proxmox to utilize KVM as its primary hypervisor to create and manage multiple VMs on a single physical host at the same time

* Provides hardware-assisted virtualization support, which enables efficient and high-performance virtualization by utilizing processor extensions
