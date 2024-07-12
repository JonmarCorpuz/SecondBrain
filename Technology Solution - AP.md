
* The functions of an AP can be split between an AP and a WLC

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AP Types

## Wireless Lan Controller

* Can be located either inside the same subnet or VLAN as the APs it manages or outside
* Connected to the wired network via a trunk link

### WLC Deployment Types

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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AP Deployment Methods

## Autonomous

Autonomous APs are self-contained systems that don't rely on a Wireless LAN Controller  

* Configured individually via a CLI or web GUI
* An IP address for remote management should be configured on the AP
* RF parameters must be manually configured per AP (Ex: *How much power it should use to transmit*, *Which channel it should use*, *etc.*)
* Security policies are handled individually by each AP (Ex: *ACLs*, *etc.*)
* There's no central monitoring or management of APs
* Each AP should connect to the wired network with a trunk link
* Data traffic from wireless clients has a very direct path to the wired network or to other wireless clients associated with the same AP
* Should be used in small networks because they're not viable in medium to large networks
* Can function either in repeater, outdoor bridge, or workgroup bridge mode
* If a client wants to send traffic to an external network, it sends the frame to its WAP, which then forwards it to its default gateway over the wired network, which will then forward it according to its routing table
* If a client wants to send traffic to a device associated with the same AP, then the traffic has no need to enter the wired network since the frame will simply be sent to the AP and be forwarded to the destination

## Lightweight

* Handles real-time operations (Ex: *Transmitting RF traffic*, *Receiving RF traffic*, *Encrypting traffic*, *Decrypting traffic*, *Sending out beacons*, *Sending out probes*, *etc.*)
* Used in a split-MAC architecture because the functions are split between APs and the WLC
* The WLC is used to centrally configure the lightweight APs
* The WLC and lightweight APs authenticate each other using digital certificates installed on each device to ensure that only authorized APs can join the network
* Uses the CAPWAP protocol to communicate and create two tunnels between each AP and the WLC
* Because all traffic from wireless clients is tunneled to the WLC with CAPWAP, APs connect to switch access ports
* Instead of the AP mapping each SSID to a VLAN and forming the border between the wired network and the wireless network, the WLC takes that role
* Traffic from a wireless client is sent to the AP and then tunneled to the WLC, the WLC will then send it over the wired network to the default gateway, which will forward it as appropriate (Even if the traffic is destined for a host assicated with the same AP, it's first tunneled to the WLC and then tunneled back and sent to the destination)

| Lightweight AP Mode | Description |
| --- | --- |
| Local | The default mode where the AP offers a BSS or multiple BSSs for clients to associate with |
| FlexConnect | Offers one or more BSSs for clients to associate with and allows the AP to locally switch traffic between the wired and wireless networks if the CAPWAP tunnels to the WLC go down |
| Sniffer | Dedicated to capturing 802.11 frames and sending them to a device running packet capture software (Ex: *Wireshark*, *etc.*) and the AP doesn't offer a BSS for clients |
| Monitor | Dedicated to receiving 802.11 frames to detect rogues devices and the AP doesn't offer a BSS for clients (If a client is found to be a rogue device, an AP can send de-authentification messages to disassociate the rogue device from the AP) |
| Rogue Detector | Listens to traffic on the wired network only and correlates it with the information it receives from the WLC in order to detect rogue devices (Ex: *A list of suspected rogue clients*, *AP MAC addresses*, *etc.*) and the AP doesn't use its radio |
| SE-Connect (Spectrum Expert Connect) | Dedicated to RF spectrum analysis on all channels and can send information to software (Ex: *Cisco Spectrum Expert*, *etc.*) on a PC to collect and analyze the data, also the AP doesn't offer a BSS for clients |
| Bridge/Mesh | A dedicated bridge between sites, which can go over long distances and be made between the APs |
| Flex Plus Bridge | Adds FlexConnect functionality to the Bridge/Mesh mode and allows wireless APs to locally forward traffic even if connectivity to the WLC is lost |

## Cloud-Based

* A mix between autonomous APs and split-MAC architecture
* Autonomous APs that are centrally managed in the cloud (Ex: *Cisco Meraki*, *etc.*)
* Data traffic is sent to the wired network like when using autonomous APs
* Only management and control traffic is sent to the cloud (Ex: *RF spectrum information*, *Management information*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
