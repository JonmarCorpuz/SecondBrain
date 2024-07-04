Routing is the process that routers use to determine the path that IP packets should take over a network to reach their destination

* Routers store routes for the destinations that they know in their routing table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Routing Table

A routing table is a data structure that contains routes to particular network destinations

* A router will use the more specific route that matches the packet's destination IP address (The more specific route = The matching route with the longuest prefix length)
* Each route in a routing table is an instruction (*To reach destinations in network X, send the packet to next-hop Y*)
* A router will drop a packet if it doesn't match any routes in its routing table

## Administrative Distance

* Used to determine which routing protocol is preferred
* A lower AD is preferred and indicates that the routing protocol is considered more trustworthy

| AD | Route type |
| --- | --- |
| 0 | Directly Connected |
| 1 | Static Route |
| 20 | External BGP |
| 90 | EIGRP |
| 100 | IGRP |
| 110 | OSPF |
| 115 | IS-IS |
| 120 | RIP |
| 170 | External EIGRP | 
| 200 | Internal BGP |
| 255 | Unusable Route (The router doesn't believe the source of that route and doesn't install it in the routing table) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Routing Methods

## Static Routing

* The routing table isn't automatically updated (If an interface goes down, the route will still remain in the routing table)

## Floating Static Route


## Dynamic Routing

* Routers form adjacencies with adjacent routers to advertise and exchange information about the routes they know to other routers and vice-versa
* If multiple routes to a destination are learned, the router will determine which route is superior and will add it to the routing table (The superior route is the one with the lower metric)
* The routing table is automatically updated (If an interface goes down, the router removes the route from the routing table and replaces it with the next best route if there's one)
* Metrics are used to compare routes that are learned via the same routing protocol

### Interior Gateway Protocol

An IGP is a type of dynamic routing protocol that's used to share routes within a single autonomous system (Ex: *OSPF*, *EIGRP*)

| IGP Algorithm Type | Description | Protocols |
| --- | --- | --- |
| Distance Vector |   | RIP, EIGRP |
| Link State |   | OSPF, IS-IS |

| IGP Protocol | Metric | Description |
| --- | --- | --- |
| RIP | Hop count | Each router in the path counts as one hop and the total metric is the total number of hops to the destination |
| EIGRP | Metric based on bandwidth and delay |  |
| OSPF | Cost | The cost of each link is calculated based on bandwidth and the total metric is the total cost of each link in the route |
| IS-IS | Cost | The total metric is the total cost of each link in the route (All links have a cost of 10 by default and aren't calculated based on bandwidth) |

#### Distance Vector Protocols

* Operate by sending the known destination networks and their metric to reach them to their directly connected neighbors (Shares their routing table with them)
* Route sharing method is called "routing by rumor" because a router doesn't know about the networks beyond their neighbors, they only know the information that their neighbors tell them
* The routers only learn the distance (metric) and vector (direction) of each route

#### Link State Protocols

* Every router will create a connectivity map of the network by advertising information about their interfaces to its neighbors, which are then passed along to other routers, until all routers in the network develop the same map of the network
* After every router has developed the same connectivitiy map of the network, they'll use it to calculate the best routes to each network it knowns about
* Uses more resources (CPU) on the router because more information is shared
* Tend to be faster in reacting to changes in the network
* The router's route table will contain the best route to each destination network it knows about
* The route with the lowest metric is considered as the best route (If a router learns two or more routes via the same routing protocol to the same destination with the same metric, both will be added to the routing table and the traffic will be load-balanced over both routes, which is known as **Equal Cost Multi-Path Load Balancing**)

### Exterior Gateway Protocol

An EGP is a type of dynamic routing protocol that's used to share routes between different autonomous systems (Ex: *BGP*)

| EGP Algorithm Type | Description | Protocols |
| --- | --- | --- |
| Path Vector |   | BGP |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Route Types

| Route Symbol | Meaning |
| --- | --- |
| C | Connected route |
| L | Local route |
| O | OSPF Dynamic route |
| D | EIGRP route |

## Connected Route 

A connected route is a route to the network that an interface is physically connected to

* Automatically added to the routing table when an IP address is configured to an interface

## Local Route 

A local route is a route to the exact IP address that's configured on one of the device's interfaces

* Automatically added to the routing table when an IP address is configured to an interface
* Tells the router that the packets received using this route is destined for the router itself and that it should receive it for itself

## Default Route

The default route is the least specific route possible that includes all IP addresses 

* The default route is **0.0.0.0 0.0.0.0**, which includes all address from 0.0.0.0 to 255.255.255.255

## Static Route
