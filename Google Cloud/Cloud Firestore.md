# Cloud Firestore Overview

Google's Firestore is a managed NoSQL document database where the data is organized into a structure called a document

* Uses the concept of a document as the basic building block
* Automatically partitions data and scales up or down when needed
* Supports transactions, indexes, and SQL-like queries
* Used for nonanalytic and nonrelational storage needs (Ex: *Product catalogs with varying properties*, *User profiles*, *User navigation history*, *etc.*)
* Doesn't support relational operations (Ex: *Joining tables*, *Sums*, *Counts*, *etc.*)
* Provides strong consistency and real-time updates

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Documents

A document is a collection of key-value pairs

* Allow for flexible schemas where the set of keys that may be included doesn't have to be defined prior to use in document databases (Helpful when applications must accomodate a range of attributes, some of which may not be known at design time)

## Collections

A collection is a set of documents

## Entities

An entity is a set of key-value pairs within a document

* There's no requirement for all entities to have all the same properties since Cloud Firestore is a schema-less database

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Firestore Modes

## Native Mode

* Provides a different data modelbased on documents and collections

## Datastore Mode
