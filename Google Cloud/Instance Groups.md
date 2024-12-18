# Instance Group Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-09-29%20122816.png)

# Managed Instance Group

* Each instance in the group is identical and created using the same template
* Provides automatic scalability, availability, and autohealing
* Provides the ability to deploy rolling updates and canary updates
* Supports stateful workloads
* Has some limitations (https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#limitations)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-09-29%20122816.png)

| MIG Use Case Example |
| --- |
| Stateless serving workloads (Ex: *Website frontend*, *etc.*) |
| Stateless batch, high-performance, or high-throughput compute workloads (Ex: *Image processing from a queue*, *etc.*) |
| Stateful applications (Ex: *Databases*, *legacy applications*, *long-running batch computations with checkpointing*, *etc.*) |

## Stateless MIG

## Stateful MIG

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Unmanaged Instance Group

* Not all instances in the group are identical
* Customers manage the VMs themselves
* Used when customers need to work with different configurations within different VMs in the group

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Instance Group Deployment Methods

## Zonal

Deploys instances to a single zone

## Regional

Deploys instances to across multiple zones within the same region

* Increases resiliency by spreading the workload across multiple zones

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Instance Group Update Methods

## Rolling Update

## Rolling Restart/Replace

## Canary Deployment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Instance Group Policies

## Distribution Policy

* `Even` deploys managed instances even across zones
* `Any` deploys managed instances to zones based on availability and reservations
