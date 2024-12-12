# Cloud IAM Overview

Google's Cloud Identity and Access Management allows users to manage who has access to read and modify their GCP resources

* Enables customers to define fine-grained access controls on resources in the cloud
* Uses the concepts of users, roles, and permissions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP IAM Components

| GCP IAM Component | Description |
| --- | --- |
| Resource | |
| Member | |
| Permission | (Not directly assigned to a member) |
| Action | |
| Role | A set of permissions to perform specific actions on specific resources (Can have multiple permissions and can be assigned to multiple members) |
| Policy | A set of bindings that associate one or more members with a specific role |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP Members

* A member's type is identified using its prefix

## GCP Member Types

| GCP Member Type | Description |
| --- | --- |
| user | Represents a person |
| serviceaccount | Represents an application account |
| group | A collection of users and service accounts |
| domain | |

### Service Accounts

* Identified by an email address (Ex: *id-compute@developer.gserviceaccount.com*)
* Uses a private and a public RSA key-pair rather than a password
* Can't be logged in via browsers or cookies

| Service Account Type | Description |
| --- | --- |
| Default | |
| User Managed | |
| Google-Managed | |

#### Default Service Accounts

* Not recommended since it has the Editor role assigned to it by default

#### User Managed Service Accounts

* Provides fine grained access control

| User Managed Service Account Role Type | Description |
| --- | --- |
| Users | |
| Admins | |

#### Google-Managed Service Accounts

* Used by GCP to perform operations on a user's behalf

### Group

* Assigned a unique IP address

### Domain

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP IAM Roles

## GCP IAM Role Types

| GCP IAM Role Type | Description | 
| --- | --- |
| Basic/Primitive | A set of predefined roles that provide broad levels of access to resources within a project (*roles.viewer*, *roles.editor*, *roles.owner*)
| Predefined | Fine grained roles that are predefined and managed by Google (Ex: *Storage Admin*, *Storage Object Admin*, *Storage Object Viewer*, *etc.*) |
| Custom | Custom roles that are created by the client |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP IAM Policy

* Represented by a policy object
* Can be set on the resource level, project level, folder level, and organization level
* Policy inheritance is transitive (Resources inherit the policies of all its parents and you can't restrict an IAM policy at a lower level if it's given at a higher level)
* The effective policy for a resource is the union of the policy on that resource and its parents

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP Organization Policy

* Provides fine grained permissions about what can be done on specific resources
* Overrides IAM Policies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Good IAM Practices

| Good IAM Practices | Description |
| --- | --- |
| Principle of Least Privilege | Give the least possible privileges that are needed for a role by using either predefined roles or customized service accounts |
| Separation of Duties | Involve at least two people in sensitive tasks |
| Constant Monitoring | Review Cloud Audit Logs to audit changes to IAM policies and access to Service Account keys |

---

# Organizational IAM

* Cloud identities have super admins, which assign the role of Organization Administrator Identity and Access Management to users who manage the organization (Google Cloud will automatically grant Project Creator and Billing Account Creator IAM roles to all users in the domain)
* Users with the Organization Admin IAM role are responsible for defining the structure of the resource hierarchy, defining IAM policies over the resource hierarchy, and delegating other management role to other users
* When a member of a Cloud Identity account creates a billing account or project, Google Cloud will automatically create an organization resource 
* All projects within a billing account will be children of the organization resource













