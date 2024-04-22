AWS Simple Storage Service is a scalable object storage service that stores data in a flat structure, using unique identifiers to look up objects when requested

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/xpDo1_CATs6a3dnaA9cVzA_4b9ae8b78cb3407baf58440f97a67cf1_Reading2.1A.png)

* Allows businesses and developers to store and retrieve any amount of data from anywhere on the web using URLs
* Designed to provide high durability for stored objects by replicating data across multiple geographically dispersed data centers, ensuring that the data remains available in the event of a failure or disaster
* Can scale to accommodate virtually unlimited amounts of data
* Ensures that data is accessible whenever needed and offers high availability with SLAs guaranteeing uptime of 99.999999999% durability for objects by replicating every single object in a bucket over different physical facilities in an AWS Region
* Provides multiple layers of security to protect stored data (Ex: *Encryption at rest and in transit*, *ACLs*, *Bucket policies*, *etc.*)
* Offers different storage classes to optimize costs and performance based on data access patterns and retention requirements (Ex: *Standard S3*, *Standard Infrequent Access S3*, *Intelligent-Tiering S3*, *Glacier S3*, *Glacier Deep Archive S3*, *etc.*)
* Allows users to define lifecycle policies to automatically transition objects between different storage classes or delete them after a specified period
* Supports versioning, allowing users to keep multiple versions of an object in the same bucket, which helps protect against accidental deletions or overwrites and enables users to restore previous versions of objects if needed
* Can host static websites directly from a bucket, making it easy to serve static content
* Integrates seamlessly with other AWS services (Ex: *AWS Lambda*, *Amazon CloudFront*, *Amazon RDS*, *Amazon EMR*, *etc.*), enabling users to build scalable and cost-effective solutions for various use cases

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# S3 Storage Structure

* The underlying storage type for S3 is object storage, meaning that all of the same characteristics of object storage are also characterisitics of S3
* Uses a flat structure, meaning that data is stored in rows (records) and columns (fields) using a single table or file where each row is a self-contained data entry
* All files and folders live at the same flat level
* Uses unique identifiers to look up objects when requested

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# S3 Components

## S3 Objects

An object in S3 is a file containing data (Ex: *Text files*, *Images*, *Videos*, *etc.*) and metadata (Ex: *Object creation date*, *Object size*, *Storage class*, *etc.*)

* Stored in S3 Buckets
* Each object in S3 has a unique key that serves as its identifier within the S3 Bucket

### S3 Object Lifecycle Policies

S3 object lifecycle policies are sets of rules that define actions to be automatically applied to a group of objects within an S3 bucket

* Automates transition actions, which are actions used to define when the user should transition their objects to another storage class
* Automates expiration actions, which are actions that define when objects expire and should be permanently deleted

## S3 Bucket

An S3 Bucket is a public cloud storage container that's used to store, organize, and manage objects

* Each S3 Bucket must have a unique name that's globally unique across all AWS accounts regions, be DNS compliant, and be reachable over HTTP or HTTPS
* Used to organize and manage objects stored in S3, where each object has the three following components: The content (*Data*), metadata (*Size*, *Name*, *etc.*) and a unique identifier
* Supports various control mechanisms (Ex: *Bucket policies*, *ACLs*, *IAM*, *etc.*)
* Can be interacted with using the AWS Management Console, APIs, CLIs, or SDKs
* Everything uploaded onto an S3 Bucket is private by default
* Redundantly stores all the objects that are stored inside across multiple devices and AZs
* Can contain folders to help users organize their objects despite not having any actual file hierarchy that'll support this on the backend

### S3 Bucket Policies

* Defined using a JSON format
* Applies to every object in the bucket that it's attached to
* Attached to S3 Buckets only and cannot be used for folders or objects
* Specifies what actions are allowed or denied on the bucket that it's attached to
* Reinforces encryptin in transit (Ex: *Client-side encryption*, *SSL*, *etc.*) and at rest (Ex: *Server-side encryption*, *Client-side encryption*, *etc.*)

```JSON
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "YOUR_PRINCIPAL_ID"
            },
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::YOUR_BUCKET_NAME",
                "arn:aws:s3:::YOUR_BUCKET_NAME/*"
            ]
        }
    ]
}
```

### S3 Bucket States

* Unversioned (Default state), meaning that no new or existing objects in the bucket has a version
* Versioning-enabled, meaning that all objects in the bucket can have different versions
* Versioning-suspended, meaning that versioning is suspended for new objects but all existing objects will keep their object versions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# S3 Storage Classes

## S3 Standard

S3 Standard

## S3 Intelligent-Tiering

S3 Intelligent-Tiering 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/D8fzzMCvRVyI7RdBJLkFTw_7951069382b045c994fbac7ac76f4ff1_Reading2.2A.png)

* Useful if the user's data has unknown or changing access patterns
* Stores objects in two tiers: A frequent access tier and an infrequent access tier
* Monitors the access pattern of the user's data and automatically moves it to the most cost-effective storage tier based on frequency of access

## S3 Standard-Infrequent Access 

S3 Standard-IA is for data that's accessed less frequently, but requires rapid access when needed

* Offers high durability, high throughput, and low latency
* Well-suited for long-term backups and disaster recovery files 

## S3 One Zone-Infrequent Access 

S3 One Zone-IA

* Stores data in a single AZ

## S3 Glacier 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8lPIyU4NRyKS1l0B0okGOQ_b48af64b58f843caada35f01685a0cf1_Reading2.2B.png)

### S3 Glacier Instant Retrieval

S3 Glacier Instant Retrieval

### S3 Glacier Flexible Retrieval

S3 Glacier Flexible Retrieval

* Offers low-cost storage for archive data that's aynchronously accessed only one or two times per year

### S3 Glacier Deep Archive

S3 Glacier Deep Archive 

* Supports long-term retention and digital preservation for data that may be accessed only once or twice in a year
* Designed for customers in highly regulated industries that retain data sets for 7 to 10 years or longer to meet regulatroy compliance requirements

## S3 Outposts

S3 on Outposts 

* Delivers object storage to the user's on-premises AWS Outposts environment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# S3 Features

## S3 CRR

S3 Cross-Region Replication is a S3 feature that automatically replicates data across AWS regions

* Designed to enhance data availability, protection, and compliance by allowing users to copy S3 objects from a source bucket in one AWS region to a destination bucket in a different region
* Ensures data locality for compliance requirements and reduces latency by locating data closer to users
* Helps protect against regional failures by ensuring that applications can continue to operate by accessing data from a replicated bucket in another region if the primary data source becomes unavailable
* Supports replicating all or a subset of data based on S3 object tags
* Ensures that every version of an object is replicated
* Involves specifying a source bucket, a destination bucket in another region, and an optional replication rule that defines what objects to replicate
* Enables users to set up replication at a bucket level, a shared prefix level, or an object level
