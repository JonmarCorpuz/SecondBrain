# ReplicaSet Overview

A [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/) is a controller that maintains a stable set of identical Pods running at any given time 

* Can detect if not enough Pods for that application or workload are running and will correct that by creating the missing Pods
* Used to update and delete Pods
* Best practice to use Deployments instead unless you require custom update orchestration or don't require any updates at all
