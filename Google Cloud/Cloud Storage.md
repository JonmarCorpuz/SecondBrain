# Cloud Storage Overview

Google's Cloud Storage is a managed service for storing unstructured data

* Used when you need to store large volumes of data and don't need fine-grained access to data within an object while it's in the object store (Ex: *Data that needs to be saved but no longer actively analyzed*, *etc.*)
* Stores objects using a key-value approach and treat entire objects as a unit
* Always encrypts data on the server side (A newly created bucket is assigned with a Google managed key that's used to encrypt the data by default)
* Allows clients to encrypt their objects before uploading it to Cloud Storage
* Allows you to store replicas of objects in multiple cloud regions for high availability, durability, and low latency (Multi-region storage)
* Allows faster access to data when users or applications are distributed across regions through mutli-region storage
* Doesn't support concurrency and locking (If multiple clients are writing to a file, then the last data written to the file is stored and persisted)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Buckets

* Bucket names start with the **goog** prefix and should not contain the word google
* Bucket names are globally unique and are used as part of object URLs
* A bucket can contain unlimited objects that each belong to different storage classes
* Regional resources and are replicated across zones within the region
* Web addressasble, meaning that you can allow anyone with the URL to the bucket to access its contents (Users can prevent this by enabling the Enforce Public Access Prevention On This Bucket option)

## Objects
  
* Each object it identified by a unique key and stored in a bucket
* Maximum size is 5TB
* Objects can be versioned to prevent accidental deletion and provide history (The live version is the latest version and the older versions are uniquely identified by an object key along with a generation number)
* Object versions take up storage space since you're storing multiple versions of an object
* Noncurrent objects are uniquely identified (object key + generation number)

| Object Version | Description |
| --- | --- |
| Live | The latest version of an object |
| Noncurrent | An older version of an object that has been replaced by a newer version |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Storage Classes

A storage class is a piece of metadata that's used by every object to control their availability and pricing model (Objects accessed less frequently are charges less)

* Helps optimize your costs based on your access needs
* High availability for all storage classes (99.9999999% annual durability)
* Low latency for all storage classes
* Unlimited storage (Autoscaling is automatically configured and there's no minimum object size required)
* The APIs used across storage classes are the same (Ex: *Storing data to the archive storage class is the same way you'd store data to the standard class*)

| Storage Class | Minimum Storage Duration | Use Case |
| --- | --- | --- |
| Standard | None | Frequently used objects or objects that need to be stored for a short period of time |
| Nearline Storage | 30 days | Objects that are read or modified once a month on average |
| Coldline Storage | 90 days | Objects that are read or modified once a quarter |
| Archive Storage | 365 days | Objects that are read or modified once a year |

## Standard

* Used for frequently used data (Hot data) or data that's needed only for a short period of time
* No minimum storage duration

## Nearline Storage

* Used for objects that's read or modified once a month
* Minimum storage duration of 30 days

## Coldline Storage 

* Used for objects that are read or modified at most once a quarter
* Minimum storage duration of 90 days

## Archive Storage

* Used for objects that are accessed less than once a year
* Minimum storage duration of 365 days
* Commonly used for archiving, disaster recovery, and other use cases where the data will be accessed less than once per year and will be stored for at least 365 days

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Storage Class Transitions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Uploading Objects

| Object Upload Option | Description |
| --- | --- |
| Simple Upload | Used to upload small files that can be re-uploaded in case of failures |
| Multipart Upload | Used to upload small files that can be re-uploaded in case of failures |
| Resumable Upload | Used to upload small and large files (Costs one additional HTTP request) |
| Streaming Transfer | Used to upload an object of unknown size |
| Parallel Composite Upload | Used to upload a large object by dividing it up into 32 chunks and uploading it in parallel |

## Simple Upload

* Used to upload small files that can be re-uploaded in case of failures
* No metadata will be associated with an uploaded object

## Multipart Upload

* Used to upload small files that can be re-uploaded in case of failures
* Metadata will be associated with an uploaded object

## Resumable Upload

* Used to upload small and large files
* If an upload fails, it'll resume from where it failed

## Streaming Transfer

* Used to upload an object of unknown size

## Parallel Composite Upload

* Used to upload a large object by dividing it up into 32 chunks and uploading it in parallel
* Significantly fast if the network and disk speeds are not limiting factors

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Downloading Objects

| Object Download Option | Description |
| --- | --- |
| Simple Download | Used to download objects to a specific destination |
| Streaming Download | Used when you don't know the size of the object you want to download or you want to stream the object to a process |
| Sliced Object Download | Used to download large objects by slicing them |

## Simple Download 

* Used to download objects to a specific destination

## Streaming Download

* Used when you don't know the size of the object you want to download or you want to stream the object to a process

## Sliced Object Download

* Used to download large objects by slicing them

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Object Lifecycle Management Policy

* When specific conditions are met for an object within a bucket, the specified actions will automatically happen
* The rules include a condition and an action (If the condition is true, then the action is executed)

## Policy Conditions

| Object Lifecycle Management Policy Condition | Description |
| --- | --- |
| Age | |
| CreatedBefore | |
| IsLive | |
| MatchesStorageClass | |
| NumberOfNewerVersions | |

## Policy Actions

| Object Lifecycle Management Policy Action | Description |
| --- | --- |
| SetStorageClass | Changes an object's storage class to another |
| Deletion | Deletes an object |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Object Versioning

* A copy of an object is archived each time the object is overwritten or when it's deleted
* Useful when wanting to keep a history of changes to an object or want to mitigate the risk of accidentally deleting an object

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Storage Access Management

| Cloud Storage Access Management Method | Description |
| --- | --- |
| IAM | Assigns access permissions to an entire Cloud Storage bucket |
| ACL | Assigns access permissions to a sub set of objects in a Cloud Storage bucket |
| Signed URL | Assigns access permissions to a specific object in a Cloud Storage bucket for a limited amount of time |

## Signed URL

A signed URL is a URL that gives permissions for a limited time to perform specific actions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Bucket Storage Locations

## Regional Bucket

A specific geographical location

* Redundant across zones

## Dual Regional Bucket

A pair of regions

## Multi-Regional Bucket

A large geographical region (*US*, *EU*, *etc.*)

* Used when contents need to be stored in multiple regions to ensure acceptable times to access content
* Provides redundancy in case of zone-level failures
* More costly than regional and dual-regional buckets

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Bucket Security

* Using Uniform Access Control instead of ACLs is considered to be best practices

## Fine-Grained Access

* Allows users to specify access controls on individual objects as well as on buckets

## Uniform Access 

* Access to objects in a bucket is controlled by bucket-level permissions managed by the IAM service

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Storage Operations

Move objects between buckets
```Bash
gsutil mv gs://SOURCE_BUCKET_NAME/SOURCE_OBJECT_NAME gs://DESTINATION_BUCKET_NAME/DESTINATION_OBJECT_NAME
```

Rename an object
```Bas
gsutil mv gs://SOURCE_BUCKET_NAME/OLD_OBJECT_NAME gs://DESTINATION_BUCKET_NAME/NEW_OBJECT_NAME
```
