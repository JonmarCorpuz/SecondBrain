# App Engine Overview

Google App Engine is a PaaS offering that enables developers to build and deploy applicaitons on a fully managed serverless platform

* AppEngine is regional and services are deployed across multiple zones (You can't change an application's region once the project is created)
* Supports various programming languages using pre-configured runtimes and versioning
* Allows developers to use custom run-time and write code in any language
* Less flexibility compared to Compute Engine (Users have less to manage but have less control over the compute resources that are used to execute the application
* Maximum of one application per project (An App Engine application is a high-level resource created in a project)
* One application can host multiple microservices
* Uses a combination of resident instances (Instances that run contiunuously) and dynamic instances (Instances that are added based on load)
* Dynamic instances are used to autoscale when an application's load increases

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Runtime Environments

* Provides complete isolation from the underlying server's OS as well as other applications running on that server by running applications in a language specific sandbox
* Runs containerized applications in the App Engine environment
* Uses Docker containers
* Pricing is based on instance hours
* The health of the application is monitored by Google and is corrected as needed without any intervention from the user

## Standard Environment

* Well suited for applications that are written in one of the supported languages and don't need OS packages or other compiled software that would have to be installed along with the application code
* Consists of preconfigured, language specific runtime
* Can scale down to zero instances if there are no requests to the application

## Flexible Environment 

* Well suited for applications that can be decomposed into services and where each service can be containerized
* Users can customize their runtime environments by configuring a container (Ex: *Specifying what additional softare or run commands to install during startup using aa Dockerfile*)
* Provides access to background processes and local disks
* Requires a minimum of one instance to run (Even when there are not requests being made to the application)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Runtime Scaling

## Basic Scaling

App Engine will try to keep costs low so it doesn't start another instance until there's a request that can't be serviced in the first generation

* Creates dynamic instances

## Automatic Scaling

App Engine automatically creates new instances as load increases

* Creates dynamic instances

## Manual Scaling

The user specifies the number of instances for each version of a service

* Creates resident instances

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Service

A service is the code executed in the App Engine environment

* Structured to perform a single function with complex applications made up of microservices (Ex: *One microservice may handle API requests for data access while another performs authentication*)
* Enables versions to allow multiple versions of an application to run at the same time (Each version of a service runs on an instance that's managed by App Engine)
* You can have multiple services in a single platform (Each service can have different settings)
* Defined by their source code and their configuration file (The combination of these two consitutes a version of the application)

## Version

* Each version can run in one or more instances
* Multiple versions can co-exist

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Service Request Routing

## Routing With URLs

| URL Path | Description | Syntax |
| --- | --- | --- |
| Default Service | | https://<project_id>.<region_id>.r.appspot.com |
| Specific Service | | https://<service>-dot-<project_id>.<region_id>.r.appspot.com |
| Specific Version of Service | | https://<version_id>-dot-<service>-dot-<project_id>.<region_id>.r.appspot.com |

## Routing With Dispatch File

* Configure dispatch.yaml with routes

## Routing With Cloud Load Balancing

* Configure routes on Load Balancing instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# New Version Deployment Methods

| New Version Deployment Method | Description |
| --- | --- |
| Deploy new version and shift traffic all at one | |
| Deploy new version without immediately shifting traffic to it and then migrate all traffic to it at once | |
| Deploy new version without immediately shifting traffic to it and then gradually shift traffic to it | |
| Deploy new version without immediately shifting traffic to it and then control the pace of migration by splitting traffic | |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Traffic Splitting Methods

* If you have more than one version of an application running, you can split traffic between them

## IP Splitting 

* Splits traffic based on a request's source IP address
* Can have issues (Ex: *IP addresses can change*, *If all requests originate from a corporate VPN with a single IP, this can cause all requests to go to the same version*, *etc.*)
* App Engine creates a hash using the IP address of each version (This can be an issue if users change IP address)

## Cookie Splitting

* The HTTP request header for the `GOOGAPPUID` cookie will contain a hash value between 0 and 999 (Allows the user to access the same version of the application even if they change IP addresses)
* Useful when you want to assign users to versions

## Random Selection

* Useful when you want to evenly distribute workload
* Used when there's no `GOOGAPPUID` cookie set in the HTTP request header

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Files

* Applications are configured through the app.yaml configuration file

## app.yaml

## cron.yaml

## dispatch.yaml

## queue.yaml
