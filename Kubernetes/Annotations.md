# Annotations Overview

[Annotations](https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/) are non-identifying key-value pairs attached to Kubernetes objects, just like labels

* Aren't supposed to store identifying metadata
* Can be used by external tools (*Monitoring tools*, *Systems*, *Logging agents*, *etc.*) to attach custom data to resources (*Configurations*, *Metrics collection endpoints*, *etc.*)
* Can be used to configure ingress controllers (*Traffic routing*, *SSL termination*, *Security settings*, *Path rewrites*, *Load balancing rules*, *etc.*)
* Can store build and version information (*Build timestamps*, *Version numbers*, *Git commit hashes*, *etc.*)
* Can be used by Kubernetes operators or controllers to customize runtime behavior for specific resources

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Annotation Components

```YAML
metadata:
  annotations:
    <PREFIX>/<NAME>: <VALUE>
```

## Prefix

* Must be a DNS subdomain

## Name

* Should be less than 63 characters
* Should contain only alphanumeric characters, dots, underscores, and dashes
