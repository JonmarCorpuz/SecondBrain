The Cisco Discovery Protocol is a Layer 2 Cisco proprietary protocol that's used to discover and gather information about directly connected Cisco devices

* Allows Cisco devices to share information with other Cisco devices (Ex: *Hostname*, *IP address*, *Device type*, *Device capabilities*, *Operating system version*, *etc.*)
* Considered as a security risk since they share information about the devices in the network
* Enabled on Cisco devices by default

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CDP Messages

* CDP messages are periodically sent to the 0100.0CCC.CCCC multicast MAC address
* Cisco devices don't forward CDP messages to other devices, meaning that a Cisco device can only become a CDP neighbor with other directly connected Cisco devices (When a device receives a CDP message, it'll process and then discard it)
* Sent once every 60 seconds by default

