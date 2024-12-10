# Cloud Firestore Overview

Google's Firestore is a NoSQL document database that was built for automatic scaling, high performance, and ease of application development

* Uses the concept of a document, or collection of key-value pairs, as the basic building block
* Documents allow for flexible schemas, meaning the set of keys that may be included doesn't have to be defined prior to use in document databases (Helpful when applications must accomodate a range of attributes, some of which may not be known at design time)
* Accessed via a REST API that can be used from applications running in Compute Engine, Kubernetes Engine, or App Engine
* Scales automatically based on load, as well as shard or partition data as needed to maintain performance
* Supports transactions, indexes, and SQL-like queries
* Provides mobile and web client libraries
* Well suited for applications that demand high scalability and structured data and don't always need strong consistency when reading data (Ex: *Product catalogs*, *User profiles*, *User navigation history*, *etc.*)
