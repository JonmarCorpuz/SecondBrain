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

# Storage Options

| Storage Option | Description |
| --- | --- |
| Google Cloud Hyperdisk | |
| Hyperdisk Storage Pools | |
| Persistent Disk | |
| Local SSD Disk | |

## Google Cloud Hyperdisk

## Hyperdisk Storage Pools

## Persistent Disk

Persistent Disks are durable network storage devices that an instance can access

* Data on each Persistent Disk volume is distributed across several physical disks
* Google manages the physical disks and the data distribution to ensure redundancy and optimal performance
* Located independently from instances, meaning that it can be detached and moved

| Persistent Disk Types | Description |
| --- | --- |
| Balanced (pd-balanced) | |
| Performance (pd-ssd) | |
| Standard (pd-standard) | |
| Extreme (pd-extreme) | |

### Balanced Persistent Disks

### Performance Persistent Disks

### Standard Persistent Disks

### Extreme Persistent Disks

## Local SSD Disk
