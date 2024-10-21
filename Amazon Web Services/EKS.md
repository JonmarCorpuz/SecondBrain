Amazon Elastic Kubernetes Service is a managed Kubernetes service that allows users to simplify the process of deploying, managing, and scaling containerized applications using Kubernetes on AWS infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Amazon%20EKS.png)

* Provides a fully managed Kubernetes control plane, eliminating the need for users to manage the control plane's infrastructure
* Allows users to quickly create Kubernetes clusters using the AWS Management Console, CLI or API
* Enables users to scale their Kubernetes clusters dynamically based on workload demand by allowing them to add or remove worker nodes (EC2 instances) to accommodate changes in resource requirements
* Automatically adjusts the cluster capacity accordingly and distributes Kubernetes master nodes across multiple AZs within an AWS Region, ensuring high availability and fault tolerance against infrastructure failures
* Seamlessly integrates with other AWS services (Ex: *AWS ELB, AWS IAM*, *Amazon VPC*, *etc.*)
* Offers built-in security features (Ex: *Encryption at rest and in transit*, *etc.*)
* Follows a pay-as-you-go pricing model

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Managing Containers

To run and manage containers, the user needs to install the Amazon EKS Container Agent on their EC2 instance

* An instance with the container agent installed is often called a worker node
* An EKS Container is called a pod
* Runs on top of Kubernetes
