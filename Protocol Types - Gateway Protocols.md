A gateway protocol is a type of networking protocol that's used by routers or gateways to exchange routing information between different autonomous systems

* Enables routers to make informed decisions about how to forward data packets to their destinations across interconnected networks

# Gateway Protocol Components

## Autonomous Systems

An autonomous system is a network or group of networks under a common administrative control and sharing a common routing policy, which is a set of rules or configurations that govern how routers make decisions about forwarding data packets

* Each AS is assinged a Autonomous System Number by the Internet Assigned Numbers Authority, making it globally unique
* The ASN is used by the BGP protocol to identify and distinguish between autonomous systems on the internet
* Autonomous systems use Interior Gateway Protocols to exchange routing information within their own networks and Exterior Gateway Protocols to exchange routing information with other autonomous systems

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Gateway Protocol Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/IGP_EGP.jpg)

## Interior Gateway Protocols

An Interior Gateway Protocol is a type of routing protocol that's used within a single autonomous system to exchange routing information between routers

### Open Shortest Path First

The OSPF protocol is a link state routing protocol, which is a protocol that determines the best route for data through a network, within a single autonomous system

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/The-Role-of-the-Area-Border-Router-ABR.png)

### Enhanced Interior Gateway Routing Protocol

The EIGRP protocol is an advanced distance-vector routing protocol, which is a protocol that's used to determine the best path for data packets based on distance metrics, that's used on a network for automating routing decisions and configuration

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Exterior Gateway Protocols

An Exterior Gateway Protocol is a type of routing protocol that's used to exchange routing information between routers in different autonomous systems or administrative domains

### Border Gateway Protocol

The Border Gateway Protocol is an exterior gateway protocol used in large-scale networks to enable the exchange of routing and reachability information between autonomous systems
