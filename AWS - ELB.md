AWS Elastic Load Balancing is a service provided by AWS that automatically distributes incoming application traffic across multiple targets 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Example.PNG)

* ELB is a regional service, meaning that the user doesn't have to worry about maintaining nodes in each AZ or having to configure high availability themselves
* Automatically scales to handle and distribute incoming traffic across multiple targets in multiple AZs to ensure high availability and fault tolerance
* Designed to handle additional throughput 
* Enables AWS ELB to automatically adjust the number of targets based on changes in demand or health status by integrating with AWS Auto Scaling, ensuring that applications can dynamically scale to handle varying levels of traffic without manual intervention
* Continuously monitors the health of targets by periodically sending health checks
* Supports SSL/TLS termination, allowing it to offload the SSL/TLS encryption and decryption process from the backend targets in order to improve performance and reduce the computational overhead on the targets
* Integrates with various AWS services (Ex: *Amazon EC2*, *Amazon ECS*, *etc.*), allowing it to load balance traffic to a wide range of target types
* Can load balance to IP addresses, meaning that it can work in a hybrid mode and load balance to on-premises servers as well

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AWS ELB Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Types.PNG)

## Classic Load Balancer (CLB)

A Classic Load Balancer is the classic load balancer that automatically distributes incoming application or network traffic across multiple targets to ensure that no single target becomes overwhelmed with traffic

* Supports OSI Layer 4 (TCP) and OSI Layer 7 (HTTP/HTTPS) load balancing
* Performs health checks on registered instances to ensure that only healthy instances receive traffic
* Helps improve fault tolerance and availability by distributing traffic evenly across multiple AZs within a single AWS region
* Ensures that requests from the same client are consistently routed to the same target instance by integrating session stickiness (Session affinity)
* Can seamlessly integrate with other AWS services 

## Application Load Balancer (ALB)

An Application Load Balancer is an OSI Layer 7 load balancer that automatically distributes traffic based on HTTP or HTTPS requests in order to provide high availability, scalability, and flexibility for applications and other resources

* Allows for dynamic scaling and flexibility by routing traffic to target groups based on the contents of an HTTP/HTTPS request (Ex: *HTTP/HTTPS header*, *URLs*, *etc.*)
* Provides layer 7 functionalities directly to the client (*Fixed responses*, *Redirections*, *Session resumption*, *Cross-zone load balancing*, *etc.*)
* Able to authenticate users before they're allowed to pass through the load balancer by using the OpenID Connect protocol and integrating with other AWS services
* Uses the round-robin routing algorith to ensure that each server receives the same number of requests
* Uses the least outstanding request routing algorithm
* Provides sticky sessions that are based on the cookie of the client
* Supports additonal features (Ex: *Path-based routing*, *Host-based routing*, *Integration with AWS Lambda functions* , *TLS offloading*, *WebSocket traffic*, *etc.*)
* Can seamlessly integrate with other AWS services

## Gateway Load Balancer (GLB)

* Designed to help users deploy, scale, and manage third-party virtual appliances
* Used to give one gateway for distributing traffic across multipe virtual appliances while scaling them based on demand

## Network Load Balancer (NLB)

A Network Load Balancer is an OSI layer 4 load balancer for routing connections to various targets within a VPC

* Handles extermely high volumes of traffic while maintaining ultra-low latency
* Handles traffic based on IP protocol data, making it highly efficient for handling TCP and UDP traffic
* Provides a single static IP address for each AZ it operates in, allowing clients to establish connections directly to the load balancer
* Uses a flow hash routing algorithm
* Provides sticky sessions that are based on the source IP address of the client
* Preserves source IP addresses of clients
* Supports additional features (Ex: *TLS offloading*, *Static and elastic IP addresses*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ELB Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/i9pCEqt4SsCB_h-15irXaw_a37c73d64d7e4da1ab2055a798c5cef1_image.png)

## ELB Listener

An ELB listener is a configuration that defines how the ELB should handle incoming client connections

* A port and the communication protocol (Ex: *HTTP*, *HTTPS*, *DNS*, *TCP*, *etc.*) that the ELB will use to receive incoming traffic must be defined when creating an ELB listener
* An additional port and communication protocol (Ex: *HTTP*, *HTTPS*, *DNS*, *TCP*, *etc.*) that the ELB will use to communicate with a target group must be defined when creating an ELB listener
* Incoming traffic will then be forwarded to the appropriate target group (Ex: *EC2 instances*, *Containers*, *IP addresses*, *Lambda functions*, *etc.*)
* Users can configure multiple endpoints (ports and protocols) on their ELB to handle different types of traffic 

## ELB Target Group

* The user defines the type of backend that they want to direct their traffic to
* A health check needs to be defined for each target group

## ELB Rule

* Enables users to associate a target group to a listener
* Made up of a condition that decides which target group to send the traffic to

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ELB Routing Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Route%20Traffic%20Example.PNG)

## External-Facing Load Balancer

## Internal-Facing Load Balancer

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ELB Features

## Connection Draining

Connection draining allows already existing connections with an instance that's being deregistered or that's become unhealthy to remain while preventing new connections from happening

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8-YYaL_kRKKfxEta7-itsA_fd10181ed20449a28e87cf67ded460f1_image.png)

* ELB will monitor the number of active connections to the unhealthy instance and will wait until there are no more active connections before completely removing the instance from its pool of active instances
* Ensures that active connections aren't abruptly terminated when instances are removed from service
* Helps maintain smooth operation and user experience changes in an infrastructure

## Health Checking

A health check is a mechanism used to monitor the health of the reigstered instances behind the load balancer to ensure that only healthy instances receive traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8-YYaL_kRKKfxEta7-itsA_fd10181ed20449a28e87cf67ded460f1_image.png)

* Defined by users by specifying the protocol, port, and endpoint that the load balancer should use to perform health checks
* The ELB will periodically send health check requests to the registered instance based on the configuration parameters
* An instance is healthy either when it replies back to the ELB with a 200 HTTP response or if a TCP connection towards the backend of an instance is successful
* Determines if an instance is capable of handling traffic
* Unhealthy instances will automatically stop receiving traffic until it becomes healthy again
* Improves the availability and reliability of a network or application
