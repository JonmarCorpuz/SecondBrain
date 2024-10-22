# Cloud Audit Log Overview

Provides information about administrative activities and accesses within your Google Clour resources

# Audit Log Entries

| Cloud Logging Log Entry | Description |
| --- | --- |
| The Service | |
| The Operation | |
| The Audited Resource | |
| The Subject Making the Call | |

# Audit Log Types

## Admin Activity Log 

Logs for API calls or other actions that modify the configuration of resources (Ex: *VM creation*, *Paatching resources*, *Change in IAM permissions*, *etc.*) 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer

## Data Access Log 

Logs for everyone that reads resource configurations (Ex: *Listing resources*, *etc.*)

* Requires either one of the following permissions: Logging/Private Logs Viewer or Project/Owner
  
## System Event Audit Log 

Logs for Google Cloud administrative actions (Ex: *On host maintenance*, *Instance preemption*, *Automatic restart*, *etc.*) 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer

## Policy Denied Audit Log 

Logs for when a user or service account is denied access 

* Requires either one of the following permissions: Logging/Logs Viewer or Project/Viewer 
