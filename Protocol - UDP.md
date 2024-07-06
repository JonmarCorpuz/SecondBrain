The User Datagram Protocol is a connectionless communication protocol that's used for transmitting data

* Connectionless, meaning that the sending host doesn't establish a connection with the destination host before sending data
* Doesn't provide reliable communication and segments are sent "best-effort", meaning that acknowledgements aren't sent for received segments (If a segment is lost, UDP has no mechanism to re-transit it)
* Doesn't provide sequencing (There's no sequence number field in the UDP header, so if segments arrive out of order, UDP has no mechanism to put them back in order
* Doesn't provide flow control
* Provides Layer 4 addressing using port numbers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# UDP Header

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/djfdskfdsfdsjfhsdlkfhdskldsjfldksf.jpg)

## Source Port

## Destination Port

## Length

## Checksum

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# UDP Port Numbers

| Port Number | Protocol |
| --- | --- |
| 53 | DNS |
| 67 | DHCP Server |
| 68 | DHCP Client |
| 69 | TFTP |
| 161 | SNMP Agent |
| 162 | SNMP Manager |
| 514 | Syslog |
