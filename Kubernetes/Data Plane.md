# Worker Nodes Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20171455.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Container Runtime

* Responsible for running the containers on each worker node
* K8 supports several runtimes (*Docker*, *containerd*, *CRI-O*, *etc.*)

## Pods

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubelet

* An agent that runs on each worker node and communicates with the control plane
* Ensures that containers are running in the pods as defined by the pod specifications

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kube-proxy

* Manages network rules on each worker node
* Maintains network connectivity and load balancing services
* Ensures that requests are routed to the appropriate pods

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# K8 Objects

* Optional

## ReplicaSets

## StatefulSets

## Deployments

## Jobs

## Service
