AWS Fargate is a serverless compute engine for containers that allows users to run containers without having to manage the underlying infrastructure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AWS%20Fargate.png)

* Scales and manages the infrastructure by allocating the right amount of compute, eliminating the need to choose and handle EC2 instances and cluster capacity and scaling
* Allows users to focus on building and deploying applications in containers
* Abstracts away the underlying infrastructure, enabling users to deploy and manage containers without managing servers or clusters
* Allows users to deploy containerized applications using familiar orchestration tools and APIs
* Supports both task-level and pod-level scheduling, meaning that users can define task definitions (for ECS) and pod specifications (for EKS) and Fargate will automatically provision the necessary compute resources to run their containers
* Ensures that applications remain isolated from each other by running each task or pod in their own isolated environment
* Automatically scales based on workload demand
* Seamlessly integrates with other AWS services
* Provides built-in security features (Ex: *Encryption at rest and in transit*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/AWS%20Container.png)
