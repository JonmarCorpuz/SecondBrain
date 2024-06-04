OpenVPN is an open-source VPN software that provides a secure and reliable way to establish encrypted connections over a public network

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/rebdjfdsjbvdihfgblsdjfdsnkf.png)

* Supports client-to-server and site-to-site VPN deployments

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# How OpenVPN Works

1. **Connection Initiation**: The VPN client initiates a connection to the VPN gateway by sending a request to establish a secure channel, which includes information such as the VPN gateway's IP address or domain name, authentication credentials, and encryption preferences
2. **Authentication**: Once the connection request is received by the VPN gateway, it'll authenticate the client using the credentials that they provided
3. **Key Exchange**: If the authentication was successful, the VPN client and the VPN gateway will exchange cryptographic keys and negotiate encryption parameters using the SSL/TLS protocol
4. **Tunnel Establishment**: OpenVPN will then establish a secure tunnel between the VPN client and the VPN gateway using the negotiated encryption parameters, which will encapsulate all the data being transmitted between the two in order to protect it from interceprtion or tampering by unauthorized parties
5. 
