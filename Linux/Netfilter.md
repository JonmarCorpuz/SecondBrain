# Netfilter Overview

Netfilter is a framework and the core component responsible for implementing network-related tasks in Linux systems (Ex: *Packet filtering*, *NAT*, *Packet mangling*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Netfilter Features

## Packet Filtering

Netfilter allows packets to be filtered based on various criteria (Ex: *Source IP address*, *Destination IP address*, *Ports*, *Protocols*, *Packet states*, *etc.*)

## Network Address Translation

Netfilter enables NAT operations in order to allow packets to be translated as they traverse a network device (Ex: *Port forwarding*, *Source NAT*, *Destination NAT*, *etc.*)

## Packet Mangling

Netfilter supports packet mangling, which is the process of altering the contents of packets as they pass through a network device (Ex: *Modifying packet header fields*, *Modifying payload data*, *etc.*)

* Can be used to prioritize certain types of traffic over others based on their characteristics (Ex: *Traffic type* ,*etc.*)
* Can be used to shape network traffic in order to control the rate at which packets are transmitted to help manage bandwidth usage and prevent network congestion
* Can be used to distribute incoming traffic across multiple network paths or servers in order to optimize performance and reliability
* Can enhance network security by obscuring or altering packet headers to make it more difficult for attackers to identify and exploit vulnerabilities (Ex: *Hide information about the network infrastructure*, *Implement port knocking*, *etc.*)
* Can facilitate protocol conversion by modifying packet headers to match the requirements of different network protocols or applications

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Netfilter Tools

## iptables

The Internet Protocol tables is a command-line tool used for configuring the firewall functionality in the Linux kernel

* Allows administrators to set rules to filter packets based on various criteria (Ex: *IP addresses*, *Ports*, *Protocols*, *Packet states*, *etc.*)
* Can be used for various tasks (Ex: *NAT*, *Firewall*, *Packet filtering*, *etc.*)

## nftables

nftables is a framework within the Linux kernel for packet classification and filtering

* Serves as a replacement for the older iptables and related tools
* Supports atomic rule updates, meaning that changes to firewall rules are applied all at once in order to help prevent situations where partially applied rules could leave the system in an inconsistent state
