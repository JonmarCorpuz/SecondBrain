# Persistent Disk Overview

Google's Persistent Disk is a reliable and high-performance block storage for VM instances

* Lifecycle is independent from a VM instance
* Can be attached and detached from a VM instance
* Storage size can be increased when you need it while it's attached to a VM instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Persistent Disk Deployment Types 

| Persistent Disk Deployment Type | Description |
| --- | --- |
| Zonal | |
| Regional | |

## Zonal PD

* Data is replicated in one zone
* Offers redundancy against hardware failure

## Regional PD

* Data is replicated in multiple zones within the same region (2 zones in the same region)
* Offers redundancy against zonal failures 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Persistent Disk Types

| Persistent Disk Type | Description |
| --- | --- |
| pd-standard | |
| pd-balanced | |
| pd-ssd | |

| Feature | pd-standard | pd-balanced | pd-ssd |
| --- | --- | --- | --- |
| Underlying Storage | HDD | SSD | SDD |
| Sequential IOPS Performance | Good | Good | Very Good |
| Random IOPS Performance | Bad | Good | Very Good |
| Cost | Cheapest | In Between | Expensive |
| Use Cases | Big Data | Cost and Performance Balance | High Performance |

## Standard PD

* Uses HDDs

## Balanced PD

* Uses SSDs

## SSD PD

* Uses SSDs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Persistent Disk Backups

| Persistent Disk Backup Method | Description |
| --- | --- |
| Snapshots | |
| Machine Image | |

| Backup Scenario | Machine Image | Persistent Disk Snapshot | Custom Image | Instance Template |
| --- | --- | --- | --- | --- |
| Single Disk Backup | Yes | Yes | Yes | No |
| Multiple Disk Backup | Yes | No | No | No |
| Differential Backup | Yes | Yes | No | No |
| Instance Cloning and Replication | Yes | No | Yes | Yes |
| VM Instance Configuration | Yes | No | No | Yes |

## PD Snapshots

PD snapshots are point-in-time backups of your PD

* Take up storage
* Can be scheduled and autodeleted
* Can be either mutli-regional or regional
* Can be shared across projects
* Can be used to create new VM instances
* Incremental, meaning that new snapshots will only contain the changes that were made since the last snapshot was taken
* Deleting a snapshot only deletes data that's not needed by other snapshots
* Performance is reduced while snapshots are being taken (Recommended to take snapshots during off-peak hours)
* Faster to create from disk than to create from images but creating PDs from images is faster than creating from snapshots (Recommended to create an image from a snapshot)

## Machine Images

* Created from a VM instance (Backs up VM instance's configuration along with all its attached PDs)
* Contains everything you need to create a VM instance (Ex: *Configurations*, *Metadata*, *Permissions*, *Data from the boot disk*, *Data from other disks*, *etc.*)
* Recommended for disk backups, instance cloning, and replication
