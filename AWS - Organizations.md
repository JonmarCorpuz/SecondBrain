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

* Helps ensure that resources are tagged consistently across accounts
