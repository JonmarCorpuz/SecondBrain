Quality of Service refers to the ability to prioritize and manage network traffic to ensure that certain types of data packets receive preferential treatment over others

* Helps improve performance, reliability, and predictability of network services (Ex: *Minimize delay*, *Minimize packet loss*, *etc.*)
* Enables cost savings as well as more advanced features for voice and video traffic (Ex: *Integration with collaboration software*, *etc.*)
* Offers a set of tools used by networks to apply different treatments to different packets (Ex: *Reserve a certain amount of a link's bandwidth for specific kinds of traffic*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# QoS Components

| QoS Component | QoS Standard |
| --- | --- |
| One-way delay | 150 milliseconds or less |
| Jitter | 30 milliseconds or less |
| Loss | 1% or less |

## Bandwidth 

The bandwidth refers to the overall capacity of a link

* Measured in bits per second (Ex: *Kbps*, *Mbps*, *Gbps*, *etc.*)

## Delay

The delay refers to a one-way delay, which is the amount of time it takes for traffic to go from source to destination

* Can also refer to a two-way delay, which is the amount of time it takes for traffic to go from source to destination and return

## Jitter

The jitter refers to the variation in one-way delay between packets sent by the same application (The difference in how long it takes between different packets from the same source to reach the same destination)

* Can negatively affect the audio quality of phone calls

## Loss

The loss refers to the percentage of packets sent that don't reach their destination

* Can be cause by faulty cables or a congested network (Ex: *If a device's packet queues get full it'll start discarding packets*, *etc.*)
* Can negatively affect the audio quality of phone calls

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# QoS Traffic Classification

Traffic classification organizes network traffic (packets) into traffic classes (categories)

* Allows organizations to give priority to certain traffic classes

## Traffic Classification Using ACLs

* Traffic which is permitted by an ACL will be given certain treatment while other traffic will not

## Traffic Classification Using Network Based Application Recognition

NBAR allows network devices to recognize and classify applications and protocols based on their unique signatures through deep packet inspection

*  Uses a database of signatures to recognize different applications and protocols

## Traffic Classification Using Priority Code Point

PCP is a field in the 802.1Q tag that's used in Ethernet frames to indicate the priority level of the frame for QoS purposes

* Can only be used when there's a dot1q tag
* Also known as Class of Service (CoS)
* It's use it defined by IEEE 802.1p
* Can only be used over trunk link and access link with a voice VLAN connections since it's only found in the dot1q header

| PCP Value | Traffic Type | Description |
| --- | --- | --- |
| 0 | Best effort (Default) | There's no guarantee that data is delivered or that it meets any QoS standard (Regular traffic not high-priority) |
| 1 | Background |  |
| 2 | Excellent effort |  |
| 3 | Critical applications |  |
| 4 | Video |  |
| 5 | Voice |  |
| 6 | Internetwork control |  |
| 7 | Network control |  |

## Traffic Classification Using Differentiated Services Code Point 

The DSCP is a field in the IP header that's used to classify and manage network traffic to provide different levels of QoS 

* DSCP values are used in the IP header to classify packets into different service classes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Queuing

Queuing in QoS refers to the process of managing and prioritizing packets within network queues based on predefined rules and policies

* Used to control the order in which packets are processed and transmitted, which helps in optimizing network performance and ensuring that critical traffic receives preferential treatment over less important traffic
* If a network device receives messages faster than it can forward them out of the appropriate interface, the messages are placed in a queue
* Queued messages will be forwarded in a First In First Out manner, meaning that messages will be sent in the order that they're received
* If the queue gets full, the incoming packets will be dropped, also known as tail drop, which can lead to TCP global synchronization, which is when multiple TCP connections simultaneously reduce their transmission rates in response to network congestion or packet loss (Network congestion --> Tail drop --> Global TCP window size decrease --> Network underutilized --> Global TCP window size increase --> Network congestion)

## Random Early Detection

* Prevents tail drop and TCP global synchronization by randomly dropping packets from select TCP flows when the amount of traffic in the queue reaches a certain threshold (Those TCP flows that dropped packets will reduce the rate at which traffic is sent, which all TCP flows reduce and then increase the rate of transmission at the same time in waves)

### Standard Random Early Detection

### Weighted Random Early Detection

* Allows a user to control which packets are dropped depending on the traffic class (Ex: *Drop HTTP packets when the queue is full*, *etc.*)
* Traffic classes configured with the lowest priority are those that will be dropped sooner when the queue reaches a certain threshold

## Queue Management

* QoS may use multiple queues for different types of traffic 
* A scheduler is used to decide which queue traffic is forwarded from next since only one frame can be sent out an interface at once by using a scheduling method
* Prioritization allows the scheduler to give certain queues more priority than others
* Ingress traffic --> (routing, etc.) --> Classification --> Queuing --. Scheduling --> Transmission

### Scheduling Method

* Round-robin = Packets are taken from each queue in order, cyclically
* Weighted = More data is taken from high priority queues each time the scheduler reaches that queue

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Trust Boundaries

The trust boundary defines where devices trust and don't trust the QoS markings of received messages

* If the markings are trusted, the device will forward the message without changing the markings, but if they aren't trusted then the device will change the markings according to the configured policy before forwarding it (Ex: *If an IP phone sends an EF packet, the switch will trust it and forward it as is, but if a PC sends an EF packet, then the switch will change it to a DF before forwarding it*, *etc.*)
* It's recommended to set the trust boundary to an IP phone that's connected to the network's switch
