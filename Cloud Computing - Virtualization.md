Virtualization is technology that enables the creation of virtual versions of computing resources (Ex: *RAM*, *CPU*, *etc.*) in a virtual environment (*Virtual Machine*) by creating an abstraction layer over a device's hardware

* An abstraction layer allows a single device to be divided into multiple virtual machines (*VMs*)
* Virtualization enables the creation of virtualized resources (Ex: *RAM*, *CPU*, *etc.*) that are then consumed by a hypervisor for allocation to VMs 

# Virtualization Benefits

* Decreased expenses: Virtualization can decrease the number of hardware needed for a company's infrastructure
* Scalability: Virtualization makes scaling easier and can delegate a server's resources to VMs as needed based on usage
* Efficiency: Virtualization can make it easier to decrease the resources allocated to a virtual machine if there's reduced usage
* Maximizing resource utilization: VMs have access to the logical resources that were abstracted away from the physical resources and assigned to the virtual machine

# Hypervisors

A hypervisor, also known as a VMM (Virtual Machine Monitor) or virtualization engine, is a software or hardware component that enables the creation and management of VMs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ereytuyiytutyretrwerrqwewqewqrer.png)

* Its primary function is to create and manage virtual machines (Guest OS) on a physical host machine (Host OS), allowing them to behave independently and run their own OS and applications

### Type 1 Hypervisor

A Type 1 Hypervisor (Bare-metal) is a virtualization hypervisor that runs directly on the physical hardware of a host system (Ex: *VMWare ESXi*, *Proxmox*, *VMWare vSphere*, *Xen*, *KVM*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/10f4dce97b527ea3d144442b2190270c.png)

* The physical resources are pooled together and shared by the VMs that are running on the server
* Creates an abstraction layer directly between hardware and VMs without a common OS between them
* The hypervisor is the OS and often operates without a traditional GUI (Headless)
* Designed for scale and for deploying a large number of virtual machines at once
* Extremely lightweight to dedicate the most resources to virtual machines

### Type 2 Hypervisor

A Type 2 Hypervisor (Hosted) is a virtualization hypervisor that runs on top of a host OS (Ex: *VMWare Workstation*, *VMWare Fusion*, *VirtualBox*, *Parallels*, *QEMU*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/44d3a52445a0194a28eb710bf16f52d6.png)

* Creates an abstraction layer from a software application built on top of a pre-existing OS
* Often managed directly from the application through a GUI
* Often designed for end-users or individuals
* Not strictly designed to run a large number of virtual machines for scale

## Hypervisor Functions

### Memory Ballooning

Memory ballooning is a hypervisor function that efficiently allocates and manages memory resources among VMs on a host machine

* Allows hypervisors to reclaim unused memory from a VM that's running on top of the hypervisor and re-allocate that unused memory for others to use
* This is possible due to the fact that VMs think they're talking to the actual hardware in the chassis and not a piece of hypervisor software, enabling the hypervisor to take advantage of this by restricting what hardware resources each VM can access and balance those resources between the virtual machines running on top of the hypervisor

### Overcommitting

Overcommitting enables a hypervisor to allocate more virtual resources to VMs than the physical resources available on the underlying hardware

* Overcommitment includes:
	* RAM overcommitment
	* CPU overcommitment, also known as virtual CPU to physical CPU ratio (vCPU to pCPU ratio)

* This concept is based on the assumption that not all servers will use the memory assigned to them, resulting in the unused memory to be dynamically allocated to the other VMs that require additional resources for operations (Ex: *RAM*, *CPU*, *etc.*)
* Overcommitments are largely determined by the applications that are running on the VM (Ex: *If the CPUs are intensive, then a low ratio may be required*, *If the applications aren't CPU bound and present a light load on the physical CPUs, then a higher overcommitment ratio can be implemented*, *etc.*)
* By overcommitting physical resources to the virtual services, the allocation and usage of the physical resources can be maximized, resulting in a lower cost of operations
* When there's resource contention, a VM may be paused from accessing the CPU in order to allow other VMs equitable access to the CPU

### Hyper-Threading

Hyper-threading enables a single physical processor core to appear as two logical processes, allowing it to execute multiple threads concurrently

* Each logical processor is referred to as a virtual core
* Each core can be started, stopped, and controlled independently from the other
* HT is transparent to the OS or hypervisor that's accessing the CPU, meaning that the VMs will see two cores when in reality there's only one
* HT is only possible when the hypervisor or OS supports symmetrical multiprocessing, which is where two or more identical processors can be connected to a single shared main memory and are capable of processing tasks concurrently

