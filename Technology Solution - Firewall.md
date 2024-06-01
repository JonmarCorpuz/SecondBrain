A firewall is a network security device or software that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/sdfbkdfndfnkdbskdsbjkdsbknsgbkn.png)

* Establishes a barrier between secure and controlled internal networks that can be trusted and untrusted outside networks 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Firewall Components

## Access Control Lists

### Standard ACL

### Extended ACL

### Named ACL

### Time Based ACL

### Dynamic ACL

### Reflective ACL

### TCP Establish ACL

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Firewall Types

## Stateless Firewall

A stateless firewall is a type of firewall that doesn't maintain any knowledge of the state or context of active connections passing through it

* Operates at the Network layer of the OSI model (Layer 3) and is seen as a router hop 
* Evaluates each individual packet based solely on predetermined criteria (Ex: *Source IP addresses*, *Destination IP addresses*, *Port numbers*, *Protocol types*, *etc.*)
* When a packet arrives at a stateless firewall, it examines the packet headers and compares them against a set of static rules or ACLs
* Less effective at identifying and blocking certain types of threats
* Lack the ability to perform advanced security functions (Ex: *Packet inspection*, *Deep packet inspection*, *etc.*)

## Stateful Firewall

A stateful firewall is a type of firewall that keeps track of the state of active connections passing through it

* Operates at the Network layer of the OSI model (Layer 3) and is seen as a router hop 
* Monitors the state of active connections and makes decisions about allowing or blocking traffic based on the context of those connections (Ex: *Source IP address*, *Destination IP address*, *Source port number*, *Destination port number*, *etc.*)
* Maintains a state table, which records the state of each connection (Ex: *Source IP addresses*, *Destination IP addresses*, *Port numbers*, *Sequence numbers*, *Packet headers such as SYN, SYN-ACK, and ACK*, *etc.*)
* When a packet arrives at the firewall, it checks its state table to determine whether the packet is part of an existing authorized connection or if it's attempting to establish a new and potentially unauthorized connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Transparent Firewall

A transparent firewall is a type of firewall

* Operates at the Data Link layer of the OSI model (Layer 2) and isn't seen as a router hop
