# Worker Nodes Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20171455.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Container Runtime

* Responsible for running the containers on each worker node
* K8 supports several runtimes (*Docker*, *containerd*, *CRI-O*, *etc.*)

## Pods

A [Pod](https://kubernetes.io/docs/concepts/workloads/pods/#:~:text=the%20smallest%20deployable%20units%20of%20computing%20that%20you%20can%20create%20and%20manage%20in%20Kubernetes) is the smallest deployable units of computing that you can create and manage in Kubernetes

* Contains a group of one or more containers and a specification for how to run the containers
* Allows containers to share storage and network resources
* Its contents are always co-located and co-scheduled, and run in a shared context
* Containers running in the same Pod can communicate with each other via localhost, as well as read and write to the same volumes

### Pod Lifecycle

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20171455.png)

| Pod Lifecycle | Description |
| --- | --- |
| Pending | One or more containers are not ready to run |
| Running | All containers have been created and at least one is still running, or in the process of starting or restarting |
| Succeeded | All containers in the Pod have terminated successfully and will not be restart |
| Failed | All containers in the Pod have terminated, and at least one container has terminated in failure (non-zero exit code) |
| Unknown | The Pod's status couldn't be obtained, either due to a communication error with the Node running the Pod or due to some other issue |

How Pods handle container errors ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20192429.png)

## Containers

* Health probles can be configured in each container so that they're restarted or stop receiving traffic if considered unhealthy

### Init Containers

[Init containers](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/#:~:text=specialized%20containers%20that,Pod) are specialized containers that run before app containers in a pod, that run during Pod startup

### App Containters

### Ephemeral Containers

An [ephemeral container](https://kubernetes.io/docs/concepts/workloads/pods/ephemeral-containers/#:~:text=a%20special%20type,accomplish%20user%2Dinitiated) is a special type of container that runs temporarily in an existing Pod to accomplish user-initiated actions (*Troubleshooting*, *etc.*)

* Used to inspect services rather than to build applications

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
