# Google App Engine Overview

Google App Engine is a PaaS offering that enables developers to build and deploy applicaitons on a fully managed serverless platform

* Manages the underlying computing and network infrastructure
* AppEngine is regional and services are deployed across multiple zones (You can't change an application's region once the project is created)
* Supports various programming languages using pre-configured runtimes
* Allows developers to use custom run-time and write code in any language
* Less flexibility compared to Compute Engine (Users have less to manage but have less control over the compute resources that are used to execute the application
* Maximum of one application per project (One application can host multiple microservices)
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

## Flexible Environment 

* Users can customize their runtime environments by configuring a container
* Provides access to background processes and local disks
* Works well in cases where an application code needs libraries or other third-party software installed
* Requires a minimum of one instance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Runtime Scaling

## Basic 

App Engine will try to keep costs low so it doesn't start another instance until there's a request that can't be serviced in the first generation

* Can cause a delay in the time to process

## Automatic

App Engine automatically creates new instances as load increases

## Manual

The user specifies the number of instances for each version of a service

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Service

* Provide a specific function
* Enables versions to allow multiple versions of an application to run at the same time (Each version of a service runs on an instance that's managed by App Engine)
* You can have multiple services in a single platform
* Each service can have different settings

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

| Traffic Splitting Method | Description | 
| --- | --- |
| IP Splitting |  |
| Cookie Splitting |  |
| Random |  |

## IP Splitting 

* Splits traffic based on a request's source IP address
* Can have issues (Ex: *IP addresses can change*, *If all requests originate from a corporate VPN with a single IP, this can cause all requests to go to the same version*, *etc.*)

## Cookie Splitting

* Cookies (GOOGAPPUID) can be controlled from your application to generate the appropriate cookie to accurately assign users to versions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# App Engine Files

## app.yaml

## cron.yaml

## dispatch.yaml

## queue.yaml
