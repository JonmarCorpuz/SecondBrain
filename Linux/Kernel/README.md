# Linux Kernel Overview

The Linux kernel is a program that's loaded and run by a boot loader (Ex: *GRUB*), which reads the kernel file from disk into memory and then transfers control to it

* Has command-line parameters and GRUB is responsible for passing those parameters to the kernel
* The Linux kernel has an API, which uses systems calls to call in functions from the user space
* Provides virtual filesystem entries (*proc*, *sys*, *debugfs*) that we can use to interact directly with the kernel, get information directly from the kernel. and change things in the kernel
* The kernel filesystem has device files, which allows us to interact with device drivers by doing operations (*Read*, *Write*,* Open*) on those device files
* A gatekeeper that enforces privileges (The capabilities of a process to see if it's allowed to perform some sort of privileged operation)
* Executes supervisor instructions (There are assembly language instructions that can only be executed by the kernel)
* Implements security policies (Ex: *The underlying mechanisms used by SELinux*)
* Provides controlled access to hardware and other resources to make sure things are done in an orderly and safe manner
* The Linux kernel is modular
* The kernel image is relatively small and sufficient to boot to user space to begin running some processes, and once we have processes, we can load additional functionality into the kernel through the loadable kernel module mechanism, which allows you to load the drivers you need and add other functionality that aren't driver related
