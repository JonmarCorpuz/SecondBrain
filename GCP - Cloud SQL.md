Google's Cloud SQL is a fully managed relational database service for MySQL, PostgreSQL, and SQL Server

* A regional service that provides high availability (99.95%) and failover (Creates a Standby with automatic failover)
* Uses either SSds or HDDs
* Provides automatic encryption for tables and backups
* Allows you to create read replicas for read workloads (*Cross-zone*, *Cross-region*, *External*)
* Supports automatic storage increase without downtime and point-in-time recovery
* Allows you to export data to and import data from Cloud Storage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# High Availability

* Requires you to choose a Primary and a Secondary zone within a region
* The changes made on the Primary zone are replicated synchronously to the Secondary zone
* The Secondary zone can't be used as a Read Replica (You can't connect to both the Primary and Secondary zone at the same time)
