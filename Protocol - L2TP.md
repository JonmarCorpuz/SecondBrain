The Layer 2 Tunneling Protocol is a tunneling protocol that's used to establish VPNs or provide remote access to network resources over a public network by creating a tunnel between a VPN client and a VPN gateway over an existing IP network

* Operates at the Data Link layer of the OSI model (Layer 2)
* The established tunnel will be used to encapsulate the data packets being transmitted between the VPN client and the VPN gateway in order to provide a secure communication channel
* Encapsulates the data packets using the L2TP haader, which contains control information, and the Point-to-Point payload, which carries the user data, allowing the data packets to traverse the IP network while maintaining their integrity and confidentiality
* Often used in conjunction with IPsec to provide security features (Ex: *Encryption*, *Authentication*, *etc.*)
