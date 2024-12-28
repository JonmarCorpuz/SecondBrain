# Cloud SQL Overview

Google's Cloud SQL is a fully managed relational database service that allows users to set up MySQL, PostgreSQL, and SQL Server databases on VMs without having to attend to database administration tasks

* Used when data is structured and modeled for relational databases
* Used for databases that don't need to scale horizontally (Cloud SQL databases scale vertically)
* Used when you have extremely large volumes of relational data or data that needs to be globally distributed while ensuring consistency and transaction integrity across all servers
* Uses either SSds or HDDs
* Provides automatic encryption for tables and backups
* Supports automatic storage increase without downtime and point-in-time recovery

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# High Availability

* Requires you to choose a Primary and a Secondary zone within a region
* The changes made on the Primary zone are replicated synchronously to the Secondary zone
* The Secondary zone can't be used as a Read Replica (You can't connect to both the Primary and Secondary zone at the same time)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Workload Read Replicas

## Cross-Zone

## Cross-Region

## External
