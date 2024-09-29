# Instances

A virtual machine instance is a virtualized computing environment that runs on a physical host machine

* Can be edited only when stopped
* Each instance runs in a specific zone (Zonal)

## Instance Types

| Instance Type | Description |
| --- | --- |
| Preemptible | Short-lived cheaper VM instance for workloads that don't require continuous availability | 
| Spot | Same as a preempt instance but without the maximum 24 hour runtime |
| Standard | A regular VM instance |

### Preemptible Instances

A preempt instance is a short-lived VM instance that's used for workloads that don't require continuous availability

* Has a maximum runtime of 24 hours
* Can be reclaimed by GCP at any time
* No Service Level Agreement
* No automatic restarts
* No migrating to regular instances

### Spot Instances

A spot instance is the same as a preempt instance but without the 24 hour maximum runtime

* No Service Level Agreement
* No automatic restarts

### Standard Instances

# Instance Template

* Can't be modified once it's created
* Specifies which network and subnet that the created instances will be created in

## Regional Instance Template

* Can only be used in the region it's in
* Reduces cross-region dependency
* Allows you to meet compliance requirements on the physical location of the data

## Global Instance Template

* Can be used in any region

# Instance Group

## Managed Instance Group

* Each instance in the group is identical and created using the same template
* Provides automatic scalability, availability, and autohealing
* Provides the ability to deploy rolling updates and canary updates
* Supports stateful workloads
* Has some limitations (https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#limitations)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-09-29%20122816.png)

| MIG Deployment Type | Description |
| --- | --- |
| Zonal MIG | Deploys instances to a single zone |
| Regional MIG | Deploys instances to multiple zones across the same region |

| MIG Type | Description |
| --- | --- |
| Stateless MIG | |
| Stateful MIG | |

| MIG Update Type | Description |
| --- | --- |
| Rolling Update | |
| Rolling Restart/Replace | |
| Canary Deployment | |

| MIG Use Case Example |
| --- |
| Stateless serving workloads (Ex: *Website frontend*, *etc.*) |
| Stateless batch, high-performance, or high-throughput compute workloads (Ex: *Image processing from a queue*, *etc.*) |
| Stateful applications (Ex: *Databases*, *legacy applications*, *long-running batch computations with checkpointing*, *etc.*) |

## Unmanaged Instance Group

* Not all instances in the group are identical
* Customers manage the VMs themselves

# Instance Storage



# Sources

Instance Groups:
* https://cloud.google.com/compute/docs/instance-groups
