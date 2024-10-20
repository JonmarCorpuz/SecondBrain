# GCE Overview

The Google Compute Engine is a the service engine that provisions VMs to users using Google's cloud infrastructure

* Allows the creation and management of VM instances, as well as their lifecycles and network configurations
* Provides scalable, flexible, and reliable computing resources for a wide range of applications
* Offers various types of VMs with different components to suite different workloads (Ex: *CPU*, *Memory*, *Storage configurations*, *etc.*)
* Provides persistent disks for VM storage and allows users to create snapshots of persistent disks for backup and disaster recovery
* Provides networking features (Ex: *VPC*, *Subnets*, *Firewall rules*, *Routes*, *Load-balancing*, *Autoscaling*, *etc.*)

| Compute Engine Element | Description | Example |
| --- | --- | --- |
| Name | <machine_type_family>-<workload_type>-<number_of_gpu> |
| Labels | |
| Region | |
| Zone | |
| Machine Configuration | |
| Boot Disk | |
| Firewall | |

# Machine Configuration

* Machine name is <machine_type_family>-<workload_type>-<number_of_cpu> (Ex: e2-standard-4)

## Machine Family

A machine family is a curated set of VM configurations that are optimized for specific workloads

* Machine families are further classified by series, generation, and processor type
* Each machine family have a set of characteristics that are tailored to certain performance needs
* Each machine family offers various machine types

| Machine Family | Description | Machine Types |
| --- | --- | --- |
| General Purpose | Provides a balanced mix of compute, memory, and network resources |  |
| Compute-Optimized | Provides high compute performance per core for compute-intensive workloads |  |
| Memory-Optimized | Provides large amounts of memory for memory-intensive workloads |  |
| Storage-Optimized | Provides large amounts of storage for workloads that are low in core usage and high in storage density |  |
| Accelerator-Optimized | Provides GPU acceleration for workloads that require GPUs |  |

## Machine Type

A machine type is a set of specific predefined or customized configuration of VM resources (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*) (The more vCPU you have, the more memory and networking capabilities you have)

* Machine type availability can vary from region to regions

| Machine Type | Description |
| --- | --- |
| Predefined Machine Type | A predefined configuration of VM resources (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*) |
| Custom Machine Type | A custom configuration of VM resources (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*) |

### Predefined Machine Type

A predefined machine type is a predefined configuration of VM resources (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*)

### Custom Machine Type

A custom configuration of VM resources (Ex: *vCPU*, *RAM*, *GPU*, *local SSD*, *etc.*)

* Created by a user when the predifined machine types aren't sufficient for their workloads
* Allows you to adjust the amount of vCPUs, memory, and GPUs to suite your needs
* Billed per vCPU and memory that is provisioned to each VM instance
* Remember to use images with GPU libraries installed otherwise the added GPU won't be used (GPUs aren't support on all machine types)

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
| Autoscaling | A feature that automatically adjusts the number of compute resources based on predefined criteria or metrics |

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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Node Groups

A node group is a homogeneous set of sole-tenant nodes in a specific zone

* A node group can have zero or more nodes, and can contain multiple VMs running on machine types of various sizes, as long as the machine type has two or more vCPUs

## Sole-Tenant

A sole-tenant node is a physical Compute Engine server that's dedicated to host a group of VM instances on the same hardware

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/skdhgfhgsdfgosdfgdsfgjkfdsjkgfdsgjk.png)

* Sole-tenant nodes can help you meet dedicated hardware requirements for BYOL scenarios that require per-core or per-processor licenses
* Sole-tenant nodes provide visibility into the node's underlying hardware, which allows you to track core and processor usage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Instance Storage 

| Storage Type | Description | 
| --- | --- |
| Local SSD | |
| Persistent Disk | |

## Local SSD

* Physically attached to the host of the VM instance
* Temporary data that persists until the VM instance stops (Lower durability and availability)
* Lifecycle tied to VM instance
* Provides very fast I/O and throughput, as well as very low latency
* Data is automatically encrypted but you can't configure the encryption keys
* Supports SCSI and NVMe interfaces
* Can't be detached and attached to another VM instance
* Doesn't support snapshots

## Persistent Storage

* Network storage
* Lifecycle isn't tied to a VM instance
* Supports snapshots
* A persistent disk is automatically attached by default that's used as the boot disk

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSHing Into Linux VMs

Option 1: Console (SSH Button)
* Ephemeral SSH key pair is created

Option 2: Gcloud

Option 3: Use customized SSH keys
* Metadata managed
* OS Login (Set enable-oslogin to true in metadata)
