# Google Cloud Platform Overview

* Google uses a security-hardened version of the Kernel Virtual Machine hypervisor, which provides virtualization on Linux systems running on x86 hardware
* Users APIs to make services programmatically accessible (Most are not enabled by default)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Storage Services

## Object Storage

Object storage is a system that manages the use of storage in terms of object or blobs

* Each object is stored in a bucket, which are individually addressable by a URL
* Designed for highly reliable and durable storage of objects
* Object storage is not limited by the size of disks or SSDs since they're stored on the cloud but has more limited functionality than filesystem-based storage systems
* Multiple copies of objects are stored across multiple zones and sometimes regions to improve availability and durability
* Keeps data independent of the lifecycle of a VM instance but doesn't support OS-level or filesystem-level access (You have to use higher-level protocols to access objects)
* Can store large volumes of data that can be copied to persistent disk when needed

## File Storage 

* Provides a hierarchical storage system for files
* Provides network-accessible filesystems that can be accessed by multiple servers
* Suitable for applications that require operating system-like file access to files
* Decouples the filesystem from specific VMs
* The filesystem, its directories, and its files exist independent of VMs or applications tha may access those files

## Block Storage

* Used for storing data on disks and with persistent storage devices
* Uses a fixed-size data structure called a block to organize data
* Commonly used in ephemeral and persistent disks attached to VMs
* Block storage is available on disks that are attached to VMs in GCP
* Faster to retrieve data from block storage than it is from object storage

## Caches

Caches are in-memory data stores that maintain fast access to data

* The latency of in-memory stores is designed to be submillisecond 
* Helpful when you need to keep read latency to a minimum in your application 
* Used for fast access to data but doesn't provide persistent storage
* In-memory is more expensive than SSD or HDD storage
* Caches are volatile (You lose the data stored in the cache when power is lost or the OS is rebooted)
* Caches can get out of sync with the persistent storage (This happens if the persistent storage is updated but the new data is not written to the cache and when this happens, it can be difficult for an application that depends on the cache to detect that the data within the cache is now invalid)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Network Peering Services

## VPN

## Interconnect

## Shared VPC 

## VPC Networking Peering

## Direct Peering

## Carrier Peering 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Observability Services

## Cloud Monitoring

## Cloud Logging

## Error Reporting

## Cloud Trace

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AI And Machine Learning Services

## AutoML

## Translation AI

## Natural Language

## Vision AI

## Recommendations AI

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Security Management Services

## Cloud IAM

## Cloud Armor

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Relational Databases Services

* Supports frequent queries and updates to data
* Used when users need a consistent view of data (Users that are reading data from a relational database at the same time will see the same data)
* Supports database transactions (There's no chance that some operations are executed and others are not)

## Cloud Spanner

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NoSQL Databases Services

* NoSQL databases don't use the relational model and don't require a fixed structure or schema

## Cloud Firestore

## BigTable
