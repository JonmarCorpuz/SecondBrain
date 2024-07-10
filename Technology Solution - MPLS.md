The Multiprotocol Label Switching is a high-performance telecommunication network protocol that directs data from one network node to the next based on short path labels rather than long network addresses

* MPLS is technology that runs in a service provider's network
* A shared infrastructure because many customer enterprises connect to and share the same infrastructure to make WAN connections
* Provides the use of VPNs
* Many different type of connections can be used to connect to the service provider's MPLS network for WAN service (Ex: *Fiber optic ethernet*, *4G*, *5G*, *Cable TV*, *Leased lines*, *etc.*)

| MPLS Label | Meaning | Uses MPLS |
| --- | --- | --- |
| CE Router | Customer Edge Router | No |
| PE Router | Provider Edge Router | Yes |
| P Router | Provider Core Router | Yes |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# MLPS VPN Types

## Layer 2 MPLS VPN

* The CE and PE routers don't perform peering
* The SP network is entirely transparent to the CE routers, meaning that the CE routers will all act like they're all directly connected to each other and in the same subnet
* The CE routers can perform peering (Ex: *OSPF*, *etc.*)

## Layer 3 MPLS VPN

* The CE and PE routers perform peering (Ex: *OSPF*, *etc.*)
