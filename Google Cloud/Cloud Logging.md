# Cloud Logging Overview

Cloud Logging is a service for collecting, storing, filtering, and vieweing log and event data

* Log data is ingested by the Cloud Logging API, which are then routed to either a Required log sink, the Default log sink, or a user-defined log sink

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log Sinks

* Associated with a Google Cloud resource
* The Required and Default sinks are created by default for each billing, account, project, or organization

## Require Sinks

* Used to store admin activity, system events, and access transparency logs
* The logs are stored for 30 days by default 

## Default Sinks

## User-Defined Sinks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log Routers

Log Router is a service that receives log messages and applies inclusion and exclusion filters to determine which log sinks should receive the message

* Supports using combinations of sinks to route logs to multiple storage locations

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log Metrics

* Based on the content of log messages
