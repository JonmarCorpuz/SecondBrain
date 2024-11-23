# Resource Quota Overview

Resource quotas are used to set limits on how much resources Kubernetes objects might use

* Ensures that resources are distributed fairly among applications
* Prevents a single application or namespace from consuming excessive resources
* Resource quotas are applied at the namespace level

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Resource Quota Components

* Resources requests and limits are defined at the container level within Pods and specify how much of each resource a container needs

```YAML
resources:
  requests.<RESOURCE>: <VALUE>
  limits.<RESOURCE>: <VALUE>
```

## Resource Requests

Requests specify the minimum amount of CPU or memory a container should always have available after scheduling

## Resource Limits

Limits specify the maximum amount of CPU or memory that a container is allowed to use
