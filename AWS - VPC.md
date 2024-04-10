An Amazon Virtual Private Cloud allows users to create and manage isolated virtual networks within the AWS cloud environment

* Enables users to define and control a virtual network environment that closely resembles a traditional network 
* Enables users to create multiple isolated virtual private networks (VPCs) within their AWS account, where each VPC operates as a logically isolated section of the AWS cloud and allows users to define its own IP address range, subnets, route tables, and network access control policies
* Allows users to define custom routing tables to control the flow of traffic within their virtual network
* Provides users several options for connecting their virtual network to the internet (Ex: *Internet Gateways*, *NAT gateways*, *Virtual Private Gateways*, *etc.*), allowing them to control inbound and outbound internet traffic to and from your VPC resources
* Offers robust security features to help users secure their virtual environment (Ex: *Security groups to control traffic to their instances*, *VPN connections to encrypt data in transit between their VPC and on-premises networks*, *etc.*)
* Seamlessly integrates with other AWS services, allowing users to deploy and manage a wide range of cloud resources within their virtual environment

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

# VPC Components

## AWS IGW

An Internet Gateway is a horizontally scalable, redundant, and highly available VPC component that allows communication between instances within a user's VPC and the internet

* Serves as a gateway through which traffic can flow between the user's VPC and the internet, allowing its instances to establish outbound connections to the internet in order to access resources, services, and data that's hosted outside the VPC
* Typically associated with public subnets within a VPC
* Often used in conjunction with NAT Gateways or NAT instances, which reside in public subnets, to allow private instances within a VPC to initiate outbound connections to the internet while still maintaining a level of security
* Handles both incoming and outgoing traffic
* Can be shared by multiple VPCs
* Each VPC can only be associated with one IGW at a time
* Can ensure that only authorized traffic is allowed to enter or leave the VPC by implementing security groups and NACLs to control the traffic that flows through the IGW

## AWS VGW

A Virtual Private Gateway is a VPC component that enables communication between a user's VPC and other AWS services or remote networks securely and privately over an encrypted VPN connection or a Direct Connect dedicated network connection

* Users can create routes from their on-premises network to their VPC and vice versa, allowing resources within the user's VPC to communicate with resources in their on-premises network as if they were part of the same network
* Automatically replicates the VGW across multiple AZs within a region to ensure continuous connectivity
* Ensures secure communication between a user's VPC and their on-premises network by using industry-standard encryption protocols (Ex: *IPSec*, *etc.*)

## Route Tables

### Main Route Table

### Custom Route Table

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
