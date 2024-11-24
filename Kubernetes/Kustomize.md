
* Allows you to customize Kubernetes manifests without needing to duplicate and modify the original files or their copies
* Follows the principle of declarative management, in which you can declare which customizations and patches you wish to apply
* Calculates the final resulting manifests
* Addresses the challenges of managing configurations of similar applications for different environments, which can lead to a lot of duplication and overhead when using only Kubernetes-native manifests
* Dosen't require templating syntax since it uses only standard YAML
* Allows you to modify only specific parts of a resource
* Allows you to dynamically generate ConfigMaps and Secrets from files or environment variables, making it easier to manage sensitiv information and configuration data

# Kustomize Components

## Base

A base is a set of common YAML Kubernetes configurations that are shared across environments

* Reusable
* Provide the foundation for your different environment configurations

## Overlay

An Overlay is a set of environment-specific changes that are layered on top of the base

* Through overlays, environments can apply their own customizations (*Change replica counts*, *Change image tags*, *Enable/disable certain features*, *etc.*)
* When building the final configuration, Kustomize merges the overlay on top of the base, leaving the base intact while still being able to generate a customized configuration for the specific environment
