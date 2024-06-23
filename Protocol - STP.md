The Spanning Tree Protocol (IEEE 802.1D) is a network protocol that ensures a loop-free topology in Ethernet networks by placing redundant ports in a blocking state

* Operates at the Data Link Layer of the OSI model (Layer 2)
* STP is run by default on network switches
* Ports in a blocking state act as backups that can enter a forwarding state if an active interface fails

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ihbjgudfafdgbhjaobjodfsggdasfhjbnou.jpg)

## BPDU

A Bridge Protocol Data Unit is a frame used in STP implementations to prevent loops in Ethernet networks

* Used by switches running STP to exchange information with each other, as well as update and maintain the STP topology
* STP-enabled switches send and receive **Hello BPDUs** out of all interfaces every two seconds and if a switch receives a **Hello BPDU** on an interface, then it'll know that that interface is connected to another switch

## Root Bridge

The root bridge is the reference point for all spanning tree calculations within a network of interconnected switches

* The switch with the lowest Bridge ID becomes the root bridge

### Bridge ID

A Bridge ID (BID) is a unique identifier assigned to each switch in a Spanning Tree Protocol network

* Each switch in the network will advertise its own BID, which consists of a bridge priority and its MAC address
* When switches receive BID information from neighboring switches, they'll compare the received BIDs with their own and the switch with the lowest BID is elected as the root bridge

#### Bridge Priority

The Bridge Priority is a configurable value assigned to each switch

* Set to 32768 by default but can be manually adjusted
* Lower priority values indicate a higher priority for becoming the root bridge

#### MAC Address

The MAC address is a switch's unique physical address

* In the event that multiple switches have the same bridge priority, the switch with the lowest MAC address among them will be selected as the root bridge

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Designated Port

A designated port is the port that's selected to forward traffic on a specific network segment

* Each switch in a STP network must have only one designated port, which will be responsible for forwarding traffic towards the root bridge
* The designated port is the port with the lowest cost to reach the root bridge
* If multiple ports on a switch offer the same shortest path to the root bridge, the one with the lowest port number will be the one that'll be selected as the designated port
* Designated ports will be placed in a fowarding state in order to allow traffic to pass through

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Blocked Port

A blocked port is a switch port that's put into a blocking state to prevent loops in the STP network topology

* Remains in a listening and learning state, ready to become active if the active path fails
* Blocked ports don't forward traffic but are actively monitoring the network for any changes in the topology and can only send or receive BPDUs
* Serves as backup links in case the active path fails

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Root Port

The root port is the port on a non-root switch that provides the shortest path to the root bridge within the STP network

* The root port is calculated based on its path cost to reach the root switch, which is based on the cumulative cost of all the links between the non-root switch and the root switch, and determined by the speed of the link (faster links have lower costs)
* The root port is placed in a forwarding state to allow traffic to pass through

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How STP Works

1. **Root bridge election**, which is the reference point for all spanning tree calculations to determine the shortest path to all other switches in the network
2. **Determination of root ports and designated ports**, which is done after the root bridge has been elected and is where non-root switches will select a root port
3. **Blocking redundant paths**, which is where STP will identify and block redundant paths in the network to prevent loops
4. **Dynamic reconfiguration**, which is when STP will dynamically reconfigure the network topology in resonse to changes by recalculating the spanning tree to ensure that there are no loops and that traffic can still flow through the network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Types

## STP (802.1D)

## RSTP (802.1w)

## MSTP (802.1s)

## PVST+

## RPVST+

