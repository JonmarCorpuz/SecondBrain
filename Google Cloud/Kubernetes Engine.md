# Kubernetes Engine Overview

The Google Kubernetes Engine is a managed Kubernetes service for containers and container clusters running on GCP

* Uses the Container-Optimized OS (A hardened OS built by Google)
* Multiple clusters can be managed as a group (fleet)
* Allows you to manage multiple microservices within a cluster
* Provides the benefits of using Kubernetes without the administrative overhead
* Provides load balancing across Compute Engine VMs that are deployed in GKE

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Engine Container Exeternal Deployment Methods

## LoadBalancer

Externally exposes the service using the Cloud Service Provider's load balancer 

## ClusterIP 

Internally exposes the service using the cluster's interal IP address 

## NodePort 

Externally exposes the service using the node's IP address at a static port

## ExternalName 

Externally exposes the service using the value mapped to the value of the externalName field in the DNS server 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Engine Cluster Types

## Single Zone Zonal Cluster

* All nodes within the cluster are running in the same zone

## Multi Zone Zonal Cluster

* Not all nodes within the cluster are running in the same zone

## Regional Cluster

* All nodes within the cluster are running within the same zone whiel having one or more regions are running a replica of the control place

## Private Cluster

* A VPC-native cluster where the Master and Worker nodes are only accessible within their private network

## Alpha Cluster

* An instable cluster that's running with alpha features enabled for testing purposes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Engine Cluster Modes

## Standard Cluster 

* Users are responsible for configuring and managing the Nodes
* Follows a pay-per-node model where the customer is charged for the resources within their GKE cluster

## Autopilot Cluster 

* Provides a hands-off experience (GKE will configure and manage the cluster infrastructure for you)
* Reduces your operational costs in running Kubernetes clusters by following a pay-per-pod model

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Kubernetes Engine Policies

## Autoscaling

## Autohealing

## Automatic Upgrades

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Node Pools

Node pools are collections of Nodes all within the same configuration
