# VRRP Overview

The Virtual Router Redundancy Protocol is an open standard First Hot Redundancy protocol used to provide high availability and failover capability for routers on a LAN

* 224.0.0.18 multicast address
* 0000.5e00.01XX virtual MAC address where XX is the VRRP group number
* Allows users to configure a different master router in each subnet or VLAN to load balance

# VRRP Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/667919245926862848.png)

## Virtual Router

The virtual router is a logical entity created by VRRP that represents a group of routers that are working together to provide redundancy and failover capabilities

* Identified by its own IP and MAC addresses

## Master Router

The master router is the active router within the VRRP group

* Forwards traffic to the virtual router
* Responsible for sending periodic advertisement messages to inform other routers of its status

## Backup Router

The backup router is a standby router within the VRRP group

* Monitors the health of the master router by receiving and processing advertisement messages

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Router Priority

Each router within a VRRP group are assigned a priority value, which determines its eligibility to become the master router

* The highest priority becomes the master router

# How VRRP Works

1. **Router Election**: Routers within a VRRP group will elect one router as the master and the others as backups (If multiple routers have the same priority, the router with the highest IP address is elected as the master)

2. **Advertisement Messages**: The master router will periodically send VRRP advertisement messages to inform the backup routers of its status and the health of the virtual router

3. **Backup Router Monitoring**: The backup routers will continuously monitor the health of the master router by receiving and processing advertisement messages (If a backup router detects that the master router is no longer sending advertisement messages, it assumes that the master router has failed)

4. **Master Router Failover**: When a backup router detects that the master router has failed, it initiates a failover process by having the next appropriate backup router to take over the role of the master router

5. **Preemption**: When the failed master router recovers and rejoins the VRRP group, it may attempt to reclaim its roles as the master router if it has a higher priority than the current master

6. **Continuous Monitoring**: The routers within the VRRP group will continue to exchange advertisement messages to monitor the health and status of the master router
