A virtual machine instance is a virtualized computing environment that runs on a physical host machine

* Each VM instance is associated with a project within the GCP
* You can only edit a VM instance only when it's stopped
* VM instances are Zonal, meaning that they run in a specific zone within a specific region
* Automatic Basic Monitoring is enabled by default for each VM instance to monitor default metrics (Ex: *CPU utilization*, *Inbound and outbound network bytes*, *Disk throughput*, *etc.*)
* Requires the Compute Engine API to be enabled

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Instace Types 

| VM Instance Type | Description |
| --- | --- |
| Preempt | Short-lived cheaper VM instance for workloads that don't require continuous availability |
| Spot | Same as a preempt VM instance but without the maximum runtime |
| Regular | |

## Preempt VM Instances

A preempt VM is a short-lived cheaper VM instance for workloads that don't require continuous availability

* Lasts only 24 hours and can be reclaimed by GCP at any time
* Used if an application is fault tolerant and it's workload isn't immediate (Ex: *A batch program that should run within the next month*)
* Not always available
* No SLA and can't be migrated to regular VMs
* No automatic restarts

## Spot VM Instances

A spot VM is a cheaper VM instance for workloads that don't require continuous availability

* A latest version of preempt VM instances without the 24 hour runtime
* Used if an application is fault tolerant and it's workload isn't immediate (Ex: *A batch program that should run within the next month*)
* Not always available
* No SLA and can't be migrated to regular VMs
* No automatic restarts

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Instance Components

| VM Instance Component | Description | 
| --- | --- |
| Internal IP Address | Internal to a Google Cloud network |
| External IP Address | Internet addressable |

## Internal IP Address

* All VM instances are assigned at least one internal IP address
* Still assigned to a VM intance even after it's stopped

## External IP Address

* Lost when a VM instance is stopped unless it was assigned a static IP address (A static address should be in the same region as your VM instance and should be released when you're no longer using it since you're billed for a static IP address even when you're not using it)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Instance Templates

* Can't be modified once it's created (To make modifications, simply copy the existing template and modify it)
* A image family can be specified (The latest non-deprecated version of the family is used by default)
* Can be used to create VM instances in multiple different regions and zones

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

