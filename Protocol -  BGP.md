The Border Gateway Protocol is an exterior gateway protocol used in large-scale networks to enable the exchange of routing and reachability information between autonomous systems

* The most scalable routing protocol
* Designed for use between different autonomous systems to allow them to communicate with each other
* Makes routing decisions based on paths, policies, and network policies
* Enables ISPs to connect their networks to the rest of the internet by advertising the routes to their networks, allowing the routers on the internet to dynaically exchange routing information, adapt to changes in network topology, and ensure efficient and reliable packet delivery

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# BGP Components

## BGP Speakers

A BGP speaker is any network device that's capable of running the BGP protocol

* Exchanges routing information with each other to make routing decisions about how to route traffic between different networks or ASes
* BGP speakers communicate through BGP messages, 

## BGP Peers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# BGP Message Types

## Open Message

An Open message is the first message sent between two BGP speakers when establishing a BGP session between the both of them

* Contains parameters necessary for setting up the BGP session (Ex: *BGP version number*, *Autonomous System Number*, *Hold time*, *etc.*)

## Keepalive Message

A Keepalive message ensures that the connection between BGP speakers remains active and that they're still reachable

* Serves as a means to maintain the connectivity and state of the BGP session between two BGP speakers
* Sent periodically between BGP speakers after the initial establishment of the BGP session
* The interval at which Keepalive messages are sent is determined during the session negotiation process and is typically configured as part of the BGP session parameters
* Functions as a form of heartbeat mechanism between BGP speakers
* Minimizes the overhead associated with Keepalived message transmision by consisting only of an empty payload with a fixed BGP header

## Update Message

An Update message exchanges routing information between BGP speakers

* Contains information about new routes, withdrawn routes, and modifications to existing routes, as well as their Network Layer Reachability Information, which specifies the network prefixes that the sender is advertising or withdrawing, and path attributes, which provides additional characteristics of the route (Ex: *AS path*, *Next hop*, *Origin*, *etc.*)

## Notification Message

A Notification message signals errors or exceptional conditions during a BGP session

* Results in the termination of the BGP session between the affected BGP peers to prevent further communication issues
