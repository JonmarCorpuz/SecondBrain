An agent refers to a software entity that performs specific tasks on behalf of another application or user

* Operate autonomously or semi-autonomously
* Typically deployed to manage, monitor, and control network resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Agent Types

## SNMP Agents

An SNMP agent is used to monitor network-attached devices

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/How-SNMP-works-diagram.png)

* Resides on a network device (Ex: *Router*, *Switch*, *Server*, *Printer*, *etc.*)
* Collects data about its host device (Ex: *Performance metrics*, *Utilization statistics*, *etc.*)
* Communicates the data it collects to an SNMP manager or network management system using SNMP protocols either as a response to a request from the manager or proactively through a trap mechanism, which is an unsolicited notification of significant events or errors
* Receives and acts on commands from the SNMP manager (Ex: *Configuration changes*, *Request for status updates*, *etc.*)

## Proxy Agent

A proxy agent is an intermediary entity between a client device and another server from which a client might be requesting data

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1_LxwoTFnUgznI0UmnEsxs4w.png)

* Can reside on a separate server or on the same machine as a gateway service
* Useful for managing, filtering, and enhancing network traffic between clients and servers
* Reduces bandwidth usage and speeds up access to data by storing local copies of frequently accessed web content and compressing outbound and inbound data 
* Can enforce access control policies by blocking requests to certain websites or filtering incoming content
* Can monitor and log all web traffic by intercepting all incoming and outgoing data
* Can perform load balancing by distributing the incoming requests to multiple servers
