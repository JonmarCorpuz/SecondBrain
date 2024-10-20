# Google VPC Overview

Google's VPC is a service that provides an isolated network in Google Cloud for GCP resources

* Traffic within a VPC is isolated and not reachable by default from all other Google Cloud VPCs
* Allows users to control their VPC's incoming and outgoing traffic
* A global resource that can contain resources from any region (The subnets within a VPC are associated with regions)

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

# VPC Subnets

## VPC Subnet Creation Modes

| VPC Subnet Creation Mode | Description |
| --- | --- |
| Automatic | |
| Custom | |

### Automatic 

* A subnet is automatically created in every region

### Custom

## Subnet Types

* Each subnet is associated with a specific region

| VPC Subnet | Description |
| --- | --- |
| Public Subnet | A network where its resources can be accessed from the Internet |
| Private Subnet | A network where its resources can't be accessed from the Internet |

### Public Subnet

* Resources in a public subnet can communicate with resources in private subnets

### Private Subnet 

* Enabling the Private Google Access will allow VMs to connect to Google's API using private IP addresses (Using private IP addresses will keep the communication within the network)
* Enabling FlowLogs will allow users to troubleshoot any VPC related network issues

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Network Modes

| VPC Network Mode | Description |
| --- | --- |
| Auto Mode VPC Network | |
| Custom Mode VPC Network | |

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

VPC network peering is a networking feature that allows two VPCs networks to connect directly with each other 

* Enables private communication between resources in different VPC networks without using external networking solutions and protocols (All communication happens using internal IP addresses)
