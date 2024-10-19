The Transmission Control Protocol provides reliable, connection-oriented communication between devices on a network

* Provides Layer 4 addressing using port numbers
* **Connection-oriented**, meaning that before sending data to the destination host, the two hosts communicate to establish a connection, and once the connection is established, the data exchange begins
* Provides **reliable communication** since the destination host must acknowledge that it received each TCP segment by using the acknowledgement field of the TCP header
* Provides **sequencing** by adding sequence numbers in the sequencing field of the TCP header to allow destination hosts to put segments in the correct order even if they arrive out of order
* Provides **flow control**, meaning that the destination host can tell the source host to either decrease or increase the rate that data is sent so that it isn't overwhelmed by receiving traffic faster that it can process it
* Provides **TCP retransmission**, meaning that if a segment isn't acknowledged after a certain amount of time, it'll be sent again

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# TCP Communication

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ksdbjlfkldsdfjhbsghlgk.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Connection Establishment (Three-Way Handshake)

The Transmission Control Protocol uses a three-way handshake to establish a connection between a client and a server

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-19%20125455.png)

1. The client sends a synchronize (**SYN**) packet to the server to indicate its desire to initiate a connection
2. The server responds with a **SYN-ACK** packet to acknowledge the client's request and indicate that it's ready to establish a connection
3. The client sends an **ACK** packet back to the server to confirm the receipt of the server's SYN-ACK packet and establishes the connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Connection Termination (Four-Way Handshake)

The Transmission Control Protocol uses a four-way handshake to terminate a connection between a client and a server

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/uhgytfyuijopkbhljnmdsk.png)

1. The client sends a finish (**FIN**) packet to the server to indicate that it wants to terminate the connection
2.1 The server acknowledges the receipt of the finish packet with an acknowledge (**ACK**) packet
2.2 The server sends its own finish (**FIN**) packet to the client to indicate that it's ready to terminate the connection
3. The client acknowledges the server's finish packet with an acknowledge (**ACK**) packet and terminates the session

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## TCP Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/HEADER-768x432.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/TCP-headersssssss.png)

### Source port (16 Bits)

The source port field specifies the port number of the sender process 

### Destination port (16 Bits)

The destination port field specifies the port number of the receiver process 

### Sequence Number (32 Bits)

The sequence number field indicates the position of the data in the byte stream being sent to help in reassembling the data at the receiving end 

* Unique to the host only
* Hosts will set a random initial sequence number when initiating communication with another device

### Acknowledgement number (32 Bits)

The acknowledgement number field contains the next sequence number that the sender should expect to receive 

* TCP uses forward acknowledgement, which indicates the sequence number of the next segment that the host expects to receive (Ex: *During a TCP Three-Way Handshake, PC1 sends a SYN with a sequence number of 10 and PC2 will reply with an ACK with an ackownledgement value of 11, PC1 will then send back an ACK with a sequence number of 11 since that's what PC2 is expecting*)

### Data offset

The data offset field indicates the size of the TCP heaer in 32-bit workds to help in locating the start of the TCP data within the TCP segment 

### Reserved

The reserved field is reserved for future use

* Must be set to zero 

### Flags

The flags field controls the behavior of the TCP connection

| TCP Flag | Meaning | Purpose |
| --- | --- | --- |
| **URG** | Urgent | Indicates that certain data within the TCP segment is urgent and should be prioritized by the receiver (URG packets are immediately sent to the destined application, regardless of any buffered data ) |
| **ACK** | Acknowledge | Indicates the acknowledgement of the receipt of data from the sender |
| **PSH** | Push | Indicates that the receiver should deliver data to the receiving application immediately, without buffering |
| **RST** | Reset | Indicates an immediate termination of the connection |
| **SYN** | Synchronize | Indicates the initiation of a connection | 
| **FYN** | Finish | Indicates the termination of a connection | 

### Window Size

The window size field specifies the size of the receive window 

* Used for flow control
* Allows more data to be sent before an acknowledgement is required by using a sliding window, which is a feature that manages the amount of data that can be sent before receiving an acknowledgement from the receiver

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Port Numbers

| Port Number | Protocol |
| --- | --- |
| 20 | FTP Data |
| 21 | FTP Control |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP | 
| 110 | POP3 |
| 443 | HTTPS |
