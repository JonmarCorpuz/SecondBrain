# Containerization Overview

Containerization is a software deployment process that bundles an application's code with all the files and dependencies it needs to run on any infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-10-29%20181015.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Containers

A container is a software package that contains only the necessary code and dependencies to execute a particular application

* Portable and can be deployed on multiple OS environments
* Provides a consistent environment
* Lightweight software components that run efficiently and can be quickly launched since it doesn't need to boot an OS (Container images don't contain an OS)
* Uses less memory and fewer resources
* All containers on the same host uses computing resources from the same shared OS but each container are isolated and won't interfere with the operations of other containers
* Provides better resource control
* Provides process-level isolation since all containers on the same machine all share their host's OS kernel
* Can't be modified during its lifetime in order to make containers more secure by ensuring consistency across multiple components (Users must create a new container image and redeploy it if a container needs to be updated)

## Container Engine

* All containers run within a container engine
* Containers are less isolated compared to VMs since the container engine runs directly on the host OS

## Microservices

A microservice is an independent and isolated component of an application that's running within a container

* Microservices can be modified without interfering with the OS, hardware, or other application services 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
