The Rapid per VLAN Spanning Tree (**802.1w**) is an evolution of the original STP that's designed to reduce the time required to converge on a loop-free topology in Ethernet networks

* Much faster at converging and adapting to network changes than 802.1D
* All VLANs share one STP instance
* Not a timer-based spanning tree algorithm like 802.1D, meaning that it offers an improvement over the 30 seconds or more that 802.1D takes to move a link to a Forwarding state
* Works on a bridge-bridge handshake mechanism, which allows ports to move directly to a Forwarding state
* Elects a root bridge with the same rules as STP
* Elects root ports with the same rules as STP
* Has STP's UplinkFast and Backbone Fast features built-in RSTP
* Compatible with STP, meaning that interfaces on a RSTP enabled switch that are connected to a STP enabled switch will operate in STP mode rather than RSTP

# RSTP Port States

| RSTP Port State | Stable/Transitional | Send BPDUs | Receive BPDUs | Frame Forwarding | MAC Address Learning |
| --- | --- | --- | --- | --- | --- |
| Discarding | Stable | NO | YES | NO | NO |
| Learning | Transitional | YES | YES | NO | YES |
| Forwarding | Stable | YES | YES | YES | YES |

* The Listening STP port state isn't used anymore

## Discaring 

* Combines the Blocking and Disabled STP port states into one
* Includes ports that were administratively shutdown and ports that are blocking traffic in order to prevent Layer 2 loops

## Learning

## Forwarding

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# RSTP Port Roles

## Root Port 

* The root port is the same as the root port in STP
* The port that's closest to the root bridge becomes the root port for the switch
* The only switch that doesn't have a root port is the root bridge

## Designated Port

* The designated port is the same as the designated port in STP
* There can only be one designated port per segment

## Non-Designated Port

* The non-designated port role is split into two separate roles in RSTP, which are the alternate port and backup port roles

### Alternate Port

The RSTP alternate port role is a discarding port that receives a superior BPDU from another switch and acts as a backup route to the route port

* If the root port fails, the switch can immediately move its best alternate port to a Forwarding state and make it the new root port without having it go through any transitional states

### Backup Port

The RSTP backup port role is a discarding port that receives a superior BPDU from another interface on the same switch, which only happens when two interfaces are connected to the same segment via a hub 

* Only used when on an interface that's connected to a hub
* If a switch's designated port fails, then the backup port will immediately become the designated port and begin forwarding traffic
* If a switch has multiple interfaces connected to a hub, the interface with the lowest port ID will be selected as the designated port while the rest will become backup ports

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# RSTP BPDU

* All switches originate and send their own BPDUs from their designated ports 

## Protocol Identifier

## Protocol Version

## BPDU Type

## BPDU Flags

## Root Identifier

## Root Path Cost

## Bridge Identifier

## Port Identifier

## Message Age

## Max Age

## Hello Time

## Forward Delay

## Version 1 Length
