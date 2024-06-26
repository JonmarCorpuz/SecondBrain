Cisco's Adaptive Security Appliance is a security device that provides various security services for networks of various sizes 

* Can act as a stateful firewall in order to enfore security policies to control the flow of traffic between different network segments
* Supports VPN technologies in order to allow secure communication over public networks (Ex: *Sire-to-site VPN*, *Remote access VPN*, *etc.*)
* Includes IPS capabilities to detect and prevent network-based attacks in real-time by inspecting traffic for known threats and anomalous behavior and taking action to block or mitigate potential attacks
* Can offer Advanced Malware Protection technology
* Provides application layer visibility and control, allowing administrators to enforce policies based on specific applications and protocols
* Can integrate with IAM systems for user authentication and authorization, allowing administrators to create access control policies based on user identities (Ex: *User base authentication*, *etc.*)
* Generates logs and reports that provide visibility into network traffic, security events, and device performance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cisco ASA Access Control Components

## Security Levels

Security levels are used to determine the trustworthiness of a port and the permissions of traffic flowing between interfaces

### Security Level 0

The level 0 security level is considered the least trusted

### Security Levels 1-99

The security levels between 1 and 99 are assigned to interfaces based on their trustworthiness

* Traffic between interfaces with security levels from 1 to 99 is controlled by ACLs and NAT rules

### Security Levels 100

The level 100 security level is considered the most trusted

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cisco ASA VPN Components

## Internet Security Association and Key Management Protocol Policies

An ISAKMP policy is a set of parameters that governs the process of establising a secure communication channel (**IPsec tunnel**) between two networking devices (Ex: *Encryption algorithm*, *Authentication method*, *Hashing Alogrithm*, *Diffie-Hellman group*, *Lifetime*, *ISAKMP key*, *ISAKMP policy priority*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cisco ASA Features

## Firewall

### Stateful Firewall

### Virtual Firewall

### Transparent Firewall

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## IPS

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## VPN

### IPSec

### VPN Load Balancing

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Authencation

### User Base Authentication

### Authentication Proxy

### Neighbor Router Authentication

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Modular Policy Framework

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Web Base Management

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Failover

Failover refers to the ability of the ASA to automatically switch traffic processing from a primary unit to a secondary unit in the event of a failure or downtime

### Active-Standby Failover

### Stateful Failover

### Stateless Failover

### Transparent Failover

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Clustering

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## NAT

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## TCP Intercept

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Unicast Reverse Path Forwarding

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Port to Application Mapping

PAM is the process of associating a particular port number with a specific application or service

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ldfbhbdsbjdbddfkdjbbjkdfjbkd.png)

* Each network service or application running on a device listens for incoming connections on a specific port number

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Event Logging

