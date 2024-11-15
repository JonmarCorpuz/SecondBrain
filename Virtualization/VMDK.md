# VMDK Overview

The [Virtual Machine Disk File](https://www.diskinternals.com/vmfs-recovery/vmdk-file-format/) is a container file format that stores the data of any virtual machine deployed on a VMware-owned environment (*VMware Workstation*, *VirtualBox*)

* Simulates physical hard drives in virtual environments
* Clones physical hard drives for virtual environments and acts as an "offsite" backup for the VMs hosted in the virtual environment
* Can get corrupted, damaged, or missing due to several possible reasons (*Human errors*, *Virus attacks*, *etc.*)
* Represented with the .vmdk extension and represents an independent VM

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# .vmdk File

## Text Descriptor File

The [text descriptor file](https://www.diskinternals.com/vmfs-recovery/vmdk-file-format/#:~:text=the%20descriptor%20file%20contains%20information%20about%20the%20VM%20IDs%2C%20structure%2C%20and%20other%20important%20information) contains information about a VM's virtual hard drive (*VM ID*, *VM structure*, *etc.*)

* If this file is not found, then the VMDK is considered damaged and you'll need to recover the descriptor file for the VMDK file to open the connected VM

## 

# *-flat.vmdk

* The virtual equivalent of a physical hard drive
* Where raw data is written to
* Combined with the descriptor file and presented as a single file (You won't find this file listed in your directory)
