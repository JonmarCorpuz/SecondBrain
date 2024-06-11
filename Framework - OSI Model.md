The Open Systems Interconnection model is a conceptual framework that breaks down the communication process into seven layers

* Defines a layered approach to network communication, with each layer responsible for specific functions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSI Model Layers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/NCDafYdORnKavM8aa711kg_fa51b33b7ddd4d9497a7a08deb522fe1_C2M2L2_Item02_img2_OSI-model_v3_new.png)

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
* May fragment packets into smaller units for transmission across networks with different maximum packet sizes
* May detect errors in transmitted packets and take corrective actions (Ex: *Requesting retransmission of corrupted packets*, *etc.*)

## 2. Data Link Layer

The data link layer is responsible for providing reliable data transfer across a physical link or medium between neighboring network nodes 

* Implemented in NICs and network switches
* Ensures that data packets are delivered error-free and in sequence over the physical link
* Encapsulates network layer packets into frames by adding header and trailer information for transmission over the physical medium (Ex: *Source and destination MAC addresses*, *Frame type and error detection information*, *etc.*)
* Uses physical addresses to identify devices on the same local network
* Ensures that multiple devices connected to the same network can share the bandwidth efficiently by governing access to the physical medium using different access control methods (Ex: *CSMA/CD for Wi-Fi*, *etc.*)
* Performs error detection and correction mechanisms to ensure data integrity during transmission over the physical medium (Ex: *CRC for error detection and retransmission of corrupted frames*, *etc.*)
* Regulates the flow of data between devices to prevent congestion and buffer overflow (Ex: *Sliding window protocols*, *etc.*)
* Supports *Ethernet*, *Wi-Fi*, *PPP*, *etc.*

## 1. Physical Layer

The physical layer deals with the physical transmission of data between devices

* Includes the actual hardware components and physical medium used for communication
* Defines the characteristics of the physical medium used for communication (Ex: *Cable type*, *Frequency spectrum*, *etc.*)
* Specifies how digital data is converted into signals suitable for transmission over the physical medium
* Determines the maximum transmission rate or bandwidth supported by the physical medium
* Ensures compatibility and interoperability between devices by specifying the physical connectors, pinouts, and electrical characteristics used to connect devices to the network medium

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSI vs TCP/IP

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AlNgVaY3SdO6d9FGNfawRg_6288440de8ae467a872cff2df38909e1_C2M2L2_Item-04_img3_OSI-TCP-layer-comparison.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/j8zOXD2lQta9WYdXdVj1lQ_3f8299c40e714116aa76af397fd175e1_C2M2L2_Item-04_img4_Data-unit-comparison.png)
