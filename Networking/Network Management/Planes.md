# Planes Overview

A plane refers to different functional layers or aspects of a system

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Plane Types

## Data Plane

* Involves all the tasks that forwards user data and traffic from one interface to another

## Control Plane

* Controls what the data plane does (Ex: *Building the router's routing table*, *etc.*)
* Performs overhead work
* Usually managed by the CPU

### Southbound Interface

* Used for communications between the controller and the network devices it controls
* Typically consists of a communication protocol and API
* Using the SBI, the controller communicates with the managed devices and gathers information about them (Ex: *The devices in the network*, *How the devices are connected together*, *The available interfaces on each device*, *The configuration for each device*, *etc.*)

### Northbound Interface

* The NBI is what allows us to interact with the controller, access the data it gathers about the network, program it, and make changes in the network via th SBI
* Northbound APIs allow apps to access information in a format that's easy for programs to understand

## Management Plane

* Performs overhead work
* Consists of protocols that are used to manage devices
* Usually managed by the CPU

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
