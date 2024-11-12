# Maximum Transmission Unit Overview

The [Maximum Transmission Unit](https://www.cloudflare.com/en-gb/learning/network-layer/what-is-mtu/) (MTU) is a measurement representing the largest data packet that a network-connected device will accept

# Path MTU Discovery

The [Path Maximum Transmission Discovery Unit]() (PMTU) is a standardized technique in computer networking for determining the MTU size on the network path between two IP hosts, usually with the goal of avoiding IP fragmentation

* Works by setting the Don't Fragment (DF) flag in the IP headers of outgoing packets
* Any device along the path whose MTU is smaller than the packet will drop it and send back an ICMP Fragemntation Needed (Type 3, Code 4) message containing its MTU, allowing the host to reduce its path MTU appropriately (This process is repeated until the MTU is small enough to traverse the entire path without fragmentation)
