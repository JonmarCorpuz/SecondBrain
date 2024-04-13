Amazon DynamoDB is a fully managed NoSQL serverless database service that organizes data into items that each has their own attributes and stores it in SSDs while replicating it across multiple AZs and mirroring them across multiple drives

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture%20d%E2%80%99%C3%A9cran_13-4-2024_162825_www.coursera.org.jpeg)

* Offers consistent, single-digit millisecond latency for read and write operations, making it suitable for applications requiring real-time data access
* Handles administrative tasks (Ex: *Hardware provisioning*, *Configuration*, *Patching*, *Backups*, *etc.*)
* Provides high availability and performance by automatically distributing data and traffic 
* Supports both document and key-value data models
* Enables the integration with AWS IAM for fine-grained access control
* Support encryption at rest and in transit
* Provides continuous backups, enabling point-in-time recovery within a specified retention period
* Enables users to replicate data across multiple AWS regions for global high availability and disaster recovery
* Captures changes that were made to the database and allows developers to trigger actions based on those changes, enabling real-time data processing and analytics (DynamoDB Streams)
* Integrates seamlessly with other AWS services (Ex: *AWS Lambda*, *Amazon S3*, *Amazon Redshift*, *Amazon EMR*, *AWS Management Console*, *etc.*) for building serverless architectures and data analytics pipelines
* Has flexible schemas, meaning that users can add and remove attributes from items in the table at any time and not every item in the table has to have the same attributes

# DynamoDB Components

## Tables

A table is a collection of data

## Items

An item is a group of attributes that is uniquely identifiable among all of the other items

## Attributes

An attribute is a fundamental data element 
