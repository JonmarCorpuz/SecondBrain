# PA Firewall Overview

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
* The configuration from the active firewall will sync with the standby firewall, allowing it to have the same exact configurations as the active firewall (I think)
* Active-active requires another HA interface to be configured in order to do a VR sync, as well as a virtual IP for the inside interface and the outside interface
* In active-active, you can't have a single NAT statement that can be duplicated across two files
* Virtual IP on outside interface
* Active/Active NAT HA binding
* Both firewalls must be the same model

## Virtual Firewalls

* Virtual firewalls inside our physical appliance
* Isolate policies between tenants
* Virtual system 1 is the default virtual system

## Virtual Routers

* Enables organizations to seperate routing instances (Ex: *Virtual router for inside routing*, *Virtual router for outside routing*, *etc.*)

## VPN Tunneling

### Site-to-site IPsec tunnels

### GlobalProtect VPN

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# PA Firewall Management

## PAN-OS Version Types

* Don't ever go from one version to another without updating into the base version for the release that you want to upgrade to
* Always backup the configuration file of a PA firewall before upgrading to the next base version

### Base

### Maintenance

* Two options: GlobalProtect portal and GlobalProtect gateway
* GlobalProtect Portal prerequisites:
  1. Create a VPN User and VPN Users Group
  2. Create an Authentication Profile
  3. Create a Certificate Signing Request (CSR) or self-signed certificate
  4. Create a SSL/TLS Service Profile that we'll point the certificate to
  5. Configure and Enable the GlobalProtect Portal
 
* Snapshots
* Format disks
* Repair partitions
