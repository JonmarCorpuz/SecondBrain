AWS Virtual Private Network allows users to establish secure connections between their on-premises network or client devices and their AWS infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AWS VPN Methods

## AWS Site-to-Site VPN

AWS Site-to-Site VPN enables secure, encrypted connections between a user's on-premises network and their VPC

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-04-22%20231939.png)

* Allows users to extend their corporate network into the AWS cloud to provide seamless and secure access to AWS resources from their data center, office, or other on-premises locations
* Ensures the confidentiality and integrity of data transmitted over the VPN connection by industry-standard IPSec VPN tunnels to encrypt network traffic between a user's on-premises network and their AWS VPC
* Allows users to connect their on-premises network to their AWS infrastructure without requiring dedicated leased lines or physical connections by establishing them over the public internet
* VPN connections are established using IPSec VPN tunnels between a VGW in the user's VPC and a customer gateway device deployed in their on-premises network
* Provides a secure communication channel between the user's on-premises network and their VPC by encrypting all traffic traversing the tunnel
* Enables seamless communication between a user's on-premises applications and services hosted on AWS by allowing users to configure route propagation to allow traffic between their on-premises network and resources in their VPC
* Supports high availability and redundancy
* Provides monitoring and management capabilities through the AWS Management Console, AWS CLI, and AWS CloudWatch

## AWS Client VPN

AWS Client VPN enables users to securely connect remote users or client devices to their AWS resources and services

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-04-22%20232123.png)

* Enables authorized users to securely connect to their VPC from remote locations
* Provides a secure communication channel over the internet
* Eliminates the need for the user to manage VPN servers or infrastructure by creating a managed VPN endpoint within the user's VPC infrastructure
* Acts as a gateway for remote clients to establish VPN connections to the user's VPC
* Supports multiple VPN protocols (Ex: *OpenVPN*, *IKEv2/IPSec*, *etc.*)
* Enables the user to remotely authenticate remote users using their existing credentials or certificates by supporting various authentication methods (Ex: *Active Directory Integration*, *AWS Directory Service*, *Mutual certificate authentication*, *etc.*)
* Enables users to define access control policies to either restrict or allow access to specific resources within their VPN based on user identities, groups, or attributes
* Allows users to track connection status, traffic volume, and client activity by providing monitoring and logging features for Client VPN connections
* Supports thousands of concurrent VPN connections and provides high availabiltiy and redundancy
