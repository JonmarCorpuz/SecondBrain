# Docker Networking Overview

| Docker Networking Type | Description |
| --- | --- |
| Bridge Network | The default network type for containers where each container on a bridge network gets an IP address from the pricate subnet of the bridge network |
| Host Network | A container shares the network stack of the host machine, meaning that it'll use the host's IP address and ports |
| None Network | Disables all networking for the container |
| Overlay Network | Allows containers running on different hosts to communicate with each other securely |
| MACVLAN Network | Allows you to assign a MAC address to each container, making them appear as physical devices on your network |
| IPVLAN Network | Allows containers to be directly exposed to the host's physical network |
| User-Defined Bridge Network | Allows containers to communicate with each other via container names, rather than IP addresses |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Bridge Network

* Allows containers to communicate with each other within the same network
* Acts like a switch that Docker containers will connect to
* Provides its own DHCP and DNS services
* Copies the host's /etc/resolv.conf file into the created containers to allow them to use the same DNS configurations
* Container ports need to be manually exposed to external networks
* Containers in the default network can't communicate with other docker networks by default (You can still ping container names by default since it still performs container to container DNS action)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
 
# Host Network

* There's no network isolation from the host
* Doesn't require you to manually expose any ports

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# None Network 

* The container has no network interfaces except for a loopback interface
* Completely isolates a container from any network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Overlay Network

* Used in a multi-host networking environment where services need to communicate across multipel hosts

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# MACVLAN Network

* Containers can communicate with each other, with the host, and with external networks as if they were physical machines while sharing the same physical port as the host machine
* Containers will receive their own MAC addresses and IP addresses on the host's network
* Promiscuous mode enabled on all devices (*Host*, *Switch*, *VM*, *etc.*) because some switches may not allow multiple MAC address on one switchport (Ex: *Port security*, *etc.*)
* Still provides hostname DNS resolution to allow containers ping other containers using their name
* Exposing ports isn't needed since each container will have their own IP address

| MACVLAN Mode | Description |
| --- | --- |
| Bridge | |
| 802.1q | (Requires trunking to be set up) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPVLAN Network

* Operates at Layer 3
* Used in environments where advanced IP addressing schemes are needed

| IPVLAN Mode | Description |
| --- | --- |
| L2 | (Shares the host's MAC address) |
| L3 | Containers connect to the host as if the host is a router and external traffic is controlled by routes (No more L2 operations, such as broadcast traffic, ARP, MAC addresses, BPDU traffic) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# User-Defined Bridge Network 

* Allows for better isolation and custom IP address ranges
* Useful for setting up isolate networks for different sets of containers on the same Docker host
* Containers in one Docker network can't communicate with other containers in other Docker networks by default (You can still ping container names by default since it still performs container to container DNS action)
