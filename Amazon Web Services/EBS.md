Amazon Elastic Block Store is a block storage service that allows users to create and attach persistent block storage volumes to EC2 instances

* Provides durable, low-latency storage that can be used as primary storage for EC2 instances (Ex: *Boot/root volumes to store an OS*, *A storage layer for databases*, *Applications*, *etc.*)
* Amazon EBS volumes persist independently of the lifecycle of the EC2 instance to which they're attached, meaning that data stored on EBS volumes remains intact even if the associated EC2 instance is stopped, terminated, or replaced
* Provides block-level storage, allowing EBS volumes to be formatted and used like physical hard drives that can later be attached to EC2 instances
* Built on replicated backend storage providing high availability and durability, meaning that the stored data persists independently of the EC2 instance lifecycle
* Can be dynamically resized, snapshotted, and encrypted
* AZ specific and can only be attached to EC2 instances within the same AZ
* EBS volumes are automatically replicated within its AZ when it gets created to prevent data loss from single points of failure
* Supports on-the-fly changes, meaning that users can modify the volume type, volume size, and I/O operations per second capacity without stopping the EC2 instance
* Not all EBS volumes support multi-attach, meaning that they can only connect to one EC2 instance at a time
* EBS volumes have size limitations

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Amazon EBS Volume Types

Amazon EBS offers different volume types that are optimized for various performance and cost requirements

## SSD Backed Volumes

* Provide strong performance for random I/O

### EBS Provisioned IOPS SSD

### EBS General Purpose SSD

## HDD Backed Volumes

* Provide strong performance for sequential I/O

### Throuput Optimized HHD

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EBS Backups

## EBS Snapshots

* Snapshot backups are stored redundantly in mutliple AZs using S3
* Can be used to create multiple new volumes either in the same AZ or a different one, which will end up being an exact copy of the original volume at the time the snapshot was taken

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EBS Multi-Attach
