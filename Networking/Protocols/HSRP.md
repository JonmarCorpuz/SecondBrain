The Hot Standby Router Protocol is a Cisco proprietary First Hop Redundancy Protocol that allows for the configuration of a group of routers that'll work together in order to provide redundancy and high availability

* Allows users to configure a different active router in each subnet or VLAN to load balance
* All routers in the group have to use the same version of HSRP since both versions aren't compatible with one another

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# HSRP Components

## 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# HSRP Versions

## HSRPv1

* 224.0.0.2 multicast address
* 0000.0c07.acXX virtual MAC address where XX is the HSRP group number

## HSRPv2

* Supports IPv6 and increases the number of groups that can be configured
* Uses the 224.0.0.102 multicast address
* 0000.0c9f.fXXX virtual MAC address where XXX is the HSRP group number
