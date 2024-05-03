The Transmission Control Protocol/Internet Protocol model is a framework consisting of communication protocols that define how data is transmitted and received over networks

* Structured as a stack of protocols, with each layer handling specific aspects of the communication process

# TCP/IP Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/063014_1912_TCPIPANDTHE2.jpg)

## Application Layer (Layer 4)

Responsible for providing network services directly to end-users and application programs

* Responsible for making network requests and responding to requests
* Defines which internet services and applications any user can access
* Protocols in the Application Layer determine how the data packets will interact with the receiving devices (Ex: *HTTP*, *HTTPS*, *SMTP*, *SSH*, *FTP*, *DNS*, *etc.*)
* Relies on the underlying layers to transfer the data across the network

## Transport Layer (Layer 3)

Responsible for the end-to-end communication between devices

* Includes protocols to control the flow of traffic across a network (Ex: *TCP*, *UDP*, *etc.*)

## Internet Layer (Layer 2)

Responsible for the logical addressing and routing of packets 

* Ensures that the data packets are delivered to the destination host
* Ensures that IP addresses are attached to data packets to indicate the location of the sender and receiver
* Determines which protocol is responsible for delivering the data packets (Ex: *IP*, *ICMP*, *IGMP*, *etc.*) 

## Network Access Layer (Layer 1)

The Network Access/Data Link layer is responsible for the physical and logical link between devices 

* Corresponds to the physical hardware involved in network transmission (Ex: *Hubs*, *Modems*, *Cables*, *Wiring*, *etc.*)
* Includes protocols that govern the transmission of data frames over specific types of physical media (Ex: *Ethernet*, *Wi-Fi*, *ARP*, *etc.*)
