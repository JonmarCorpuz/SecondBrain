The Internet Key Exchange protocol is a protocol used in IPsec VPNs to establish and manage SAs and cryptographic keys between two devices before any data is transmitted

* Negotiates the parameters of the SA (Ex: *Encryption algorithms, *Authentication methods*, *Key exchange mechanisms*, *etc.*)
* Facilitates the exchange of the keys used for encryption and authentication between two devices in order to ensure that those keys are securely exchanged

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IKE Phases

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hgfghfgdfhgsdgfgddfhhgdfdfhfdsdgfsdgdsg.PNG)

## Phase 1: IKE SA Establishment

In IKE Phase 1, IPsec peers will create an IKE SA (Phase 1 tunnel) in order to set up the communications channel between two devices

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dfdgsgdgsgdsgddddfsdfdsfdsfdasfsadf.png)

* Slow and heavy
* VPN peers will first authenticate each other using an authentication method (Ex: *Pre-shared keys*, *Digital certificates*, *etc.*)
* After successful authentication, each side will create a Diffie-Hellman private key that'll be used to decrypt data and to sign things, and from that private key will derive a corresponding public key, which will be used to encrypt data and exchanged between the two devices, and using their own private key and the other's public key, they'll independently generate a shared Diffie-Hellman key that's the same for both sides
* The two devices will then use the Diffie-Hellman key to exchange key materials and agreements (Ex: *Encryption algorithm*, *etc.*), which they'll then use to independently generate a final Phase 1 symmetrical encryption key that'll be used to encrypt everything that'll be passing through the Phase 1 tunnel
* Diffie-Hellman allows both devices to have the same symmetric encryption key without having it passed between them

### Main Mode

### Agressive Mode

## Phase 2: IPsec SA Establishment

In IKE Phase 2, IPsec peers will then create an IPsec SA (Phase 2 tunnel) in order to set up the VPN

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/hfghdfggjhdfhvhrdgsdgursdhrejftjhtjt.png)

* Faster and agile
* Runs over the Phase 1 tunnel
* Can be torn down when no more interesting traffic occurs while the Phase 1 tunnel remains intact, making establishing a Phase 2 tunnel faster and require less work
* Both devices will agree upon how the VPN will be constructed by first agreeing upon the method of communication (Ex: *The first host will communicate the encryption algorithms that it supports using the Phase 1 tunnel and the second host will pick out the best encryption algorithm from the list that they support as well*)
* After agreeing upon the method of encryption, the key material will then be used to create a symmetricl IPsec key, which is a key that's designed and will be used for large scale data transfer
* The IPsec key will be then used to encrypt and decrypt interesting traffic across the VPN tunnel
* Across each Phase 1 tunnel, there's a pair of SAs, one from right to left and one from left to right, which are used to transfer the data between networks at either side of a VPN

### Quick Mode

