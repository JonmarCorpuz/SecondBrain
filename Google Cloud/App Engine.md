# Google App Engine Overview

Google App Engine is a PaaS offering that enables developers to build and deploy applicaitons on a fully managed serverless platform

* AppEngine is regional and services are deployed across multiple zones (You can't change an application's region once the project is created)
* Allows developers to focus on writing code without worying about provisioning, maintaining, or scaling servers
* Supports various programming languages using pre-configured runtimes
* Allows developers to use custom run-time and write code in any language
* Less flexibility compared to GCE
* Maximum of one application per project (One application can host multiple microservices)
* Uses a combination of resident instances (Instances that run contiunuously) and dynamic instances (Instances that are added based on load)

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
* Automatically scales down and up depending on traffic (Scales down to zero instances if there's no requests being made to the application)

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

# Service Request Routing

| Service Request Routing Method | Description |
| --- | --- |
| Routing With URLs | |
| Routing With Dispatch File | |
| Routing With Cloud Load Balancing | |

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

# GAE YAML Files

| GAE YAML File | Description |
| --- | --- |
| app.yaml | |
| cron.yaml | |
| dispatch.yaml | |
| queue.yaml | |
