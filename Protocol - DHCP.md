The Dynamic Host Configuration Protocol is a network management protocol that allows hosts to automatically learn various aspects of their network configuration without manual configuration (Ex: *IP address*, *Subnet mask*, *Default gateway*, *DNS server*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Components

## DHCP Servers

* Uses port UDP 67

### Uncentralized DHCP Server

### Centralized DHCP Server

## DHCP Clients

* Uses port UDP 68

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Messages

## DHCPDISCOVER

* A broadcast message

## DHCPOFFER

* The message sent back to the DHCP client can be either broadcast or unicast (The client's IP address isn't officially configured yet, meaning that some client's won't accept unicast messages and that's why broadcast must be used)

## DHCPREQUEST

* A client will typically accept the first offer it receives
* A broadcast message 

## DHCPACK

* The message sent back to the DHCP client can be either broadcast or unicast (The client's IP address isn't officially configured yet, meaning that some client's won't accept unicast messages and that's why broadcast must be used)

## DHCPNACK

## DHCPDECLINE

## DHCPRELEASE

* A unicast message

## DHCPINFORM

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Packet Components

## Magic Cookie

## DHCP Options

| DHCP Option | Purpose |
| --- | --- |
| 50 |  |

