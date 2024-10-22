# Kerberos Overview

Kerberos is a network authentication protocol and system that provides strong authentication for users and services over a non-secure network

* Users who log into a service using Kerberos will be assigned tickets, which represent proof of a previous authentication, that they can present to a service to demonstrate that they have already previously authenticated into the network

# Kerberos Authentication

1. The user sends their username and a timestamp encrypted using a key derived from their password to the Key Distribution Center (KDC)

2. The KDC will create and send back a Ticket Granting Ticket (TGT) and a Session Key
	 * The TGT is a ticket that allows the already authenticated user to request additional tickets to access specific services without having to authenticate themselves over and over again
	 * The Session Key is what will allow a user to generate the requests for the service that they want to request to use

	* The TGT is encrypted using the krbtgt account's password hash and includes a copy of the Session Key as part of its contents, meaning that the KDC has no need to store the Session Key since it can recover it simply by decrypting the TGT if needed

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/d36f5a024c20fb480cdae8cd09ddc09f.png)

3. When a user wants to connect to a service that's on the network that they previously authenticated in, they'll use their TGT to ask the KDC for a Ticket Granting Service (TGS)
	* The TGS is a ticket that allows the already authenticated user to connect to the service that the TGS was created for without having to request to use the service over and over again
	* To request a TGS, the user will send their username and a timestamp encrypted using their Session Key, along with their TGT and a Service Principle Name (SPN), which indicates the service and server name that they want to access

4. The KDC will send back the user a TGS along with a Service Session Key
	* The TGS is encrypted using a key derived from the Service (SRV) Owner's password hash 
	* The TGS contains a copy of the Service Session Key on its encrypted contents so that the Service Owner can access it by decrypting the TGS


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/84504666e78373c613d3e05d176282dc.png)

5. The TGS will then be sent to the desired service that the user wants to access and use to authenticate and establish a connection
	* The desired service will then use its configured account's password hash to decrypt the receiving TGS and validate the Service Session Key in order to establish a connection

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8fbf08d03459c1b792f3b6efa4d7f285.png)
