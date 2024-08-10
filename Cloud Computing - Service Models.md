A cloud service model is a service model that offers a variety of different services through the cloud

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/f04ce2f08624ac4c7973ad4e6e6275cd.png)

# Cloud Computing Services

| Cloud Computing Service | Description |
| --- | --- |
| Infrastructure as a Service (IaaS) | |
| Platfrom as a Service (PaaS) | |
| Software as a Service (SaaS) | |
| Function as a Service (FaaS) | |
| Container as a Service (CaaS) | |
| Desktop as a Service (DaaS) | |

## IaaS

Infrastructure as a Service enables consumers to use virtualized computing resources offered by a CSP over the Internet (*Virtual machines*, *Data storage*, etc.) 

| IaaS Customer Responsibility | IaaS CSP Responsibility |
| --- | --- |
| Application Code | Virtualization |
| Application Runtime | Networking |
| Operating System | Physical Hardware |
| Load Balancing | Storage |
| Autoscaling | |
| Availability | |
| Patching | |

* Consumers don't manage or control the underlying cloud infrastructure but have control over the OS, middleware, runtime, data, and applications that they want to deploy
* Consumers can purchase a basic computing hardware platform and then build their solutions on top of that

## PaaS

Platform as a Service provides a platform created by a CSP that enables consumers to develop, run, and manage applications without dealing with the underlying infrastructure 

| PaaS Customer Responsibility | PaaS CSP Responsibility |
| --- | --- |
| Application Code | Application Runtime |
| | Operating System |
| | Virtualization |
| | Networking |
| | Physical Hardware |
| | Storage |
| | Autoscaling |
| | Availability | 
| | Load Balancing |

* Consumers don't manage or control the underlying cloud infrastructure but have control over the data and applications that they want to deploy
* Enables consumers to deploy onto the cloud infrastructure consumer-created or consumer-acquired applications that were created using programming languages and tools that are supported by the CSP
* Consumers can rapidly deploy their applications quickly without having to purchase and install their own servers and associated equipment

## Serverless 

Serverless infrastructure is a cloud computing model where the CSP dynamically manages the infrastructure and resources required to run code

* ALlows developers to focus on writing and deploying code without having to worry about managing servers or infrastructure
* Zero visibility into the network infrastructure (Ex: *Which server is running your application*, *etc.*)

### FaaS

Function as a Service allows developers to execute code in response events without the need to manage or provision servers

| FaaS Customer Responsibility | FaaS CSP Responsibility |
| --- | --- |
| Functions | Application Runtime |
| | Operating System |
| | Virtualization |
| | Networking |
| | Physical Hardware |
| | Storage |
| | Autoscaling |
| | Availability | 
| | Load Balancing |

### CaaS

Container as a Service provides users a platform for users to manage, deploy, and run containerized applications

| CaaS Customer Responsibility | CaaS CSP Responsibility |
| --- | --- |
| Containers | Application Runtime |
| | Operating System |
| | Virtualization |
| | Networking |
| | Physical Hardware |
| | Storage |
| | Autoscaling |
| | Availability | 
| | Load Balancing |

* Offers the ability to automatically scale containerized applications vertically based on demand

## SaaS

Software as a Service enables consumers to access software applications that are offered by a CSP via the cloud without having to host the software on their machines 

| SaaS Customer Responsibility | SaaS CSP Responsibility |
| --- | --- |

* Consumers don't manage or control the underlying cloud infrastructure
* The CSP has complete responsibility for the management and support of their applications
* All networking, processing, storage, and applications are offered as a service in this model

## XaaS

XaaS provides consumers access to any service

## DaaS

Desktop as a Service enables consumers to access virtual desktop environments over the Internet

* Provides consumers with a Virtual Desktop Infrastructure (VDI), where all of its applications are hosted in the cloud and can consist of any type of application
* DaaS CSPs manage all the maintenance and configurations as well as licensing and version updates
