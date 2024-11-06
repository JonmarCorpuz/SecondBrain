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

* Analyzing time-series data requires that the data points be available on evenly spaced time boundaries, which is done through an alignment
* Creates a new time-series with a constant interval between data points
* Alignment is typically applied to multiple time-series in preparation for further manipulation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/fa-alignment-period.png)

| Alignment Step | Description |
| --- | --- |
| Step 1: Bucketing the data | Dividing the raw time-series data into time intervals, also known as the alignment period |
| Step 2: Computing a single value | You choose how a single value is computed by using an [aligner](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#aligner) |

#### Alignment Period Duration

The [duration](https://cloud.google.com/monitoring/api/v3/aggregation#picking-alignment-periods) of an alignment period depends on the granularity of what you're trying to find in the data and the sampling period of the data, which is how often it's reported

| Alignment Period Duration Factor | Description |
| --- | --- |
| [Granularity](https://cloud.google.com/monitoring/api/v3/aggregation#align-granularity) | |
| [Sampling Rate](https://cloud.google.com/monitoring/api/v3/aggregation#align-sampling) | |

##### Granularity

* Long alignment periods are better for exploring trends over longer periods of time
* [Long alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are typically not useful for looking at short-term anomalous conditions (*Short spikes in traffic*, *etc.*)
* [Short alignment periods](https://cloud.google.com/network-intelligence-center/docs/flow-analyzer/alignment-period-aggregation#granularity) are better for more granular monitoring

#### Aligners

An [aligner](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#aligner) is a string that specifies the [operation](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#aligner) to be applied to the data points in each alignment period of a time-series

* Replaces the data values in each alignment period with a single value, for example: ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20174521.png) ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20175028.png)

##### Sampling Rate

The alignment period [sampling rate](https://cloud.google.com/monitoring/api/v3/aggregation#align-sampling) refers to the frequency with which the data is written

* If the alignment period is the same as the sampling period, then there is one data point in each alignment period, which means that the applied [aligners](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#aligner) will result in the same aligned time series ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-04%20190033.png)
* When choosing an alignment period, make it longer that the sampling period, but short enough to show relevant trends
* The sample data that was collected during the sample period will be ingested by Cloud Monitoring and won't be available during that period

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

### Reduction

Reduction ([Cross-series aggregation](https://cloud.google.com/monitoring/api/v3/aggregation#reduction-intro)) is the process of combining multiple aligned time-series into a new time-series by replacing all the values on the alignment-period boundary with a single value using a [Reducer](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#reducer), which is a function that is applied to the values across a set of time-series to produce a single value

* Works across separate time-series and they must be aligned before they can be reduced

#### Reducers

A [Reducer](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#reducer) is an operation that describes how to aggregate data points from multiple time-series into a single time-series, where the value of each data point in the resulting series is a function of all the already aligned values in the input time-series

* Example: ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20175545.png) ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20175956.png) ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20180138.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

### Grouping

[Grouping](https://cloud.google.com/monitoring/api/v3/aggregation#aggr-grouping) allows you to apply a [Reducer](https://cloud.google.com/monitoring/api/ref_v3/rest/v3/projects.alertPolicies#reducer) across subsets of your time-series rather than across the entire set of time-series by selecting one or more labels

* Time-series are grouped on the basis of their values for the selected labels
* Grouping results in one time-series for each group
* Example: ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-05%20180908.png)
