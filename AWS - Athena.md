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
