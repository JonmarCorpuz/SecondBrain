# Cloud IAM Overview

Google's Cloud Identity and Access Management allows users to manage who has access to read and modify their GCP resources

* Enables customers to define fine-grained access controls on resources in the cloud
* Uses the concepts of users, roles, and permissions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAM Components

| IAM Component | Description |
| --- | --- |
| Resource | |
| Member | |
| Permission | (Not directly assigned to a member but rather to roles, which are then assigned to users) |
| Action | |
| Role | A set of permissions to perform specific actions on specific resources (Can have multiple permissions and can be assigned to multiple members) |
| Policy | A set of bindings that associate one or more members with a specific role |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Members

* A member's type is identified using its prefix

## Service Accounts

* Identified by an email address (Ex: *id-compute@developer.gserviceaccount.com*)
* Uses a private and a public RSA key-pair rather than a password
* Can't be logged in via browsers or cookies
* Treated as an identity when assigned to a resource and treated as an object when given access to a user
* Created automatically when resources are created (Ex: *A service account will be created for a VM when the VM is created*)

| Service Account Type | Description |
| --- | --- |
| Default | |
| User Managed | |
| Google-Managed | |

### Default Service Accounts

* Not recommended since it has the Editor role assigned to it by default

### User Managed Service Accounts

* Provides fine grained access control

| User Managed Service Account Role Type | Description |
| --- | --- |
| Users | |
| Admins | |

### Google-Managed Service Accounts

* Used by GCP to perform operations on a user's behalf

## Group

* Assigned a unique IP address

## Domain

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAM Roles

* A role is a collection of permissions
* Granted to users by binding a user to a role

## Basic Roles

A set of predefined roles that provide broad levels of access to resources within a project (*roles.viewer*, *roles.editor*, *roles.owner*)

## Predefined Roles

Fine grained roles that are predefined and managed by Google (Ex: *Storage Admin*, *Storage Object Admin*, *Storage Object Viewer*, *etc.*) 

## Custom Roles

Custom roles that are created by the client 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IAM Policy

* Represented by a policy object
* Can be set on the resource level, project level, folder level, and organization level
* Policy inheritance is transitive (Resources inherit the policies of all its parents and you can't restrict an IAM policy at a lower level if it's given at a higher level)
* The effective policy for a resource is the union of the policy on that resource and its parents

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Organization Policy

* Provides fine grained permissions about what can be done on specific resources
* Overrides IAM Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Organizational IAM

* Cloud identities have super admins, which assign the role of Organization Administrator Identity and Access Management to users who manage the organization (Google Cloud will automatically grant Project Creator and Billing Account Creator IAM roles to all users in the domain)
* Users with the Organization Admin IAM role are responsible for defining the structure of the resource hierarchy, defining IAM policies over the resource hierarchy, and delegating other management role to other users
* When a member of a Cloud Identity account creates a billing account or project, Google Cloud will automatically create an organization resource 
* All projects within a billing account will be children of the organization resource

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Predefined Roles

## Billing 

* `Billing Account Creator` allows the user to create new self-service billing accounts
* `Billing Account Administrator` allows the user to manage billing accounts but cannot create them
* `Billing Account User` allows the user to link projects to billing accounts
* `Billing Account Viewer` allows the user to view billing account cost and transactions

## Compute Engine

* `Compute Admin` allows the user to have full control over Compute Engine instances
* `Compute Network Admin` allows the user to create, modify, and delete most networking resources while providing read-only access to firewall rules and SSL certifications
* `Compute Security Admin` allows the user to create, modify, and delete SSL certificates and firewall rules
* `Compute Viewer` allows the user to to list Compute Engine resources










