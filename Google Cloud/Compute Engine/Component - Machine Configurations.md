
* Machine name looks like `<MACHINE_TYPE_FAMILY>-<WORKLOAD_TYPE>-<NUMBER_OF_CPU>` (Ex: *e2-standard-4*)

# Machine Family

A machine family is a curated set of VM configurations that are optimized for specific workloads

| Machine Family | Description |
| --- | --- |
| General Purpose | Provides a balanced mix of compute, memory, and network resources |
| Compute-Optimized | Provides high compute performance per core for compute-intensive workloads |
| Memory-Optimized | Provides large amounts of memory for memory-intensive workloads |
| Storage-Optimized | Provides alrge amounts of storage for workloads that are low in core usage and high in storage density |
| Accelerator-Optimized | Provides GPU acceleration for workloads that require GPUs |

* Machine families are classified by series, generation, and processor type
* Each machine family have a set of characteristics that are tailored to certain performance needs
* Each machine family offers various machine types

# Machine Type

A machine type is a set of specific predefined or customized configuration of VM resources

* Machine type availability can vary from region to region
* The more vCPU a machine has, the more memory and networking capabilities it has

| Machine Type | Description |
| --- | --- |
| Predefined | A non-configurable predefined configuration of instance resources |
| Custom | A custom configuration of instance resources |

## Predefined Machine Type

| Predefined Machine Type | vCPU to memory ratio |
| --- | --- |
| highcpu | 1 to 3 GB memory per vCPU |
| standard | 3 to 7 GB memory per vCPU |
| highmem | 7 to 14 GB memory per vCPU |
| megamem | 14 to 19 GB memory per vCPU |
| hypermem | 19 to 24 memory per vCPU |
| ultramem | 24 to 31 GB per vCPU |
