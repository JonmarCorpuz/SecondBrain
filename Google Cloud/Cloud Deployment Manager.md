# Cloud Deployment Manager Overview

Cloud Deployment Manager is a Google Cloud service for creating configuration files that define resources to use with an application

* Makes it relatively simple to deploy an application and resources in a repeatable process by allowing engineers to define configuration files that describe the resources that they would like to deploy

# Cloud Deployment Manager Files

* YAML file that's made up of resource specifications that use key-value pairs to define properties of the resource
* Configuration files start with the works resources, followed by resource entities that are defined using the `name` (The name of the resource), `type` (The type of the resource), and `properties` (A key-value pair that specify configuration parameters for the resource) fields

