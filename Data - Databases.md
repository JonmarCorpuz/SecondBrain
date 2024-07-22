A database is an organized collection of data or information that's stored and managed electronically

* Allows data to be accessed, manipulated, and updated by multiple users or applications simultaneously

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Database Management System

A DBMS is software that enables users to interact with databases

* Provides an interface for creating, querying, updating, and managing databases, as well as controlling access to the data stored within them
* Uses a Data Definition Language (DLL) to allow users to define the structure of the database (Ex: *Tables*, *Fields*, *Data types*, *Relationships*, *Constraints*, *etc.*)
* Uses a Data Manipulation Language (DML) to provide mechanisms for inserting, updating, deleting, and querying data stored in the database
* Ensures that only authroized users can access and modify the data by managing user authentication and authroization, and offering additional security features (Ex: *RBAC*, *Encryption*, *etc.*)
* Ensures data consistency and integrity by handling concurrent access to the dabase by multiple users or applications
* Uses different techniques to prevent conflicts and maintain data integrity (Ex: *Locking*, *Transaction management*, *etc.*)
* Ensures data durability and reliability by enabling data backup, recovery, and restoration capabilities
* Optimizes query execution and performance by analyzing query plans, indexing data, caching frequently accessed data, etc.
* Supports scaling out and replicating databases across multiple servers to handle growing data volumes, improve performance, and provide fault tolerance
* Enforces data integrity constraints to maintain data consistency and accuracy (Ex: *Uniqueness*, *Referential integrity*, *Data validation rules*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Database Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/15623398368289_SQL%20vs%20NoSQL.png)

## Relational Database

A relational database is a type of BDMS that organizes data into tables that each consists of rows and columns (Ex: *MySQL*, *PostgreSQL*, *Oracle*, *SQL Server*, *Amazon Aurora*, *etc.*)

* Data is structured logically into tables that consist of rows and columns 
* Each row in a table represents a record or tuple and each column represents a field or attribute
* Tables are organized based on their logical relationships
* The relationship between two different table is done using foreign keys
* Once the database is operational, it remains fixed and becomes difficult to change
* Ensures that data is persisted with high integrity and adheres to the ACID (Atomicity, Consistency, Isolation, and Durability) principle

### Schema 

A schema refers to the way that the data is organized and how relationships among data elements are enforced

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1_aMlw5Z3EN950koxWOJdneg.png)

* Includes descriptions of the tables, their columns, data types, constraints, and relationships between tables

### Rows

A row (record) contains all information about a specific entry

### Columns

A column contains an attribute about a specific entry

### Primary Keys

A primary key is a column that uniquely identifies each row in a table

* Ensures that each row in the table is uniquely identifiables
* Provides a way to reference individual records
* Each value in the primary key column must be unique within the table
* Cannot contain null values

### Foreign Keys

A foreign key is a column in one table that establishes a link to the primary key column in another table

* Represents a dependency between the data in two related tables
* The values in the foreign key column of one table corresponds to the values in the primary key column of another table
* Enforce referential integrity by ensuring that values in the foreign key column match existing values in the referenced primary key column
* Used to establish relationships between tables in a relational database schema (Ex: *Parent-child relationships*, *One-to-many relationships*, *etc.*)

## Non-Relational Database

A non-relational database is a type of BDMS that uses flexible data models to store data (Ex: *Graph databases*, *Key-value pairs*, *Wide-column stores*, *etc.*)

* Doesn't follow the traditional tabular structure of relational databases
* Designed to handle large volumes of structured, semi-structured, and unstructured data
* Often used in situations where scalability, flexibility, and performance are critical

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Database Architecture Types

## On-Premises Database

An on-premises database refers to a database system that's deployed and maintained within the physical premises of an organization

## Cloud-Based Database

