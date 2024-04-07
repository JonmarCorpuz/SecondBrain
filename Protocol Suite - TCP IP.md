The Transmission Control Protocol/Internet Protocol model is a framework consisting of communication protocols that define how data is transmitted and received over networks

* Structured as a stack of protocols, with each layer handling specific aspects of the communication process

# TCP/IP Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/tcp-ip-model.png)

## Application Layer

The Application Layer is the fourth layer of the TCP/IP protocol suite and is responsible for providing network services directly to end-users and application programs

* Responsible for making network requests and responding to requests
* Defines which internet services and applications any user can access
* Protocols in the Application Layer determine how the data packets will interact with the receiving devices (Ex: *[[Protocol (HTTP)|HTTP]]*, *[[Protocol (HTTPS)|HTTPS]]*, *[[Protocol (SMTP)|SMTP]]*, *[[Protocol (SSH)|SSH]]*, *[[Protocol (FTP)|FTP]]*, *[[Protocol (DNS)|DNS]]*, *etc.*)
* Relies on the underlying layers to transfer the data across the network

## Transport Layer

The Transport Layer is the third layer of the TCP/IP protocol suite and is responsible for the end-to-end communication between devices

* Includes protocols to control the flow of traffic across a network (Ex: *[[Protocol (TCP)|TCP]]*, *[[Protocol (UDP)|UDP]]*, *etc.*)

## Internet Layer

The Internet Layer is the second layer of the TCP/IP protocol suite and is responsible for the logical addressing and routing

* Ensures that the data packets are delivered to the destination host
* Ensures that IP addresses are attached to data packets to indicate the location of the sender and receiver
* Determines which protocol is responsible for delivering the data packets (Ex: *[[Protocol (IP)|IP]]*, *[[Protocol (ICMP)|ICMP]]*, *etc.*) 

## Network Access Layer

The Network Access Layer (or Data Link Layer) is the first layer of the TCP/IP protocol suite and is responsible for dealing with the physical connection between devices on the same network

* This layer corresponds to the physical hardware involved in network transmission (Ex: *Hubs*, *Modems*, *Cables*, *Wiring*, *etc.*)
* Includes protocols that govern the transmission of data frames over specific types of physical media (Ex: *Ethernet*, *Wi-Fi*, *ARP*, *etc.*)
