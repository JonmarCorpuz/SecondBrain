Google's Cloud Storage is a managed service for storing unstructured data

* Very flexible and inexpensive
* Stores objects using a key-value approach and treat entire objects as a unit
* Provides access control at the object level
* Provides REST API to access and modify objects
* Can store all file types (Ex: *Text*, *Binary*, *Backup*, *Archives*, *etc.*)
* Always encrypts data on the server side (A newly created bucket is assigned with a Google managed key that'sused to encrypt the data by default)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Storage Components

| Cloud Storage Component | Description |
| --- | --- |
| Object | An individual piece of data (Ex: *A file*, *An image*, *A video*, *etc.*) |
| Bucket | A container that'll hold the objects that you want to store in Cloud Storage |

## Object

* Each object it identified by a unique key
* Maximum size is 5TB
* Objects can be versioned to prevent accidental deletion and provide history (The live version is the latest version and the older versions are uniquely identified by an object key along with a generation number)
* Object versions take up storage space since you're storing multiple versions of an object

## Bucket

* Bucket names start with the **goog** prefix and should not contain the work google
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
* High availability (99.9999999% annual durability)
* Low latency
* Unlimited storage (Autoscaling is automatically configured and there's no minimum object size required)
* The APIs used across storage classes are the same (Ex: *Storing data to the archive storage class is the same way you'd store data to the standard class*)

| Storage Class | Description |
| --- | --- |
| Standard | |
| Nearline Storage | |
| Coldline Storage | |
| Archive Storage | |

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
| Simple Upload | |
| Multipart Upload | |
| Resumable Upload | |
| Streaming Transfer | |
| Parallel Composite Upload | |

## Simple Upload

* Used to upload small files that can be re-uploaded in case of failures
* No object metadata

## Multipart Upload

* Used to upload small files that can be re-uploaded in case of failures
* Objects contain metadata

## Resumable Upload

* Used to upload small and large files
* If an upload fails, it'll resume from where it failed

## Streaming Transfer

* Used to upload an object of unknown size

# Parallel Composite Upload

* Used to upload a large object 
* The object is divided up to 32 chunks and uploaded in parallel
* Significantly fast if the network and disk speeds are not limiting factors

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Downloading Objects

| Object Download Option | Description |
| --- | --- |
| Simple Download |  |
| Streaming Download |  |
| Sliced Object Download |  |

## Simple Download 

* Downloading objects to a specific destination

## Streaming Download

* You don't know the size of the object or you want to stream the object to a process

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
