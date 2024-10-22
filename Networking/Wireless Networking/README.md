Wireless networking refers to the technology that allows devices to connect and communicate with each other without the need for physical cables or wires

* Uses radio waves or other wireless signals to transmit data between devices
* All devices within range receive all frames (Just like devices connected to an Ethernet hub), which can lead to data privacy concerns and collisions when devices communicate on the same channel at the same time, making privacy of data within the LAN a greater concern
* It's important to encrypt the data within the LAN or else anyone with a device in range of the transmitter can access that data
* Uses Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA) to facilitate half-duplex communications (A device will wait a random period of time for other devices to stop transmitting before it transmits data itself)
* Wireless communications are regulated by various international and national bodies

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wireless Networking Components

## Wireless Access Points

A wireless AP is a device that connects to a wired network and provides wireless connectivity to devices in its range

| AP Operational Mode | Description |
| --- | --- |
| Repeater | Extends the range of a BSS by retransmitting any signal it receives from the AP |
Universal Workgroup Bridge (uWGB) | Operates as a wireless client of another AP, which can be used to connect wired devices to the wireless network |
Workgroup Bridge (WGB) | Cisco-proprietary version of uWGB |
| Outdoor Bridge | Connects networks over long distances without a physical cable connecting them by using specialized antennas that focus most of the signal power in one direction |

## Wireless Routers

A wireless router is a device that combines the functions of a router and an AP

## Wireless Network Interface Cards

A wireless NIC is a hardware that's installed in devices to enable wireless communication

## Wireless Controllers

A wireless controller is a device or software application that manages and controls multiple wireless APs in a centralized manner

* Allows administrators to centrally configure and manage settings for all connected APs (Ex: *SSIDs*, *Security policies*, *Radio frequencies*, *etc.*)
* Facilitates the distribution and installation of firmware updates to all APs from a single interface to ensure uniformity and security compliance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wireless Standards

## 802.11 (Wi-Fi)

* The Wi-Fi Alliance tests and certifies equipment for 802.11 standards compliance interoperability with other devices

### 802.11b

* Frequency: 2.4 GHz
* Maximum speed of up to 11 Mbps 

### 802.11a

* Frequency: 5 GHz
* Maximum speed of up to 54 Mbps

### 802.11g

* Frequency: 2.4 GHz
* Maximum speed of up to 54 Mbps

### 802.11n

* Frequency: 2.4 GHz and 5 GHz
* Maximum speed of up to 600 Mbps

### 802.11ac

* Frequency: 5 GHz
* Maximum speed of up to 3.5 Gbps 

### 802.11ax

* Frequency: 2.4 GHz and 5 GHz
* Maximum speed of up to 9.6 Gbps

### 802.11ay

* Frequency: 60 GHz
* Maximum speed of up to 100 Gbps

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wireless Deployment Models

## Hardware-Based Controllers

## Virtual Controllers

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wireless Signal

## Wireless Signal Quality Factors

* Signal range
* Devices using the same channels can cause interference (Ex: *A wireless LAN in your neighbor's apartment*, *etc.*)

| Wireless Signal Issue | Description |
| --- | --- |
| Signal Absorption | When a wireless signal passes through a material and is converted into heat, weakening the original signal |
| Signal Reflection | When a signal bounces off of a material (Ex: *Metal*, *etc.*) |
| Signal Refraction | When a wave is bent when entering a medium where the signal travels at a different speed (Ex: *Glass*, *Water*, *etc.*) |
| Signal Diffraction | When a wave encounters an obstacle and travels around it, which can result in blind spots behind the obstable |
| Signal Scattering | When a material causes a signal to scatter in all directions (Ex: *Dust*, *Smog*, *Uneven surfaces*, *etc.*) |

## Radio Frequency

* The sender applies an alternating current to an antenna to send wireless signals, which creates electromagnetic fields which propagate out as waves, which can be measured in multiple ways (Ex: *Amplitude*, *Frequency*, *etc.*)
* The visible frequency range is about 400 THz to 790 THz
* The radio frequency range is from 30 Hz to 300 Hz and is used for many purposes
* Wi-Fi uses two main frequency ranges (bands)

| Electromagnetic Wave Measurement | Description |
| --- | --- |
| Amplitude | The maximum strengh of the electric and magnetic fields |
| Frequency | The number of up and down cycles per a given unit of time (The most common measurement of frequency is hertz) |
| Period | The amount of time of one cycle |

| Wi-Fi Frequency Band | Frequency Range | 
| --- | --- |
| 2.4 GHz Band | 2.400 GHz to 2.4835 GHz |
| 5 GHz Band | 5.150 GHz to 5.825 GHz |

## Channels

* Each Wi-Fi band is divided up into multiple channels (Ex: *The 2.4 GHz band is divided into several channels, each with a 22MHz range*, *etc.*)
* You can use any channel in a small wireless LAN that only has a single AP
* You must use multiple channels in large wireless LANs to avoid using overlapping channels in order to avoid interference (In the 2.4 GHz band, it's recommended to use channels 1, 6, and 11)
* The 5GHz band consists of non-overlapping channels, so it's much easier to avoid interference between adjacent wireless APs
* Placing APs in a honeycomb pattern helps provide complete coverage of an area without interference between channels

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Service Sets

* 802.11 defines different kinds of service sets, which are groups of wireless network devices
* All devices in a service set share the same Service Set Identifier (SSID), which is a human-readable name that identifies the service set and doesn't need to be unique

## Independent Basic Service Sets

An IBSS is a wireless network in which two or more wireless devices connect to each other without using an AP

* Also called an AD HOC network
* Can be used for file transfer (Ex: *AirDrop*, *etc.*)
* Not scalable beyond a few devices

## Infrastructure Service Sets

* Each wireless BSS or ESS is mapped to a VLAN in the wired network

### Basic Service Set

* A Basic Service Set ID (BSSID) is the MAC address of the AP's radio, which uniquely identifies the AP (Other APs can use the same SSID, but not the same BSSID)
* Wireless devices will request to associate with the BSS
* Wireless devices that have associated with the BSS are called clients or stations
* The area around an AP where its signal is usable is called a Basic Service Area (BSA)
* Clients communicate with the AP and not directly with each other

### Extended Service Sets

* Allows you to create larger wireless LANs beyond the range of a single AP
* APs with their own BSSs are connected by a wired network
* Each BSS uses the same SSID
* Each BSS has a unique BSSID
* Each BSS uses a different channel to avoir interference
* Provides a seamless Wi-Fi experience when moving between APs by performing roaming, which is when clients are able to pass between APs without having to reconnect
* BSAs should overlap about 10-15%

## Mesh Basic Service Sets

* Can be used in situations where it's difficult to run an Ethernet connection to every AP
* Mesh APs uses two radios, one to provide a BSS to wireless clients, and another one to form a backhaul network, which is used to bridge traffic from AP to AP
* Contains at least one Root Access Point (RAP), which is an AP that's connected to the wired network
* APs that aren't a RAP are called Mesh Access Points (MAPs)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Distribution System

* The upstream wired network is called the Distribution System (DS)
* It's possible for an AP to provide multiple wireless LANs, each with a unique SSID
* Each wireless LAN is mapped to a separate VLAN and connected to the wired network via a trunk
* Each wireless LAN uses a unique BSSID, usually by incrementing the last digit of the BSSID by one

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Wireless Network Security

* It's important to encrypt wireless traffic sent between the wireless clients and the AP because wireless signals aren't contained within a wire, meaning that any device within range of the signal can receive the traffic
* All devices on the WLAN will use the same encryption protocol, however each client will use a unique encryption/decryption key so that other devices can't read its traffic
* A group key is used by an AP to encrypt traffic that it wants to send to all of its clients (All of the clients associated with the AP keep that key so that they can decrypt the traffic)
* A Message Integrity Check (MIC) is added to messages to help protect their integrity
