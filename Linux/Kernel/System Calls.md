# System Call Overview

Systems calls are functions implemented by the kernel and meant to be called from user space

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-11-02%20071933.png)

* A system call is a way for user-space code to call a function in the kernel
* Applications call functions in libraries (*Std C Lib*), which some of them invoke kernel system calls
* System calls may interact with hardware (*An application may interact with a disk by performing read and write operations*)
* Located in /include
* Called through the standard library (*libc*, *etc.*)

# System Call Mechanics

* Standard library uses architecture-dependent means to invoke the system call mechanism
* Suited sized parameters are usually put in parameters
* When the kernel is invoked, it determines which system call that the user space is trying to call and calls it
* If an error occurs, the system calls return a negative value to the library (On error, the library sets "errno" to abs, and returns -1 back to the program), and when no error, library returns the value it obtained from the kernel
