# Kubernetes Overview

Kubernetes is an open-source container orchestration platform 

* Automates the deployment, scaling, and management of clusters and the containers within
* Makes an application highly available and scalable by allowing workloads to be scaled up or down to match demand
* Highly portable, meaning that it can be run anywhere with nearly any type of infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Cluster

A Kubernetes cluster is simply a group of worker nodes that are managed by the master node (Control Plane)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/piptiprtierpitepirepriwepirpewripweir.png)

| Kubernetes Cluster Component | Description |
| --- | --- |
| **Master Node** (Control Plane) | The node that manages the Kubernetes cluster |
| **Worker Node** | A node that runs the workload (pods) |
| **Node Pool** | A group of worker nodes within a cluster with the same configurations |

## Master Node

The Master Node, also known as the Control Plane, is the node the manages the Kubernetes cluster

* Always replicate the master nodes across multiple zones for high availability
* Capable of monitoring the metrics of the worker nodes

| Master Node Component | Description |
| --- | --- |
| **Kube-apiserver** | The frontend that handles all communication from other nodes and the outside for a Kubernetes cluster by exposing the Kubernetes API |
| **Kube-scheduler** | Monitors the cluster to ensure that every newly created Pod is assigned to a node |
| **Kube-controller-manager**  | Responsible for running the controller processes, which are components that manage the state of resources in the cluster |
| **etcd** | A distributed key-value store database that stores all the cluster's data and its current state |
| **Cloud-controller-manager** | Enables communication between a Kubernetes cluster and a cloud provider's APIs to allow the separation of components that communicate internally within the cluster and those that communicate externally by interacting with a cloud provider |

### Kube-apiserver

* Allows us to communicate with the Master Node through the kubectl command-line tool

### Kube-scheduler

* Ensures that the node has enough resources to run the pod
* Prioritizes nodes based on various factors (Ex: *Resource availability*, *Pod distribution*, *Custom priorities*, *etc.*)

### Kube-controller-manager 



| Kube-controller-manager Controller | Description |
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

* The other control plane components rely on etcd as an information store and query it for information

## Worker Node

* Some CPU on the worker node is reserved by the Control Plane since the nodes need to communicate back to it

| Worker Node Component | Description |
| --- | --- |
| Pods | A pod contains a running process in the cluster |
| Kubelet | An agent that runs on every node and manages the lifecycle of containers within a node to ensure that they're running and healthy by communicating with the Master Node |
| Kube-proxy | Responsible for network communication within the cluster |
| Container Runtime | A software component that provides the necessary tools and services to create, run, manage, and stop containers (Ex: *Docker*) |

### Pods

A Pod is the smallest and simplest unit in the Kubernetes object model that can be created, deployed, and managed

* Each Pod is assigned an ephemeral IP address and can contain one or more containers 
* All the containers within the same Pod can communicate easily with each other since they share the same resources (Ex: *Network*, *Storage*, *IP address*, *Ports*, *Shared persistent disks*)
* Pods are treated as the smallest unit of replication in Kubernetes
* A Pod runs on a node, which is either a virtual or physical machine that's hosting the Pod

| Pod Status | Description |
| --- | --- |
| **Running** | The Pod has been bound to a node and has successfully created all of the containers, where at least one of them is still running or is in the process of starting or restarting |
| **Pending** | The Pod has been accepted by the Kubernetes system but one or more of the container images have not been created yet |
| **Succeeded** | All the containers in the Pod have been terminated successfully and won't be restarted |
| **Failed** | All the containers in the Pod have been terminated but at least one of them returned a non-zero exit code indicating a failure |
| **Unknown** | The state of the Pod couldn't be obtained |

### Kubelet

* Acts as an agent that ensures containers are running in a Pod
* Communicates with the Kubernetes API server to receive Pod specifications and report back the status of the node and the Pods running on it

### Kube-proxy

* Creates networking rules so traffic can flow and be directed to a Pod 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/bhlfbhfblkbsbbsdfsfbdsbfbdsf.png)

| Kubernetes Component | Description |
| --- | --- |
| ReplicaSet | Maintains a set of replica pods, which is a copy of a pod that's created and managed by Kubernetes, to guarantee the availability of the specified number of pods |
| Deployment | Allows the user to define a desired state, which is the configurations and operational status that the user defines for their applications and resources within the cluster |
| StatefulSets | Enables stateful applications to run on Kubernetes |
| Service | Ensures that a single IP address can be associated with a Pod and its replicas by acting as an access point |

## ReplicaSet

* Ensures that the specified number of stateless Pods are running for a specific microservice version
* If a stateless Pod is deleted, isn't running, or fails then ReplicaSet will create a new one to replace it
* Managed by a deployment

## Deployment 

* Once the desired state is defined, the deployment controller will change the actual state of the container to the desired state

* Represents a microservice
* Manages new releases ensuring zero downtime
* Deploying a new version of a microservice, it'll create a new replica set for the new version of the microservice and replace those from the old version
* Each Pod is identical and is used for stateless applications

## StatefulSets

StatefulSets enable stateful applications to run on Kubernetes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/jkhjkjhkghjghjghfghfghfgfdgd.png)

* Stateful Pods can't be created in any order and require a unique and persistent identity, network identifiers, and storage

| StatefulSet Pod | Description |
| --- | --- |
| Master Pod | The only Pod that can read and write to the database |
| Slave Pod | These Pods can only read the database and has an accurate replication of the master Pod's storage |

## Service

A Service is a method for exposing a Pod so that other users and resources can interact with it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/mcvmcvmcvmncmvnmcvnmcvmcvnmc.png)

* Ensures that the external world doesn't get impacted as Pods within your cluster go down and come up

| Kubernetes Service Type | Description |
| --- | --- |
| ClusterIP | |
| LoadBalancer | |
| NodePort | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Object YAML Configuration

* A Kubernetes object is a persistent entity in the Kubernetes system that represents the state of the cluster (Ex: *What applications are running*, *What resources the running applications are using*, *etc.*)

| Required Fields | Description |
| --- | --- |
| apiVersion | The version of the Kubernetes API that you're going to use to create this object |
| kind | The kind of object that you're going to create |
| metadata | Contains data that can be used to uniquely identify the object |
| spec | The desired state of the object |

Service YAML configuration file example
```YAML
apiVersion: v1
kind: Service
metadata:
  name: example-nginx-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 8080
      targetPort: 80
  type: ClusterIP
```

Deployment YAML configuration file example
```YAML
apiVersion: apps/v1
kind: Deployment
metadata:
  name: example-nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```
