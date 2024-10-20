# Access Control List Overview

* Configured globally on a device and must be applied to an interface (Configuring an ACL in global configuration mode won't make the ACL take effect)
* Made up of one or more Access Control Entities
* The device will check the ACEs in the ACL from top to bottom and once it finds a match, it'll stop checking the other ACEs in the ACL and will take action based on the first matching ACE (All ACEs below the matching entry will be ignored)
* Applied to either inbound or outbound traffic depending on the interface that it was applied to
* A maximum of one ACL can be applied to one interface per direction
* If a packet doesn't match an ACE in the ACL, the device will implicitly deny and drop it (Implicit deny, which tells the device to deny and drop all traffic that doesn't match any of the configured ACEs in the ACL)

| Number Range | ACL Type |
| --- | --- |
| 1-99 and 1300-1999 | Standard ACLs |
| 100-199 and 2000-2699 | Extended ACLs |

## Standard Access Control Lists

* Matches traffic based on only the source IP address of the packet
* Each interface has an inbound and outbound traffic direction
* Should be applied as close to the destination as possible (Standard ACLs are less specific, so if they're applied close to the source there's a risk of blocking more traffic than intended)
* The network device may re-order the /32 ACEs to improve the efficiency of processing the ACL

### Standard Numbered Access Control Lists

* Identified with a number
* Different types of ACLs have a different range of numbers that can be used

### Standard Named Access Control Lists

* Identified with a name

## Extended Access Control Lists

* Matches traffic based on more parameters than the standard ACL, which makes them more precise (Ex: *Source IP address*, *Destination IP address*, *Source port number*, *Destination port number*, *Protocol*, *etc.*)
* Should be applied as close to the source as the source as possible in order to limit how far the packets travel in the network before being denied 

## Dynamic Access Control Lists

## Reflexive Access Control Lists

## Time-Based Access Control Lists

## TCP Established Access Control Lists

* Blocks or denies synchronization during connection establishment

