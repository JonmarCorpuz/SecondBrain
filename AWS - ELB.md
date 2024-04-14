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

* Provides load balancing across multiple EC2 instances
* Supports TCP and HTTP(S) protocols

## Application Load Balancer (ALB)

* Operates at the Application Layer (Layer 7)
* Routes traffic based on request data (*URL path*, *HTTP headers*, *HTTP methods*, *Source IP address*, *etc.*)
* Sends responses directly to the client (*Fixed responses*, *Redirect clients*, *etc.*)
* Supports TLS offloading
* Able to authenticate users before they're allowed to pass through the load balancer by using the OpenID Connect protocol and integrating with other AWS services
* Uses the round-robin routing algorith to ensure that each server receives the same number of requests
* Uses the least outstanding request routing algorithm
* Provides sticky sessions that are based on the cookie of the client
* Supports advanced features (Ex: *Path-based routing*, *Host-based routing*, *Integration with AWS Lambda functions* ,*etc.*)

## Network Load Balancer (NLB)

* Operates at the Transport Layer (Layer 4)
* Provides ultra-high performance, low-latency balancing for TCP and UDP traffic
* Uses a flow hash routing algorithm, which is based on the protocol, source IP address, source port, destination IP address, destination port, and the TCP sequence number
* Provides sticky sessions that are based on the source IP address of the client
* Supports TLS offloading
* Can handle millions of requests per second
* Supports static and elastic IP addresses
* Preserves source IP addresses of clients

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ELB Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/i9pCEqt4SsCB_h-15irXaw_a37c73d64d7e4da1ab2055a798c5cef1_image.png)

## ELB Listener

* A port and the protocol to be used must be defined when creating a listener

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

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8-YYaL_kRKKfxEta7-itsA_fd10181ed20449a28e87cf67ded460f1_image.png)
