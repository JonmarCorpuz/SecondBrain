The Spanning Tree Protocol (IEEE 802.1D) is a network protocol that ensures a loop-free topology in Ethernet networks by placing redundant ports in a blocking state

* Operates at the Data Link Layer of the OSI model (Layer 2)
* STP is run by default on network switches
* Ports in a blocking state act as backups that can enter a forwarding state if an active interface fails

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP BPDU

A Bridge Protocol Data Unit is a frame used in STP implementations to prevent loops in Ethernet networks

* Used by switches running STP to exchange information with each other, as well as update and maintain the STP topology
* STP-enabled switches send and receive **Hello BPDUs** out of all interfaces every two seconds and if a switch receives a **Hello BPDU** on an interface, then it'll know that that interface is connected to another switch
* Only forwarded to Designated ports

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Root Bridge

The root bridge is the reference point for all spanning tree calculations within a network of interconnected switches

* The switch with the lowest Bridge ID becomes the root bridge
* All ports on the root bridge are designated ports that are put in a forwarding state, while the other switches in the topology must have a path to reach the root bridge
* A root bridge only gives up its position if it receives a BPDU that contains a lower bridge ID than its own bridge ID
* once all switches in the topology agree on the root bridge, only the root bridge will be able to generate BPDUs, while the other switches may only forward them

## Bridge ID

A Bridge ID (BID) is a unique identifier assigned to each switch in a Spanning Tree Protocol network

* Each switch in the network will advertise its own BID, which consists of a bridge priority and its MAC address
* When switches receive BID information from neighboring switches, they'll compare the received BIDs with their own and the switch with the lowest BID is elected as the root bridge

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fdlshjfgsfkjgskdgfhksflghskdlgsdfjkgsdfgsdf.jpg)

### Bridge Priority

The Bridge Priority is a configurable value assigned to each switch

* Set to 32768 by default but can be manually adjusted
* Lower priority values indicate a higher priority for becoming the root bridge
* The Bridge Priority can only be changed in units of 4096 and the Extended System ID will then be added to this number to make the total bridge priority

### Extended System ID

The Extended System ID refers to the VLAN ID

* Used in STP's PVST, which runs a separate STP instance in each VLAN, allowing each VLAN to have different forwarding and blocking interfaces

### MAC Address

The MAC address is a switch's unique physical address

* In the event that multiple switches have the same bridge priority, the switch with the lowest MAC address among them will be selected as the root bridge

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Ports

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ihbjgudfafdgbhjaobjodfsggdasfhjbnou.jpg)

## Designated Port

A designated port is the port that's selected to forward traffic on a specific network segment

* Each switch in a STP network must have only one designated port, which will be responsible for forwarding traffic towards the root bridge
* The designated port is the port with the lowest cost to reach the root bridge
* If multiple ports on a switch offer the same shortest path to the root bridge, the one with the lowest port number will be the one that'll be selected as the designated port
* Designated ports will be placed in a fowarding state in order to allow traffic to pass through
* This is the only port that a switch will forward STP BPDUs to

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Blocked Port

A blocked port is a switch port that's put into a blocking state to prevent loops in the STP network topology

* Remains in a listening and learning state, ready to become active if the active path fails
* Blocked ports don't forward traffic but are actively monitoring the network for any changes in the topology and can only send or receive BPDUs
* Serves as backup links in case the active path fails

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Root Port

The root port is the port on a non-root switch that provides the shortest path to the root bridge within the STP network

* The root port is placed in a forwarding state to allow traffic to pass through
* If multiple ports have the same lowest root cost, then the port connection to th neighboring switch with the lowest Bridge ID will become the root port, and if this still results in the same path cost, then the port connected to a neighboring port that has the lowest STP port ID will be elected as the root port and is calculated using the following: STP Port ID = Port Priority (128 by default) + Port Number

### Root Cost

* The root port is calculated based on its path cost to reach the root switch, which is based on the cumulative cost of all the links between the non-root switch and the root switch, and determined by the speed of the link (faster links have lower costs)
* The cost only counts the cost of the outgoing interface (If the other end of the link is the destination interface, then the cost for that link would be 0)

| Link Speed | STP Cost |
| --- | --- |
| 10 Mbps | 100 |
| 100 Mbps | 19 |
| 1 Gbps | 4 |
| 10 Gbps | 2 |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Port States

| STP Port State | Stable/Transitional | Send BPDUs | Receive BPDUs | Frame Forwarding | MAC Address Learning |
| --- | --- | --- | --- | --- | --- |
| **Forwarding** | Stable | YES | YES | YES | YES |
| **Listening** | Transitional | YES | YES | NO | NO |
| **Learning** | Transition | YES | YES | NO | YES |
| **Blocking** | Stable | NO | YES | NO | NO |
| **Disabled** | Unavailable | NO | NO | NO | NO |

## Forwarding

* Root and Designated ports remain stable in a Forwarding state
* Forwards and receives STP BPDUs
* Sends and receives normal traffic
* Learns MAC addresses from the frames that arrive on the interface

## Listening 

* A transitional state that's passed through when an interface is activated or when a blocking port must transition to a Forwarding state
* Interfaces with the Designated or Root role are the only ones that can go into a Listening state
* 15 seconds long by default and can be determined by the Forward delay timer, which is also used for ports in a Learning state
* Only forwards and receives STP BPDUs
* Doesn't send or receive regular traffic
* Doesn't learn MAC addresses from regular traffic that arrive on the interface

## Learning

* A transitional state that's passed through when an interface is activated or when a blocking port must transition to a Forwarding state
* Interfaces with the Designated or Root role are the only ones that can go into a Learning state
* 15 seconds long by default and can be determined by the Forward delay timer, which is also used for ports in a Listening state
* Only forwards and receives STP BPDUs
* Doesn't send or receive regular traffic
* Learns the MAC addresses from regular traffic that arrive on the interface since the port is preparing to start forwarding traffic and to do so it needs to start building its MAC address table beforehand

## Blocking

* Non-designated ports remain stable in a Blocking state
* Disabled to prevent loops
* Doesn't send or receive regular network traffic but can receive and process STP BPDUs to be aware of the Spanning Tree topology and be ready to transition towards a forwarding state if they need to
* Doesn't forward STP BPDUs
* Doesn't learn MAC addresses

## Disabled

* Administratively disabled

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How STP Works

1. The switch with the lowest Bridge ID will be elected as the root bridge and will make all of its ports as a designated port, which will all be put in a forwarding state
2. Each remaining switch in the topology will select the port with the lowest root cost to the root bridge and make it their root port, which will be put in a forwarding state
3. Each non-root bridge will elect only one designated port, which is the port that'll be put into a forwarding state in order to forward BPDUs, and the assign the other ports into a non-designated port, which will put into a blocking state

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Timers

| STP Timer | Purpose | Duration |
| --- | --- | --- |
| **Hello** | How often the root bridge sends Hello BPDUs | 2 seconds |
| **Forward Delay** | How long the switch will stay in the Listening and then the Learning state | 15 seconds per state |
| **Max Age** | How long an interface will wait after ceasing to receive Hello BPDUs to change the STP topology (Resets every time it receives a Hello BPDU) | 20 seconds (10 Hello BPDUs) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# STP Types

## STP (802.1D)

## RSTP (802.1w)

## MSTP (802.1s)

## PVST+

## RPVST+

