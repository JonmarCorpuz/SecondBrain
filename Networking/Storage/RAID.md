Redundant Array of Independent Disks is a storage technology that combines multiple physical disk drives into a single logical unit

* Improves data reliability, redundancy, and performance by distributing or replicating data across the array of disks
* The configuration and operation of RAID arrays, which are configurations of multiple physical storage drives that work together to provide improved performance and/or fault tolerance, can take place either in software on the OS or RAID controllers, which are hardware or software components that manage and control the operation of a RAID array

# RAID Levels

## RAID 0

RAID 0 (Striping) is a RAID level that involves the striping of data across multiple disks in a storage array, which is a data distribution technique that divides data into blocks with each block being written across multiple disks in the storage array

* The striping process allows for parallel read and write operations across all the disks, which can lead to improved performance
* Provides no redundancy or fault tolerance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture9.png)

## RAID 1

RAID 1 (Mirroring) is a RAID level that involved the duplication of data across two or more disks in a storage array

* Every piece of data is mirrored onto a separate disk, creating an exact copy of the information
* Provides redundancy and fault tolerance, as the data will remain accessible even if one disk in the array fails

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture10.png)

## RAID 5

RAID 5 is a RAID level that strips data across multiple disks and distributes them across all disks in order to provide parity, which is a form of redundancy that's used to provide fault tolerance and data recovery in the event of a disk failure

* Provides a balance between data striping, performance, and fault tolerance
* The parity of data is used for fault tolerance, allowing the recovery of data in the event of a single disk failure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture11.png)

## RAID 6

RAID 6 is a RAID level that strips data across multiple disks and distributes them across all disks in order to provide dual parity, which refers to the use of two separate sets of parity in a storage system

* Enhances fault tolerance by allowing the storage system to withstand the simultaneous failure of up to two disks without resulting in data loss

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture12.png)

## RAID 10

RAID 10 is a RAID level that combines striping (RAID 0) and mirroring (RAID 1)

* Provides both high performance and fault tolerance by merging the features of RAID 0 and RAID 1
* Data is mirrored and then striped for improved performance by allowing parallel read and write operations across multiple disks
* Can tolerate the failure of one or more disks within a mirrored set without losing data

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture13.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Capture14.png)
