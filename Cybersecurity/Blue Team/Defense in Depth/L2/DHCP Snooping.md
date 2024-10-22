# DHCP Snooping Overview

DHCP snooping is a Layer 2 security feature that's used to filter DHCP messages received on untrusted ports

* Only filters DHCP messages
* All ports are untrusted by defaultand it's up to you to configure which ports will be trusted (Usually, uplink ports, which point away from end hosts, are configured as trusted and downlink ports, which are interfaces pointing towards end hosts, remain untrusted)
* DHCP snooping doesn't inspect incoming and outgoing DHCP messages on the trusted ports 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

