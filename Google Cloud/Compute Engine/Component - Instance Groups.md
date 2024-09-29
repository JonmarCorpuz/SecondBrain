
# Managed Instance Group

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

# Unmanaged Instance Group

* Not all instances in the group are identical
* Customers manage the VMs themselves
