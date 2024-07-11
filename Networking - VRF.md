Virtual Routing and Forwarding is a technology that's used to create multiple isolated virtual routing tables on a physical router or switch in order to allow different segments of a network to coexist and operate independently on the same hardware

* Provides enhanced network segmentation and security for Layer 3
* Divides a single physical router's interfaces into multiple VRF instances
* Traffic in one VRF cannot be forwarded out of an interface in another VRF (VRF Leaking can be configured to allow traffic to pass between VRFs)
* Commonly used by service providers to allow one device to carry traffic from multiple customers (Each customer's traffic is isolated from the other and can overlapp without any issues since they're each connected to their own VRF)
* Interfaces configured with VRF will be disabled and remove any IP address that was previously assigned
* Interfaces in different VRFs can have the same IP address

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VRF Types

## VRF

* Commonly used to facilitate MPLS

## VRF-Lite

* VRF without MPLS
