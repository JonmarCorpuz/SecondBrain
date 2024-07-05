The Open Shortest Path First protocol is a link state routing protocol, which is a protocol that determines the best route for data through a network, that's used within a single autonomous system

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/The-Role-of-the-Area-Border-Router-ABR.png)

* Maintains a map of the network and updates itself whenever any changes are made to the network topology
* Each router constructs a shortest path tree and computes the best path to each subnet
* Reduces the amount of routing information each router must maintain and the routing update traffic by allowing each OSPF networks to be divided into areas
* Can quickly adapt to network changes through rapid dissemination of state changes to all routers in the network
* Enables more efficient path selection by using cost as its routing metric that's based off of the consumed bandwidth of links and calculated using the Shortest Path First algorithm (Dijkstra's algorithm)
* Supports multiple equal-cost paths to a destination, which can be used simultaneously to improve network utilization
* Allows for the configuration of authentication to ensure that routing exchanges occur only between trusted routers
* Routers will flood Link State Advertisements until all routers in the OSPF area have received it and developed the same Link State Database, which stores information about the network in Link State Advertisements (All routers share the same LSDB)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Components

## OSPF Process ID

* The OSPF process ID is locally significant, meaning that routers with different process IDs can become OSPF neighbors

## Link State Advertisements

* Each LSA has an aging timer (30 minutes by default)
* After the aging timer expires, each LSA will be flooded again to all routers in the OSPF area

## Link State Database

## Areas

An OSPF area is a set of routers and links that share the same LSDB

* OSPF areas should be contiguous, meaning that each individual area should be connected and not divided up (Ex: *There shouldn't be two area 1s that aren't physically connected to each other*, *etc.*)
* All OSPF areas must have at least one ABR connected to the backbone area
* OSPF interfaces in the same subnet must be in the same area (If they aren't in the same area, they won't become OSPF neighbors and won't exchange information about the networks they know about

### Backbone Area

The backbone area (Area 0) is an area that all other areas must connect to

### Intra-area Route

An intra-area route is a route to a destination inside the same OSPF area

### Interarea Route

An interarea route is a route to a destination in a different OSPF area

## Routers

### Router ID

A router ID is a unique identifier that's used to uniquely identify each router in an OSPF area

### Internal Routers

Internal routers are routers that has all their interfaces in the same OSPF area

### Area Border Routers

ABRs are routers that has multiple interfaces in multiple OSPF areas

* Maintain a separate LSDB for each area that they're connected to
* Connecting an ABR to more than two OSPF areas can overburden the router

### Autonomous System Boundary Router

An ASBR is an OSPF router that connects the OSPF network to an external network

### Backbone Routers

Backbone routers are routers that are connected to the backbone OSPF area

## Metric

* OSPF's metric is called cost, which is the total cost of the bandwidth of the outgoing interfaces
* Automatically calculated based on the bandwidth of the interface and by dividing a reference bandwidth value, which is 100 by default, by the interface's bandwidth (Ex: *Reference 100 mbps / Interface 10 mbps = Cost of 10*)
* **Reference bandwidth / Interface bandwidth**
* The lowest cost is 1 (Ex: *Reference 100 mbps / Interface 1000 mbps = Cost of 1*)
* The reference bandwidth should be greater than the fastest link in your network
* Loopback interfaces have a cost of 1
* It is recommended to change the reference bandwidth and then use the **ospf cost** command to change the cost of individual interfaces

## Intervals

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Process

1. Become neighbors with other routers connected to the same segment
2. Exchange LSAs with neighbor routers
3. Calculate the best routes to each destination and insert them into the routing table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Types

## Flat-Area OSPF

* The bigger an OSPF area is, the more slower the performance (Ex: *More time is needed to calculate routes*, *More processing power is required*, *LSDBs will become larger and take up more memory on the routers*, *Any small changes in the network will cause every router to flood LSAs and run the SPF algorithm again*, *etc.*)
* Doesn't have to use area 0

## Multi-Area OSPF

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Versions

## OSPFv1

## OSPFv2

* Old and no longer in use

* Used for IPv4

## OSPFv3

* Used for IPv4 and IPv6

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Area Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ospf-stub-areas.png)

## Backbone Area

## Stub Area

## Totally Stubby Area

## Not-So-Stubby Area

## Totally Not-So-Stubby Area
