# Manifest Files

A Kubernetes [manifest file](https://www.loft.sh/blog/kubernetes-manifest#:~:text=Kubernetes%20manifests%20are%20YAML%20or%20JSON%20files%20that%20define%20the%20desired%20state%20of%20objects%20in%20a%20cluster) is a YAML or JSON file that defines the desired state of K8 objects in a cluster

| Manifest File Field | Description |
| --- | --- |
| `apiVersion` | Defines which API group and the respective version of the API being used to create the object |
| `kind` | Defines which exact object or resource is being managed by the configuration file (Must be supported by the specified apiVersion) |
| `metadata` | Defines data that's used to uniquely identify the object (*name*, *namespace*, *labels*, *annotations*, *etc.*) |
| `spec` | Defines the actual configuration for the objects being managed by the configuration file (The exact shape of the configuration varies according to both the apiVersion and the kind fields) |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# kubeconfig

* Contains information on how to communicate with the cluster API
