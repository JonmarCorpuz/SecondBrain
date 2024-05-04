Layered architecture refers to the hierarchical organization of network protocols and functionalities into distinct layers that are each responsible for specific tasks

* Simplifies network design and implementation by breaking down complex networking functionalities into manageable layers that operate independently of the others
* Facilitates interoperability, scalability, and easier troubleshooting within networking systems
* Enables the development of standardized protocols and protocol suites

# Layered Architecture Types

## Open Systems Interconnection

The Open Systems Interconnection model is a standardized concept of communication protocols that define how data is transmitted and received over networks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/OSI-7-layers.jpg)

### Application Layer (Layer 7)

The Application Layer is the seventh layer of the OSI model and is responsible for providing network services directly to end-users or application processes

* Protocols in the Application Layer determine how the data packets will interact with the receiving devices (Ex: *HTTP*, *SMTP*, *SSH*, *FTP*, *DNS*, *etc.*) 

### Presentation Layer (Layer 6)

The Presentation Layer is the sixth layer of the OSI model and is responsible for data translation, encryption, and compression

* Ensures that data is presented in a readable format for the Application Layer
* Deals with issues like character encoding and data format conversions

### Session Layer (Layer 5)

The Session Layer is the fifth layer of the OSI model and is responsible for managing sessions or connections between applications on different devices

* Establishes, maintains, and terminates sessions, allowing for full-duplex or half-duplex communication
* Describes when a connection is established between two devices, where an open session between devices allows them to communicate with each other
* Session layer protocols occur to keep the session open while data is being transferred and terminate the session once the transmission is complete
* Responsible for activities other activities, such as authentication, reconnection, and setting checkpoints during a data transfer
	* Checkpoints ensure that interrupted data transmissions resume back at the last session checkpoint that they were at
* Sessions include a request and response between applications
	* Functions in the Session Layer respond to requests for services from processes in the Presentation Layer and send requests for services to the Transport Layer

### Transport Layer (Layer 4)

The Transport Layer is the fourth layer of the OSI model and is responsible for ensuring end-to-end communication, error recovery, and flow control between devices

* Handles the speed of data transfer, the flow of the data transfer, and the fragmentation of data packets into smaller fragments to make them easier to transport
	* Fragmented packets needs to be reassembled at their destination so that they can be processed at the Session Layer
	* The speed and rate of the transmission also has to match the connection speed of the destination system

### Network Layer (Layer 3)

The Network Layer is the third layer of the OSI model and is responsible for handling the routing, addressing, and logical network topology

* Determines the best path for data to travel from the source to the destination across multiple networks
* The intended destination can be found based on the IP address that resides in the frame of the data packets

### Data Link Layer (Layer 2)

Responsible for formatting data into frames and preparing it for transmission over the physical layer, as well as handling the reception of incoming frames

### Physical Layer (Layer 1)


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Transmission Control Protocol/Internet Protocol

The Transmission Control Protocol/Internet Protocol is a set of networking protocols that define how data is transmitted and received over the Intenert

* Structured as a stack of protocols, with each layer handling specific aspects of the communication process
* Provides the foundation for communication in computer networks by specifying how devices establish connections, transfer data, and route packets between networks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/063014_1912_TCPIPANDTHE2.jpg)

### Application Layer (Layer 4)

Responsible for providing network services directly to end-users and application programs

* Responsible for making network requests and responding to requests
* Defines which internet services and applications any user can access
* Protocols in the Application Layer determine how the data packets will interact with the receiving devices (Ex: *HTTP*, *HTTPS*, *SMTP*, *SSH*, *FTP*, *DNS*, *etc.*)
* Relies on the underlying layers to transfer the data across the network

### Transport Layer (Layer 3)

Responsible for the end-to-end communication between devices

* Includes protocols to control the flow of traffic across a network (Ex: *TCP*, *UDP*, *etc.*)

### Internet Layer (Layer 2)

Responsible for the logical addressing and routing of packets 

* Ensures that the data packets are delivered to the destination host
* Ensures that IP addresses are attached to data packets to indicate the location of the sender and receiver
* Determines which protocol is responsible for delivering the data packets (Ex: *IP*, *ICMP*, *IGMP*, *etc.*) 

### Network Access Layer (Layer 1)

The Network Access/Data Link layer is responsible for the physical and logical link between devices 

* Corresponds to the physical hardware involved in network transmission (Ex: *Hubs*, *Modems*, *Cables*, *Wiring*, *etc.*)
* Includes protocols that govern the transmission of data frames over specific types of physical media (Ex: *Ethernet*, *Wi-Fi*, *ARP*, *etc.*)
