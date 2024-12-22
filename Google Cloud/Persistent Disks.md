# Persistent Disk Overview

* Supports multiple readers without a degradation in performance in order to allow multiple instances to read a single copy of data
* Can also be resized as needed while in use without the need to restart your VMs but you'll need to perform some commands in order to make that additional space accessible to the VM's filesystem
* Since they are block storage devices, you can create filesystems on them
* Not directly attached to any Compute Engine resources but accessed through the network instead (Network accessible)
* Can be mounted on multiple VMs to provide multireader storage
* Data at rest is encrypted by default

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSD 

* Used when high throughput is important
* Provides consistent and faster performance for both random access and sequential access patterns but costs more
* Automatically encrypts data on the disk

## Local SSD

* High-performance local block storage but have no redundancy

## Balanced Disk

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# HDD 

* Have longer latencies but costs less (A good option when storing large amounts of data and performing batch operations that are less sensitive to disk latency than interactive applications)

## Standard Disk

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Persistent Disk Location

## Zonal

* Stores data across multiple physical drives in a single zone (If the zone becomes inacessible, then you lose all access to your disks)

## Regional

* Replicates data blocks across two zones within a region but are more expensive 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


