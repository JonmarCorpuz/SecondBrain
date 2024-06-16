A Palo Alto firewall are firewalls that are developed and manufactured by Palo Alto Networks

* Enforces security policies from top to bottom (**Security overruling**)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PA Firewall Interface Types

## Management Interfaces

* Management Profiles should only have access to this interface

## Network Interfaces

## VLAN Interfaces

## Layer 2 Interfaces

## Layer 3 Interfaces

* Every layer 3 interface must be assigned to a virtual router so that it can forward traffic to other interfaces

## Tap Interfaces

## Loopback Interfaces

## Tunnel Interfaces

* Can be assigned as a layer 2 or layer 3 interface 

## V-Wire Interface

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fdertetretwetrtrtwrterreryttytrytryetwtertwrtwfgdhdfghdf.png)

* Logically connects two physical interfaces
* No routing happens on v-wire interfaces
* Allocated to a physical interface
* Allows the firewall to work and enforce security rules in transparent mode, which makes it so that a user or network doesn't know that they're passing through a stateful firewall

## HA Interfaces

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PA NGFW Firewall Features

## Antivirus

* Palo Alto Wildfire

## Anti-Spyware

## URL Filtering

## DoS Protection

## High Availability Cluster

* Active-Standby, only one PA will forward traffic while the other PA will standby in case the active-primary goes down (Everything that's done on the active unit will be synced to the standby unit, meaning that the standby PA will have a copy of what the active PA was doing)
* Active-Active, all PA will forward traffic at the same time in order to provide load balancing (Needs a configured virtual IP)
* Heartbeat information (Everything in the active firewall will be mirrored to the standby firewall, so make sure that the standby firewall is connected to the same networks as the active firewall via the same ports)

## Virtual Firewalls

* Virtual firewalls inside our physical appliance

## Virtual Routers

* Enables organizations to seperate routing instances (Ex: *Virtual router for inside routing*, *Virtual router for outside routing*, *etc.*)

## VPN Tunneling

* Site-to-site IPsec tunnels

## GlobalProtect
