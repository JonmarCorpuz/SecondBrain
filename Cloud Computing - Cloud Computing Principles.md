Cloud computing is a paradigm shift in the way IT services are delivered and consumed

| Cloud Computing Principles | Description | 
| --- | --- |
| Resource Pooling | The process of allocating resources into a group (pool), which are then made available to multiple consumers by the hypervisor |
| Rapid Elasticity | The ability to quickly automatically provision computing resources as soon as it's needed or release them when they're no longer required |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Resource Pooling

Resource pooling is the process of allocating resources into a group (pool), which are then made available to multiple consumers by the hypervisor

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-01-15%20155723.png)

* The pooled resources (Ex: *RAM*, *Processors*, *Storage*, *etc.*) are dynamically allocated and reallocated to consumers on an as-needed basis
* Resource pooling hides the physical hardware from the VMs 
* Enables consumers to share resources (Ex: *Storage*, *Processes*, *RAM*, *Networks*, *etc.*) in order to pay for only what they need

## Types of Resource Pools

| Resource Pool Type | Description |
| --- | --- |
| Compute Pool | A shared pool of computing resources (*CPU*) |
| Memory Pool | A shared pool of system memory (*RAM*) |
| Network Pool | A shared pool of network resources and services (*Bandwidth*) |
| Storage Pool | A shared pool of external storage systems (*Storage Area Network*) |

### Compute Pools

A shared pool of computing resources (*CPU*)

#### CPU Affinity 

CPU affinity is the capacity of assigning a VM or a specific process running within a VM to a particular physical CPU or a set of CPUs instead of having the hypervisor dynamically assigning it one every time

* When a VM has CPU affinity enabled and a running process was already assigned to a CPU, when the hypervisor will receive the processing thread, it'll be assigned to the CPU it originally ran on
* Advantage: Can sometimes increase performance if remnants of the previous process are still in the CPU, enabling for efficiencies in cache hits (Data that's already present in the cache memory)
* Disadvantage: Can result in suboptimal allocation of compute resources (Ex: *A particular CPU assigned to a VM can have a very high utilization rate while another CPU might be sitting idle*, *etc.*)
* Hypervisor companies recommend to disable CPU affinity and allow the hypervisor to assign processing threads based on its knowledge of physical CPU utilization rates

### Memory Pools

A shared pool of system memory (*RAM*)

* When a VM's OS consumes all the memory available, it'll begin utilizing storage for its operations (Ex: *The swap file will be used in place of RAM*, *etc.*)
* When configuring a VM, it is important to consider that storage space must be allocated for the swap file and that the storage latency of the swap file will have a negative impact on the performance of the server

### Storage Pools

A shared pool of external storage systems (*Storage Area Network*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Rapid Elasticity

Rapid elasticity refers to the ability to quickly automatically provision computing resources as soon as it's needed or release them when they're no longer required

* Allows businesses to pay only for the resources that they need
* Ensures applications maintain optimal performance levels
* Improves user experience by minimizing latency and downtime since resources are always matched to the current demand

| Rapid Elasticity Types | Description |
| --- | --- |
| Horizontal Scaling | Involves adding or removing VM instances |
| Vertical Scaling | Involves increasing or decreasing the resources allocated to a single VM instance (Ex: *CPU*, *Memory*, *etc.*) |
