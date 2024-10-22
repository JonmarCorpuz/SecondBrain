# VoIP Overview

Voice over Internet Protocol is a technology that allows voice communication and multimedia sessions to be transmitted over the internet rather than traditional telephone networks

* Calls are converted into data packets and transmitted over IP networks using standard internet protocols
* Costs less than traditional telephone service since it uses existing internet connections rather than dedicated telephone lines
* Can be used from anywhere with an internet connection
* Offers voice mail, call forwarding, conference calling, and integration with other communication tools
* Highly scalable

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How VoIP Works

1. Analog-to-digital Conversion: When a user speaks into a microphone or headset, the analog voice signal is converted into digital data, which will represent the voice signal in a format that can be transmitted over digital networks, using an Analog-to-Digital Converter (ADC)

2. Packetization: The digital voice data is then divided into small packets for transmission over IP networks, where each packet contains a portion of the voice data, along with header information (Ex: *Source IP address*, *Destination IP address*, *etc.*)

3. Transmission: The voice packets are then transmitted over the internet or a private IP network using standard networking protocols (Ex: *TCP/IP*, *UDP/IP*)

4. Reassembly: The destination machine will then reassemble the voice packets in the correct order and convert them back into analog voice signals using a Digital-to-Analog Converter (DAC)

5. Voice Playback: The reassembled analog voice signal is then played through a speaker or headset, allowing the recipient to hear the message of the sender
