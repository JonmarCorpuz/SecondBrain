CloudFormation is a service that helps users automatically model, provision, and manage AWS and third-party resources by treating infrastructure as code

* Allows users to use programming languages or a simple text file (Ex: *JSON*, *YAML*, *etc.*) to model and provision all the resources needed for their applications across all regions and accounts in an automated and secure manner
* Provides users a common language for them to describe and provision all the infrastructure resources in their cloud environment
* Enables users to create and manage a collection of related AWS resources while provisioning and updating them in an orderly and predictable fashion
* Allows for flexible and dynamic infrastrucutre setup that can be adjusted according to specific requirements by allowing users to define parameters to customize their resources for each deployment
* Automatically handles the order of resource provisioning based on their dependencies
* Allows for easy rollback to a previous state in case of configuration errors
* Allows users to replicate workloads across multiple AWS accounts or Regions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# CloudFormation IaC Templates

CloudFormation Infrastructure as Code templates are declarative code files that define the AWS resources that the user wants to create and manage

* Written in JSON or YAML format
* Allows users to define their entire infrastructure in code that can be versioned and reused by describing what resources are needed but not how to create them
* Each resourced defined in a IaC template is defined with specific properties that configure its settings
* Allows users to include parameters that are passed at runtime
* The return values that are returned after the deployment of a CloudFormation template (Ex: *IP address of an EC2 instance*, *The endpoint of a database*, *etc.*) can be used to query the deployed resources
* Deploying a CloudFormation template creates a stack, which is a collection of AWS resources that are managed as a single unit, allowing users to easily manage all components together 
