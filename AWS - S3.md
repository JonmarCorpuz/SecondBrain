AWS Simple Storage Service is a scalable object storage service provided by AWS

* Allows businesses and developers to store and retrieve any amount of data from anywhere on the web using URLs
* Designed to provide high durability for stored objects by replicating data across multiple geographically dispersed data centers, ensuring that the data remains available in the event of a failure or disaster
* Can scale to accommodate virtually unlimited amounts of data
* Offers high availability, with service-level agreements guaranteeing uptime of 99.99% or higher, ensuring that the data is accessible whenever needed
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
* Uses unique identifiers to look up objects when requested

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# S3 Components

## S3 Bucket

An S3 Bucket is a public cloud storage container that's used to store objects

* Each S3 Bucket must have a unique name that's globally unique across all AWS accounts regions, be DNS compliant, and be reachable over HTTP or HTTPS
* Used to organize and manage objects stored in S3, where each object has the three following components: The content (*Data*), metadata (*Size*, *Name*, *etc.*) and a unique identifier
* Supports various control mechanisms (Ex: *Bucket policies*, *ACLs*, *IAM*, *etc.*)
* Can be interacted with using the AWS Management Console, APIs, CLIs, or SDKs
* Everything uploaded onto an S3 Bucket is private by default

### S3 Bucket Policies

* Defined using a JSON format
* Attached to only S3 Buckets
* Specifies what actions are allowed or denied on the bucket that it's attached to
