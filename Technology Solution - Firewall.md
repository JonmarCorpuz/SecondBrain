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

## Stateful Firewall

A stateful firewall is a type of firewall that keeps track of the state of active connections passing through it

* Monitors the state of active connections and makes decisions about allowing or blocking traffic based on the context of those connections (Ex: *Source IP address*, *Destination IP address*, *Source port number*, *Destination port number*, *etc.*)
* Maintains a state table, which records the state of each connection (Ex: *Source IP addresses*, *Destination IP addresses*, *Port numbers*, *Sequence numbers*, *Packet headers such as SYN, SYN-ACK, and ACK*, *etc.*)
* When a packet arrives at the firewall, it checks its state table to determine whether the packet is part of an existing authorized connection or if it's attempting to establish a new and potentially unauthorized connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
