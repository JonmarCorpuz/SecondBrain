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



## Update Message



## Notification Message


