# WLC Overview

* Can be located either inside the same subnet or VLAN as the APs it manages or outside
* Connected to the wired network via a trunk link
* Connects to a switch via a Link Aggregation Group (Only supports static LAG)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# WLC Components

| WLC Component | Description |
| --- | --- |
| WLC Ports | The physical ports that cables connect to |
| WLC Interfaces | The logical interfaces within the WLC |

## WLC Ports

| WLC Port | Description |
| --- | --- |
| Service Port | A dedicated management port |
| Distribution System Port | A standard network ports that connect to the distribution system (wired network) for data traffic |
| Console Port | A standard console port (RJ45 or USB) |
| Redundancy Port | Connects to another WLC to perform a HA pair |

### Service Port

* Used for out-of-band management
* Must connect to a switch access port because it only supports one VLAN
* Can be used to connect to the device while it's performing operations (Ex: *Booting*, *Performing system recovery*, *etc.*)

### Distribution System Port

* Usually connect to switch trunk ports
* Can form a LAG if multiple distribution ports are used

## WLC Interfaces

| WLC Interface | Description |
| --- | --- |
| Management Interface | Used for management traffic |
| Redundancy Management Interface | Used to connect to and manage the standby WLC |
| Virtual Interface | Used when communicating with wireless clients to forward traffic (Ex: *Relay DHCP requests*, *Perform client web authentication*, *etc.*) |
| Service Port Interface | Used for out-of-band management |
| Dynamic Interface | Used to map a WLAN to a VLAN

### Management Interface

* CAPWAP tunnels are formed to and from the WLC's management interface

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# WLC Deployment Types

| WLC Deployment Types | Description |
| --- | --- |
| Unified | The WLC is a hardware appliance in a central location of the network |
| Cloud-Based | The WLC is a VM running on a server, usually in a private cloud in a data center |
| Embedded | The WLC is integrated within a switch |
| Mobility Express | The WLC is integrated within an AP |

#### Unified WLC Deployment

The WLC is a hardware appliance in a central location of the network

* Can support up to about 6000 APs (If more than 6000 APs are needed, then additional WLCs can be added to the network)

#### Cloud-Based WLC Deployment

The WLC is a VM running on a server, usually in a private cloud in a data center

* Can support up to about 3000 APs (If more than 3000 APs are needed, then more WLC VMs can be deployed)

#### Embedded WLC Deployment

The WLC is integrated within a switch

* Can support up to 200 APs (If more than 200 APs are needed, then more switches with embedded WLCs can be added)

#### Mobility Express WLC Deployment

The WLC is integrated within an AP

* Can support up to 100 APs (If more than 100 APs are needed, more APs with embedded Mobility Express WLCs can be added)
