The Network Address Translation is a process used in routers to modify network address information in packet headers while in transit across a traffic routing device

* Allows multiple devices within a local network to share a single public IP address for accessing the internet

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# NAT Types

## PAT

Port Address Translation is a type of NAT that allows multiple devices within a private network to share a single public IP address

* Each device within the private network is assigned a unique port number and when those devices communicate with external servers or devices on the internet, the device performing PAT will keep track of the source port number assigned to each interal device and will then translate both the private IP address and the source port number to a single public IP and a unique port number on the networking device
