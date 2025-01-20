# Minikube Overview

Minikube is a tool that sets up a Kubernetes environment on a local machine

* Technically a Kubernetes distribution but is referred to as a tool rather than a distribution
* Supports Linux, Windows, and macOS
* Provides only a single-node Kubernetes cluster that's stored onl local directories inside the Minikube machine by default (A multi-node cluster can be deployed if desired)

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Minikube Drivers

* Supports a flexiible deployment mode based on the concept of drivers (Depending on the driver the user chooses for deployment, their Kubernetes node(s) can run either inside a Docker container, inside a VM on a supported platform (*VirtualBox*, *KVM*, *Hyper-V*, *etc.*), or directly on bare metal if your host OS supports it
* Drivers are available for your installation depending on which system you're using to run Minikube
* The driver you choose depends on what level of performance and isolation you want from Minikube

## Docker Container

* Provides the second best performance

## Virtual Machine

* Provides the lowest level of perfomance but the most isolation from the host system

## Bare Metal

* Only supported on Linux since Kubernetes master nodes can run natively only on a Linux system
* Provides the best performance

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Install Minikube

## Linux 

```Bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## Windows 

```PowerShell
New - Item - Path 'c:\' -Name '
minikube ' -ItemType Directory -Force
Invoke - WebRequest - OutFile 'c:\minikube\minikube.exe' - Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' - UseBasicParsing
```

## MacOS

```macOS
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube
```

![](https://github.com/JonmarCorpuz/LetsLearn/blob/main/Assets/Whitespace.png)

# Minikube Commands

Start Minikube
```Bash
minikube start
```

Interact with your Minikube Kubernetes cluster
```Bash
minikube kubectl cluster-info
```

Enable Web-based Kubernetes dashboard
```Bash
minikube dashboard
```

Install an ingress controller (Minikube doesn't provide an ingress controller by default)
```Bash
minikube addons enable ingress
```

Create a multi-node cluster
```Bash
minikube start --nodes NUMBER_OF_NODES -p CLUSTER_NAME
```
