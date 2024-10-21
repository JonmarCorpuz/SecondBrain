# AWS Global Infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/lIc5YSi_SuCX4wI4pGNmsg_b3dde14493c846fdbd18a10956d6b3f1_AZs.png)

## Regions

Regions are geographic locations worldwide where the CSP hosts its data centers

* Named after the location where they reside (Ex: *Northern Virginia Region*, *Oregon Region*, *etc.*)
* Independent from one another, meaning that data isn't replicated from one Region to another without explicit consent and authorization
* AWS Region considerations include compliance (*If a company needs to comply with regulations that require customer data to be stored in a specific geographic territory, then they should choose a Region that meets their compliance requirements*, latency (*The delay or time lapse between the initiation of a process and its completion*), pricing (*Instead of charging a flat rate worldwide, AWS charges based on the financial factors specific to the location*), and service availability (*Some services may not be available in some Regions*)

## Availability Zones

An Availability Zone is a physical location of a data center within a region

* Consists of one or more data centers with redundant power, networking, and connectivity, which all operate in discrete facilities with undisclosed locations and are connected using redundant high-speed and low-latency links
* Inside every region is a cluster of AZs
* At a minimum, you should use two AZs so that if one entire AZ fails, your application will have infrastructure up and running in at least a second AZ to take over the traffic

## Data Center

A data center refers to a physical facility that houses the servers, storage devices, networking components, and other hardware necessary to run the various AWS services and support customer workload

