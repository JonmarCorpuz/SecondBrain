Amazon DynamoDB is a fully managed NoSQL serverless database service that organizes data into items that each has their own attributes and stores it in SSDs while replicating it across multiple AZs and mirroring them across multiple drives

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture%20d%E2%80%99%C3%A9cran_13-4-2024_162825_www.coursera.org.jpeg)

* Offers consistent, single-digit millisecond latency for read and write operations, making it suitable for applications requiring real-time data access
* Handles administrative tasks (Ex: *Hardware provisioning*, *Configuration*, *Patching*, *Backups*, *etc.*)
* Provides high availability and performance by automatically distributing data and traffic 
* Supports both document and key-value data models
* Support encryption at rest and in transit
* Provides continuous backups, enabling point-in-time recovery within a specified retention period
* Enables users to replicate data across multiple AWS regions for global high availability and disaster recovery
* Captures changes that were made to the database and allows developers to trigger actions based on those changes, enabling real-time data processing and analytics (DynamoDB Streams)
* Integrates seamlessly with other AWS services (Ex: *AWS Lambda*, *Amazon S3*, *Amazon Redshift*, *Amazon EMR*, *AWS Management Console*, *etc.*) for building serverless architectures and data analytics pipelines
* Has flexible schemas, meaning that users can add and remove attributes from items in the table at any time and not every item in the table has to have the same attributes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DynamoDB Components

## Tables

A table is a collection of data

## Items

An item is a group of attributes that is uniquely identifiable among all of the other items

## Attributes

An attribute is a fundamental data element that's similar to a field or column in a relational database

* Each attribute is composed of a name (key) and a value
* Can be added or removed from items without needing to modify the table's schema

### Scalar Attributes

A scalar attribute is an attribute that represents a single value

* Can be of various data types supported by DynamoDB (Ex: *String*, *Number*, *Binary*, *Boolean*, or *Null*)

### Multi-Valued Attributes

A multi-valued attribute can hold multiple values of the same data type

* DynamoDB supports three types of multi-valued attributes: String Set, Number Set, and Binary Set

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DynamoDB Throughput Modes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Throughput%20stuff.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DynamoDB Streams

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DynamoDB Accelerator (DAX)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f8NtZW24REOc8OUeH-spNA_1e7e8bff75544f98b9e872e9e1485af1_Reading1.6A.png)

DAX is a fully managed, highly available, in-memory cache for DynamoDB that's designed to deliver up to a hundred times performance improvement

* Does the heavy lifting that's required to add in-memory acceleration to a user's DynamoDB tables
* Developers don't need to manage cache invalidation, data population, or cluster management
* Users don't need to modify the application logic because DAX is compatible with existing DynamoDB API calls
* Designed to run within a VPC environment
