# VPC Firewall Overview

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VPC Firewall Rules

* Defined at the network level
* Used to control the flow of network traffic to VMs
* Stateful, meaning that if traffic is allowed in one direction and a connection is established, then it's allowed in the other direction as well (Ex: *If an SSH connection on port 22 is allowed, then all later traffic matching this rule is permitted as long as the connection is active*)
* All VPCs start with two implied rules that cannot be deleted (One rule allows egress traffic to all destinations while the other denies all incoming traffic from any source)
* When a VPC is automatically created, the default network is created with four allow network rules with a priority of 65534 (Allow incoming traffic from any VM instance on the same network, Allow incoming TCP traffic on port 22 for SSH, Allow incoming TCP traffic on port 3389 for RDP, Allow ICMP from any source on the network)

## Direction

## Priority

* Specified by an integer from 0 (Highest priority) to 65535 (Lowest priority)
* Highest-priority rules are applied over any other matching rule that has a lower priority

## Action

* Either allow or deny

## Target

## Source

## Destination

## Protocol

## Port

## Enforcement Status

* Either enabled or disabled
