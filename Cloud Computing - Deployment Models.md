# Cloud Deployment Models

Cloud deployment models help differentiate between cloud offerings in the marketplace

## Private Cloud

The <mark style="background: #ADCCFFA6;">Private Cloud</mark> deployment model is a cloud service that's dedicated to <mark style="background: #C9E2EEA6;">a single consumer</mark> 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-01-15%20151350.png)

## Public Cloud

The <mark style="background: #ADCCFFA6;">Public Cloud</mark> deployment model is a cloud service that's <mark style="background: #C9E2EEA6;">used and shared among multiple consumers</mark> 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-01-15%20151214.png)

## Hybrid Cloud

The <mark style="background: #ADCCFFA6;">Hybrid Cloud</mark> deployment model is a cloud service that <mark style="background: #C9E2EEA6;">combines public cloud services and private cloud services for different resources</mark> 

* Can include a combination of a CSP's services and an organization's on-premise resources
* Organizations can use hybrid cloud environments to reduce their costs and maintain some control over network resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-01-15%20151826.png)

## Community Cloud

The Community Cloud deployment model is a cloud service that's shared among organizations with common interests, requirements, or compliance needs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-01-15%20151711.png)

# Cloud Deployment Elements

## Migration Timelines

* Timelines must be established for the migration to the cloud
* Most migrations will be better served if performed incrementally in order to reduce the risk of an outage or having to back out the migration because of unforeseen issues
* Migration onto the cloud will usually take place during a maintenance window, which is a scheduled time that maintenance can be performed and outages are planned for ongoing support of operations (*There must be time for testing and validation after the migration where all stakeholders can test and verify that the systems are working as planned after the migration*, *etc.*)
* Time must be allocated in the even that a back-out is required and that the original site or installation must come back online*, *
* It's best to begin an organization's migration onto the cloud with small, easy-to-implement, non-critical systems as candidates to migrate to the cloud

## Documentation

* All systems should be accurately diagrammed and configurations should be saved in a file separate from the systems being migrated
* Complete and accurate documentation needs to be created and maintained for the migration to the cloud and the ongoing support of the cloud deployment
* Shows what security devices will be used and where they are to be placed in the network
* Network planning and documentation should start early in the cloud rollout process and be performed in collaboration with the CSP in order to allow for the correct selection and procurement of all needed networking hardware and software
* Includes detailed explanations and topologies of the network (Ex: *The numbering of all interfaces and their associated IP subnets and VLANs*, *VPN links*, *Routing tables*, *ACLs*, *The connection to the CSP's network*, *Links to the corporate office and all data centers*, *etc.*)
* Includes the routing, redundancy, and security protocols to be used (Ex: *VLANs*, *STP*, *VXLAN*, *etc.*)
* Includes configuration scripts, which are useful for initial installation and for ongoing maintenance and troubleshooting
* Includes sections on the access and distribution networks in the cloud (Ex: *A network management section that provides a map for the network operations center and illustrates how the network management systems are connected to the network and what devices they're monitoring*, *etc.*)
* Includes benchmarking, which is taking sample performance metrics that need to be collected as part of the documentation process, which will enable an organization to measure performance and identify potential issues when performing post-migration validations (Ex: *CPU usage*, *Memory utilization*, *Storage consumption*, *Database I/O performance*, *Network bandwidth consumed*, *etc.*)

## Service Level Agreement (SLA)

A service level agreement is a formal contract or agreement between a CSP and a customer that outlines the specific terms, conditions, expectations, and penalties regarding the level of service and performance the customer can expect

* Essential for establishing a clear understanding of the services that are being provided, the responsibilities of both parties, and the metrics used to measure and ensure the quality of service

