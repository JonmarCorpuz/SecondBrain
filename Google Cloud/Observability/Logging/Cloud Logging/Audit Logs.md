

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Google Cloud Logging Features

| Google Cloud Logging Feature | Description |
| --- | --- |
| Logs Explorer | Allows you to search, sort, and analyze logs using queries |
| Logs Dashboard | Provides visualizations of logs |
| Logs Metric | Allows you to collect custom metrics using queries or matching strings |
| Logs Router | Allows you to route logs to specific log buckets |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Logging Agent

* The Logging Agent needs to be installed on the VM instances that you want to ingest logs from 
* Based on fluentd

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Logging Log Types

| Cloud Logging Log Type | Description |
| --- | --- |
| Cloud Audit Log | Captures who did what, when, and where |
| Access Transparency Log | Captures actions performed by the GCP team on your content |

## Cloud Audit Log

Provides information about administrative activities and accesses within your Google Clour resources

### Audit Log Entries

| Cloud Logging Log Entry | Description |
| --- | --- |
| The Service | |
| The Operation | |
| The Audited Resource | |
| The Subject Making the Call | |

### Audit Log Types

#### Admin Activity Log 

Logs for API calls or other actions that modify the configuration of resources (Ex: *VM creation*, *Paatching resources*, *Change in IAM permissions*, *etc.*) 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer

#### Data Access Log 

Logs for everyone that reads resource configurations (Ex: *Listing resources*, *etc.*)

* Requires either one of the following permissions: Logging/Private Logs Viewer or Project/Owner
  
#### System Event Audit Log 

Logs for Google Cloud administrative actions (Ex: *On host maintenance*, *Instance preemption*, *Automatic restart*, *etc.*) 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer

#### Policy Denied Audit Log 

Logs for when a user or service account is denied access 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer 

## Access Transparency Log

Provides logs of actions taken by Google staff when accessing you Google Cloud content

* Can help customers track compliance with their legal and regulatory requirements for their organization

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log Bucket

A log bucket is a storage container within Cloud Logging that holds log entries

* Provides a structured and organized way to manage and store log data from various sources
* Allows you to create different buckets for different logging purposes in order to organize your logs
* Allows you to define retention policies that determine how long logs are kept before they're deleted

| Log Bucket Type | Description |
| --- | --- |
| _Required | Holds Admin activity, System Events, and Access Transparency logs |
| _Default | Holds all other logs that aren't stored in the _Required bucket |

## _Required Log Bucket

* Free and can't be deleted
* The retention period is 400 days be default and can't be changed

## _Default Log Bucket

* You're billed based on Cloud Logging pricing
* The bucket can't be deleted but you can disable the _Default log sink route to disable log ingestion
* The retention period is 30 days by default and can be edited to be between 1 and 3650 days
