# Instances

A virtual machine instance is a virtualized computing environment that runs on a physical host machine

* Can be edited only when stopped
* Each instance runs in a specific zone (Zonal)

## Instance Types

| Instance Type | Description |
| --- | --- |
| Preemptible | Short-lived cheaper VM instance for workloads that don't require continuous availability | 
| Spot | Same as a preempt instance but without the maximum 24 hour runtime |
| Standard | A regular VM instance |

### Preemptible Instances

A preempt instance is a short-lived VM instance that's used for workloads that don't require continuous availability

* Has a maximum runtime of 24 hours
* Can be reclaimed by GCP at any time
* No Service Level Agreement
* No automatic restarts
* No migrating to regular instances

### Spot Instances

A spot instance is the same as a preempt instance but without the 24 hour maximum runtime

* No Service Level Agreement
* No automatic restarts

### Standard Instances

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Block Storage Options

| Storage Option | Description |
| --- | --- |
| Google Cloud Hyperdisk | Google's next generation block storage |
| Hyperdisk Storage Pools | |
| Persistent Disk | Durable network storage devices that an instance can access |
| Local SSD Disk | A physical drive that's directly attached to the same server of its instance |

## Google Cloud Hyperdisk

Google Cloud Hyperdisk is Google's next generation block storage

* Decouples storage performance from an instance's type and size by offloading and dynamically scaling out storage processing
* Offers substantially higher performance, flexibility, and efficiency when compared to Persistent Disk

| Google CLoud Hyperdisk Type | Description |
| --- | --- |
| Hyperdisk Balanced | |
| Hyperdisk ML | |
| Hyperdisk Extreme | |
| Hyperdisk Throughput | |
| Hyperdisk Balanced High Availability | |

## Hyperdisk Storage Pools

## Persistent Disk

Persistent Disks are durable network storage devices that an instance can access

* Data on each Persistent Disk volume is distributed across several physical disks
* Google manages the physical disks and the data distribution to ensure redundancy and optimal performance
* Located independently from instances, meaning that it can be detached and moved
* Performance scales automatically wiith size
* Can be resized and more can be added to a VM if needed

| Persistent Disk Type | Description |
| --- | --- |
| Balanced (pd-balanced) | |
| Performance (pd-ssd) | |
| Standard (pd-standard) | |
| Extreme (pd-extreme) | |

### Balanced Persistent Disks

* Provides a balance between performance and cost
* Have the same maximum IOPS as SSD persistent disks and lower IOPS per GiB
* Offers performance levels suitable for most general-purpose applications at a price point between that of standard and performance persistent disks
* Backed by SSDs

### Performance Persistent Disks

* Suitable for enterprise applications and high-performance databases that require lower latency and more IOPS than standard persistent disks provide
* Backed by SSDs

### Standard Persistent Disks

* Suitable for large data processing workloads that primarily use sequential I/Os
* Backed by SSDs

### Extreme Persistent Disks

* Offers consistently high performance for both random access workloads and bulk throughput
* Designed for high-end database workloads
* Allows customers to provision the target IOPS
* Not available for all machine types
* Backed by SSDs

## Local SSD Disk

A physical drive that's directly attached to the same server of its instance

* Can offer better performance but is ephemeral
