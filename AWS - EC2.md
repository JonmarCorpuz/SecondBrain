Amazon Elastic Compute Cloud is a web service provided by AWS that allows users to rent virtual virtual servers (Instances) on which they can run their own applications

* Provides resizable compute capacity in the cloud, enabling users to quickly scale their computing resources up or down as needed
* Users can easily scale the number of instances up or down to handle changes in demand of their applications (Elasticity) 
* Offers a wide range of instance types (Ex: *Compute-optimized instances*, *Memory-optimized instances*, *GPU instances*, *etc.*)
* Follows a pay-per-use pricing model
* Allows users to quickly launch instances with their desired OS, software, and configurations with pre-configured instance templates using AMIs
* Offers various security features (Ex: *Virtual Private Clouds for network isolation* *Security groups for controlling inbound and outbound traffic*, *Integration with AWS IAM*, *etc.*)
* Integrates seamlessly with other AWS services (Ex: *Amazon S3*, *Amazon RDS*, *Amazon EBS*, *Amazon CloudWatch*, *AWS Lambda*, *etc.*)
* EC2 instances are available in multiple AWS regions worldwide, each consisting of multiple Availability Zones
* Allows users to enable auto-scaling groups to automatically adjust the number of EC2 instances based on predefined criteria (Ex: *CPU utilization*, *Incoming traffic*, *etc.*), ensuring that the application can handle varying workloads efficiently
* Can be managed through the AWS CLI, SDKs, or through automation tools and infrastructure orchestration services

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EC2 Instances

An EC2 instance is a virtual server hosted in the AWS cloud that users can use to run their applications

* The user is responsible for the logical controls (Ex: *Guest OS*, *Security and patching*, *Networking*, *Scaling*, *etc.*) while AWS is responsible for the physical hardware
* EC2 instances are a combination of vCPUs, memory, network, instance storage, and GPUs
* By default, EC2 instances are placed in a network called the Amazon VPC, allowing users to get easily started with Amazon EC2 without having to learn how to create and configure a VPC (Any resources placed inside the default VPC will be public and accessible by the internet)

## EC2 Instance Families

An EC2 instance family is a group of instance types that share similar characteristics and are optimized for specific workloads or use cases

### General-Purpose EC2 Instance

A general-purpose EC2 instance provides a balance of compute, memory, and networking resources, and is designed to support a wide range of workloads

* Suitable for small-scale to medium-scale application deployments
* Versatile and can be used for a variety of workloads (Ex: *Web servers*, *Deployment environments*, *Enterprise applications*, *Small to medium-sized databases*, *etc.*)
* Provides a balance of compute power, memory, and networking capabilities, allowing it to handle a diverse set of workloads efficiently
* Offers a cost-effective option for running workloads that don't have a specialized requirements for compute, memory, or storage resources
* Optimized for average workloads with moderate CPU and memory usage patterns, providing reliable performance for most common use cases

| General-purpose EC2 Instance family | Description                                                                                                                                                                 |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| T3 instances                        | Offers a balance of baseline performance and the ability to burst higher CPU performance levels when needed (Suitable for workloads with variable CPU utilization patterns) |
| M5 instances                        | Offers a balance of compute, memory, and networking resources (Suitable for a wide range of general-purpose workloads)                                                      |
 
### Compute Optimized EC2 instance

A compute optimized EC2 instance delivers high computational performance and is optimized for workloads that require significant processing power

* Powered by processors that offer high clock speeds and efficient single-threaded performance, making them suitable for compute-intensive tasks 
* Equipped with high-speed networking instances in a cluster or with other AWS services
* Ensuring that both compute and memory resources are adequately provisioned for the workload by providing sufficient memory to support memory-intensive workloads

| Compute optimized EC2 instance family | Description                                                                                                                    |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| C5 instances                          | Offers a balance of compute power, memory, and networking resources (Suitable for applications and high-performance computing) |
| C6g instances                         | Offers a good balance of compute power and cost-effectiveness (Suitable for various compute-intensive workloads)               |

### Memory Optimized EC2 instance

A memory optimized EC2 instance delivers high performance for memory-intensive workloads and is optimized for providing a large amount of RAM along with sufficient compute and networking resources to support applications that require significant memory capacity

* Equipped with a large amount of RAM compared to other instance types, allowing them to handle memory-intensive workloads (High memory capacity)
* Offers a high ratio of memory to CPU cores, ensuring that applications have ample memory resources available to process data efficiently (High memory-to-CPU ratio)
* Ensures fast data transfer rates between instances and other AWS services by including high-performing networking interfaces
* Well-suited for workloads that involve processing large datasets or performing complex data analysis tasks in memory
* Commonly used for applications such as in-memory databases, real-time data processing, and big data analytics

| Memory optimized EC2 instance | Description                                                                                          |
| ----------------------------- | ---------------------------------------------------------------------------------------------------- |
| R5 instances                  | Offers a balance of high memory capacity and compute power (Suitable for memory-intensive workloads) |
| X1 instances                  | Offers up to 3.9 TB of RAM per instance (Suitable for memory-intensive workloads)                    |

### Accelerated Computing EC2 instance

An accelerated computing EC2 instance is designed to accelerate certain types of computational workloads using specialized hardware and is optimized for tasks that can benefit from parallel processing and high-performance computing capabilities provided by those accelerators

* Commonly used for applications such as machine learning, deep learning, video encoding, scientific simulations, rendering, and other compute-intensive workloads
* Equipped with hardware accelerators that are specifically designed to offload and accelerate certain types of computational tasks
* Offers high computational performance, allowing users to process large datasets or perform complex calculations efficiently
* Enables parallel processing of tasks across multiple cores or processing units, enabling faster execution of compute-intensive workloads compared to traditional CPU-based instances
* Optimized for specific types of workloads that can benefit from the performance advantages offered by hardware accelerators

| Accelerated computing EC2 instance | Description                                                                                                                                                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| P3 instances                       | Provide high computational performance and are optimized for training deep learning models and running GPU-accelerated applications (Suitable for high-performance computing, machine learning, and other compute-intensive workloads) |
| G4 instances                       | Offers a balance of performance, cost-effectiveness, and energy efficiency (Suitable for graphics-intensive applications, video transcoding, machine learning inference, and other GPU-accelerated workloads)                          |

### Storage Optimized EC2 instance

A storage optimized EC2 instance provides high storage capacity and performance for data-intensive workloads, and is optimized to deliver fast access to large volumes of data


* Well suited for applications that require high-performance storage subsystems
* Offers a large amount of storage capacity, typically in the form of high-speed, low latency SSD storage, allowing users to store and process large datasets without sacrificing performance
* Optimized for high disk throughput, enabling fast read and write operations to storage volumes
* Provides low-latency access to data, allowing applications to retrieve and process data quickly
* Designed for data-intensive workloads that involve processing large volumes of data
* Commonly used for applications such as data warehousing, big data analytics, content delivery, and media streaming

| Storage optimized EC2 instance | Description                                                                                                                                                                                |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| I3 instance                    | Offers high-speed, low-latency NVMes SSD storage and are optimized for I/O intensive workloads (Suitable for applications such as NoSQL databases, data warehousing, and analytics)        |
| D2 instance                    | Provides high-capacity HDD storage and are optimized for sequential read and write operations (Suitable for applications such as distributed file systems, data lakes, and log processing) |

## Creating and Launching an EC2 Instance

In order to create an EC2 instance, you need to define the hardware specifications (Ex: *CPU*, *Memory*, *Storage*, *etc.*) and logical configurations (Ex: *Networking location*, *Firewall rules*, *Authentication*, *OS*, *etc.*)

* When launching an EC2 instance, the first setting you configure is which OS you want by selecting an AMI

## Relationship Between AMIs and EC2 Instances

EC2 instances are live instantiations of what is defined in an AMI

![](VBk76PGITdKLGz9RPTGtXw_16b6431eb1354ab889f7433d964da9f1_image.png)

* AMI is how you model and define your instance, while the EC2 instance is the entity you interact with
* When you launch a new instance, AWS allocates a VM that runs on a hypervisor, where the AMI you selected is copied onto the root device volume, which contains the image used to boot the volume

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EC2 Instance Lifecycle

An EC2 instance transitions between different states from the moment a user creates it all the way through to its termination

![[EC2 Instance Lifecycle.png]]

## Pending

When an instance is launched, it enters a pending state where the instance is preparing to enter the running state

* When the instance is pending, billing hasn't started yet
* Pending is where AWS performs all actions needed to set up an instance (Ex: *Copying the AMI content to the root device*, *Allocating the necessary networking components*, *etc.*)

## Running

A running instance is an instance that's ready to be used

* This stage is where the billing begins
* As soon as an instance is running, you're able to take other actions on the instance (Ex: *Reboot*, *Terminate*, *Stop*, *etc.*)

## Rebooting

Rebooting an instance is the process of restarting or rebooting an EC2 instance

* The instance remains on the same host computer and maintains its public and private IP address, and any data on its instance store
* The instance is temporarily stopped and then started again

## Stopping 

The stopping phase is the process of stopping an EC2 instance, where its running state is terminated

* Stopped state
	* The instance is no longer running
	* Data on any EBS volumes attached to the instance persists, allowing to start the instance again later with the same data intact
	* When starting a stopped instance, it resumes from where it was stopped while retaining its instance ID, private and public IP addresses, and any attached EBS volumes

* Stop-hibernate state
	* The instance's RAM contents are preserved on the root EBS volume
	* Beneficial for instances that need to retain their in-memory state and resume quickly with all applications and data intact
	* Starting up a stop-hibernated instance will resume from the hibernated state, allowing for faster boot times as it doesn't need to reload the OS and application state

## Terminating

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EC2 Storage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/EC2%20Storage.png)

## EC2 Instance Store

EC2 instance store refers to the temporary block-level storage that's physically attached to the host computer running the EC2 instance

* Provides very high I/O speeds and low latency since it's physically located on the same host computer as the EC2 instance
* The size and number of instance store volumes available depends on the specific EC2 instance type and size
* The data lifecycle of the data stored on instance store volumes is ephemeral, meaning that it doesn't persist if the instance is stopped, hibernated, or terminated, and the data is cryptographically erased when the instance is stopped or terminated
* Instance store volumes are best suited for temporary, frequently changing data (Ex: *Caches*, *Buffers*, *Scratch data*, *etc.*) and for hosting applications that replicate data to other EC2 instances (Ex: *Hadoop clusters*, *etc.*)
* 

## External Storage

* Multiple EBS volumes can be attached to EC2 instances, which can then be configured on the OS of the EC2 instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EC2 Instance Metrics

An EC2 instance metric is a type of data that's used to measure the performance of an EC2 instance

* Provides valuable insights into the performance, health, and utilization of EC2 instances

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EC2 Features

## EC2 Auto Scaling

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/pVmtoRo0R2KIdGTo68hnWQ_d8a3718739a7477398aaff28f86847f1_image.png)
