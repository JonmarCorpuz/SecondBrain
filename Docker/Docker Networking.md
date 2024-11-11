# Docker Networking Overview

* Containers in a Docker network receive a unique IP address, which allows all containers within the same network to communicate with each other
* We can assign names to containers and use them as aliases (This is best since IP addresses may change on container recreation and names are more stable)
* Containers can be connected to multiple networks and will receive a unique IP address per network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Network Drivers

## Bridge 

The bridge network driver creates a private network on the host machine where your containers can communicate with each other

* Suitable for most single-host scenarios

## Host

* Useful for maximum performance when strict isolation is not required

## None


## Overlay

* Essential for creating swarm clusters or distributed applications

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Bridged Network

* Containers in bridge networks can be made reachable from the host network by exposing ports
