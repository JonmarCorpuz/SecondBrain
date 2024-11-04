# Alerting Policies Overview

An alerting policy is a set of conditions that define when and how to receive notifications about an incident

| Alerting Policy Component | Description |
| --- | --- |
| Condition | Describes the circumstances that trigger an alert |
| Notification Channel | Specifies where to send an alert notification once an incident is created for the alert |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Metric-Based Alerting Policies

Metric-based alerting policies monitor time-series data (metrics data) to notify users of trends over time

* How they work: They're calculated from included and excluded logs, and operate on metrics from all projects in the metrics scope of the monitoring project
* Creates an incident when a metric's value meets a condition for a specified period

## Sampling

Sampling is a technique for refining raw time-series data by removing some of the data from consideration

## Aggregation

Aggregation is a technique for refining raw time-series data by combining multiple pieces of data into a smaller set along dimensions you specify, also known as an alignment period

The [alignment period](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#understanding_alignment_period) divides raw time series data into buckets in which the raw data is regularlized in time so it can be combined with other aligned time series

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/fa-alignment-period.png)

| Alignment Step | Description |
| --- | --- |
| Step 1: Bucketing the data | Dividing the raw time-series data into time intervals, also known as the alignment period |
| Step 2: Computing a single metric value for the points in the alignment period | You choose how that single point is computed (*Sum all the values*, *Compute their average*, *Use the maximum*, *etc.*) |

* Long alignment periods are better for exploring trends over longer periods of time
* [Long alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are typically not useful for looking at short-term anomalous conditions (*Short spikes in traffic*, *etc.*)
* [Short alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are better for more granular monitoring

### Alignment Options


## Retest Window

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log-Based Alerting Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SQL-Based Alerting Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


