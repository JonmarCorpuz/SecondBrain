Google's Cloud Deployment Manager is an infrastructure management service that allows users to automate the creation and management of their Google Cloud resources using YAML configuration files

* Helps avoid configuration drift
* Can act as a version control for a user's environments
* Resources created by the Deployment Manager should always be modified using the Deployment Manager
* Deployment Manager understands dependencies (Ex: *Creates VPCs first, then subnets, and then the database*, *etc.*)
* 
