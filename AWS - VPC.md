An Amazon Virtual Private Cloud allows users to create and manage isolated virtual networks within the AWS cloud environment

* Enables users to define and control a virtual network environment that closely resembles a traditional network 
* Enables users to create multiple isolated VPCs within their AWS account, where each VPC operates as a logically isolated section of the AWS cloud and allows users to define its own IP address range, subnets, route tables, and network access control policies
* Allows users to define custom routing tables to control the flow of traffic within their virtual network
* Provides users several options for connecting their virtual network to the internet (Ex: *Internet Gateways*, *NAT gateways*, *Virtual Private Gateways*, *etc.*), allowing them to control inbound and outbound internet traffic to and from your VPC resources
* Offers robust security features to help users secure their virtual environment (Ex: *Security groups to control traffic to their instances*, *VPN connections to encrypt data in transit between their VPC and on-premises networks*, *etc.*)
* Seamlessly integrates with other AWS services, allowing users to deploy and manage a wide range of cloud resources within their virtual environment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AWS VPC Types

## Default VPC

A default VPC is created in each AWS region for every AWS user by default

* Pre-configured with default settings (Ex: *Default subnet in each AZs*, *Default security group*, *Default network ACL*, *etc.*)
* Often used to quickly deploy resources without having to configure a custom VPC

## Custom VPC

A VPC that a user creates themselves

* Allows users to fully customize their VPC's configuration
* Gives the user full control over the CIDR block, subnets, route tables, internet gateways, NAT gateways, security groups, network ACLs, etc.
* Often used to meet specific networking and security requirements

## VPC Peering

VPC peering allows users to connect two VPCs within the same AWS region

* Enables communication between instances, services, and microservices in the peered VPCs as if they were in the same network using private IP address
* Traffic stays within the AWS network and doesn't traverse the internet
* Facilitates data sharing between applications or environments running in different VPCs
* Only works with VPCs that are in the same AWS region

### How VPC Peering Works

1. The user establishes a peering connection between two VPCs, which will represent a one-to-one relationship between the two
2. Once the peering connection is established, they'll update the route tables in each VPC to route the traffic that's destined for the CIDR block of the other VPC through the peering connection
3. The user then configures security group rules and network ACLs to allow the desired traffic between instances in the peered VPCs
4. Instances in the peered VPC should now be abled to communicate with each other using private IP addresses as if they were in the same network

## VPC Endpoint

The VPC Endpoint is a service that enables users to privately connect their VPC to supported AWS services without requiring an Internet gateway, NAT device, VPN connection, or AWS Direct Connect

* Allows instances in the user's VPC to communicate with AWS services using private IP addresses, enhancing security and reducing latency

### Gateway VPC Endpoint

### Interface VPC Endpoint

## Transit Gateway

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Components

## IGW

An Internet Gateway is a horizontally scalable, redundant, and highly available VPC component that allows communication between instances within a user's VPC and the internet

* Serves as a gateway through which traffic can flow between the user's VPC and the internet, allowing its instances to establish outbound connections to the internet in order to access resources, services, and data that's hosted outside the VPC
* Typically associated with public subnets within a VPC
* Often used in conjunction with NAT Gateways or NAT instances, which reside in public subnets, to allow private instances within a VPC to initiate outbound connections to the internet while still maintaining a level of security
* Handles both incoming and outgoing traffic
* Can be shared by multiple VPCs
* Each VPC can only be associated with one IGW at a time
* Can ensure that only authorized traffic is allowed to enter or leave the VPC by implementing security groups and NACLs to control the traffic that flows through the IGW

## VGW

A Virtual Private Gateway is a VPC component that enables communication between a user's VPC and other AWS services or remote networks securely and privately over an encrypted VPN connection or a Direct Connect dedicated network connection

* Users can create routes from their on-premises network to their VPC and vice versa, allowing resources within the user's VPC to communicate with resources in their on-premises network as if they were part of the same network
* Automatically replicates the VGW across multiple AZs within a region to ensure continuous connectivity
* Ensures secure communication between a user's VPC and their on-premises network by using industry-standard encryption protocols (Ex: *IPSec*, *etc.*)

## Route Tables

A route table is a set of rules that determine how network traffic is directed within the VPC, between VPCs, and with other networks

* Contains a set of rules (route) that specify where network traffic should be directed based on its destination
* Each route consists of a destination CIDR block and a target
* Ensures that traffic destined for IP addresses within the VPC's CIDR block stays within the VPC and doesn't leave the network by including default routes for local traffic within the VPC
* Used to establish connectivity between a VPC and on-premises network
* Allows for route sharing and communication between different parts of the user's network infrastructure by propagating routes learned from VPN connections or VPC peering connections to other route tables within the VPC

### Main Route Table

The main route table refers to the default route table that gets automatically created for each VPC

* Contains default routes for local traffic within the VPC
* Allows instances within the VPC to communicate with each other using private IP addresses without the need for additional routing configuration
* Automatically associated with all subnets in the VPC by default

### Custom Route Table

The custom route table refers to a user-defined route table that the user creates and customizes to control the routing of network traffic within a VPC

* Allows users to define custom routes and routing policies to control the flow of traffic within the VPC and between the VPC and other networks
* Can be associated with one or more subnets within the VPC

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Creating a VPC Network

## Creating a VPC

The user needs to declare two specific settings in order to create a VPC:
  * The region they're selecting
  * The IP range for the VPC in the form of CIDR notation

## Creating VPC Subnets

In order to provide more granular control to their resources, the user will then divide the address range of their VPC into subnets (Ex: *Public subnet for public facing resources*, *Private subnet for private resources*, *etc.*). The user needs three main things in order to create a subnet:
  * The VPC they want the subnet to live in
  * The AZ they want their subnet to live in
  * The CIDR range for their subnet that's within their previously specified VPC CIDR range

## Configuring VPC Routing

VPC routing is done using route tables

* Proper routes in the VPC's route table is one of the components that's needed to ensure that instances can communicate with the internet (If the route table has a route to the IGW then it does have internet access and vice versa)

## VPC Security

Users can secure their VPCs using NACLs and security groups

### NACLs

NACLs are stateless, numbered set of rules that control the traffic allowed to and from subnets in a VPC

* Operates at the subnet level
* Stateless, meaning that a user needs to configure an outbound traffic rule that corresponds to an inbound rule
* Consists of numbered rules in sequential order that each either allows or denies traffic based on specified criteria (Ex: *Protocol*, *Port range*, *IP address*, *etc.*)
* Logs traffic that match specific rules to allows users to monitor and analyze network traffic patterns and potential security threats

### Security Groups

Security groups are virtual firelwalls that control inbound and outbound traffic for AWS instances and other resources within a VPC

* Operates at the instance level
* Allows users to specify which traffic is allowed to reach their instances and which isn't
* Stateful, meaning that allowing inbound traffic for a specific protocol and port will automatically allow the return traffic for that connection regardless of any outbound rules
* Changes to security groups take effect immediately
* Each instance can be associated with multiple security groups
* Provides logging and monitoring features to allow users to track changes, monitor traffic, and analyze security group activity
