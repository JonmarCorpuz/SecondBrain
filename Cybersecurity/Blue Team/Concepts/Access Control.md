# Access Control Overview

Access control is a security mechanism used to regulate and manage access to network resources and assets based on predefined policies and rules in order to ensure that only authorized individuals or entities are granted access to them

* Helps prevent unauthorized access or misuse to network resources or assets

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Access Control Methods

| Access Control Method | Meaning | Description |
| --- | --- | --- |
| PAC | Physical Access Control | |
| LAC | Logical Access Control | |
| NAC | Network Access Control | |
| MAC | Mandatory Access Control | |
| DAC | Discretionary Access Control | |
| RBAC | Role-Based Access Control | |
| ABAC | Attribute-Based Access Control | |
| CBAC | Context-Based Access Control | |

## Physical Access Control

Physical access control restricts entry to physical locations (Ex: *Locks*, *Keys*, *Access cards*, *Biometric scanners*, *etc.*) 

## Logical Access Control

LAC regulates access to digital resources using a various authentication, authorization, and encryption mechanisms in order to protect data and resources and ensure that only authorized users can access them and perform actions on them

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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/kokjojoojojohhohuouoorjhgoojgorjgorjgorgjrojg.png)

* Access is determined by the role a user is assigned rather than the individual themself
* Reduces the risk of unauthorized access by ensuring that users only have access to the resources that they need for their roles

## Attribute-Based Access Control

ABAC is a flexible access control model that evluates access decisions based on multiple attributes (Ex: *User attributes*, *Resource attributes*, *Environmental attributes*, *Contextual attributes*, *etc.*)

* User attributes include user roles, user department, user location, user clearance level, and user group membership
* Resource attributes include resource type, resource sensitivty, resource owner, resource location, and resource metadata
* Environmental attributes include date and time, network location, device information, and connection security
* Contextual attributes include session context, policy context, and external factors

## Context-Based Access Control

CBAC is a security mechanism that controls access to network resources based on contextual information (Ex: *Application protocol*, *Session state*, *User identity*, *Time of access*, *Source IP address*, *Destination IP address*, *Packet payload information*, *Packet header information*, *etc.*)

* Operates on the Network, Transport, and Application layers of the OSI model (Layers 3, 4, and 7)
* Performs deep packet inspection to analyze the contents of network packets at the Application layer
* Examines the payload of packets to identify the application protocols being used
* Allows administrators to define access control policies based on contextual information (Ex: *Application type*, *User identity*, *Time of access*, *Session state*, *etc.*)
* Maintains awareness of the state of network connections and sessions, allowing it to make access control decisions based on the context of each connection
* May generate real-time alerts and audit trails upon detecting suspicious activity using CBAC inspection rules

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Access Control Models

## AGDLP

The **Account, Global, Domain, Local, Permission** is an access control model that's used to organize, scale, and manage permissions effectively within Active Directory by structuring group membership in a way that simplifies access control and permission assignment across domains and forests

* **A**ccount refers to a user or group account
* **G**lobal refers to a global group that can contain user accounts, groups, or other global groups from any domain within a forest
* **D**omain local group refers to a group that can contain user accounts, global groups, or other domain local groups from any domain within a particular domain tree or forest
* **L**ocal group refers to a local groups that's used within a single domain
* **P**ermissions refer to the actual permissions that are assigned to the groups or accounts

## AGUDLP

The **Account, Global, Universal, Domain, Local, Permission**

* **A**ccount refers to a user or group account
* **G**lobal group refers to a global group that can contain user accounts, groups, or other global groups from any domain within a forest
* **U**niversal group refers to a group that can contain user accounts, global groups, and other universal groups from any domain within a forest
* **D**omain local group refers to a group that can contain user accounts, global groups, or other domain local groups from any domain within a particular domain tree or forest
* **L**ocal group refers to a local groups that's used within a single domain
* **P**ermissions refer to the actual permissions that are assigned to the groups or accounts

## AGLP

The **Account, Global, Local, Permission**

* **A**ccount refers to a user or group account
* **G**lobal group refers to a global group that can contain user accounts, groups, or other global groups from any domain within a forest
* **L**ocal group refers to a local groups that's used within a single domain
* **P**ermissions refer to the actual permissions that are assigned to the groups or accounts

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Access Control Lists

* Configured globally on a device and must be applied to an interface (Configuring an ACL in global configuration mode won't make the ACL take effect)
* Made up of one or more Access Control Entities
* The device will check the ACEs in the ACL from top to bottom and once it finds a match, it'll stop checking the other ACEs in the ACL and will take action based on the first matching ACE (All ACEs below the matching entry will be ignored)
* Applied to either inbound or outbound traffic depending on the interface that it was applied to
* A maximum of one ACL can be applied to one interface per direction
* If a packet doesn't match an ACE in the ACL, the device will implicitly deny and drop it (Implicit deny, which tells the device to deny and drop all traffic that doesn't match any of the configured ACEs in the ACL)

| Number Range | ACL Type |
| --- | --- |
| 1-99 and 1300-1999 | Standard ACLs |
| 100-199 and 2000-2699 | Extended ACLs |

## Standard Access Control Lists

* Matches traffic based on only the source IP address of the packet
* Each interface has an inbound and outbound traffic direction
* Should be applied as close to the destination as possible (Standard ACLs are less specific, so if they're applied close to the source there's a risk of blocking more traffic than intended)
* The network device may re-order the /32 ACEs to improve the efficiency of processing the ACL

### Standard Numbered Access Control Lists

* Identified with a number
* Different types of ACLs have a different range of numbers that can be used

### Standard Named Access Control Lists

* Identified with a name

## Extended Access Control Lists

* Matches traffic based on more parameters than the standard ACL, which makes them more precise (Ex: *Source IP address*, *Destination IP address*, *Source port number*, *Destination port number*, *Protocol*, *etc.*)
* Should be applied as close to the source as the source as possible in order to limit how far the packets travel in the network before being denied 

## Dynamic Access Control Lists

## Reflexive Access Control Lists

## Time-Based Access Control Lists

## TCP Established Access Control Lists

* Blocks or denies synchronization during connection establishment

