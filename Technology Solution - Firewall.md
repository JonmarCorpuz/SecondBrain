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

## Stateless Inspection Firewall

A stateless inspection firewall is a type of firewall that doesn't maintain any knowledge of the state or context of active connections passing through it

* Operates at the Network layer of the OSI model (Layer 3) and is seen as a routed hop 
* Evaluates each individual packet based solely on predetermined criteria (Ex: *Source IP addresses*, *Destination IP addresses*, *Port numbers*, *Protocol types*, *etc.*)
* When a packet arrives at a stateless firewall, it examines the packet headers and compares them against a set of static rules or ACLs
* Less effective at identifying and blocking certain types of threats
* Lack the ability to perform advanced security functions (Ex: *Packet inspection*, *Deep packet inspection*, *etc.*)

## Stateful Inspection Firewall

A stateful inspection firewall is a type of firewall that keeps track of the state of active connections passing through it

* Operates at the Network layer of the OSI model (Layer 3) and is seen as a routed hop 
* Monitors the state of active connections and makes decisions about allowing or blocking traffic based on the context of those connections (Ex: *Source IP address*, *Destination IP address*, *Source port number*, *Destination port number*, *etc.*)
* Maintains a state table, which records the state of each connection (Ex: *Source IP addresses*, *Destination IP addresses*, *Port numbers*, *Sequence numbers*, *Packet headers such as SYN, SYN-ACK, and ACK*, *etc.*)
* When a packet arrives at the firewall, it checks its state table to determine whether the packet is part of an existing authorized connection or if it's attempting to establish a new and potentially unauthorized connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Transparent Firewall

A transparent firewall is a type of firewall that acts as a bridge by inspecting and moving network frames between interfaces

* Operates at the Data Link layer of the OSI model (Layer 2) and isn't seen as a routed hop
* Filters traffic based on the source and destination MAC addresses 
* Can be seen as a "stealth firewall" that supports outside and inside interfaces
* Helps organizations solve issues relating to traffic visibility and threat protection without having to re-addressing their network (Ex: *Site-to-Site network communication*, *etc.*)

## Identity Firewall

An identity firewall is a type of firewall that provides IAM capabilities along with traditional firewall functionality to enforce access control policies based on user identities

* Allows organizations to implement more granular and context-aware security policies in order to reduce the risk of unauthorized access
* Allows administrators to configure access rules and security policies based on usernames and user group names instead of only through source IP addresses
* Integrates with Microsoft Active Directory in conjunction with an external Active Directory Agent that provides the actual identity mapping

## Proxy Firewall

A proxy firewall, also known as an application firewall or proxy server firewall, is a type of firewall that inspects and filters traffic at the application layer

* Operates at the Application layer of the OSI model (Layer 7)

## Unified Threat Management Firewall

A Unified Threat Management Firewall is a type of firewall that integrates multiple security features into a single platform or appliance (Ex: *IPS*, *Antivirus*, *VPN*, *Firewall*, *DLP*, *etc.*)

* Offers simplified management, reduced complexity, and often cost savings compared to deploying and managing multiple standalone security solutions

## Next-Generation Firewall

A Next-Generation Firewall is a type of firewall that incorporates traditional firewall features along with additional capabilities to provide deeper inspection and more granular control over network traffic

* Designed to identify and control applications at the network level, allowing administrators to enforce policies based on various elements (Ex: *Ports*, *Protocols*, *Applications*, *Application functions*, *etc.*)
* Can integrate with authentication systems to identify users and apply policies based on their identities in order to enable organizations to enforce access controls and security policies on a per-user basis
* Can perform SSL inspection by decrypting and inspecting SSL-encrypted traffic to identify and block threats hidden within encrypted communications
* May incorporate advanced threat detection and prevention mechanisms (Ex: *Sandboxing*, *Threat intelligence feeds*, *Behavior-based analysis*, *etc.*)

## Threat-focused Next Generation Firewall

A threat-focused NGFW is a type of firewall that places primary emphasis on threat detection, prevention, and response capabilities

* Incorporates advanced threat detection mechanisms to identify known threats traversing the network (Ex: *IPS*, *Signature-based detection*, *Anomaly detection*, *Behavioral analysis*, *etc.*)
* Leverages real-time threat intelligence feeds from internal and external sources to enhance threat detection accuracy and effectiveness
* Integrates multiple security features and technologies into a single platform (Ex: *Firewall*, *IPS*, *Antivirus*, *URL Filtering*, *Application control*, *Encryption inspection*, *etc.*)
* Incorporates contextual awareness capabilities, allowing them to analyze network traffic in the context of user identities, device types, application behaviors, and network protocols in order to perform more accurate threat detection and better enforcement of security policies
* Includes automated threat response capabilities by automating response actions based on predefined policies and security rules in order to help mitigate the impact of security incidents more quickly and efficiently
* Designed to scale and perform efficiently in high-volume network environments by supporting high-speed data throughput and low latency while maintaining effective threat detection and prevention capabilities
* Can integrate with SOAR platforms to enable centralized management, orchestration, and automation of security operations
