# RIP Overview

The Routing Information Protocol is a distance-vector routing protocol

* Helps routers dynamically exchange routing tables to determine the best path for data packets within a network
* Operates using the Bellman-Ford algorithm
* Uses hop count as its metric to determine the best route, which is the route with the less hops
* The maximum hop count is 15 (Anything more than that is considered unreachable)
* Slow convergence times and its metric is based solely on hops, which may not always reflect the best path in terms of latency or bandwidth
* RIP-enabled routers will share their routing table every 30 seconds

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# RIP Versions

## RIPv1

* Used for IPv4
* Only advertises classful addresses (Class A, Class B, and Class C)
* Doesn't support VLSM and CIDR
* Doesn't include subnet mask informationin advertisements
* Messages are broadcast to 255.255.255.255

## RIPv2

* Used for IPv4
* Supports VLSM and CIDR
* Inclydes subnet mask information in advertisements
* Messages are multicast to 224.0.0.9

## RIPng

* Used for IPv6

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# RIP Message Types

## Request

* Used to ask RIP-enabled neighbor routers to send their routing table

## Response

* Used to send the local router's routing table to neighboring routers
