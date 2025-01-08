# Google VPC Overview

Google's VPC is a service that provides an isolated network in Google Cloud for GCP resources

* When an organization moves to a public cloud, it shares infrastructure with other customers of that public cloud but they can logically isolate its cloud resources by creating a VPC
* Google Cloud VPCs can span the globe without relying on the public Internet (Traffic from any server on a VPC can be securely routed through the Google global network to any other point on that network)
* Your backend servers on GCP can access Google services without need a public IP address for back-end servers
* Traffic within a VPC is isolated and not reachable by default from all other Google Cloud VPCs
* A global resource that can contain resources from any region (The subnets within a VPC are associated with regions)
* VPCs in Google Cloud can be linked to on-premises VPNs using IPSec

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Types

| VPC Type | Description |
| --- | --- |
| Shared VPC | Allows multiple projects within an organization to share a common VPC network |

## Shared VPC

* Created at the organization or shared folder level
* Allows a VPC network to be shared between projects in the same organization
* A shared VPC contains one host project and multiple service projects

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Google Private Access

* Used to reach Goole Cloud resources without using an external IP address
* Allows you to connect to Google APIs through the VPC's default network gateway
* Traffic to Google APIs from on-premises systems needs to be sent to either `private.googleapi.com` or `restrictred.googleapi.com`

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Private Service Connect

* Used with Google Cloud resources that may or may not have external IP addresses as well as on-premises systems
* This option allows you to connect to a Private Service Connect endpoint in your VPC network and that endpoint will forward requests to Google APIs and services

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Serverless VPC Access

* Allows Cloud Run, App Engine Standard, and Cloud Functions to reach private IP addresses from those services

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Flow Logs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Dynamic Routing

## Regional Routing

* Enables Goolge Cloud Routers to learn routes with the region

## Global Routing

* Enable Google Cloud Routers to learn routes on all subnetworks in the VPC

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS Policy

* Allows users to choose a DNS policy that enables DNS name resolution provided by Google Cloud or make changes to name resolution order

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


# VPC Subnets

* Each subnet is associated with a specific region (Subnets are regional)

## Public Subnet

* Resources in a public subnet can communicate with resources in private subnets

## Private Subnet 

* Enabling the Private Google Access will allow VMs to connect to Google's API using private IP addresses (Using private IP addresses will keep the communication within the network)
* Enabling FlowLogs will tunr on logging for network traffic (Allows users to troubleshoot any VPC related network issues)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Network Modes

## Auto Mode VPC Network

* Subnets are automatically created in each region
* Automatically used by default VPCs

## Custom Mode VPC Network

* No subnets are automatically created (You have complete control over subnets and their IP ranges)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Firewall Rules

* Allows users to control the traffic that goes in and out of their network
* The firewall rules are stateful, meaning that if traffic is allowed to come in, then that same traffic is allowed to go out
* Each firewall rules is assigned a priority between 0 (Highest priority) and 65535 (Lowest priority)

| VPC Firewall Rule Type | Description |
| --- | --- |
| Ingress Rule | Incoming traffic from an external source to internal GCP targets |
| Egress Rule | Outgoing traffic to destination from GCP targets |

| VPC Firewall Rule | Description |
| --- | --- |
| default-allow-internal | Allow incoming traffic from VM instances in the same network |
| default-allow-ssh | Allow incoming TCP traffic on port 22 |
| default-allow-rdp | Allow incoming TCP traffic on port 3389 |
| default-allow-icmp | Allow incoming ICMP from any source on the network |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Network Peering

VPC network peering is a networking feature that allows two VPC networks to connect directly with each other 

* Allows for interproject connectivity even if an organization is not defined
* Enables private communication between resources in different VPC networks without using external networking solutions and protocols (All communication happens using internal IP addresses)

Specify peering between two projects when an organization doesn't exist (Execute this command on both projects involved using the appropriate options in order to allow private traffic flow between the two VPCs)
```Bash
gcloud compute networks peerings create NETWORK_PEERING_NAME --network NETWORK --peer-project PROJECT_ID --peer-network PEER_NETWORK --auto-create-routes
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Shared VPC

* Requires the Shared VPC Admin role either at the organization or folder level in order to be able to create a shared VPC

Assign the Shared VPC Admin role to an organization
```Bash
gcloud organizations add-iam-policy-binding ORGANIZATION_ID --member='user:USER_EMAIL' --role="roles/compute.xpnAdmin"
```

Assign the Shared VPC Admin role to a folder
```Bash
gcloud resource-manager folders add-iam-policy-binding FOLDER_ID --member='user=USER_EMAIL' --role="roles/compute.xpnAdmin"
```

Create a Shared VPC
```Bash
gcloud compute shared-vpc enable HOST_PROJECT_ID
```

Associate a project to the host project
```Bash
gcloud compute shared-vpc associated-projects add SERVICE_PROJECT_ID --host-project HOST_PROJECT_ID
```
