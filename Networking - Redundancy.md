# Layer 2 Redundancy

## EtherChannels

# Layer 3 Redundancy

## EtherChannels

## First Hop Redundancy Protocols

A FHRP is a computer networking protocol that's designed to protect the default gateway used on a network by allowing two or more routers to provide backup for that address 

* In the event of a failure of an active router, the backup router will take over the address
* FHRP enabled routers will share a virtual Router IP address that the end devices on the network will use as their default gateway and a virtual MAC address that's generated for the virtual IP address and that devices will use to send packets to the default gateway (Each FHRP uses a different format for the virtual MAC)
* Non-preemptive by default, meaning that the current active router will not automatically give up its role, even if the former active router returns
* When a standby router becomes active, it'll broadcast a gratuitous ARP message so that all the switches in the network will update their MAC address tables (If the previous active router comes back online, by default it won't take back its role as the active router and will become a standby router instead)
