The Enhanced Interior Gateway Routing Protocol is an advanced distance-vector routing protocol that's used to dynamically determine the best path for data packets based on distance metrics

* Used on a network for automating routing decisions and configuration
* Reduces network traffic and speeds up convergence (the time it takes for all routers in the network to have a consistent view of the network) by sending updates only when there are changes in the network topology
* Prevents routing loops by employing various techinques (Ex: *Route poisoning*, *Split horizon*, *Holddown timers*, *etc.*)
* Provides more precise and efficient route selection based on current network conditions (Ex: *Bandwidth*, *Hop count*, *etc.*)
* Can enhance network performance by spreading traffic across several paths to avoid overloading any single route
* Can manage large routing tables and reduce the amount of routing information that must be processed and stored by routers by employing various features (Ex: *Route summarization*, *Route aggregation*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Metric Calculation

The metric calculation in EIGRP considers the K-values used to calculate the best route

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/jhbfidbjfndngkdfnjsdfdfasd.png)

* The K-value can be between 0 and 255 and independently set
* A K-value should be equal to zero (0) if it isn't considered in the metric calculation and one (1) if it is
* Neighboring devices must have matching K-values

## K1. Bandwidth

Bandwidth refers to the maximum rate of data transfer across a given path

## K2. Delay

Delay refers to the time it takes for a packet to travel from the source to the destination

## K3. Load

The load refers to the current traffic usage on a link

* Represented as a fraction of 255 (with 255 being 100% utilization)
* A dynamic metric that can change over time as traffic conditions change

## K4. Reliability

Reliability refers to the trustworthiness of a network link

* Represented as a fraction of 255 (with 255 being 100% reliable)
* Typically based on the historical stability and error rate of the link

## K5. Maximum Transmission Unit

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
