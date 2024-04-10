Amazon Elastic Block Store is a block storage service that allows users to create and attach persistent block storage volumes to EC2 instances

* Provides durable, low-latency storage that can be used as primary storage for data, applications, and OSes running on EC2 instances
* Amazon EBS volumes persist independently of the lifecycle of the EC2 instance to which they're attached, meaning that data stored on EBS volumes remains intact even if the associated EC2 instance is stopped, terminated, or replaced
* Provides block-level storage, allowing EBS volumes to be formatted and used like physical hard drives that can later be attached to EC2 instances
* Built on replicated backend storage providing high availability and durability, meaning that the stored data persists independently of the EC2 instance lifecycle
* Can be dynamically resized, snapshotted, and encrypted
* AZ specific and can only be attached to EC2 instances within the same AZ

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Amazon EBS Volume Types

Amazon EBS offers different volume types that are optimized for various performance and cost requirements

## SSD Backed Volumes

## HDD Backed Volumes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EBS Multi-Attach
