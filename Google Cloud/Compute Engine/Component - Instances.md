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

# Storage Options

| Storage Option | Description |
| --- | --- |
| Google Cloud Hyperdisk | |
| Hyperdisk Storage Pools | |
| Persistent Disk | |
| Local SSD Disk | |

## Google Cloud Hyperdisk

## Hyperdisk Storage Pools

## Persistent Disk

| Persistent Disk Types | Description |
| --- | --- |
| Balanced (pd-balanced) | |
| Performance (pd-ssd) | |
| Standard (pd-standard) | |
| Extremee (pd-extreme) | |

## Local SSD Disk
