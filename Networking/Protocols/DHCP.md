The Dynamic Host Configuration Protocol is a network management protocol that allows hosts to automatically learn various aspects of their network configuration without manual configuration (Ex: *IP address*, *Subnet mask*, *Default gateway*, *DNS server*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Components

## DHCP Servers

* Uses port UDP 67

### Uncentralized DHCP Server

### Centralized DHCP Server

* DHCP relay agents are configured to forward a client's broadcast DHCP messages to a remote DHCP server as unicast messages since centralized DHCP servers won't always be able to receive a DHCP client's broadcast message since broadcast messages don't leave the local subnet

## DHCP Clients

* Uses port UDP 68

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Messages

## DHCPDISCOVER

The DHCPDISCOVER message is used by a DHCP client to discover available DHCP servers on the local network by sending out broadcast messages  

* The first step in the DHCP process
* Sending out a broadcast message ensures that all the DHCP servers in the local network receive the message
* Client source IP address is 0.0.0.0 since it doens't have an IP address yet
* A broadcast message

## DHCPOFFER

The DHCPOFFER message is sent by DHCP servers in response to a DHCPDISCOVER message from a DHCP client

* The second step in the DHCP process
* The message sent back to the DHCP client can be either broadcast or unicast (The client's IP address isn't officially configured yet, meaning that some client's won't accept unicast messages and that's why broadcast must be used)
* Offers the DHCP client with an IP address and other network configuration details
* Includes the IP address of the DHCP server that's making the offer

## DHCPREQUEST

The DHCPREQUEST message is used by DHCP clients to confirm or renew configuration parameters that from a DHCP server

* A client will typically accept the first offer it receives
* A broadcast message 

## DHCPACK

The DHCPACK message is used by the DHCP server to confirm that the IP address lease and configuration parameters have been successfully assigned to the DHCP client

* The message sent back to the DHCP client can be either broadcast or unicast (The client's IP address isn't officially configured yet, meaning that some client's won't accept unicast messages and that's why broadcast must be used)

## DHCPNACK

## DHCPDECLINE

## DHCPRELEASE

* A unicast message

## DHCPINFORM

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Packet Components

## Magic Cookie

A magic cookie refers to a specific value that's used to identify the start of the options field in DHCP messages

* Ensures that DHCP clients and servers can recognize and correctly interpret the options provided in the messages

## DHCP Options

DHCP options are additional parameters that can be included in DHCP messages to provide clients with various network configuration details beyond just an IP address

| DHCP Option | Purpose | Description |
| --- | --- | --- |
| 1 | Subnet Mask | Specifies the subnet mask for the client's IP address |
| 3 | Default Gateway | Specifies the IP address of the default gateway that the client should use to reach other networks |
| 6 | Domain Name Server | Lists the IP addresses of DNS servers that the client should use for name resolution |
| 12 | Hostname | Allows the cluent to specify its hostname |
| 15 | Domain Name | Provides the domain name that the client should use for DNS resolution |
| 42 | Network Time Protocol Servers | Lists the IP addresses of NTP servers for time synchronization |
| 44 | NetBIOS over TCP/IP Name Server | Specifies the IP addresses of WINS servers for NetBIOS name resolution |
| 51 | IP Address Lease Time | Specifies the lease time in seconds for the IP address assigned to the client |
| 53 | DHCP Message Type | Indicates the type of DHCP message (Ex: *DHCPDISCOVER*, *DHCPOFFER*, *DHCPREQUEST*, *DHCPACK*, *etc.*)
| 54 | Server Identifier | Specifies the IP address of the DHCP server that sent the message |
| 66 | TFTP Server Name | Provides the name or IP address of a TFTP server for network booting |
| 67 | Bootfile Name | Specifies the name of the file to be booted by the client |
| 119 | Domain Search | Provides a list of domain names that the client should search when resolving hostnames |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Packet Fields

## Client Hardware Address

The CHADDR field indicates the MAC address of the client

* Used to identify the client since DHCP messages that are going out of the local network to reach a remote DHCP server won't have the client's MAC address as the source MAC address
