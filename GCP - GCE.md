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

| Compute Engine Machine Type | Description |
| --- | --- |
| Predefined Machine Type | |
| Custom Machine Type | A custom machine type created by the user to satisfy their needs |

### Predefined Machine Type

A machine type is a predefined configuration for VMs that specifies a set of hardware combinations (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*)

| Predefined Machine Type | Description |
| --- | --- |
| highcpu | |
| standard | |
| highmem | |
| megamem | |
| hypermem | |
| ultramem | |

### Custom Machine Type

A custom machine type is a custom machine type created by the user to satisfy their needs

* Allows you to adjust the amount of vCPUs, memory, and GPUs to suite your needs
* Billed per vCPU and memory that is provisioned to each VM instance

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

# GCE Features

| GCE Feature | Description |
| --- | --- |
| Availability Policy | A set of configurations that defines how GCP handles the availability and behavior of VM instances under different condititions |

## Availability Policy

An Availability Policy is a set of configurations that defines how GCP handles the availability and behavior of VM instances under different condititions (Ex: *What should happen to a VM instance during periodic infrastructure maintenance*, *Host failure*, *etc.*)

* Includes settings that determine a VM instance's behavior during planned and unplanned disruptions

| Availability Policy Feature | Description |
| --- | --- |
| On Host Maintenance | A running instance will be either migratated to another host in the same zone or stopped if the host that it's currently on goes offline |
| Automatic Restart | A running instance will be automatically restarted if they're terminated due to non-user-initiated reasons |

### On Host Maintenance

Live Migration is when a running instance will be either migratated to another host in the same zone or stopped if the host that it's currently on goes offline

* Doesn't change any attributes or properties of the VM instance
* Supported VM instances include instances with local SSDs
* Not supported VM instances include preemptible instances and instances to which you have added GPUs
* Configured using an Availability Policy

### Automatic Restart 

Automatic Restart is when a running instance will be automatically restarted if they're terminated due to non-user-initiated reasons (Ex: *Maintenance event*, *Hardware failure*, *etc.*)
