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
