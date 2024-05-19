The Transmission Control Protocol provides reliable, connection-oriented communication between devices on a network

* Operates at the Layer 4 of the OSI model

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How TCP Works

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ksdbjlfkldsdfjhbsghlgk.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Connection Establishment

The Transmission Control Protocol uses a three-way handshake to establish a connection between a client and a server

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-19%20125455.png)

### 1. Client Sends SYN Packet

The client sends a synchronize packet to the server to indicate its desire to initiate a connection

### 2. Server Responds With SYN-ACK Packet

The server responds with a SYN-ACK packet to acknowledge the client's request and indicate that it's ready to establish a connection

### 3. Client Responds With ACK Packet

The client sends an ACK packet back to the server to confirm the receipt of the server's SYN-ACK packet and establishes the connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Connection Termination

The Transmission Control Protocol uses a four-way handshake to terminate a connection between a client and a server

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/uhgytfyuijopkbhljnmdsk.png)

### 1. Client Sends FIN Packet

The client sends a finish packet to the server to indicate that it wants to terminate the connection

### 2. Server Sends ACK Packet

The server acknowledges the receipt of the finish packet with an acknowledge packet

### 3. Server Sends FIN Packet

The server sends its own finish packet to the client to indicate that it's ready to terminate the connection

### 4. Client Sends ACK Packet

The client acknowledges the server's finish packet with an acknowledge packet and terminates the session

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# TCP Header

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/HEADER-768x432.png)

## TCP Header Flags

The TCP header flags field controls the behavior of the TCP connection

### URG

The urgent flag indicates that certain data within the TCP segment is urgent and should be prioritized by the receiver

* URG packets are immediately sent to the destined application, regardless of any buffered data 

### ACK

The acknowledge flag indicates the acknowledgement of the receipt of data from the sender

### PSH

The push flag indicates that the receiver should deliver data to the receiving application immediately, without buffering

### RST

The reset flag indicates an immediate termination of the connection

### SYN

The synchronize flag indicates the initiation of a connection

### FYN

The finish flag indicates the termination of a connection

## TCP Header Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/TCP-headersssssss.png)

### Source port

The source port field specifies the port number of the sender process 

### Destination port

The destination port field specifies the port number of the receiver process 

### Sequence Number

The sequence number field indicates the position of the data in the byte stream being sent to help in reassembling the data at the receiving end 

### Acknowledgement number

The acknowledgement number field contains the next sequence number that the sender should expect to receive 

### Data offset

The data offset field indicates the size of the TCP heaer in 32-bit workds to help in locating the start of the TCP data within the TCP segment 

### Reserved

The reserved field is reserved for future use

* Must be set to zero 

### Flags

The flags field controls the behavior of the TCP connection

### Window Size

The window size field specifies the size of the receive window 
