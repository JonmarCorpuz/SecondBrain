Google's Cloud Identity and Access Management allows users to manage who has access to read and modify their GCP resources

* Provides very granular control

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

| GCP Member Type | Description |
| --- | --- |
| user | |
| serviceaccount | |
| group | |
| domain | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP IAM Roles

| GCP IAM Role Type | Description | 
| --- | --- |
| Basic/Primitive | A set of predefined roles that provide broad levels of access to resources within a project (*roles.viewer*, *roles.editor*, *roles.owner*)
| Predefined | Fine grained roles that are predefined and managed by Google (Ex: *Storage Admin*, *Storage Object Admin*, *Storage Object Viewer*, *etc.*) |
| Custom | Custom roles that are created by the client |

| Role Launch Stage | Description |
| --- | --- |
| Alpha | |
| Beta | |
| General Availability | |
| Disabled | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GCP IAM Policy

* Represented by a policy object
