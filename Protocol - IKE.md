The Internet Key Exchange protocol is a protocol used in IPsec VPNs to establish and manage SAs and cryptographic keys between two devices before any data is transmitted

* Negotiates the parameters of the SA (Ex: *Encryption algorithms, *Authentication methods*, *Key exchange mechanisms*, *etc.*)
* Facilitates the exchange of the keys used for encryption and authentication between two devices in order to ensure that those keys are securely exchanged

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IKE Phases

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hgfghfgdfhgsdgfgddfhhgdfdfhfdsdgfsdgdsg.PNG)

## Phase 1: IKE SA Establishment

Phase 1 is responsible for establishing a secure channel for further communication by negotiating and establishing the parameters of the IKE SA (Ex: *Authentication methods*, *Encryption algorithms*, *etc.*)

* Performs a Diffie-Hellman key exchange to establish a shared secret key between two devices
* The VPN peers negotiate encryption parameters to ensure compatibility and security between the VPN peers (Ex: *Encryption algorithm*, *Hash algorithm*, *Authentication method*, *etc.*)

### Main Mode

### Agressive Mode

## Phase 2: IPsec SA Establishment

Phase 2 is responsible for securing the actual data transmission between two VPN peers by negotiating and establishing the parameters of the IPsec SA (Ex: *Encryption algorithms*, *Authentication algorithms*, *etc.*)

* The VPN peers exchange the proposals for the parameters of the IPsec SA that was established in the Phase 1 (Ex: *Encryption algorithm*, *Hash algorithm*, *Security protocol*, *etc.*)
* Generates the keys that'll be used for encrypting and decrypting data in order to ensure the confidentiality and integrity of the data during transit

### Quick Mode

