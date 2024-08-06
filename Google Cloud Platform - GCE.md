The Google Compute Engine is a the service engine that provisions VMs to users using Google's cloud infrastructure

* Allows the creation and management of VM instances, as well as their lifecycles and network configurations
* Provides scalable, flexible, and reliable computing resources for a wide range of applications
* Offers various types of VMs with different components to suite different workloads (Ex: *CPU*, *Memory*, *Storage configurations*, *etc.*)
* Provides persistent disks for VM storage and allows users to create snapshots of persistent disks for backup and disaster recovery
* Provides networking features (Ex: *VPC*, *Subnets*, *Firewall rules*, *Routes*, *Load-balancing*, *Autoscaling*, *etc.*)

| Compute Engine Element | Description |
| --- | --- |
| Name | <machine_type_family>-<workload_type>-<number_of_gpu> |
| Labels | |
| Region | |
| Zone | |
| Machine Configuration | |
| Boot Disk | |
| Firewall | |

# Machine Configuration



## Compute Engine Machine Family

A machine family is a curated set of processor and hardware configurations that are optimized for specific workloads

* Machine families are further classified by series, generation, and processor type

| Compute Engine Machine Family | Description |
| --- | --- |
| General Purpose | Provides a balanced mix of compute, memory, and network resources | 
| Compute-Optimized | Provides high compute performance per core for compute-intensive workloads |
| Memory-Optimized | Provides large amounts of memory for memory-intensive workloads |
| Storage-Optimized | Provides large amounts of storage for workloads that are low in core usage and high in storage density |
| Accelerator-Optimized | Provides GPU acceleration for workloads that require GPUs |

## Compute Machine Series



## Compute Engine Machine Type

A machine type is a predefined configuration for VMs that specifies a set of hardware combinations (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*)

| Predefined Machine Type | Description |
| --- | --- |
| highcpu | |
| standard | |
| highmem | |
| megamem | |
| hypermem | |
| ultramem | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Boot Disk 

## Image

| Image Type | Description |
| --- | --- |
| Public Image | Provided and maintained by Google, open-source communities, or third party vendors | 
| Custom Image | Created by you for your projects |

## Custom Image

* Can be created from an instance, a persistent disk, a snapshot, another image, or a file in Cloud Storage
* Can be shared across projects
* Decreases boot up time by having OS patches and software already pre-installed
* Can be used to create VM instances in mutliple different regions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
