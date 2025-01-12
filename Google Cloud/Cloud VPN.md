# Cloud VPN Overview

Google's Cloud VPN is a service that securely connects your on-premises network to your GCP VPC network through an IPsec VPN tunnel

# Cloud VPN Solutions

## HA VPN

* SLA of 99.99% service availability within a region
* Supports BGP
* HA is provided by using two tunnels instead of just one

## Classic VPN 

* SLA of 99.9% service availability with a single external IP address

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPN Routing 

## Active Routing 

Active routing involves the use of dynamic routing protocols 

* Routes are autmoatically updated and excahnged between the networks as changes occur (Ensures that all routing tables are consistently synchronized without manual intervention)
* Adjusts to network changes in real time (*New subnets*, *Network failures*, *etc.*)
* Supports automatic failover and can facilitate load balancing across multiple VPN tunnels

## Passive Routing

Passive routing involves manually setting up and maintaining static routes without the use of a routing protocol

* Routes must be manually configured and updated
* Can be suitable when routes don't change more frequently
* Can lead to potential issues in network availability and performance if not managed carefully

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPN Configuration

## Active/Active

In an Active/Active VPN setup, both VPN tunnels are in use simultaneously

* This configuration is designed for load balancing and high availability

## Passive/Active

In a Passive/Active VPN setup, one tunnel is actively used for traffic while the other remains idle as a standby or backup

* This configuration is designed primarily for failover rather than load balancing
* Depending on the configuration and the use of routing protocols, the switch from active to passive can be automatic or might require manual intervention
* Simpler and more cost-effective for smaller operations or where continuous load balacing is not necessary
