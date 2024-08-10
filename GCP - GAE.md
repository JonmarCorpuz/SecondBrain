Google App Engine is a PaaS offering that enables developers to build and deploy applicaitons on a fully managed serverless platform

* Allows developers to focus on writing code without worying about provisioning, maintaining, or scaling servers
* Supports various programming languages using pre-configured runtimes
* Allows developers to use custom run-time and write code in any language
* Less flexibility compared to GCE
* Maximum of one application per project and per region (One application can host multiple microservices)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Components

| App Engine Component | Description |
| --- | --- |
| 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Runtime Environments

| App Engine Runtime Environment | Description |
| --- | --- |
| Standard |  |
| Flexible |  |

## Standard Environment

* Complete isolation from OS
* Pricing is based on instance hours
* Can scale to zero

## Flexible Environment 

* Makes use of GCE virtual machines
* Provides access to background processes and local disks
* Pricing is based on resource usage
* Requires a minimum of one instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Application Components

| App Engine Application Component | Description |
| --- | --- |
| Service | |
| Version | |

## Service 

* You can have multiple services in a single platform
* Each service can have different settings

## Version

* Each version can run in one or more instances
* Multiple versions can co-exist

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
