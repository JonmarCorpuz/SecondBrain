
![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# 802.11 Frame Format

* Depending on the 802.11 version and the message type, some of the fields might not be present in the frame (Ex: *Not all messages use all 4 address fields*, *etc.*)

## Frame Control (2 Bytes)

* Provides information (Ex: *Message type, *Subtype*, *etc.*)

## Duration/ID (2 Bytes)

* Depending on the message type, this field can indicate the time (in microseconds) the channel will be dedicated for transmission of the frame and the identifier for the association (connection)

## Addresses (6 - 24 Bytes)

* One address field is 6 bytes
* Up to four addresses can be present in an 802.11 frame

| Address Type | Description |
| --- | --- |
| Destination Address (DA) | Final recipient of the frame |
| Source Address (SA) | Original sender of the frame |
| Receiver Address (RA) | Immediate recipient of the frame |
| Transmitter Address (TA) | Immediate sender of the frame |

## Sequence Control ( 2 Bytes)

* Used to reassemble fragments and eliminate duplicate frames

## QoS Control (2 Bytes)

* Used in QoS to prioritize certain traffic

## High Troughput Control (4 Bytes)

* Added in 802.11n to enable HT operations
* Also known as Very High Throughput (VHT) Wi-Fi in 802.11ac

## FCS (4 Bytes)

* Used to check for errors in the frame

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# 802.11 Association Process

* APs bridge traffic between wireless clients and other devices, but in order for a client to send traffic through an AP, it must be associated with the AP
* A client must be authenticated and associated with an AP to send traffic through it

| 802.11 Connection State | Desription |
| --- | --- |
| Client isn't authenticated or associated with the AP |  |
| Client is authenticated but not associated with the AP |  |
| Client is authenticated and associated with the AP |  |

* Not authenticated, not associated
  1. Client sends a probe request message to learn about what APs and BSSs are available
    * The client can perform an active scan to learn about what APs and BSSs are available by sending probe reqests and listening for a probe response from an AP
    * The client can perform a passive scan to learn about what APs and BSSs are available by listening for beacon messages from an AP, which are messages that are sent periodically by APs to advertise the BSS
  2. An AP sends a probe response to say that it's available

* Authenticated, not associated
  3. The client sends an authentication request by sending a password to the AP
  4. The AP authenticates the authentication request by sending an authentication response
 
* Authenticated and associated
  5. The client sends an association request
  6. The AP approves the association request by sending back an association response


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# 802.11 Message Types

## Management

* Used to manage the BSS (Ex: *Beacon*, *Probe request*, *Probe response*, *Authentication request*, *Authentication response*, *Assocation request*, *Association response*, *etc.*)

## Control

* Used to control access to the medium, which is radio frequency (Ex: *RTS*, *CTS*, *ACK*, *etc.*)
* Assists with delivery of management and data frames

## Data

* Used to send actual data packets
