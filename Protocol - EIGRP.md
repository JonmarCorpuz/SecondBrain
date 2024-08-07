The Enhanced Interior Gateway Routing Protocol is an advanced distance-vector routing protocol that's used to dynamically determine the best path for data packets based on distance metrics

* Used on a network for automating routing decisions and configuration
* Reduces network traffic and speeds up convergence (the time it takes for all routers in the network to have a consistent view of the network) by sending updates only when there are changes in the network topology
* Prevents routing loops by employing various techinques (Ex: *Route poisoning*, *Split horizon*, *Holddown timers*, *etc.*)
* Provides more precise and efficient route selection based on current network conditions (Ex: *Bandwidth*, *Hop count*, *etc.*)
* Can enhance network performance by spreading traffic across several paths to avoid overloading any single route
* Can manage large routing tables and reduce the amount of routing information that must be processed and stored by routers by employing various features (Ex: *Route summarization*, *Route aggregation*, *etc.*)
* Sends messages using the 224.0.0.10 multicast address
* Can perform unequal-cost load-balancing (By default it performs ECMP load-balancing over 4 paths like RIP)
* Route ID priority starts with the manually configured IP address, the highest loopback interface address, and the the highest physical interface address

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Metric Calculation

The metric calculation in EIGRP considers the K-values used to calculate the best route

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/jhbfidbjfndngkdfnjsdfdfasd.png)

| K-Value | Description |
| --- | --- |
| K1. Bandwidth | The maximum rate of data transfer across a given path |
| K2. Delay | The time it takes for a packet to travel from the source to the destination |
| K3. Load | The current traffic usage on a link represented as a fraction of 255 (with 255 being 100% utilization) |
| K4. Reliability | The trustworthiness of a network link represented as a fraction of 255 (with 255 being 100% reliable) and is typically based on the historical stability of the link |
| K5. Maximum Transmission Unit | The largest size of IP packet or frame that can be sent over a network link without the need for fragmentation |

* The value of a K-value can be between 0 and 255 and independently set
* A K-value should be equal to zero (0) if it isn't considered in the metric calculation and one (1) if it is
* Neighboring devices must have matching K-values

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Routing Tables

| EIGRP Neighbor Table | Description |
| --- | --- |
| Neighbor Table | Contains information about directly connected neighbors |
| Topology Table | Contains all destinations advertised by neighboring routers, along with the metrics and paths to reach those destinations |
| Routing Table | Contains the best route to each destination in the network, which are selected from the topology table based on the path metrics |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Neighbor Relationship Formation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hbidhbdbhdbdsfnjadfnjafnjafnj.png)

| EIGRP Relationship Formation Step | Description |
| --- | --- |
| 1. Neighbor Discovery | EIGRP-capable routers send **Hello** packets to each other to initiate the discovery process |
| 2. Full Routing Information | The EIGRP-capable routers will exchange full routing information |
| 3. Acknowledgement | Each EIGRP-capable router will send an acknowledgement back to the other EIGRP-capable routers after receiving the full routing information |
| 4. Neighborship Established | The neighbor relationships between the EIGRP-capable routers are fully established |

## 1. Neighbor Discovery 

EIGRP-capable routers send **Hello** packets to each other to initiate the discovery process

* EIGRP-capable routers periodically send Hello packets to the multicast address 224.0.0.10 to discover and maintain neighbor relationships

## 2. Full Routing Information

After establishing initial contact through Hello packets, the EIGRP-capable routers will exchange full routing information

* Only routing table changes are sent to the neighboring devices after the full routing information has been exchanged between EIGRP-capable routers are exchanged in order to reduce bandwidth usage
* Exchanging routing information with other EIGRP-capable routers enable them to build a comprehensive view of the network topology

## 3. Acknowldgement

Each EIGRP-capable router will send an acknowledgement back to the other EIGRP-capable routers after receiving the full routing information

* Confirms that the routing information was received
* Ensures reliable communication between the routers

## 4. Neighorship Established

After the exchange of Hello packets, updates, and acknowledgements, the neighbor relationships between the EIGRP-capable routers are fully established

* Enables them to continue sharing routing information and maintaining updated and accurate routing tables as the network topology changes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# EIGRP Authentication
