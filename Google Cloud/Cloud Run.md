# Cloud Run Overview

Cloud Run is a serverless platform that allows users to run stateless containerized applications in a fully managed environment without having to worry about server provisioning, management, scaling, and maintenance

* Used when the full features of Kubernetes Engine aren't needed
* Used to run code in response to an event (Ex: *Uploading a file*, *Adding a message to a message queue*, *etc.*) by running a short process coded in a function or by calling a longer-running application that might be runnin on a VM, managed cluster, or App Engine
* Deploys containers within seconds without users having to create a cluster for their containers
* Provides rapid autoscaling for their stateless applications
* The service name and region isn't changeable after you've created a service
* Built on top of the Knative open standard, which is a platform that extends Kubernetes to provide a set of middleware components for building, deploying, and managing cloud-native applications
* Charges only for the resources that were used and requires zero infrastructure management
* Doesn't restrict you to using a fixed set of programming languages
* Has regional availability
* Automatically scales the number of instances based on load

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cloud Run for Anthos

* Allows users to deploy their workloads to Anthos clusters that are running either on-premises, Google Cloud, or a multi-cloud environment
