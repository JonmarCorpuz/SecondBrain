SQL Injection is a type of security vulnerability that allows a threat actor to manipulate the SQL queries that an application sends to its database in order to gain unauthorized access to data

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Types of SQL Injection

## In-Band SQLi

In-Band SQLi occurs when a threat actor uses the same communication channel to both launch the attach and gather the results

* The threat actor receives immediate feedback from the applications
* Can be easily detected since it uses the same communication channel

| In-Band SQLi Type | Description | Example |
| --- | --- | --- |
| Error-Based SQLi | Involves triggering SQL errors to gather information about the database structure (Ex: *Table names*, *Column names*, *Data types*, *etc.*) | |
| Union-Based SQLi | Leverages the UNION operator to combine the results of two or more SELECT statements by appending their own malicious query to the original query | |

## Blind SQLi

Blind SQLi is a type of SQLi where the attacker doesn't receive direct visible feedback from the database but instead from the application's responses to different inputs

| Blind SQLi Type | Description | Example |
| --- | --- | --- |
| Boolean Blind SQLi | Involves sending SQL queries that return true or flase | |
| Time-Based SQLi | Involves sending SQL queries that cause a delay in the database's response if a condition is true | |

## Out-of-Band SQLi

Out-of-Band SQLi is a type of SQLi where the attacker uses different communication channels to send the attack and retrieve the results (Ex: *Using a web request as the attack channel and the data gathering channel could be monitoring HTTP/DNS requests made to a service you control*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SQLi Queries

| SQLi Query | Purpose | Description |
| --- | --- | --- |
| select * from users where username='' and password='' OR 1=1; | Authentication Bypass | Will always return true because of the OR operator

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SQLi Remediation

| SQLi Remediation Technique | Description |
| --- | --- |
| Prepared Statements With Parameterized Queries | |
| Input Validation | |
| Escaping User Input | |
