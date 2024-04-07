The Open Systems Interconnection model is a standardized concept of communication protocols that define how data is transmitted and received over networks

# OSI Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1_17Zz6v0HWIzgiOzQYmO6lA.jpg)

## Application Layer

The Application Layer is the seventh layer of the OSI model and is responsible for providing network services directly to end-users or application processes

* Protocols in the Application Layer determine how the data packets will interact with the receiving devices (Ex: *HTTP*, *SMTP*, *SSH*, *FTP*, *DNS*, *etc.*) 

## Presentation Layer

The Presentation Layer is the sixth layer of the OSI model and is responsible for data translation, encryption, and compression

* Ensures that data is presented in a readable format for the Application Layer
* Deals with issues like character encoding and data format conversions

## Session Layer

The Session Layer is the fifth layer of the OSI model and is responsible for managing sessions or connections between applications on different devices

* Establishes, maintains, and terminates sessions, allowing for full-duplex or half-duplex communication
* Describes when a connection is established between two devices, where an open session between devices allows them to communicate with each other
* Session layer protocols occur to keep the session open while data is being transferred and terminate the session once the transmission is complete
* Responsible for activities other activities, such as authentication, reconnection, and setting checkpoints during a data transfer
	* Checkpoints ensure that interrupted data transmissions resume back at the last session checkpoint that they were at
* Sessions include a request and response between applications
	* Functions in the Session Layer respond to requests for services from processes in the Presentation Layer and send requests for services to the Transport Layer

## Transport Layer

The Transport Layer is the fourth layer of the OSI model and is responsible for ensuring end-to-end communication, error recovery, and flow control between devices

* Handles the speed of data transfer, the flow of the data transfer, and the fragmentation of data packets into smaller fragments to make them easier to transport
	* Fragmented packets needs to be reassembled at their destination so that they can be processed at the Session Layer
	* The speed and rate of the transmission also has to match the connection speed of the destination system

## Network Layer

The Network Layer is the third layer of the OSI model and is responsible for handling the routing, addressing, and logical network topology

* Determines the best path for data to travel from the source to the destination across multiple networks
* The intended destination can be found based on the IP address that resides in the frame of the data packets

## Data Link Layer

The Data Link Layer is the second layer of the OSI model and is responsible for providing error detection and correction, as well as the framing of data for transmission and creating a reliable link between directly connected nodes

* Home to switches on the local network and network interface cards (NICs) on local devices

## Physical Layer

The Physical Layer is the first layer of the OSI model and is responsible for the physical connection between devices

* Defines hardware elements (Ex: *Cables*, *Connectors*, *Transmission medium*, *etc.*)

