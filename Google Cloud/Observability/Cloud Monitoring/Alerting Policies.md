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
* Raw time-series data must be manipulated before it can be analyzed, and analysis often involves filtering some data out and aggregating some together

## Filtering

[Filtering](https://cloud.google.com/monitoring/api/v3/aggregation#filtering-intro) is a technique for refining raw time-series data by hiding some of the data from consideration

* You can filter time-series data based on either time or the value of one or more labels

## Aggregation

[Aggregation](https://cloud.google.com/monitoring/api/v3/aggregation#aggr-intro) is a technique for refining raw time-series data by combining multiple pieces of data into a smaller set along dimensions you specify, also known as an alignment period

### Alignment

An [alignment](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#understanding_alignment_period) divides raw time series data into buckets in which the raw data is regularlized in time so it can be combined with other aligned time series

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/fa-alignment-period.png)

* Analyzing time-series data requires that the data points be available on evenly spaced time boundaries, which is done through an alignment
* Creates a new time-series with a constant interval between data points
* Alignment is typically applied to multiple time-series in preparation for further manipulation

| Alignment Step | Description |
| --- | --- |
| Step 1: Bucketing the data | Dividing the raw time-series data into time intervals, also known as the alignment period |
| Step 2: Computing a single value | You choose how a single value is computed (*Sum all the values*, *Compute their average*, *Use the maximum*, *etc.*) |

#### Alignment Period Duration

The [duration](https://cloud.google.com/monitoring/api/v3/aggregation#picking-alignment-periods) of an alignment period depends on the granularity of what you're trying to find in the data and the sampling period of the data, which is how often it's reported

| Alignment Period Duration Factor | Description |
| --- | --- |
| [Granularity](https://cloud.google.com/monitoring/api/v3/aggregation#align-granularity) |

* Long alignment periods are better for exploring trends over longer periods of time
* [Long alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are typically not useful for looking at short-term anomalous conditions (*Short spikes in traffic*, *etc.*)
* [Short alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are better for more granular monitoring

#### Alignment Period Sampling Rate

The alignment period [sampling rate](https://cloud.google.com/monitoring/api/v3/aggregation#align-sampling) refers to the frequency with which the data is written

| Metric Sampling Rate | Description |
| --- | --- |
| [Google Cloud Metrics](https://cloud.google.com/monitoring/api/metrics_gcp#gcp) | |
| [Google Distributed Cloud Metrics](https://cloud.google.com/monitoring/api/metrics_anthos#anthos) | |
| [Istio Metrics](https://cloud.google.com/monitoring/api/metrics_istio#istio) | |
| [Kubernetes Metrics](https://cloud.google.com/monitoring/api/metrics_kubernetes#kubernetes) | |
| [Ops Agent Metrics](https://cloud.google.com/monitoring/api/metrics_opsagent#agent) | |
| [Legacy Mointoring and Logging Agent Metrics](https://cloud.google.com/monitoring/api/metrics_agent#oagent-vs-magent) | |
| [Knative Metrics](https://cloud.google.com/monitoring/api/metrics_knative#knative) | |
| [External Metrics](https://cloud.google.com/monitoring/api/metrics_other#other) | |

#### Retest Window

### Reduction

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Log-Based Alerting Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SQL-Based Alerting Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


