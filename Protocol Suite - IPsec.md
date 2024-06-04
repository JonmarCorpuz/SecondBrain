The Internet Protocol Security is a suite of protocols that's used to secure IP communications in order to ensure the confidentiality and integrity of data transmitted over IP networks

* Operates at the Network layer of the OSI model (Layer 3)
* Allows entities to authenticate each other in order to ensure that the communication remains between trusted parties and to prevent unauthorized access to network resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# IPsec Operation Modes

## Transport Mode

Transport mode only encrypts and authenticates the payload of the IP packet while leaving the IP header intact, allowing intermediate devices to examine and route the packet based on its destination IP address

## Tunnel Mode

Tunnel mode encapsulates and encrypts the entire IP packet into another IP packet within that same IP packet in order to provide end-to-end security between the two endpoints

* Makes the original IP packet insible to intermediate devices
