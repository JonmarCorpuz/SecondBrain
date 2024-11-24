
* Kubernetes organizes its API resources into logical groups (API Groups)

# API Groups

* Allow Kubernetes to extend and evolve without breaking existing resources or creating conflicts
* Different API Groups can define related resources
* Each API Group typically represents a versioned API with its own path
* API Groups are referenced in the `apiVersion` field of Kubernetes manifests
* Resources are split into the core API group amd named API groups

## Core API Group

* Accessible under the /api top-level path of the Kubernetes API

## Named API Group

* Accessible under the /apis top-level path of the Kubernetes API and under their own group path
* Contain additional resources and extend the functionality of Kubernetes
