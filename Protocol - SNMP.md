The Simple Network Management Protocol is a protocol that's designed to manage network performance on IP networks

* Enables real-time performance monitoring and maintenance of network health and security

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Components

## SNMP Manager

An SNMP manager is the central system that controls and monitors the network through SNMP

* Sends requests to SNMP agents on network devices and receives responses and unsolicited messages (traps) from those agents

## SNMP Agent

An SNMP agent is a software that's installed on a network device, collects information of that network devices, and reports it to the SNMP manager

## Management Information Base

An MIB is a database of a network device's statistics and control information

* Each SNMP agent maintains a MIB
* Each piece of information in the MIB is indexed using Object Identifies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Versions

## SNMPv1

## SNMPv2

## SNMPv3

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Operations

* `Get` fetches the value of a specific variable from an agent
* `Set` sets the value of a specific variable in an agent
* `GetNext` fetches the next variable in the MIB
* `GetBulk` retrieves large blocks of data (Used in SNMPv2 and SNMPv3)
* `Inform` allows SNMP managers to send information to other SNMP managers (Used in SNMPv2 and SNMPv3)
* `Trap` allows an agent to asynchronously inform the SNMP manage about a significant event
