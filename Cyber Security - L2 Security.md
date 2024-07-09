
# Port Security 

Port security is a Layer 2 network security feature that allows you to control which and how many source MAC addresses are allowed to enter the switchport

* If an unauthorized source MAC address enters the port, an action will be taken (By default it'll place the interface in an err-disabled state)
* Port security default settings only allow one MAC address
* You can configure the allowed MAC address manually (If you don't configure the MAC addresses manually, it'll only allow the first source MAC address that enters the interface)
* The maximum number of MAC addresses allowed on a switchport can be changed
* Can defend against some attacks (Ex: *DHCP starvation*, *etc.*)
* Secure MAC addresses won't age out by default
 
| Port Security Violation Mode | Description | Port Shutdown |
| --- | --- | --- |
| Shutdown | Shuts down the port by placing it in an err-disabled state and generates a syslog or SNMP message when the interface is disabled (The violation counter is set to 1 when the interface is disabled) | Shutdown |
| Restrict | Discard traffic from unauthorized MAC addresses and generates a syslog or SNMP message each time an unauthorized MAC is detected (The violation counter is incremented by 1 for each unauthorized frame) | No shutdown |
| Protect | Discards traffic from unauthorized MAC addresses and doesn't generate a syslog or SNMP message for unauthorized traffic (Doesn't increment the violation counter) | No shutdown |

| MAC Address Aging Type | Description |
| --- | --- |
| Absolute | When a MAC address is learned, the the aging timer starts and the MAC is removed after the timer expires |
| Inactivity | When a MAC address is learned, the aging timer starts but is reset every time a frame from that source MAC address is received on the interface |

| MAC Address Type | Description |
| --- | --- |
| Dynamically-learned secure MAC address | (Has a type of dynamic)
| Sticky secure MAC address | Saves the secure MAC address to the running configuration and is added to the MAC address table (Has a type of static and never ages out) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP Snooping

DHCP snooping is a Layer 2 security feature that's used to filter DHCP messages received on untrusted ports

* Only filters DHCP messages
* All ports are untrusted by defaultand it's up to you to configure which ports will be trusted (Usually, uplink ports, which point away from end hosts, are configured as trusted and downlink ports, which are interfaces pointing towards end hosts, remain untrusted)
* DHCP snooping doesn't inspect DHCP messages on the trusted ports 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Dynamic ARP Inspection 
