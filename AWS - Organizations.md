Organizations is a service that helps users centrally manage and govern their environment across multiple AWS accounts

* Automtates IAM user and IAM group creations that can already have IAM policies applied to them
* Simplifies the payment process and enables better tracking of costs and usage across the entire organization by allowing them to receive a single invoice for all their accounts

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Organizations Components

## Organizational Units

An organization unit in AWS is a group of IAM users that are grouped together for administrative purposes

* Can represent different layers of a hierarchy (Ex: *Departments*, *Divisions*, *Geographical locations*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Organizations Features

## Multi-Account Strategies

A multi-account strategy is an account strategy that involves using multiple AWS accounts within an organization to segment different business units, projects, environments, or compliance requirements

* Limits the blast radius of security incidents by using separate accounts for different operations
* Makes it easier to track costs and usage per segment
* Allows organizations to scale operations more effectively by spreading resources across accounts
* Easier to manage and monitor resources
* Helps ensure compliance with different regulatory standards by allowing organizations to apply specific controls and audits per account that are tailored to meet certain compliance needs without affecting other segments

## Security Control Policies

A security control policy is a security control that offers centralized governance over permissions for all accounts within an organization

* Allows users to define and apply permissions policies across their organization or specific OUs

## Tag Policies

A tag policy is a set of rules that help manage tags across multiple AWS accounts within an organization, which are key-value pairs used to organize and identify resources within AWS

* Tag policies are first defined in the management account of the AWS Organization and then attached to OUs or individual accounts within the organization
* Improves resource management, cost tracking, and compliance within a organization by enforcing consistent tagging practices (Ex: *Standardized tag keys and values*, *etc.*)
* Can be applied to ensure that resources in member accounts use tags correctly according to the organization's standards
* Can be used to verify that existing tags meet a tag policy's requirements
* Allows AWS services and third-party tools to use the information from tag policies to automatically correct non-compliant tags

## Guardrails

Guardrails are high-level rules that provide governance and compliance controls for all the AWS accounts within an organization

* Helps ensure that accounts follow best practices and organizational policies, allowing them to better protect their data and resources across all their accounts, ensure that all their accounts adhere to the same set of rules and policies, and help standardize operations across all their accounts
* Can automate governance and ensure that organizations can maintain control over their AWS resources even as they scale 

### Preventive Guardrails

Preventive guardrails proactively prevent actions that don't comply with certain policies or best practices before they're executed

* Help maintain compliance and reduce risks by enforcing policies directly through AWS service permissions
* Often implemented with AWS Control Tower

### Detective Guardrails

Detective guardrails identifies and reports violations of specified policies or configurations after they occur

* Allow AWS services and operations but monitor their usage to ensure they meet compliance and governance standards
