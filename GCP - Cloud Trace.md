Cloud Trace is a distributed tracing system that helps developers analyze and optimize the performance of their applications

* Collects latency data from applications to help understand how requests propagate through various services in a microservice architecture (Ex: *How long a service takes to handle a request*, *The average latency of requests*, *etc.*)
* Identifies and analyzes latency issues in your applications by examining traces and spans (Ex: *Detecting slow operations*, *Detecting bottlenecks*, *etc.*)
* Visualizes traces in a detailed timeline view, showing the relationship between different spans and their durations
* Correlates trace data with logs to get more context around issues
* Tracing requests across microservices requires you to instrument them to use tracing libraries or Cloud Trace API directly

| Cloud Trace Component | Description | 
| --- | --- |
| Trace | Latency data collected from Google Cloud services |
| Span | A single operation or segment within a trace, which contains metadata (Ex: *Operation name*, *Start and end times*, *Labels*, *etc.*) |
