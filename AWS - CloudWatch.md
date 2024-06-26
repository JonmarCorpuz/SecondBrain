AWS CloudWatch is a monitoring and observability service that allows organizations to centrally monitor AWS resources by collecting, track, and monitor metrics and log files, as well as set alarms

* Collects and stores metrics from AWS resources (Ex: *CPU utilization*, *Network traffic*, *Disk usage*, *etc.*) from various AWS services (Ex: *Amazon EC2*, *Amazon S3*, *Amazon RDS*, *etc.*)
* Allows users to collect, monitor, and store log files and metrics generated by AWS resources and applications in real-time
* Enables users to set thresholds on metrics and trigger alarms or automated actions when those thresholds are breached
* Provides a stream of system events (Ex: *Instance state changes*, *API calls*, *Schedule events*, *etc.*) that occur within AWS resources (CloudWatch Events)
* Allows users to monitor the availability and performance of their application by simulating user interactions with web applications (CloudWatch Synthetics)
* Uses machine learning algorithms to analyse metric data and automatically detect unusual patterns or anomalies (CloudWatch Anomaly Detection)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CloudWatch Components

## Metrics

* CPU utilization, which measures the percentage of CPU capacity used over a specified time period
* Network traffic, which tracks the incoming and outgoing network traffic, typically in bytes per second, to help identify network bottlenecks or spikes in data transfer
* Disk I/O, which monitors read and write operations to the resource's storage volumes, typically in bytes per second and by measuring the average disk read/write time
* Memory utilization, which measures the percentage of memory (RAM) used by the resource to help identify memory-intensive applications or instances with insufficient memory allocation
* Status check, which tracks the results of resource status checks to help monitor the health of a resource's underlying infrastructure
* Disk space, which monitors the amount of disk space available on a resource's root volume or attached EBS volumes to help prevent storage capacity issues and ensure the availability of sufficient disk space for applications and data

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CloudWatch Features

## CloudWatch Logs

* Allows users to query and filter their log data
* Allows users to turn log data into numerical CloudWatch metrics that they can graph and use on their dashboards by setting up metric filters on logs

## CloudWatch Events

## CloudWatch Synthetics

## CloudWatch Alarms

* CloudWatch alarm states include OK (The metric is within the defined threshold), ALARM (The metric is outside of the defined threshold), and INSUFFICIENT_DATA (The alarm has just started, the metric isn't available, or there's not enough data available for the metric to determine the alarm state)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CloudWatch Terminology

* Log Event: A record of activity recorded by the application or resource being monitored that comes with a timestamp and an event message
* Log stream: A sequence of log events that all belong to the same resource being monitored
* Log Group: A group of log streams that all share the same retention and permissions settings
