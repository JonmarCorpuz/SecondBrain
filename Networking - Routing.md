Routing is the process that routers use to determine the path that IP packets should take over a network to reach their destination

* Routers store routes for the destinations that they know in their routing table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Routing Table

A routing table is a data structure that contains routes to particular network destinations

* A router will use the more specific route that matches the packet's destination IP address (The more specific route = The matching route with the longuest prefix length)
* Each route in a routing table is an instruction (*To reach destinations in network X, send the packet to next-hop Y*)
* A router will drop a packet if it doesn't match any routes in its routing table

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Routing Methods

## Static Routing

## Dynamic Routing

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Route Types

| Route Symbol | Meaning |
| --- | --- |
| C | Connected route |
| L | Local route |

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
