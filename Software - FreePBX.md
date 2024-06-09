FreePBX is an open-source GUI that manages and controls a Private Branch Exchange system that was build on top of Asterisk

* Simplifies the complex task of managing and configuring Asterisk with a user-friendly web interface
* Provides a web-based management interface
* Supports various features (Ex: *Ring groups*, *Automatica call distribution*, *Conditional call routing*, *Trunking*, *etc.*)
* Supports various modules that can be added to extend functionality (Ex: *Voicemail*, *Call forwarding*, *IVR*, *Conference calling*, *Queues*, *etc.*)
* Handles VoIP and traditional telephone systems

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# FreePBX Trunking Types

Trunking refers to the configuration and use of trunks, which are communication lines or pathways that connect the PBX system to the telephone network

* Reduces costs by minimizing the number of physical connections to the telephone network
* A single trunk can carry multiple traffic at the same time (Ex: *Voice*, *Data*, *Video*, *etc.*)

## SIP Trunks

SIP trunks are trunks that use the SIP protocol to connect the PBX system to an Internet Telephony Service Provider (ITSP)

* Allows VoIP calls over the Internet

## IAX Trunks

IAX trunks are trunks that are primarily used between Asterisk servers to simplify the setup and bandwidth usage

## Analog and Digital Trunks

Analog and digital trunks are trunks that connect the PBX to traditional PSTN

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Routing Management 

## Outbound Routes

Outbound routes in FreePBX manage how calls from internal users are directed out through the trunks to the outside work

* Determine which trunk or trunks are used when a call is placed from an internal phone
* A single outbound route can be assigned multiple trunks with set priorities so that if the primary trunk is unavailable, the outbound call can be automatically routed through the next available trunk
* Allows users to specify which extensions or groups of extensions that use certain outbound routes

## Inbound Routes

Inbound routes in FreePBX manage how incoming calls from the outside world are directed to internal extensions or services within the PBX system

* Primarily defined by the Direct Inward Dialing numbers or Caller ID
* Can be routed based on the DID numbers and CID to various endpoints within the PBX (Ex: *Extensions*, *Ring groups*, *Queues*, *IVRs*, *etc.*)
* Can be routed differently based on time conditions
