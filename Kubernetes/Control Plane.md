# Master Node Overview

The Master Node, also known as the Control Plane, is the node that manages the Kubernetes cluster

* For more availability, always replicate the master nodes across multiple zones for high availability
* Capable of monitoring the metrics of the worker note

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kube-apiserver

The [Kube-apiserver](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/) is the frontend that handles all communication from other nodes and the outside for a Kubernetes cluster by exposing the Kubernetes API

* Validates and configures data for the api objects
* Allows us to communicate with the Master Node through the kubectl command-line tool

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kube-scheduler

The [Kubernetes scheduler](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-scheduler/) is a control plane process which assigns Pods to Nodes

* Determines which Nodes are valid placements for each Pod in the scheduling queue according to constraints and available resources
* Ensures that the Node has enough resources to run the Pod
* Ranks each valid Node and binds the Pod to a suitable Node

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kube-controller-manager

The [Kubernetes control manager](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-controller-manager/) is a daemon that embeds the core control loops shipped with Kubernetes through various [controllers](https://kubernetes.io/docs/concepts/architecture/cloud-controller/#functions-of-the-ccm)

## Node Controller

The [Node Controller](https://kubernetes.io/docs/concepts/architecture/cloud-controller/#node-controller) is responsible for updating Node objects when new servers are created in your cloud infrastructure

## Route Controller

THe [Route Controller](https://kubernetes.io/docs/concepts/architecture/cloud-controller/#route-controller) is responsible for configuring routes in the cloud appropriately so that containers on different nodes in your Kubernetes cluster can communicate with each other

## Service Controller

The [Service Controller](https://kubernetes.io/docs/concepts/architecture/cloud-controller/#service-controller) interacts with your cloud provider's APIs to set up infrastructure components (*Load balancers*, *etc.*) when you declare a Service resource the requires them

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# etcd

The [etcd](https://etcd.io/docs/) is a distributed key-value store database that stores all the cluster's data and its current state

* A leader-based distributed system that ensures that the leader periodically send heartbeats on time to all foloowes to keep the cluster stable
* Aims to ensure that no resource starvation occurs (Performance and stability of the cluster is sensitive to network and disk I/O, so any resource starvation can lead to heartbeat timeout, causing instability of the cluster and an unstable etcd indicates that no leader is elected. Under such circumstances, a cluster cannot make any changes to its current state, which implies no new pods can be scheduled)
* If your Kubernetes cluster uses etcd as its backing store, make sure you have a back up plan for the data
* [etcd requirements](https://kubernetes.io/docs/tasks/administer-cluster/configure-upgrade-etcd/#resource-requirements-for-etcd)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud-controller-manager

The [Kubernetes Cloud controller manager](https://kubernetes.io/docs/concepts/architecture/cloud-controller/) embeds cloud-specific control logic

* Allows you to link your cluster into your cloud provider's API and separate out the components that interact with that cloud platform from components that only interact with your cluster
* Enables cloud providers to release features at a different pace compared to the main Kubernetes project
* Structured using a plugin mechanism that allows different cloud providers to intergrate their platforms with Kubernetes
* Runs in the Master Node (Control Plane) as a replicated set of processes
* Each cloud-controller-manager implements multiple controllers in a single process

