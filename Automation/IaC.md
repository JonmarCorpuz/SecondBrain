# IaC Overview

Infrastructure as Code is the automatic management and provisioning of computing infrastructure (*Networks*, *VMs*, *Load Balancers*, *etc.*) through code (*Scripts*, *Declarative definitions*, *etc.*) instead of through manual processes

* The code can be used to define a desired state for the infrastructure, acting as a bluepring for IaC tools to provision the infrastructure and ensure that the infrastructure is always in line with it
* Allows for infrastructure development to be a collaborative process and a shared responsibility, meaning that the knowledge of infrastructure and its configuration isn't kept to a single team member
* Reduces manual effort and risk of error
* Scalable, versionable, and repeatable

| IaC Feature | Description |
| --- | --- |
| Versionable | |
| Repeatable | |
| Infrastructure Automation | Allows the automation of the provisioning, configuring, reprovisioning and re-configuring of an infrastructure |
| Data Backup and Recovery | Allows the automation of backing up and recovering data through code that'll be triggered in the event of a disaster |
| Failover Automation | Allows the automation of the failover process through code |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IaC Benefits

## Better Cost Management 

* Resources, environments, and complex infrastructures can be easily created and destroyed
* Automation considerably frees up the time of developers and infrastructure maintainers
* Tagging strategies and requirements can be easily implemented across entire infrastructures
* It becomes much easier to obtain an overview of all resources created by a specific IaC project

## Improved Reliability 

* Well-developed IaC tools guarantee a consistent behavior and infrastructure
* IaC tools provide multiple ways of deploying configurations (Ex: *Locally*, *As part of a CI/CD pipeline*, *Triggered via API calls*, *etc.*)

## Improved consistency and scalability

* Infrastructure can be easily copied and deployed multiple times with the same structure
* Modules can be created and made publicly or privately available
* Different environments can be created based on the same configuration files
* Resources can automatically scale up or down when needed

## Improved Deployment Process 

* Prevents configuration drift by identifying and reverting unexpected changes
* Creating, updating, and destroying resources becomes fully integrated with other CI/CD tasks
* Changes to infrastructure are version controlled, being easier to revert in case of incompatibility or error

## Fewer human errors 

* The planning stage shows all the changes that are expected to be carried out, and can be inspected by the engineers
* Many IaC tools support validation and integrity checks with custom conditions
* Many IaC tools support protection rules against deletion of critical resources

## Improved security strategies 

* Validation and integrity checks can be used to ensure the infrastructure complies with security requirements
* Shared infrastructure modules are normally maintained by teams
* Security strategies can be configured via IaC tools (Ex: *IAM users*, *IAM roles*, *etc.*)
* The infrastructure configuration files can be inspected by security software for vulnerabilities

## Self documenting infrastructure 

* The created infrastructure is the infrastructure documented in the code
* Many IaC tools allow detailed inspection of the resources created
* Run logs are normally stored for a period of time, allowing inspection in case of any errors or unwanted changes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IaC Tools 

* Checks for changes
* Plans deployments
* Applies any modifications

## Declarative IaC Tools

Declarative IaC tools desribes what your infrastructure should look like rather than how to achieve it by defining the desired state of your infrastructure in a declarative manner

* Idempotent, meaning the same result will be achieved when run repeatedly since the check is done against a state file
* Ensures that your infrastructure consistently matches the declared state

| Declarative IaC Tool Component | Description |
| --- | --- |
| State File | Keeps track of the current state of the infrastructure defined by the IaC tool |

| Declarative IaC Tool | Description |
| --- | --- |
| Terraform | |
| AWS CloudFormation | |
| Pulumi | |

## Imperative IaC Tools

Imperative IaC tools describes how your infrastructure should set up or modified rather than what it should look like by allowing you to specify the commands or steps required to achieve a desired infrastructure state

* The user explicitly defines the sequence of operations needed to create or configure resources that the IaC tool will execure in specific order

## Agent-Based IaC Tools

## Agentless IaC Tools
