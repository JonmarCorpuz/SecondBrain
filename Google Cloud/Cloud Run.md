# Cloud Run Overview

Cloud Run is a serverless platform that allows users to run stateless applications in a fully managed containerized environment

* Used when the full features of Kubernetes Engine aren't needed
* Supports any application that can be run in a container (Deploys containers within seconds without users having to create a cluster for their containers)
* Provides rapid autoscaling for their stateless applications
* The service name and region isn't changeable after you've created a service (Deploys immutable versions of an application and requires you to create a new container image and then deploy it if you want to make any changes)
* Built on top of the Knative open standard, which is a platform that extends Kubernetes to provide a set of middleware components for building, deploying, and managing cloud-native applications
* Has regional availability
* Automatically scales the number of instances based on load
* Allows you to run multiple versions of the same application and route traffic between them (Useful when you release a new version and want to send a small amount of traffic to the latest version)
* Applications are deployed privately and require authentication to access by default

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Run for Anthos

* Allows users to deploy their workloads to Anthos clusters that are running either on-premises, Google Cloud, or a multi-cloud environment

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Run Deployment Methods

## Code as a Service

* Used when your code is used to respond to web requests or events (Ex: *An API that returns data from a Cloud SQL database*)
* Well suited for web applications, microservices, APIs, and stream data processing
* Designed to listen to an HTTPS endpoint and respond to requests made to that endpoint
* Each Cloud Run service has an endpoint on a unique subdomain of the run.app domain (Custom domains can be used as well)
* Cloud Run manages TLS, meaning that you can use WebSockets, HTTP/2, gRPC with the endpoints

## Code as a Job

* Used when the code executes until a workload is complete (Ex: *Transforming a set of files stored in Cloud Storage and then load it into Cloud SQL*)
* The code performs a task and then terminates
* Can be scheduled to run on regular schedules
* Multiple jobs can work in parallel (Ex: *Multiple containers can be started so that multiple files can be processed simultaneously*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Run Security

* You can control who has access to the application using IAM
* You can control access at the network level by specifying an ingress setting (*Internal*, *Internal and Cloud Load Balancing*, *All*, *etc.*)
* Implementing Cloud IAP

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
