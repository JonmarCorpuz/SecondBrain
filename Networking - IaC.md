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
| Configuration Consistency | Keeps infrastructure consistent and well-documented |
| Scaling Resources | Allows resources to automatically scale to handle increased workloads |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IaC Tools 

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
