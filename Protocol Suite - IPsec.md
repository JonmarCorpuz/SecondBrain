The Internet Protocol Security is a suite of protocols that's used to secure IP communications in order to ensure the confidentiality and integrity of data transmitted over IP networks

* Operates at the Network layer of the OSI model (Layer 3)
* Allows entities to authenticate each other in order to ensure that the communication remains between trusted parties and to prevent unauthorized access to network resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPsec Protocols

## Authentication Header

The AH adds a header to the IP packet that includes a cryptographic checksum based on the packet contents in order to provide data integrity, authentication, and anti-replay protection for IP packets

* Ensures that the data hasn't been tampered with during transit
* Doesn't provide encryption for the packet payload

## Encapsulating Security Payload

The ESP encrypts a packet's payload and optionally the authentication data in order to provide confidentiality and integrity

### Transport Mode

The ESP only encrypts and authenticates the payload of the IP packet while leaving the IP header intact

* Alls intermediate devices to examine and route the packet based on its destination IP address
* Commonly used for securing end-to-end communication between two hosts

### Tunnel Mode

The ESP encapsulates and encrypts the entire IP packet within another IP packet

* Provide end-to-end security between the two endpoints
* Makes the original IP packet insible to intermediate devices
* Commonly used in VPN deployments to secure communication between networks or between a VPN client and a VPN gateway

## Internet Key Exchange

The IKE is a key managemetn protocol that's used to negotiate and establish Security Associations between IPsec peers (Ex: *VPN clients*, *VPN gateways*, *etc.*)

* Allows IPsec peers to authenticate each other, establish secure communication channels, and exchange cryptographic keys for encryption and authentication
* Uses various encryption and authentication algorithms to protect the key exchange process in order to ensure the integrity and confidentiality of the excahnged keys

### IKE Negotioation Phases

1. **Phase 1**: IPsec peers establish a secure communication channel and authenticate each other using an authentication method (Ex: *Pre-shared keys*, *Digital certificates*, *etc.*), as well as negotiate encryption and authentication parameters for subsequent communications
2. **Pahse 2**: IPsec peers will then establish Security Associations for IPsec communication (Ex: *Encryption keys*, *Authentication keys*, *Lifetimes*, *etc.*), which will define the parameters for securing communication between IPsec peers in order to ensure the confidentiality, integrity, and authenticity of the data transmitted over the VPN tunnel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
