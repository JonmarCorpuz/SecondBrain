# Data Storage Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Data%20Storage%20Types.png)

## Block Storage

Block storage is storage technology that takes any data and divides it into fixed, equal sized blocks while assigning each block a unique identifier, and then distributes those blocks across the storage network to balance efficiency and functionality

* Stores the divided data blocks on underlying physical storage, which all gets reassembled together when a user requests the data 
* Fast, reliable, and easy to access
* Not constrained to specific network environments
* Reduces data transfer overhead by using limited metadata
* Allows servers to efficiently access and retrieve data in block storage by using unique identifiers assigned to each block for read/write operations
* Delivers ultra-low latency required for high-performance workloads because of the limited metadata that gets stored
* Block storage architecture provides multiple paths to the data by decoupling data from user environments
* Well-suited for applications requiring rapid read/write capabilities
* Changes in a file will only require the affected blocks to be modified

## File Storage
File storage is a storage technology that stores data in files and organizes them into folders, which are then organized into directories and subdirectories

* A user needs to specify the full file path from the directory down to the specific folder and file name to locate a file
* Well-suited for storing and organizing structured, transactional data and manageable data volumes

## Object Storage

Object storage is storage technology that manages and manipulates data as distinct units called "objects"

* Each object contains the data itself, associated metadata, and a unique identifier
* Uses a flat, scalable storage pool
* Data is accessed through APIs
* Well-suited for storing and managing large volumes of unstructred data (Ex: *Image*, *Videos*, *etc.*)
* Provides the ability to add rich metadata to objects and a flexible, scalable, and API-driven approach to storing and managing large amounts of unstructured data
* Changes in a file will require the whole object to be modified
* Often follows a WORM (Write Once, Read Many) model
