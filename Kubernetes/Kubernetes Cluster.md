# Kubernetes Cluster Overview

A Kubernetes cluster is simply a group of worker nodes that are managed by the Master Node (Control Plane)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/piptiprtierpitepirepriwepirpewripweir.png)

| Kubernetes Cluster Component | Description |
| --- | --- |
| **Master Node** (Control Plane) | The node that manages the Kubernetes cluster |
| **Worker Node** | A node that runs the workload (pods) |
| **Node Pool** | A group of worker nodes within a cluster with the same configurations |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cluster Components

Cluster 
--> Nodes 
----> Pods 
------> Containers 
------> Workloads

## Nodes

A Node

* Executes the workloads run on the cluster
* Primarily controlled by the control plane but some commands can be manually run
* Runs the `kubelet` (An agent on the data plane that communicates with the control plane)

### Pods

A Pod is a single running instance of a running process in a Kubernetes cluster

* Contains at least one container (Can run multiple containers when two or more containers must share resources or are tightly coupled
* Shares networking and storage across contrainers
* Receives a unique IP address and a set of ports which containers will use and connect to
* Allows containers to behave as if they're running on an isolated VM (You can deploy multiple instances of the same application or different instances of different application on the same Node or different Nodes, without having to change their configuration)
* Treats the multiple containers it's hosting as a single entity for management purposes
* Generally created in groups and considered ephemeral

#### Containers

* Each container in a Pod will connect to a separate port
* Containers on the same Pod (Localhost) can talk to each other

#### Workloads

* Kubernetes organizes processes into workloads
* Distributed across Nodes in a Kubernetes cluster

