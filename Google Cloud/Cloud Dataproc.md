# Dataproc Overview 

Google's Cloud Dataproc is a managed service Apache Spark and Apache Hadoop for batch processing, querying, streaming, and machine learning

* Allows you to create clusters quickly and manage them easily
* Users can export cluster configuration but not data
* Can be deployed using both the Compute Engine and the Kubernetes Engine
* Designed for data manipulation, statistical analysis, machine learning, and other complex operations for data storage and retrieval (Not designed to be a persistent store of data)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Dataproc Clusters

```Bash
gcloud dataproc clusters create CLUSTER_NAME --zone <ZONE>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Dataproc Cluster Modes

## Standard

* 1 master and N workers

## Single Node

* 1 master and 0 workers

## High Availability

* 3 masters and N workers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Dataproc Jobs

* Submitted to a Dataproc cluster

## Spark Jobs

* Supports serverless batch jobs (Users don't have to configure cluster resources or manage clusters)

```Bash
gcloud dataproc jobs submit spark --cluster CLUSTER_NAME --jar JAR_FILE
```

## PySpark Jobs

## SparkR Jobs

## Hive Jobs

## Spark SQL Jobs

## Pig Jobs

## Hadoop Jobs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Workflow Templates

* Allows you to define and execute workflows specified as a directed graph of jobs
* Users can specify if they want to use a managed cluster to run their jobs (The workflow creates a cluster to run the jobs and then terminate it once it's done executing everything)
