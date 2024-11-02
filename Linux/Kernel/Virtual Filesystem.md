# Virtual Filesystem Overview

A virtual filesystem are filesystems where data's not stored on disk

* These directories look like directories with files but the content is dynamically generated when you look at it (Ex: *When you cat a proc file, some corresponding function in the kernel gets called to show you the results*)
* Generates up-to-date information about the kernel when called upon or accessed

# Virtual Filesystems

## proc

* Mounted on /proc at boot
* proc gets its name from "process"
* Contains a lot of information about the kernel (Ex: *Processes*, *etc.*)
* Some proc files are writable (*When writing to a proc file, some function in the kernel is called to take that value and do something with it*), which are called kernel turnable variables, but will get reset if the machine gets rebooted unless you make permanent changes
* Contains a directory for each process that's named with their PID, which contain information about its memory usage, what programs it's running, what files it has open, all the threads associated with it under the /task directory (In Linux, every process has at least one thread), etc.

## sysfs

* Mounted on /sys at boot
