The Open Shortest Path First protocol is a link state routing protocol, which is a protocol that determines the best route for data through a network, that's used within a single autonomous system

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/The-Role-of-the-Area-Border-Router-ABR.png)

* Maintains a map of the network and updates itself whenever any changes are made to the network topology
* Each router constructs a shortest path tree and computes the best path to each subnet
* Reduces the amount of routing information each router must maintain and the routing update traffic by allowing each OSPF networks to be divided into areas
* Can quickly adapt to network changes through rapid dissemination of state changes to all routers in the network
* Can scale to very large dynamic networks because updates are triggered by network changes rather than periodic updates
* Enables more efficient path selection by using cost as its routing metric that is based off of the consumed bandwidth of links
* Supports multiple equal-cost paths to a destination, which can be used simultaneously to improve network utilization
* Allows for the configuration of authentication to ensure that routing exchanges occur only between trusted routers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Components

## Router ID

A router ID is a unique identifier that's used to uniquely identify each router in an OSPF area

## Link State Advertisements

## Link State Database

## Areas

## Routing Table

## Intervals

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Types

## Flat-Area OSPF

## Multi-Area OSPF

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Area Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ospf-stub-areas.png)

## Backbone Area

## Stub Area

## Totally Stubby Area

## Not-So-Stubby Area

## Totally Not-So-Stubby Area
