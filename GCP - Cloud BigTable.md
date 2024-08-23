Google's BigTable is a low-latency NoSQL wide column database managed service for machine learning, operational analytics, and user-facing operations

* Not serverless, meaning that you need to create a database instance in order to create a database (SSD or HDD)
* HBase API compatible
* Designed for huge volumes of analytical and operational data (Ex: *IOT Streams*, *Analytics*, *Time Series Data*, *etc.*)
* Handles millions of read and write TPS at very low latency
* Supports only single-row transactions (Multi-row transactions aren't supported)
* Can scale horizontally with multiple nodes (No downtime for cluster resizing)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wide Column Database

* Each table is a sorted key/value map
* Each value in a row is indexed using a row key
* Related columns are grouped into column families
* Each column is identified by using <column>-<family>:<column>-<qualifier>
* Supports high read and write throughput at low latency
