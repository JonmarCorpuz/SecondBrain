Access control is a security mechanism used to regulate and manage access to network resources and assets based on predefined policies and rules in order to ensure that only authorized individuals or entities are granted access to them

* Helps prevent unauthorized access or misuse to network resources or assets

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Access Control Types

## Physical Access Control

Physical access control restricts entry to physical locations (Ex: *Locks*, *Keys*, *Access cards*, *Biometric scanners*, *etc.*) 

## Logical Access Control

Logical access control regulates access to digital resources using a various authentication, authorization, and encryption mechanisms in order to protect data and resources and ensure that only authorized users can access them and perform actions on them

* Uses various authentication mechanisms (Ex: *Passwords*, *Biometrics*, *Smart cards*, *etc.*)
* Uses various authorization mechanisms (Ex: *Access control lists*, *RBAC*, *etc.*)

## Network Access Control

NAC governs access to computer networks and resoures based on the identity and security posture of the devices seeking to connect

* Enforces security policies to ensure that only compliant and trusted devices are allowed to access the network

## Mandatory Access Control

MAC is a security model that enforces access control policies based on a system of security labels and access rules defined by a central authority

* A security label is a label that indicates a network resource or asset's sensitivity or classification level and is typically represented as security clearances, security classifications, or sensitivity levels
* Access rules are predefined rules that dictate which users or processes can access specific resources based on their security labels (Access decisions are made by comparing the security labels of the user and the requested resource against the access rules defined by the central authority)

## Discretionary Access Control

DAC is a security model that regulates access to resources based on the discretion of resource owners

* Resource owners have full control over who can access their resources and what level of access is granted
* Resource owners have the authority to set access permissions for that resource (Ex: *Read*, *Write*, *Execute*, *etc.*)

## Role-Based Access Control

RBAC is a policy-based access control model that assigns permissions to users based on their roles within an organization

* Access is determined by the role a user is assigned rather than the individual themself
* Reduces the risk of unauthorized access by ensuring that users only have access to the resources that they need for their roles

## Attribute-Mased Access Control

ABAC is a flexible access control model that evluates access decisions based on multiple attributes (Ex: *User attributes*, *Resource attributes*, *Environmental attributes*, *Contextual attributes*, *etc.*)

* User attributes include user roles, user department, user location, user clearance level, and user group membership
* Resource attributes include resource type, resource sensitivty, resource owner, resource location, and resource metadata
* Environmental attributes include date and time, network location, device information, and connection security
* Contextual attributes include session context, policy context, and external factors

## Context-Based Access Control

CBAC is a security mechanism that controls access to network resources based on contextual information (Ex: *Application protocol*, *Session state*, *User identity*, *Time of access*, *Source IP address*, *Destination IP address*, *Packet payload information*, *Packet header information*, *etc.*)

* Operates on the Network, Transport, and Application layers of the OSI model (Layer 2,3, and 7)
* Performs deep packet inspection to analyze the contents of network packets at the Application layer
* Examines the payload of packets to identify the application protocols being used
* Allows administrators to define access control policies based on contextual information (Ex: *Application type*, *User identity*, *Time of access*, *Session state*, *etc.*)
* Maintains awareness of the state of network connections and sessions, allowing it to make access control decisions based on the context of each connection
* May generate real-time alerts and audit trails upon detecting suspicious activity using CBAC inspection rules
