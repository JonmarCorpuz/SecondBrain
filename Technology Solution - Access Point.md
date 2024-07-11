
* The functions of an AP can be split between an AP and a WLC

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AP Types

## Wireless Lan Controller

* Can be located either inside the same subnet or VLAN as the APs it manages or outside

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
* can function either in repeater, outdoor bridge, or workgroup bridge mode

## Lightweight

* Handles real-time operations (Ex: *Transmitting RF traffic*, *Receiving RF traffic*, *Encrypting traffic*, *Decrypting traffic*, *Sending out beacons*, *Sending out probes*, *etc.*)
* Used in a split-MAC architecture because the functions are split between APs and the WLC
* The WLC is used to centrally configure the lightweight APs
* The WLC and lightweight APs authenticate each other using digital certificates installed on each device to ensure that only authorized APs can join the network
* Uses the CAPWAP protocol to communicate

## Cloud-Based
