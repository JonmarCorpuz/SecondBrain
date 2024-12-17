# Compute Engine Overview

Google's Compute Engine is a the service engine that provisions VMs to users using Google's cloud infrastructure

* Allows the creation and management of VM instances, as well as their lifecycles and network configurations
* Provides scalable, flexible, and reliable computing resources for a wide range of applications
* Offers various types of VMs with different components to suite different workloads (Ex: *CPU*, *Memory*, *Storage configurations*, *etc.*)
* Provides persistent disks for VM storage and allows users to create snapshots of persistent disks for backup and disaster recovery
* Provides networking features (Ex: *VPC*, *Subnets*, *Firewall rules*, *Routes*, *Load-balancing*, *Autoscaling*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

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

# VM Types

## Regular

## Preemptible 

* Offers the same configuration options as regular VMs
* Persists up to 24 hours and may terminate at any time
* Reduces costs
* Cannot migrate to a regular VM and automatically restart
* Commonly used for applications that are fault-tolerant and can withstand possible instance interruptions

## Spot

* Provides the same benefits as preemptible VMs but without the 24 hours time limit

## Shielded

### Secure Boot

* Protects against boot-level and kernel-level malicious code by ensuring that only authenticated OS software runs on the VM through digital signature checks (If a digital signature check fails, the boot process fails)

### vTPM

* Validates boot integrity
* Provides additional protections for key generation and protection
* Provides you with the option of enabling Integrity Monitoring, which verifies the runtime integrity of the VM

### Integrity Monitoring

* Uses a known good baseline of boot measurements to compare to recent boot measurements (If the check fails, that means some difference exists between the baseline measurement and the current measurement)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Images

## Public Image

Provided and maintained by Google, open-source communities, or third party vendors

## Custom Image

* Can be created from an instance, a persistent disk, a snapshot, another image, or a file in Cloud Storage
* Can be shared across projects
* Decreases boot up time by having OS patches and software already pre-installed
* Can be used to create VM instances in mutliple different regions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Availability Policies

An Availability Policy is a set of configurations that defines how GCP handles the availability and behavior of VM instances under different condititions (Ex: *What should happen to a VM instance during periodic infrastructure maintenance*, *Host failure*, *etc.*)

* Includes settings that determine a VM instance's behavior during planned and unplanned disruptions

| Availability Policy Feature | Description |
| --- | --- |
| On Host Maintenance | A running instance will be either migratated to another host in the same zone or stopped if the host that it's currently on goes offline |
| Automatic Restart | A running instance will be automatically restarted if they're terminated due to non-user-initiated reasons |

## On Host Maintenance

Live Migration is when a running instance will be either migratated to another host in the same zone or stopped if the host that it's currently on goes offline

* Doesn't change any attributes or properties of the VM instance
* Supported VM instances include instances with local SSDs
* Not supported VM instances include preemptible instances and instances to which you have added GPUs
* Configured using an Availability Policy

## Automatic Restart 

Automatic Restart is when a running instance will be automatically restarted if they're terminated due to non-user-initiated reasons (Ex: *Maintenance event*, *Hardware failure*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Sole-Tenant

A sole-tenant node is a physical Compute Engine server that's dedicated to host a group of VM instances on the same hardware

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/skdhgfhgsdfgosdfgdsfgjkfdsjkgfdsgjk.png)

* Only VMs in your project with node affinity labels matching the labels you specify will run on the same server together
* Help you meet dedicated hardware requirements for BYOL scenarios that require per-core or per-processor licenses
* Provide visibility into the node's underlying hardware, which allows you to track core and processor usage

## CPU Overcommit

* Increases performance by scheduling VMs with more CPU requirements than actually available if the VMs don't need all the commited resources at the same time

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Storage 

* Disks can be attached as read/write or read-only

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

# VM Connectivity Methods

## Cloud Console

Option 1: Console (SSH Button)
* Ephemeral SSH key pair is created

## SSH Using Command Line

## SSH Using Customized SSH Keys

Option 3: Use customized SSH keys
* Metadata managed
* OS Login (Set enable-oslogin to true in metadata)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Access Control

* Users can disallow the use of project-based SSH keys

## Access Scopes

* A legacy access control mechanism that existed before IAM
* Allows minimal by default

## IAM

* When enabled, only users with a role that have permission to enable IAM-based access can login (*Compute OS Login*, *Compute OS Admin*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Disk Encryption

* All data is encrypted at rest

## Google-Managed Encryption Keys

Google creates and managed the encryption keys

## Customer-Managed Encryption Keys

Customers create their own encryption keys but Google manages them

## Customer-Supplied Encryption Keys

Customers create and manage their encryption keys outside of Google

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Serial Port

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metadata

* Stored in Google's metadata server, which is available for querying using the Compute Engine API

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

