Amazon Elastic Container Service is a fully managed end-to-end container orchestration service that allows users to easily run, manage, and scale containerized applications using Docker containers and Kubernetes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/_ihG6qHQT-yZDxIWFNrDSg_0173e688f8524deaafdbb3530d7018f1_image.png)

* Simplifies the process of deploying, managing, and scaling containerized applications by handling the underlying infrastructure complexities
* Manages the scheduling and orchestration of Docker containers across a cluster of EC2 instances or AWS Fargate
* Offers built-in high availability and fault tolerance by distributing containers across multiple AZs within an AWS Region
* Support Docker containers and Docker Compose, allowing users to use Docker images to package and deploy their applications
* Uses task definitions to define containers, their configurations, networking, and storage requirements
* Runs tasks and services within ECS clusters
* Seamlessly integrates itself with other AWS services (Ex: *AWS Auto Scaling*, *AWS ELB*, *AWS IAM*, *Amazon CloudWatch*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Managing Containers

To run and manage containers, the user needs to install the Amazon ECS Container Agent on their EC2 instance, which is open-source and responsible for communicating back to the Amazon ECS service about cluster management details

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/QQCbn5jtTp-U9titkpxO6A_26e0fca673034a65bc3b6c18ed2fd8f1_image.png)

* Can be run on both Linux and Windows AMIs
* An instance with the container agent installed is often called a container instance
* An ECS Container is called a task
* Once the Amazon ECS container instances are up and running, the user can then perform actions (Ex: *Launching and stopping containers*, *Scaling in and out*, *Getting the cluster's state*, *Scheduling the placement of containers across their cluster*, *etc.*)

## Task Definition

Preparing an application to run on Amazon ECS, the user needs to create a task definition, which is a text file in JSON or YAML format that describes one or more containers that forms their application, along with various parameters (Ex: *The Docker image to use*, *Networking*, *Resource requirements*, *Data volumes*, *etc.*)

* Each task definition can contain multiple container definitions, each describing a Docker contained to be launched as part of the task
* Defines how containers within the task communicate with each other and with external services (Ex: *Networking mode*, *Port mappings*, *AMI roles*, *etc.*)
* Can include metadata (Ex: *Task family*, *Task revision*, *Task tags*, *etc.*)
* Can specify task constraints, which control how tasks are placed on container instances within ECS clusters
* Can define data volumes that containers use to persist data beyond the lifecycle of the containers, which can be stored on Amazon EBS or Amazon EFS
* Can specify placement constraints to control where tasks are placed within the cluster

