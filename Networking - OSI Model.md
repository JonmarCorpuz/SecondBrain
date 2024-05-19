The Open Systems Interconnection model is a conceptual framework that breaks down the communication process into seven layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSI Model Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/1636366469923.jpg)

## 7. Application Layer

The application layer provides services directly to end-users and applications 

* Enables the communication between different software applications
* Serves as the interface between the network and the software application that utilize the network for communication
* Supports *HTTPS*, *HTTP*, *FTP*, *SMTP*, *etc.*

## 6. Presentation Layer

The presentation layer focuses on data formatting, encryption, compressions, and other functions related to data syntax and semantics

* Ensures that data from the appication layer of one system can be understood by the application layer of another system
* Acts as a translator regardless of differences in data representation
* Allows applications to communicate without worrying about the underlying technical details by abstracting the complexities of data formats and conversions

## 5. Session Layer

The session layer is responsible for establishing, maintaining, and terminating sessions between applications

* Coordinates communication sessions between computers
* Involves managing the dialog control between devices (Ex: *Establishing sessions*, *Maintaining sessions*, *Sychronizing sessions*, *Session checkpointing* *etc.*)
* Ensures that communication sessions between applications are properly managed
* Abstracts the complexities of sessions management, providing a seamless communication experience for applications running on different systems

## 4. Transport Layer

The transport layer is responsible for the end-to-end delivery of data between hosts or endpoints on a network

* Focuses on data segmentation and reassembly, error detection and correction, flow control, and end-to-end connection establishment and termination
* Supports *TCP* and *UDP*

## 3. Network Layer

The network layer focuses on routing data packets from the source to the destination based on logical network addresses

* Assigns logical addresses to devices connected to a network
* Responsible for determining the best path for data packets to reach their destination

## 2. Data Link Layer

## 1. Physical Layer
