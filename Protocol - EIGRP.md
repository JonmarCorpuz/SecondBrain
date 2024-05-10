The Enhanced Interior Gateway Routing Protocol is an advanced distance-vector routing protocol, which is a protocol that's used to determine the best path for data packets based on distance metrics, that's used on a network for automating routing decisions and configuration

* Reduces network traffic and speeds up convergence, which is the time it takes for all routers in the network to have a consistent view of the network, by sending updates only when there are changes in the network topology
* Prevents routing loops using techinques such as route poisoning, split horizon, and holddown timers
* Provides more precise and efficient route selection based on current network conditions (Ex: *Bandwidth*, *Hop count*, *etc.*)
* Can enhance network performance by spreading traffic across several paths to avoid overloading any single route
* Can manage large routing tables and reduce the amount of routing information that must be processed and stored by routers by supporting features such as route summarization and route aggregation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Path Metrics

## Bandwidth

Bandwidth refers to the maximum rate of data transfer across a given path

## Delay

Delay refers to the time it takes for a packet to travel from the source to the destination

## Load

The load refers to the current traffic usage on a link as a franction of the link's capacity 

## Reliability

Reliability refers to the trustworthiness of a network link based on the historical stability and error rate of the link

## Maximum Transmission Unit

MTU refers to the largest size of IP packet or frame that can be sent over a network link without the need for fragmentation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Routing Tables

## Neighbor Table

A neighbor EIGRP routing table stores information about directly connected neighbors

## Topology Table

A topology EIGRP routing table contains all destinations advertised by neighboring routers, along with the metrics and paths to reach those destinations

* Also stores the backup paths for different destinations

## Routing Table

The EIGRP routing table contains the best route to each destination in the network, which are selected from the topology table based on the path metrics

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Path Selection Process

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/02fig04_alt.jpg)

1. Neighbour discovery and maintenance
2. Exchange of routing information
3. Calculation of routes using the Diffusing Update Algorithm
4. Building the routing table
5. Handling topology changes
6. Metric calculation
