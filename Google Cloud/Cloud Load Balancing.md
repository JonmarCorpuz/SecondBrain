# Cloud Load Balancer Overview

Google Cloud load balancer distributes workloads across you cloud infrastructure

* Provides a single access point to a distributed back end
* Provides high availability (If one of the VMs in the cluster fails, the workload can be directed to the other VMs within the cluster

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Load Balancer Components

| Load Balancer Component | Description |
| --- | --- |
| Backend | A group of endpoings that receive traffic from a Google Cloud Load Balancer |
| Frontend | The configuration that defines how the traffic enters the Google Cloud Load Balancer (*Public IP address*, *Ports*, *etc.*) |
| Host Rule | A configuration that helps route incoming traffic to different backend services based on the hostname in the incoming request (Primarily used in HTTP load balancers) |
| Path Rule | A configuration that directs incoming traffic to different backend services based on the URL path in the incoming request (Primarily used in HTTP load balancers) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSL/TLS Termination

SSL/TLS Termination is the process of decrypting SSL/TLS encrypted traffic at a specific point in the network (Ex: *Load Balancer*, *Reverse Proxy*, *Dedicated SSL terminator device*, *etc.*)

* Typically occurs at the edge of a network to simplify the management of SSL certificates and reduce the load on backend servers, which no longer need to perform SSL decryption
* Simplifies certificate management and reduces CPU load on backend servers, as they don't need to handle encryption and decryption

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SSL/TLS Offloading 

SSL/TLS Offloading is the process of moving the computationally intensive SSL/TLS encryption and decryption tasks (*SSL/TLS Termination*, *etc.*) away from backend servers to a dedicated device or service (Ex: *Load Balancer*, *Proxy*, *etc.*)

* Typically involves both SSL/TLS termination and sometimes re-encryption if traffic is to remain secure between the SSL/TLS Offloading device and the backend servers
* Offloading the SSL/TLS processing workload from backend servers allows them to focus on application logic, improving performance, and scalability

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Load Balancer Options

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/sdfsdfsdfsdfsdfsdfsdfsddfasdasdasfdsfasddas.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/zxxcbvvbcnbnvxcbnbmncvbvcbcvbcvbcvbcv.png)

## External Load Balancers

| External Application Load Balancer Type | Description | 
| --- | --- |
| Global External Application Load Balancer | |
| Regional External Application Load Balancer | |
| Global External Proxy Network Load Balancer | |
| Regional External Proxy Network Load Balancer | |
| Regional External Passthrough Network Load Balancer | |

## Internal Load Balancers

| Internal Load Balancer Type | Description | 
| --- | --- |
| Regional Internal Application Load Balancer | |
| Cross-Region Internal Application Load Balancer | |
| Regional Internal Proxy Network Load Balancer | |
| Cross-Region Internal Proxy Network Load Balancer | |
| Regional Internal Passthrough Network Load Balancer | |
