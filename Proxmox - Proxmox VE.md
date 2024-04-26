Proxmox is an open-source server virtualization management platform that allows users to deploy and manage VMs and containers on a single host or across multiple hosts in a cluster

* Based on Debian Linux
* Utilizes KVM for virtualization

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxmox Components

## Virtual Machine Bridge

The vmbr is a virtual network interface that's used to connect VMs and containers to the physical network

* Allows communication between the virtualized environment and external networks by serving as a brdige between the virtual network inside Proxmox and the physical network infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Proxmox Features

## Kernel-based Virtual Machine

KVM enables Proxmox to utilize KVM as its primary hypervisor to create and manage multiple VMs on a single physical host at the same time

* Provides hardware-assisted virtualization support, which enables efficient and high-performance virtualization by utilizing processor extensions
