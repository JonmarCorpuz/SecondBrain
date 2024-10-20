# GCR Overview

The Google Container Registry is a managed Docker contained registry service provided by GCP

* Allows you to store, manage, and secure Docker container images and artifacts
* Provides a private registry where you can store Docker container images securely (Images stored in GCR are accessible only to the users and services that you grant permission)
* Images can be stored in various regions around the work, which helps in reducing latency and complying with data residency requirements
* Once an image is pushed to GCR, it's immutable, meaning that it can't be changed or deleted
* Naming: <HostName>/<ProjectID>/<Image>:<Tag>
