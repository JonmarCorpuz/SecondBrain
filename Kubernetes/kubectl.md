# kubectl Overview

[kubectl](https://kubernetes.io/docs/reference/kubectl/#:~:text=a%20command%20line,the%20Kubernetes%20API) is a command line tool for communicating with a Kubernetes cluster's control plane

* Translates the commands into API requests
* For configuration, kubectl looks for a file named config in the $HOME/.kube directory (You can specify other kubeconfig files by setting the KUBECONFIG environment variable or by setting the --kubeconfig flag)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Install kubectl

```Bash
# Install kubectl
sudo curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl

#
sudo chmod +x ./kubectl

#
sudo mv ./kubectl /usr/local/bin/kubectl
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# 

```Bash
# 
export KUBECONFIG=kubeconfig.yaml
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Cluster Operations

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Node Operations

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Pod Operations

```Bash
# Run a pod
kubectl run <pod_name> --image=<docker_image>[:<image_version>] --port=<port_number>

# Deploy multiple pods using a Deployment Manifest file
kubectl apply -f <yaml_file>
```

```Bash
#
kubectl edit deployment <deployment_name>
```

```Bash
#
kubectl exec -it <pod_name> [--namespace <namespace>] -- sh

# 
kubectl port-forward <resource_type>/<resource_name> <target_port>/<exposed_port>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Object Management

## Imperative Management With kubectl

```Bash
kubectl create <RESOURCE> [CONFIGURATION]
```

```Bash
kubectl delete <RESOURCE>
```

```Bash
kubectl expose <RESOURCE> <NAME>
```

## Imperative Management With Configuration Files

```Bash
kubectl apply -f <FILENAME>
```

```Bash
kubectl diff -f <FILENAME>
```

```Bash
kubectl delete -f <FILENAME>
```

## Declarative Management With Configuration Files

```Bash

```

```Bash

```

```Bash

```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Troubleshooting

```Bash
#
kubectl get nodes

#
kubectl cluster-info

#
kubectl get pods [--namespace <namespace>] [-o wide]

# 
kubectl describe pod <pod_name> [--namespace <namespace>]

# View the application logs of the erroring pods
kubectl log <pod_name> [--namespace <namespace>]

#
kubectl get services

#
kubectl describe services <service_name>
```

