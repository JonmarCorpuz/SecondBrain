The AWS Shared Responsibility Model is a model that defines the division of responsibilities between AWS and its customers regarding security and compliance in the cloud

* Outlines which security measures AWS is responsible for implementing and managing, and which security measures customers are responsible for implementing and managing themselves
* The shared responsibility model varies depending on the type of AWS service that's being used

# AWS Responsibility Categories

![eKxMSz7eQe--4LueiSDLeA_768c8a872c8c47b78055a63415700ff1_asset-v1-AWS-AWS-AWS-OTP-AWSD16-1T2023-type-asset-block-Reading_1.5_AWS_Shared_Responsibility_Model.png](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/eKxMSz7eQe--4LueiSDLeA_768c8a872c8c47b78055a63415700ff1_asset-v1-AWS-AWS-AWS-OTP-AWSD16-1T2023-type-asset-block-Reading_1.5_AWS_Shared_Responsibility_Model.png)

## Security of the Cloud (AWS)

AWS is responsible for the security and integrity of the Cloud infrastructure (Ex: *Hardware infrastructure*, *Software infrastructure*, *etc.*) and its foundational services

* Protects and secures AWS Regions, AZs, and data centers, down to the physical security of the buildings
* Manages the hardware, software, and networking components that run AWS services 
* Manages the underlying infrastructure and foundation services in infrastructure services in container services
* Operates the infrastructure layer, OS, and platforms, as well as server-side encryption and data protection, in abstracted services

## Security in the Cloud (Customer)

Customers are responsible for the security in the Cloud for their assets (Ex: *Data encryption*, *OS and network configuration*, *Identity and Access Management*, *Application-level security*, *etc.*)

* Controls the OS and application platform, as well as encrypting, protecting, and managing customer data in infrastructure services (AWS will manage the infrastructure and foundation services)
* Encrypts and protecting customer data through network firewalls and backups in container services (AWS will manage the infrastructure and foundation services, OS, and application platform)
* Manages customer data and protecting it through client-side encryption in abstracted services (AWS will operate the infrastructure layer, OS, and platforms, as well as server-side encryption and data protection)
