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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20181849.png)

| Pod Lifecycle | Description |
| --- | --- |
| Pending | One or more containers are not ready to run |
| Running | All containers have been created and at least one is still running, or in the process of starting or restarting |
| Succeeded | All containers in the Pod have terminated successfully and will not be restart |
| Failed | All containers in the Pod have terminated, and at least one container has terminated in failure (non-zero exit code) |
| Unknown | The Pod's status couldn't be obtained, either due to a communication error with the Node running the Pod or due to some other issue |

### Container Error Lifecycle

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-14%20192429.png)

* The `CrashLoopBackOff` helps prevent quick successions of container recreation and crashing recreation by increasing the wait time every time the same container restarts, also known as a wait for exponential backoff

| Pod Restart Policy | Description |
| --- | --- |
| Always | The container will always be restarted when exits, no matter the reason |
| OnFailure | The container will always be restarted when it exits with a non-zero exit code |
| Never | The container won't restart when it exits |

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

| Object Management Method | Description |
| --- | --- |
| Imperative management with kubectl | |
| Imperative management with configuration files | |
| Declarative management with configuration files | |

## ReplicaSets

A [ReplicaSet](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/#:~:text=purpose%20is%20to-,maintain%20a%20stable%20set%20of%20replica%20Pods%20running%20at%20any%20given%20time,-.%20Usually%2C%20you%20define) maintains a stable set of replica Pods running at any given time

* Fullfills its purpose by creating and deleting Pods as needed to reach the desired number
* When a ReplicaSet needs to create new Pods, it uses its Pod template within the [spec](link.com) field 
* Linked to its Pods via the their [metadata.ownerReferences](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/#:~:text=purpose%20is%20to-,maintain%20a%20stable%20set%20of%20replica%20Pods%20running%20at%20any%20given%20time,-.%20Usually%2C%20you%20define) field, which specifies what resource the current object is owned by
* All Pods acquired by a ReplicaSet have their owning ReplicaSet's identifying information within their ownerReferences field (It's through this link that the ReplicaSet knows of the state of the Pods it is maintaining and plans accordingly)
* Identifies new Pods to acquire by using its [selector](link.com) (If there's a Pod that has no OwnerReference or the OwnerReference is not a [Controller](https://kubernetes.io/docs/concepts/architecture/controller/#:~:text=a%20control%20loop%20is%20a%20non%2Dterminating%20loop%20that%20regulates%20the%20state%20of%20a%20system) and it matches a ReplicaSet's selector, it'll be immediately acquire by said ReplicaSet)
* Used when you require custom update orchestration or don't require updates at all
* Ensures high availability and fault tolerance by replacing exited or unhealthy Pods 

## StatefulSets

## Deployments

## Jobs

## Service
