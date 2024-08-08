Container orchastartion management tool

* An open-source container ochestration solution
* Provides cluster management

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Cluster

A Kubernetes cluster is simply a group of nodes that are managed by Kubernetes that run containerized applications

| Kubernetes Cluster Component | Description |
| --- | --- |
| Master Node | Manages the Kubernetes cluster |
| Worker Node | Runs the workload (pods) |
| Node Pool | A group of worker nodes within a cluster with the same configurations |

## Master Node

The Master Node, also known as the Control Plane, is the node the manages the Kubernetes cluster

* Always replicate the master nodes across multiple zones for high availability

| Master Node Component | Description |
| --- | --- |
| API Server | Handles all communication from other nodes and the outside for a Kubernetes cluster (Ex: *Receives the request for a command*, *etc.*) |
| Scheduler | Decids which node in the cluster should run the pod |
| Control Manager | Ensures that the current state of the cluster matches the desired state defined by the user through Kubernetes manifests |
| etcd | A distributed key-value store database that stores all the cluster's data |

### API Server

### Scheduler

* Ensures that the node has enough resources to run the pod
* Prioritizes nodes based on various factors (Ex: *Resource availability*, *Pod distribution*, *Custom priorities*, *etc.*)

### Control Manager 

| Control Controller | Description |
| --- | --- |
| Node Controller | Monitors the health of nodes in the cluster and performs actions if it detects an unhealthy node |
| Replication Controller | Ensures that a specified number of pod replicas are running at any given time by creating and deleting pods to match the desired replica count |
| Endpoints Controller |  |
| Service Account and Token Controller |  |
| Namespace Controller |  |
| Persistent Volume and Persistent Volume Claim Controller | |
| Deployment Controller | |
| DaemonSet Controller | |
| Job Controller | |
| StatefulSet Controller | |

### etcd

## Worker Node

* Some CPU on the worker node is reserved by the Control Plane since the nodes need to communicate back to it

| Worker Node Component | Description |
| --- | --- |
| Pods | A pod contains a running process in the cluster |
| Kubelet | Manages the lifecycle of containers on a single node by communicating with the Master Node |

### Pods

* Each Pod is assigned an ephemeral IP address and can contain one or more containers 
* The smallest and simplest unit in the Kubernetes object model that can be created and deployed
* All the containers in a Pod share the same resources (Ex: *Network*, *Storage*, *IP address*, *Ports*, *Shared persistent disks*)

| Pod Status | Description |
| --- | --- |
| Running | The Pod has been bound to a node and has successfully created all of the containers, where at least one of them is still running or is in the process of starting or restarting |
| Pending | The Pod has been accepted by the Kubernetes system but one or more of the container images have not been created yet |
| Succeeded | All the containers in the Pod have been terminated successfully and won't be restarted |
| Failed | All the containers in the Pod have been terminated but at least one of them returned a non-zero exit code indicating a failure |
| Unknown | The state of the Pod couldn't be obtained |

### Kubelet

* Acts as an agent that ensures containers are running in a Pod
* Communicates with the Kubernetes API server to receive Pod specifications and report back the status of the node and the Pods running on it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Deployment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/bhlfbhfblkbsbbsdfsfbdsbfbdsf.png)

| Kubernetes Deployment Component | Description |
| --- | --- |
| Deployment | |
| ReplicaSet | Ensures that the specified number of Pods are running for a specific microservice version |

## Deployment 

* Represents a microservice
* Manages new releases ensuring zero downtime
* Deploying a new version of a microservice, it'll create a new replica set for the new version of the microservice and replace those from the old version

## ReplicaSet

* Ensures that the specified number of Pods are running for a specific microservice version
* If a Pod is deleted, isn't running, or fails then ReplicaSet will create a new one to replace it
* Uses label selectors to identify which Pods it should manage

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Service

A Service is a method for exposing a Pod so that other users and resources can interact with it

* Ensures that the external world doesn't get impacted as Pods within your cluster go down and come up

## Kubernetes Service Types

| Kubernetes Service Type | Description |
| --- | --- |
| ClusterIP | |
| LoadBalancer | |
| NodePort | |
