# Namespaces Overview

[Namespaces](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/) is a naming mechanism that provides groups of resources within the same single physical cluster to be logically isolated from one another

* Provides cluster resources to be divided between multiple tenants and environments
* Helps organizations organize workloads within a large Kubernetes cluster
* Names of resources need to be unique within a namespace, but not across namespaces
* Namespace-based scoping is applicable only for namespaces objects and not for cluster-wide objects
* Can prevent a single tenant from monopolizing cluster resources by applying resource quotas for different namespaces
* Can be used when defining access control policies
* Service communication requires the FQDM of the service

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Initial Namespaces

## default

The default namespace is the default namespace that Kubernetes uses when creating a new cluster

## kube-node-lease

The kube-node-lease namespace holds [Lease](https://kubernetes.io/docs/concepts/architecture/leases/) objects associated with each node 

* Node leases allow the kubelet to send [node heartbeats](https://kubernetes.io/docs/concepts/architecture/nodes/#node-heartbeats) so that the control plane can detect node failure

## kube-public

The kube-public namespace is reserved for cluster usage, in case that some resources should be visible and readable publicly through the whole cluster

* Readable by all clients

## kube-system

The kube-system namespace is created by the Kubernetes system for Kubernetes objects 
