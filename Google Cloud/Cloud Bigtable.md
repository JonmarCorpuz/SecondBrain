# Cloud Bigtable Overview

Google's BigTable is a low-latency NoSQL wide column database managed service for petabyte-scale applications that can manage up to billions of rows and thousands of columns (Ex: *Machine learning*, *Operational analytics*, *User-facing operations*, *etc.*)

* Not serverless, meaning that you need to create a database instance in order to create a database (SSD or HDD)
* Based on the wide-column data model (NoSQL model)
* Suited for applications that require low-latency write and read operations (Designed to support millions of operations per second)
* Designed for huge volumes of analytical and operational data (Ex: *IOT Streams*, *Analytics*, *Time Series Data*, *etc.*)
* Handles millions of read and write TPS at very low latency
* Supports only single-row transactions (Multi-row transactions aren't supported)
* Can scale horizontally with multiple nodes (No downtime for cluster resizing)
* Supports the HBase API (An API for data access in the Hadoop big data ecosystem)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wide Column Database

* Each table is a sorted key/value map
* Each value in a row is indexed using a row key
* Related columns are grouped into column families
* Each column is identified by using <column>-<family>:<column>-<qualifier>
* Supports high read and write throughput at low latency
