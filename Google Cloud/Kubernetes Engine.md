# Google Kubernetes Engine Overview

The Google Kubernetes Engine is a managed Kubernetes service for containers and container clusters running on GCP

* Uses the Container-Optimized OS, which is a hardened OS built by Google
* Integrated with Google Cloud Monitoring and Google Cloud Logging by default
* Automatically monitors the health of servers in the cluster and automatically repairs problems
* Multiple clusters can be managed as a group (fleet)

| GKE Feature | Description | 
| --- | --- |
| Auto-Repair | |
| Auto-Upgrade | |
| Pod Autoscaling | |
| Cluster Autoscaling | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GKE Cluster Mode

| GKE Cluster Mode | Description |
| --- | --- |
| Standard Mode | |
| Autopilot Mode | |

## Standard Cluster Mode

## Autopilot Cluster Mode

* Reduces your operational costs in running Kubernetes clusters
* Provides a hands-off experience (GKE will manage the cluster infrastructure for you)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GKE Container Exeternal Deployment Methods

| GKE Container Deployment Method | Description |
| --- | --- |
| LoadBalancer | Externally exposes the service using the CSP's load balancer |
| ClusterIP | Internally exposes the service using the cluster's interal IP address |
| NodePort | Externally exposes the service using the node's IP address at a static port |
| ExternalName | Externally exposes the service using the value mapped to the value of the externalName field in the DNS server |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GKE Cluster Types

| GKE Cluster Type | Description |
| --- | --- |
| Single Zone Zonal Cluster | All nodes within the cluster are running in the same zone |
| Multi Zone Zonal Cluster | Not all nodes within the cluster are running in the same zone |
| Regional Cluster | All nodes within the cluster are running within the same zone whiel having one or more regions are running a replica of the control place |
| Priavte Cluster | A VPC-native cluster where the Master and Worker nodes are only accessible within their private network |
| Alpha Cluster | An instable cluster that's running with alpha features enabled for testing purposes |
