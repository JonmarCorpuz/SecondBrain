# IGMP Overview

The Internet Group Management Protocol is a communication protocol used by IP hosts and adjacent multicast routers to establish and manage multicast group memberships on a network

* Allows several devices to share one IP address so that they can all receive the same data
* Operates at the Network layer of the OSI model (Layer 3)
* Helps efficiently distribute data into multiple recipients by sending it only to those who have expressed interest in receiving it (Ex: *Streaming video or audio*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IGMP Components

## Hosts

A host is a device on a network that wants to receive multicast traffic 

## Multicast Groups

A multicast group is a logical grouping of hosts that wish to receive the same multicast traffic

* Defined by a multicast group address, which is an IP address within the reserved IP address range between 224.0.0.0 and 239.255.255.255

## IGMP Messages

IGMP messages are used by hosts and multicast routers to communicate group membership information

### Membership Query

A membership query message is sent by multicast routers to determine which multicast group have interested receivers on a network segment

### Membership Report

A membership report message is sent by hosts to indicate their interest in joining a multicast group in response to a membership query or independently when they want to join a group

### Leave Group

A leave group message is sent by hosts to inform routers that they're leaving a multicast group because they're no longer interested in receiving its traffic

## Multicast Routers

A multicast router is a network device that manages multicast group memberships for their attached network segments and forwards multicast traffic to those segments where there are interested receivers

* Sends and receives IGMP messages to maintain group membership information

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IGMP Processes

## Joining a Multicast Group

When a device on a network wants to receive multicast traffic for a specific multicast group, it'll send an **IGMP join** message to its local router

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/jddjbdbjdskfdskfdsafasdf.png)

* The IGMP join message contains information about the multicast group that the device wants to join 

## Switching Multicast Group

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/sdjkffjkdslbfdsbjfkdsb.png)

## Leaving a Multicast Group

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/knjdjfodksbgjdbgsdfbdsosdklf.png)

