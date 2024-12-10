# Cloud Interconnect Overview

Google's Cloud Interconnect is a service that provides private connectivity between a user's on-premises networks and GCP network

* Provides high availability and high throughput through high speed physical connections between on-premise and VPC networks
* Data exchance happens through a private network (The public internet isn't used)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Interconnect Options

| Cloud Interconnect Connection Type | Description |
| --- | --- |
| Dedicated Interconnect | 10 Gbps or 1000 Gbos configurations |
| Partner Interconnect | 50 Mbps to 10 Gbps configurations |

## Dedicated Interconnect

* Uses the Address Allocation for Private Internets standard (RFC 1918) to connect to devices in your VPC
* A direct network connection is maintained between an on-premises or hosted data center and one of Google's colocation facilities

## Partner Interconnect

* Depends on third-party network providers to provide connectivity between the company's data center and a Google facility
