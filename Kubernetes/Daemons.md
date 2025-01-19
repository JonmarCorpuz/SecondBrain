# Daemon Overview

A daemon refers to a background process running on a Node in a Kubernetes cluster

* The processes are typically system-level operations that are crucial for the maintenance and operation of the Kubernetes Nodes and the cluster as a whole (*Logging*, *Monitoring*, *Network proxy*)
* Daemons in Kubernetes are implemented as DaemonSets

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# DaemonSets

A [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) defines Pods that offer services localized to each node

* Ensures that all or some Nodes run a copy of a specific Pod that hosts the daemon process (When Nodes are added or removed from the cluster, the DaemonSet automatically adjusts to add or remove the Pods to ensure that every Node has the required daemons running)
* Deploys services that must run on each Node to ensure that they are always running as needed (*Log collectors*, *Monitoring agents*, *Network proxies*, *etc.*)
* Helps maintain data consistenct when used to deploy storage daemons on each Node that need to manage local storage
* Can be described using a YAML file
