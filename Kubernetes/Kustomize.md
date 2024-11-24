
* Allows you to customize Kubernetes manifests without needing to duplicate and modify the original files or their copies
* Follows the principle of declarative management, in which you can declare which customizations and patches you wish to apply
* Calculates the final resulting manifests
* Addresses the challenges of managing configurations of similar applications for different environments, which can lead to a lot of duplication and overhead when using only Kubernetes-native manifests
* Dosen't require templating syntax since it uses only standard YAML
* Allows you to modify only specific parts of a resource
* Allows you to dynamically generate ConfigMaps and Secrets from files or environment variables, making it easier to manage sensitiv information and configuration data

# Kustomize Components

## Base

A base is a set of common YAML configurations that are shared across environments

## Overlay

* Applies environment-specific customizations on top of a base
