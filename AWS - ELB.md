AWS Elastic Load Balancing is a service provided by AWS that automatically distributes incoming application traffic across multiple targets 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Example.PNG)

* ELB is a regional service, meaning that the user doesn't have to worry about maintaining nodes in each AZ or having to configure high availability themselves
* Automatically scales to handle and distribute incoming traffic across multiple targets in multiple AZs to ensure high availability and fault tolerance
* Designed to handle additional throughput 
* Enables AWS ELB to automatically adjust the number of targets based on changes in demand or health status by integrating with AWS Auto Scaling, ensuring that applications can dynamically scale to handle varying levels of traffic without manual intervention
* Continuously monitors the health of targets by periodically sending health checks
* Supports SSL/TLS termination, allowing it to offload the SSL/TLS encryption and decryption process from the backend targets in order to improve performance and reduce the computational overhead on the targets
* Integrates with various AWS services (Ex: *Amazon EC2*, *Amazon ECS*, *etc.*), allowing it to load balance traffic to a wide range of target types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AWS ELB Types

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Types.PNG)

## Classic Load Balancer (CLB)

* Provides load balancing across multiple EC2 instances
* Supports TCP and HTTP(S) protocols

## Application Load Balancer (ALB)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ALB%20Components.PNG)

* Operates at the Application Layer (Layer 7) 
* Supports advanced features (Ex: *Path-based routing*, *Host-based routing*, *Integration with AWS Lambda functions* ,*etc.*)

### ALB Listener

### ALB Target Group

### ALB Rule

## Network Load Balancer (NLB)

* Operates at the Transport Layer (Layer 4)
* Provides ultra-high performance, low-latency balancing for TCP and UDP traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# ELB Categories

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ELB%20Route%20Traffic%20Example.PNG)

## External-Facing Load Balancer

## Internal-Facing Load Balancer
