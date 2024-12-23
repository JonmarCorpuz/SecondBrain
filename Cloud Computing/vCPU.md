# vCPU Overview

A virtual Central Processing Unit is a software0based version of a CPU that's created and assigned to a VM or virtualization software by a hypervisor

* Represents a software implementation of a physical CPU that doesn't exist as a real CPU, but the OS sees it as a real one
* Each vCPU in a VM's OS represents one physical CPU core

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CPU Core

A CPU core is a processing unit within a computer's CPU that executes instructions and processes data

* The number of CPU cores determines how many tasks it can handle at once
* Can run multiple threads of code at the same time through multithreading

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Process

A process is an active program that's being executed

* Includes the program code, registers, process stack, and program counter
* Each process has its own isolated memory space that isn't shared with other processes
* Starts with a single thread (Primary thread) but can create more as well

## Processing Thread

A processing thread is a thread that runs within a process 

* One or more threads can run within the contaxt of that process

## Job Units

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Thread

A thread is a sequence of instructions that a CPU core executes within a process

* The basic unit to which the OS allocates processor time
* Each thread takes up less memory than a process because it only occupies one bit of memory space
* Can execute any part of the process code, including parts currently being executed by another thread

## Thread Pool

A thread pool is a collection of worker threads that efficiently execute asynchronous callbacks on behalf of the application

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
