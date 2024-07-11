
* Based on an older protocol called LWAPP

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CAPWAP Tunnels

* CAPWAP creates two tunnels between each AP and the WLC

## Control Tunnel

* Uses UDP port 5246
* Used to configure the APs, as well as control and manage their operations
* All traffic in this tunnel is encrypted by default

## Data Tunnel

* Uses UDP port 5247
* All traffic from wireles clients are sent through this tunnel to the WLC
* All traffic in this tunnel isn't encrypted by default, but you can encrypt it with the Datagram Transport Layer Security (DTLS) protocol
