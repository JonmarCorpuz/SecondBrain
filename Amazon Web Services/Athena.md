Athena is a serverless interactive query service that users can use to analyze data in AWS S3 by using SQL

* Doesn't make a copy the user's data, meaning that users need to specify the S3 bucket prefix that Athena will look for when they create an Athena table
* The data in an S3 bucket needs to match the table's schema
* Users can create multiple Athena tables that reference different S3 buckets and join them
* Charges per amount of data that's fetched to perform a query

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Athena Data Practices

## Data Compression

Data compression is the practice of reducing the size of data files by compressing them together

* Allows Athena to scan less data per query
* Accelerates query performance since less data needs to be read from disk and processed during query execution
* Reduces query costs
* Allows users to store more data using less storage space

## Data Partitioning

Data partitioning is the practice of dividing data into separate segments or partitions

* Restricts the amount of data that's scanned by each query

## Data Convertion

Data conversion refers to the process of converting S3 bucket data into columnar data formats (Ex: *Apache Parquet*, *ORC*, *etc.*)

* Columnar data formats saves storage space in S3 and reduces disk space and I/O during query processing by performing compression by column using a compression algorithm
* When an Athena query obtains specific column values from the queried data, it uses statistics from data block predicates to determine whether to read or skip the block in order for Athena queries to fetch only the blocks that it needs
* Columnar data formats enable Athena to split the reading of data to multiple readers and increase parallelism when it processes queries
