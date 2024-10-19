The Simple Network Management Protocol is a protocol that's designed to manage network performance on IP networks

* Enables real-time performance monitoring and maintenance of network health and security (Ex: *Device status*, *Configuration changes*, *etc.*)
* Uses UDP, meaning that there are no TCP retransmissions for any lost packets

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/jdgfldjkjlrugfsjlk.png)

## Network Management Station

A NMS is a system or application that monitors and manages SNMP-enabled devices on a network

* Can ask the managed devices for information about their current status
* Can tell the managed devices to modify their configuration (Ex: *IP address*, *etc.*)
* Can receive notifications from managed devices

### SNMP Manager

An SNMP manager is the central system that controls and monitors the network through SNMP

* It's the software on the NMS that interacts with the managed devices (Ex: *Receives notifications*, *Sends requests for information*, *Sends configuration changes*, *etc.*)
* Sends requests to SNMP agents on network devices and receives responses and unsolicited messages (traps) from those agents
* UDP port 162

### SNMP Application 

* Provides an interface an interface for the network admin to interact with

## Managed Devices

A managed device is any network components or hardware device that's monitored and controlled using network management protocols (Ex: *SNMP*)

* Can notify the NMS of events

### SNMP Agent

An SNMP agent is a software that's installed on a network device, collects information of that network devices, and reports it to the SNMP manager

* Sends notifications to and receives messages from the NMS
* UDP port 161

### Management Information Base

An MIB is a database of a network device's statistics and control information

* Each SNMP agent maintains a MIB
* Each piece of information in the MIB is indexed using Object Identifiers (OID)
* OIDs are organized in a hierarchicall structure
* Contains the variables that are managed by SNMP (Ex: *Interface status*, *Traffic throughput*, *CPU usage*, *Temperature*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Messages

## SNMP Message Classes

| SNMP Message Class | Description | Messages |
| --- | --- | --- |
| Read | Messages sent by the NMS to read information from the managed devices (Ex: *What's your current CPU usage percentage*, *etc.*) | `Get`, `GetNext`, `GetBulk` |
| Write | Messages sent by the NMS to change information on the managed devices (Ex: *Change an IP address*, *etc.*) | `Set` |
| Notification | Messages sent by the managed devices to alert the NMS of a particular event (Ex: *Interface going down*, *etc.*) | `Trap`, `Inform` |
| Response | Messages sent in response to a previous message or request | `Response` |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## SNMP Messages

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/why-snmp-is-important-view.jpg)

| SNMP Message | What | Who |
| --- | --- | --- |
| `Get` | Fetches the value of a specific variable IOD that was request by an agent | Sent from the SNMP manager to the SNMP agent to retrieve the value of an OID |
| `Set` | Sets the value of a specific variable in an agent | A request from the SNMP manager to the SNMP agent to change the value of one or more variables |
| `GetNext` | Fetches the next variable in the MIB | Sent from the SNMP manager to the SNMP agent to discover the available variables in the MIB |
| `GetBulk` | Retrieves large blocks of data (Used in SNMPv2 and SNMPv3) | Sent from the SNMP manager to the SNMP agent to discover the available variables in the MIB |
| `Inform` | Allows SNMP managers to send information to other SNMP managers (A notification message that's acknowledged with a Response message) | Sent from a SNMP agent to the SNMP manager |
| `Trap` | Allows a SNMP agent to asynchronously inform the SNMP manager about a significant event (Unreliable since the SNMP manager won't send a Response message to acknowledge that it received the trap) | A notification sent from the SNMP agent to the SNMP manager | 
| `Response` |  | Sent from the SNMP manager to an SNMP agent in response to a previous message or request |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SNMP Versions

## SNMPv1

* The original version of SNMP

## SNMPv2c

* Allows the NMS to retrieve large amounts of information in a single request making it more efficient
* "c" refers to the community string used as passwords in SNMPv1 that was removed and then added back for SNMPv2c

## SNMPv3

* Ensures that only the intended devices can read the SNMP messages
* Supports strong encryption and authentication
