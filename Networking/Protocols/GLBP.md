# GLBP Overview

The Gateway Load Balancing Protocol

* Allows multiple active routers to load balance traffic within a single subnet (Ex: *PC1 and PC2 in the same subnet can both use a different router as their default gateway*)
* 224.0.0.102 multicast address
* 0007.b400.XXYY virtual MAC address where XX is the GLBP group number and the YY is the AVF number

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# GLBP Components

## Active Virtual Gateway

## Active Virtual Forwarders

* Up to four AVFs can be assigned by the AVG (The AVG itself can be an AVF as well)
* Each AVF acts as the default gateway for a portion of the hosts in a subnet

