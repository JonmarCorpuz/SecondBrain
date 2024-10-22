# Broadcast Storm Overview

A broadcast storm is when broadcast or multicast packets are rebroadcasted by network devices, creating a flood of unecessary traffic which can cause the network to be too congested for legitimate traffic to use the network

* As more devices rebroadcast, the traffic volume increases rapidly, consuming network bandwidth and resources
* This is because the Ethernet header doesn't have a TTL field
* Can lead to MAC Address Flapping, which is an event that occurs when a network switch detects the same MAC address on multiple switchports in rapid succession, because each time a frame arrives on a switchport, the switch uses the source MAC address field to learn the MAC address and update its MAC address table