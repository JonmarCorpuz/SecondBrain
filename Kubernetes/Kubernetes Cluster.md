# Kubernetes Cluster Overview

A Kubernetes cluster is simply a group of worker nodes that are managed by the Master Node (Control Plane)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/piptiprtierpitepirepriwepirpewripweir.png)

* Clusters are created with a release channel configuration that enables automatic upgrading of the cluster software (If you want more control over the upgrade process, you can choose to configure a static channel)
* Can host multiple resources for various different purposes that can each be isolate using namespaces

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
* Managed through delpoyments

#### Containers

* Each container in a Pod will connect to a separate port
* Containers on the same Pod (Localhost) can talk to each other

#### Workloads

* Kubernetes organizes processes into workloads
* Distributed across Nodes in a Kubernetes cluster

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Node Pools

A Node pool is a set of Nodes in a Kubernetes cluster that have the same configuration

* All Nodes are in the same Node pool by default after a Kubernetes cluster is created (You can add more Nodes and Node pools after the cluster has been created)
* Useful if you want to group Nodes with similar features
* The number of Nodes specified in the Node pool for a regional cluster will be the number of nodes for each zone the pool is in
