# IPsec Overview

The Internet Protocol Security is a suite of protocols that's used to secure IP communications between two devices over a public network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dfghfhdfhddfhgsdgsdgewggwer.gif)

* Operates at the Network layer of the OSI model (Layer 3)
* Allows entities to authenticate each other in order to ensure that the communication remains between trusted parties and to prevent unauthorized access to network resources
* Uses asymmetric encryption to establish a VPN tunnel and to exchange symmetric keys, which will be used for any ongoing encryption

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPsec Components

| IPsec Component | Description |
| --- | --- |
| Interesting Traffic | Refers to traffic that matches certain rules (Ex: *Network prefixes*, *Traffic types*, *etc.*) |
| Security Associations | A set of policies and cryptographic keys that define how data should be securely transmitted over a network |
| Diffie-Hellman Private Key | |
| Shared Diffie-Hellman Key | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPsec Protocols

| IPsec Protocol | Description |
| --- | --- |
| Authentication Header (**AH**) | Adds a header to the IP packet that includes a cryptographic checksum based on the packet contents in order to provide data integrity, authentication, and anti-replay protection for IP packets |
| Encapsulation Security Payload (**ESP**) | Encrypts a packet's payload and optionally the authentication data in order to provide confidentiality and integrity |
| Internet Security Association and Key Management Protocol (**ISAKMP**) | Defines the procedures and packet formats to establish, negotiate, modify, and delete SAs, but not how keys are exchanged or authenticated |
| Internet Key Exchange (**IKE**) | A key management protocol that's used within ISAKMP to negotiate and establish Security Associations between IPsec peers (Ex: *VPN clients*, *VPN gateways*, *etc.*) |

## Authentication Header

The AH protocol adds a header to the IP packet that includes a cryptographic checksum based on the packet contents in order to provide data integrity, authentication, and anti-replay protection for IP packets

* Ensures that the data hasn't been tampered with during transit
* Doesn't provide encryption for the packet payload

## Encapsulating Security Payload

The ESP protocol encrypts a packet's payload and optionally the authentication data in order to provide confidentiality and integrity

| ESP Mode | Description |
| --- | --- |
| **Transport Mode** | The ESP protocol only encrypts and authenticates the payload of the IP packet while leaving the IP header intact |
| **Tunnel Mode** | The ESP protocol encapsulates and encrypts the entire IP packet within another IP packet |

### Transport Mode

The ESP protocol only encrypts and authenticates the payload of the IP packet while leaving the IP header intact

* Alls intermediate devices to examine and route the packet based on its destination IP address
* Commonly used for securing end-to-end communication between two hosts

### Tunnel Mode

The ESP protocol encapsulates and encrypts the entire IP packet within another IP packet

* Provide end-to-end security between the two endpoints
* Makes the original IP packet insible to intermediate devices
* Commonly used in VPN deployments to secure communication between networks or between a VPN client and a VPN gateway

## Internet Key Exchange

The IKE protocol is a key management protocol that's used to negotiate and establish Security Associations between IPsec peers (Ex: *VPN clients*, *VPN gateways*, *etc.*)

* Allows IPsec peers to authenticate each other, establish secure communication channels, and exchange cryptographic keys for encryption and authentication
* Uses various encryption and authentication algorithms to protect the key exchange process in order to ensure the integrity and confidentiality of the excahnged keys

### IKE Negotioation Phases

| IKE Negotiation Phase | Description |
| --- | --- |
| **IKE Phase 1** | IPsec peers will create an IKE SA (Phase 1 Tunnel) in order to set up the communications channel between the two devices |
| **IKE Phase 2** | IPsec peers will then create an IPsec SA (Phase 2 Tunnel) in order to set up the VPN |

#### IKE Phase 1 

In IKE Phase 1, IPsec peers will create an IKE SA (Phase 1 tunnel) in order to set up the communications channel between two devices

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dfdgsgdgsgdsgddddfsdfdsfdsfdasfsadf.png)

| IKE Phase 1 Component | Description |
| --- | --- |
| IKE Security Associations | |
| Diffie-Hellman Private Key | |
| Shared Diffie-Hellman Key | |
| Symmetrical IKE Key | |

* Slow and heavy

1. VPN peers will first authenticate each other using an authentication method (Ex: *Pre-shared keys*, *Digital certificates*, *etc.*)
2. After successful authentication, each side will create a Diffie-Hellman private key that'll be used to decrypt data and to sign things (Diffie-Hellman allows both devices to have the same symmetric encryption key without having it passed between them)
3. From that private key will derive a corresponding public key, which will be used to encrypt data and exchanged between the two devices, and using their own private key and the other's public key, they'll independently generate a shared Diffie-Hellman key that's the same for both sides
4. The two devices will then use the Diffie-Hellman key to exchange key materials and agreements (Ex: *Encryption algorithm*, *etc.*), which they'll then use to independently generate a final Phase 1 symmetrical encryption key that'll be used to encrypt everything that'll be passing through the Phase 1 tunnel

#### IKE Phase 2 

In IKE Phase 2, IPsec peers will then create an IPsec SA (Phase 2 tunnel) in order to set up the VPN

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hfghdfggjhdfhvhrdgsdgursdhrejftjhtjt.png)

| IKE Phase 2 Component | Description |
| --- | --- |
| IPsec Security Associations | |
| Symmetrical IPsec Key | |

* Faster and agile
* Runs over the Phase 1 tunnel
* Can be torn down when no more interesting traffic occurs while the Phase 1 tunnel remains intact, making establishing a Phase 2 tunnel faster and require less work
* Across each Phase 1 tunnel, there's a pair of SAs, one from right to left and one from left to right, which are used to transfer the data between networks at either side of a VPN

1. Both devices will agree upon how the VPN will be constructed by first agreeing upon the method of communication (Ex: *The first host will communicate the encryption algorithms that it supports using the Phase 1 tunnel and the second host will pick out the best encryption algorithm from the list that they support as well*)
2. After agreeing upon the method of encryption, the key material will then be used to create a symmetrical IPsec key, which is a key that's designed and will be used for large scale data transfer
3. The IPsec key will be then used to encrypt and decrypt interesting traffic across the VPN tunnel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
