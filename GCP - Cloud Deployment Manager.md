Google's Cloud Deployment Manager is an infrastructure management service that allows users to automate the creation and management of their Google Cloud resources using YAML configuration files

* Helps avoid configuration drift
* Can act as a version control for a user's environments
* Resources created by the Deployment Manager should always be modified using the Deployment Manager
* Deployment Manager understands dependencies (Ex: *Creates VPCs first, then subnets, and then the database*, *etc.*)
* Users pay ony for the resources that was provisioned to them

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Deployment Manager Components

| Cloud Deployment Manager Component | Description |
| --- | --- |
| Deployment | A collection of resources that are deployed and managed together |
| Manifest | Read-only object that contains original deployment configuration |
