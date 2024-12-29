# Cloud Bigtable Overview

Google's BigTable is a low-latency NoSQL wide-column database managed service for petabyte-scale applications 

* Can manage up to billions of rows and thousands of columns (Ex: *Machine learning*, *Operational analytics*, *User-facing operations*, *etc.*)
* Stores tables that have a large number of columns
* Doesn't require a fixed schema to structure the data (Not all rows need to use all columns)
* Designed to provide consistent and low-millisecond latency
* Designed for applications with high data volumes and high-velocity ingest of data (Ex: *Time series*, *IoT*, *etc.*)
* Runs clusters and scales horizontally
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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Bigtable Instance

* Used to host your Bigtable database

# Cloud Bigtable Database

* Most of the work will be done at the CLI using the `cbt`

```Bash
echo instance = INSTANCE_NAME >> ~/.cbtrc
```

```Bash
cbt createtable TABLE_NAME
```

## Column Families

```Bash
cbt createfamily TABLE_NAME COLUMN_FAMILY_NAME
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Bigtable Cluster Modes

## Production

* Production clusters have a minimum of three Nodes
* Requires you to choose either SSD or HDD for the persistent disks used by the database

## Development
