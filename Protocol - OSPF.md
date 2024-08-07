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

## Router ID

A router ID is a unique identifier that's used to uniquely identify each router in an OSPF area

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Areas

An OSPF area is a set of routers and links that share the same LSDB

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ospf-stub-areas.png)

| OSPF Area | Description | 
| --- | --- |
| Backbone Area (Area 0) | An area that all other areas must connect to |
| Non-Backbone Area | |
| Stub Area | |
| Totally Stud Area | |
| Not-So-Stubby Area | |
| Totally Not-So-Stubby Area | |

* OSPF areas should be contiguous, meaning that each individual area should be connected and not divided up (Ex: *There shouldn't be two area 1s that aren't physically connected to each other*, *etc.*)
* All OSPF areas must have at least one ABR connected to the backbone area
* OSPF interfaces in the same subnet must be in the same area (If they aren't in the same area, they won't be able to become OSPF neighbors and won't exchange information about the networks they know about)

| OSPF Types | Description |
| --- | --- |
| Flat-Area OSPF | |
| Multi-Area OSPF | |

## Intra-area Route

An intra-area route is a route to a destination inside the same OSPF area

## Interarea Route

An interarea route is a route to a destination in a different OSPF area

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Router Types

| OSPF Router Type | Description | 
| --- | --- |
| Internal Routers | Routers that has all their interfaces in the same OSPF area | 
| Area Border Routers | Routers that has multiple interfaces in multiple OSPF areas (Maintain a separate LSDB for each area that they're connected to) | 
| Autonomous System Boundary Routers | Router that connects the OSPF network to an external network |
| Backbone Router | Routers that are connected to the backbone OSPF area |
| Designated Router | |
| Backup Designated Router | |
| Designated Router Other | |

## Designated Router

* The router with the highest OSPF interface priority in the subnet becomes the designated router (All interfaces have their priority set to 1 by default)
* If all interfaces have the same priority, the routers will then compare their OSPF router IDs and the router with the highest OSPF router ID will be elected as the designated router
* First place becomes the designated router and the second becomes the backup designated router
* If you manually set an OSPF interface priority to 0, the router can't be elected as the DR or BDR for the subnet
* If the DR election is non-preemptive, it means that once the DR is selected they'll keep their role until OSPF is reset or if the interface goes offline
* Uses the multicast address 224.0.0.6
* Forms full adjacencies with all the routers in the subnet

## Backup Designated Router

* In a non-preemptive DR and BDR election, when the DR goes down, the BDR becomes the new DR even if it doesn't have the highest interface priority or OSPF router ID, and then an election is held for the next BDR
* Uses the multicast address 224.0.0.6
* Forms full adjacencies with all the routers in the subnet

## Designated Router Other

* Remains in a 2-way state
* Only forms full adjacencies with the DR and BDR

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)


# OSPF Metric

| OSPF Metric | Description |
| --- | --- |
| Cost | The total cost of the bandwidth of the outgoing interfaces that's calculated by dividing the reference bandwidth with the interface bandwidth (**Reference bandwidth / Interface bandwidth**)

* OSPF's metric is called cost, which is the total cost of the bandwidth of the outgoing interfaces
* Automatically calculated based on the bandwidth of the interface and by dividing a reference bandwidth value, which is 100 by default, by the interface's bandwidth (Ex: *Reference 100 mbps / Interface 10 mbps = Cost of 10*)
* **Reference bandwidth / Interface bandwidth**
* The lowest cost is 1 (Values less than 1 are automatically converted to 1)
* The reference bandwidth should be greater than the fastest link in your network
* Loopback interfaces have a cost of 1
* It is recommended to change the reference bandwidth and then change the cost of individual interfaces
* FastEthernet, GigabitEthernet, and 10GigabitEthernet interfaces have the same cost

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Process

1. Become neighbors with other routers connected to the same segment
2. Exchange LSAs with neighbor routers
3. Calculate the best routes to each destination and insert them into the routing table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Messages

| OSPF Message | Purpose |
| --- | --- |
| Hello | Neighbor discovery and maintenance |
| Link-State Advertisement (LSA) | Exchanges information about the network topology |
| Database Description (DBD) | Contains a summary of a router's LSDB and checks if the LSDB of each router is the same |
| Link-State Request (LSR) | Requests specific LSAs from a neighbor router | 
| Link-State Update (LSU) | Sends specific LSAs to a neighbor router |
| Link-State Acknowledgement | Used to acknowledge that the router received a message |

## Hello 

* When OSPF is activated on an interface, the routers start sending OSPF Hello messages out of the interface at regular intervals, which are used to introduce the router to potential OSPF neighbors
* The timer interval is determined by the hello timer (10 seconds by default on an Ethernet connection)
* OSPF Hello messages check if a connected router is compatible to become an OSPF neighbor and then negotiate their neighbor relationship if it is
* Multicast to 224.0.0.5, which is the multicast address for all OSPF routers
* Encapsulated in an IP header, with a value of 89 in the Protocol field to indicate OSPF

## LSA

* Routers only exchange LSAs with the DR and BDR and not with DROthers, which reduces the amount of LSA flooding the network

### LSA Components

#### My Router ID

#### Neighbor Router ID

* The neighbor RID field is first 0.0.0.0 since it doesn't know the neighboring router's RID yet

### LSA Types

#### Type 1 (Router LSA)

* Every OSPF router generates this type of LSA
* Identifies the router using its RID
* Lists the networks that are attached to the router's OSPF-activated interfaces

#### Type 2 (Network LSA)

* Generated by the DR of each multi-access network (Ex: *Broadcast*, *etc.*)
* Lists the routers that are attached to the multi-access network

#### Type 3 

#### Type 4

#### Type 5 (AS External LSA)

* Generated by ASBRs to describe routes to destinations outside of the AS 

#### Type 6

#### Type 7

#### Type 8

#### Type 9

#### Type 10

#### Type 11

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Neighbor States

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fldkghklsjdfhgljdshfkjsdbfdkjfbsdljhflsdkfhlsd.jpg)

| OSPF Neighbor Process | Description |
| --- | --- |
| 1. Down State |   |
| 2. Init State |   |
| 3. 2-Way State |   |
| 4. Exstart State |   |
| 5. Exchange State |   |
| 6. Loading State |   |
| 7. Full State |   |

## Down State

* The router doesn't know about any OSPF neighbors yet

## Init State

* A router's Hello message was received but the router's own RID isn't in the Hello packet

## 2-Way State

* Means that the router has received a Hello packet with its own RID in it
* The router who received a Hello packet that didn't contain it's RID will send back a Hello message containing it's RID, the neighboring router that received that packet will send back a Hello packet but this time it'll contain its RID
* If two neighboring routers have reached the 2-way state, it means that all of the conditions have been met for them to become OSPF neighbors and that they're now ready to share LSAs to build a common LSDB

## Exstart State

* Two routers will now prepare to exchange information about their LSDB, but first they'll have to choose which one will become the master router in order to start the exchange with the slave router
* The master and slave router relationship is only needed for this initial exchange of LSDB information
* The router with the higher RID will become the Master and initiate the exchange, while the router with the lower RID will become the Slave

## Exchange State

* The routers will exchange Database Description packets, which are packets that contain a list of LSAs in their LSDB without any detailed information about the LSAs
* Both routers will compare the information in the DBD that they received from the neighboring router to their own LSDB to determine which LSAs they must receive from the neighbor
* Both routers move to the next state after exchanging DBDs

## Loading State

* Routers will send Link State Request messages to request that their neighbors send them any LSAs that they don't have (The missing LSAs are sent as Link State Update messages)
* The router receiving any missing LSAs will send LSAck messages back to the neighbor router to acknowledge that they received the LSAs
* Ensures that each router has the same LSAs

## Full State

* The routers have a full OSPF adjacency and identical LSDBs
* Neighboring routers will continue to send and listen for Hello packets to maintain the neighobr adjacency (They'll listen every 10 seconds by default)
* Every time a Hello packet is received, the Dead timer is reset and if the Dead time (40 seconds by default) counts down to 0 and no Hello message is received, the neighbor is removed, if the neighbor remains up then the neighbor routers will continue to share LSAs as the network changes to make sure that each router has a complete and accurate map of the network 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Types

## Flat-Area OSPF

* The bigger an OSPF area is, the more slower the performance (Ex: *More time is needed to calculate routes*, *More processing power is required*, *LSDBs will become larger and take up more memory on the routers*, *Any small changes in the network will cause every router to flood LSAs and run the SPF algorithm again*, *etc.*)
* Doesn't have to use area 0

## Multi-Area OSPF

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Versions

| OSPF Version | Description |
| --- | --- |
| OSPFv1 | (Old and no longer in use) |
| OSPFv2 | (Used for IPv4) |
| OSPFv3 | (Used for IPv4 and IPv6) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Network Types

* Not all network types work on all link types (Ex: *A serial link can't use the broadcast network type since serial links don't support Layer 2 broadcast frames*, *etc.*)

## Broadcast

* Enabled by default on Ethernet and Fiber Distributed Data Interfaces interfaces
* Routers dynamically discover neighbors by sending and listening for OSPF Hello messages using the 224.0.0.5 multicast address
* A designated router and backup designated router must be elected on each subnet (If there are no OSPF neighbors, then only a designated router is enough)
* Routers that aren't the designated router or backup designated router become a DROther
* Full adjacencies between routers are formed only with the DR and BDR routers
* Hello message intervals is 10 seconds by default
* Dead timer is 40 seconds by default

## Non-Broadcast

* Enabled by default on Frame Relay and X.25 interfaces
* Neighbors must be manually configured
* Hello message intervals is 30 seconds by default
* Dead timer is 120 seconds by default

## Point-to-Point

* Enabled by default on serial interfaces using the Point-to-Point Protocol and High-Level Data Link Control encapsulations, which are Layer 2 encapsulations that's similar to Ethernet but on serial connections
* Routers dynamically discover neighbors by sending and listening for OSPF Hell messages using the 224.0.0.5 multicast address
* There's no point in electing a DR and BDR since the encapsulations are used for point-to-point connections, allowing the two connected routers to form a full adjacency with each other without the need to elect a DR and BDR
* Hello message intervals is 10 seconds by default
* Dead timer is 40 seconds by default

## Point-to-Multipoint

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Neighbor Router Requirements

* Area number must match for two routers to become OSPF neighbors
* At least one interface on each neighboring router must be in the same subnet in order for them to become OSPF neighbors
* The OSPF process must not be shutdown (The OSPF process can be shutdown like an interface to disabled OSPF operations without removing the OSPF configurations)
* OSPF router IDs must be unique
* OSPF Hello and Dead timers must match
* Authentication settings must match (Ex: *Configured OSPF passwords*, *etc.*)
* IP MTU settings and OSPF network type must match (Even if the settings don't match, they can still become neighbors but OSPF won't function properly)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSPF Authentication
