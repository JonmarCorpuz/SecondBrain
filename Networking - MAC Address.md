A Media Access Control address is a unique identifier assigned to a network interface for communication on the physical network segment

* Used in the MAC sublayer of the Layer 2 of the OSI model (Data Link Layer)
* Each MAC address is unique to the NIC, meaning that there shouldn't be two devices on the same local network that have the same MAC address

* ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# MAC Address Types

* The type of a MAC address can be identified by observing the U/L bit (Universal Local bit), which is the 7th bit of the MAC address

## UAA

A Universally Administered Address MAC address is a type of MAC address that's globally unique and assigned to a NIC by the manufacturer at the factory

* Globally unique, permanent, and non modifiable 
* The first 24 bits of the address are the Organizationally Unique Identifier, which is assigned by the manufacturer to ensure the uniqueness of the MAC address
* The remaining 24 bits are assigned by the manufacturer to ensure the uniqueness of the address
* U/L bit is set to 0

## LAA

A Locally Administered Address is a type of MAC address that can be assigned and modified by a network administrator rather than being permanently set by the manufacturer

* Doesn't have to be gloabally unique, it just has to be unique within the network that it's in
* Used for network managing or security reasons (Ex: *Implement certain network configurations where unique MAC addresses are required*, *Address conflict or errors with the factory-assigned MAC addresses*, *etc.*)
* U/L bit is set to 1
