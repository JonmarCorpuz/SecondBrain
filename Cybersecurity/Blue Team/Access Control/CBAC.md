# Content-Based Access Control Overview

CBAC is a security mechanism that controls access to network resources based on contextual information (Ex: *Application protocol*, *Session state*, *User identity*, *Time of access*, *Source IP address*, *Destination IP address*, *Packet payload information*, *Packet header information*, *etc.*)

* Operates on the Network, Transport, and Application layers of the OSI model (Layers 3, 4, and 7)
* Performs deep packet inspection to analyze the contents of network packets at the Application layer
* Examines the payload of packets to identify the application protocols being used
* Allows administrators to define access control policies based on contextual information (Ex: *Application type*, *User identity*, *Time of access*, *Session state*, *etc.*)
* Maintains awareness of the state of network connections and sessions, allowing it to make access control decisions based on the context of each connection
* May generate real-time alerts and audit trails upon detecting suspicious activity using CBAC inspection rules
