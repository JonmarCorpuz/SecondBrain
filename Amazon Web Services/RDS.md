The Relational Database Service is a managed database service that simplifies the setup, operation, and scaling of relational databases in the cloud

* Allows users to focus on their applications rather than the underlying infrastructure
* Handles routine database tasks (Ex: *Provisioning*, *Patching*, *Backup*, *Recovery*, *Scaling*, *etc.*)
* Supports various popular relational database engines (Ex: *MySQL*, *PostgreSQL*, *MariaDB*, *Oracle*, *Microsoft SQL Server*, *Amazon Aurora*, *etc.*)
* Enables users to scale database instances vertically by adjusting compute and memory resources or horizontally by adding read replicas for read scalability
* Enables multi-AZ deployment for high availability

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Database Instance

A DB instance refers to an isolated single database environment created and managed by RDS

* Each DB instance has its own DNS endpoint and port number, allowing applications to connect and interact with the database
* Can contain multiple databases with the same engine and each database can contain multiple tables
* Underneath eachs DB instance is an EC2 instance
* Uses EBS volumes as its storage layer

## Standard Database Instance

A standard database instance is a regular standalone database instance 

* Designed to meet the general needs of various types of applications and workloads
* Commonly used for applications that require relational databases (Ex: *MySQL*, *PostgreSQL*, *Oracle*, *SQL Server*, *MariaDB*, *etc.*)
* Offers a range of configurations for compute power, memory, storage, and network capacity to accommodate diverse requirements (Ex: *Automated backups*, *Monitoring*, *Security*, *High availability*, *etc.*)

## Memory Optimized Database Instance

A memory database instance is a database instance that's tailored for workloads that require high memory capacity and performance 

* Optimized to handle momey-intensive database operations efficiently
* Enables users to store large amounts of data in memory by offering a significantly higher amount of RAM compared to standard instances, resulting in reduced disk I/O and improved overall performance
* Reduces latency and speeds up query processing by caching frequently accessed data, leading to faster database reads and writes, especially for applications with heavy read workloads or complex analytical queries
* Ensures that applications can scale up as needed without sacrificing performance by allowing users to increase or decrease the instance size to meet changing workload demands
* Well-suited for memory-intensive use cases (Ex: *In-memory databases*, *Real-time analytics*, *Caching layers*, *High-performance computing applications*, *etc.*)

## Burstable Performance Database Instance

A burstable performance database instance is a database instance designed for workloads that have fluctuating performance needs

* Characterized by their ability to provide baseline performance with the capability to burst above that baseline when required
* Each burstable performance instance has a baseline level of CPU performance that it provides continuously
* Suitable for typical workloads and ensures consistent performance under normal usage
* Baseline performance is measured in CPU Credits per hour, which can accumulate over time when the user operates below their baseline performance level
* When a user's workload requires more CPU performance than their baseline level, the instance can burst above the baseline using the user's CPU Credits to temporarily deliver high CPU performance
* Well-suited for workloads with periodic or unpredictable spikes in CPU usage
* Allows users to track their instance's performance and optimize resource allocation accordingly by providing them tools to monitor their CPU Credit balance and usage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# RDS Features

## Subnet Groups

A subnet group is the subnet where a DB instance is placed

* This is done by specifying the AZs that include the subnets that the user wants to add and the subnets in that AZ where they want their DB instance to be placed

## Automatic Backups

Automatic backups are periodic snapshots of a user's database instance's storage volume that are taken automatically and retained for a specific duration

* Provide a means of recovering a user's database instance to a previous state in the event of a failure 
* Provide Point-in-Time Recovery (PITR), which enables users to restore a database to a specific point in time within the retention period, by including transaction logs that provide users to restore their database to any specific point in time within the backup retention period, not just to the latest backup
* Capture a full snapshot of the user's entire database instance during every snapshot (Ex: *Data*, *Tables*, *Indexes*, *Configurations*, *etc.*)

## Manual Backups

* Manual snapshots exist until the user deletes them, allowing users to retain backups for longer than 35 days
* Restoring data from a manual snapshot creates a new DB instance with the data from the restored snapshot

## Multi-AZ Deployments

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Wa8sI1trTQWvLCNba70FyQ_6d2a964a1f0b45aaba34626e54bd4af1_Reading3.3A.png)

* Ensures that a user has two copies of their database running (One primary and the second on standby) for high availability purposes
* Creates a redundant copy of a user's database in another AZ, also know as a standby copy , where the data in the primary copy is synchronously replicated to the standby copy
* Uses the DNS name provided during the creation of the DB instance to failover to the standby database by promoting it to the primary database in the event of an automatic failover
* During an automatic failover, a new standby database is created by either demoting the previous primary to standby if it's still up and running or standing up a new standby DB instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Read Replicas

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/BGvmCA4yTXKr5ggOMi1y8w_192880b2735943e98a83d38076a513f1_Reading3.3C.png)

# RDS Proxy

* Allows applications to improve their ability to scale by establishing a database connection pool that they can reuse without the memory and CPU overhead needed to open a new database connection each time
* Makes applications more resilient to database failures by automatically connecting to a standby DB instance, while preserving application connections
* Can handle unpredictable surges in database traffic, allowing applications to continue scaling without abruptly failing or overwhelming the database
* Allows users to protect the database against oversubscription by allowing them to control the number of database connections that are created
* Queues or throttles application connections that can't be served immediately from the pool of connections

## Read Replicas

* A read replica is created from a source DB instance and is kept in sync with the source
* Allows read-heavy workloads to be directed to the read replica instead of the primary instance
