# Cloud Storage Overview

Google's Cloud Storage is a managed service for storing unstructured data

* Very flexible and inexpensive
* Stores objects using a key-value approach and treat entire objects as a unit
* Provides access control at the object level
* Provides REST API to access and modify objects
* Can store all file types (Ex: *Text*, *Binary*, *Backup*, *Archives*, *etc.*)
* Always encrypts data on the server side (A newly created bucket is assigned with a Google managed key that's used to encrypt the data by default)
* Allows clients to encrypt their objects before uploading it to Cloud Storage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Storage Components

| Cloud Storage Component | Description |
| --- | --- |
| Object | An individual piece of data (Ex: *A file*, *An image*, *A video*, *etc.*) |
| Bucket | A container that'll hold the objects that you want to store in Cloud Storage |

## Object

* Each object it identified by a unique key and stored in a bucket
* Maximum size is 5TB
* Objects can be versioned to prevent accidental deletion and provide history (The live version is the latest version and the older versions are uniquely identified by an object key along with a generation number)
* Object versions take up storage space since you're storing multiple versions of an object
* Noncurrent objects are uniquely identified (object key + generation number)

| Object Version | Description |
| --- | --- |
| Live | The latest version of an object |
| Noncurrent | An older version of an object that has been replaced by a newer version |

## Bucket

* Bucket names start with the **goog** prefix and should not contain the word google
* Bucket names can only contain lower case letters, numbers, hyphens, underscores, and periods (3 to 63 characters max)
* Bucket names are globally unique and are used as part of object URLs
* A bucket can contain unlimited objects that each belong to different storage classes
* Each bucket is associated with a project

| Bucket Storage Class | Description |
| --- | --- |
| Standard | Best for short-term storage and frequently accessed data |
| Nearline | Best for backups and data accessed less than once a month |
| Coldline | Best for disaster recovery and data accessed less than once a quarter |
| Archive | Best for long-term digital preservation of data accessed less than once a year |

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

* Has no minimum storage duration
* Used for frequently used data or data that's needed only for a short period of time

## Nearline Storage

* Has a minimum storage duration of 30 days
* Used for objects that's read or modified once a month on average

## Coldline Storage 

* Has a minimum storage duration of 90 days
* Used for objects that are read or modified at most once a quarter

## Archive Storage

* Has a minimum storage duration of 365 days
* Used for objects that are accessed less than once a year

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

# Object Lifecycle Management

* When specific conditions are met for an object within a bucket, the specified actions will automatically happen

| Object Lifecycle Management Condition | Description |
| --- | --- |
| Age | |
| CreatedBefore | |
| IsLive | |
| MatchesStorageClass | |
| NumberOfNewerVersions | |

| Object Lifecycle Management Action | Description |
| --- | --- |
| SetStorageClass | Changes an object's storage class to another |
| Deletion | Deletes an object |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Storage Access Management

| Cloud Storage Access Management Method | Description |
| --- | --- |
| IAM | Assigns access permissions to an entire Cloud Storage bucket |
| ACL | Assigns access permissions to a sub set of objects in a Cloud Storage bucket |
| Signed URL | Assigns access permissions to a specific object in a Cloud Storage bucket for a limited amount of time |

## Signed URL

A signed URL is a URL that gives permissions for a limited time to perform specific actions
