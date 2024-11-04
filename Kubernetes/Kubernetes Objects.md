# Kubernetes Objects Overview

A Kubernetes object is a persistent entity in the Kubernetes system

* Used to represent the state of your cluster (*What containerized applications are running and on which nodes*, *The resources available to those applications*, *The policies around how those applications behave*)
* Once you create the object, the K8 system will constantly work to ensure that the object exists (By creating an object, you're effectively telling the K8 system what you want your cluster's workload to look like, also known as your cluster's desired state)
* Requires the Kubernetes API in order to work with K8 objects (*When you use the kubectl command-line interface, the CLI makes the necessary Kubernetes API calls for you*)

# Nested Object Fields


