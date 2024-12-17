# Kubernetes Health Check Overview

Probes are periodic health checks performed by Kubernetes to determine the status of a container

* Allows Kubernetes to manage the lifecycle of containers by checking if they're healthy and ready to serve traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Readiness Probes

Readiness probes are designed to let Kubernetes know when your application is ready to serve traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/google-kubernetes-probe-readiness6ktf.gif)

* Kubernetes starts sending traffic to an application as soon as the process inside the container starts by default (Readiness probes allow Kubernetes to wait until the application is fully started before it allows the service to send traffic to that new container)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Liveness Probes

Liveness probes let Kubernetes know if your application is alive or dead

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/google-kubernetes-probe-livenessae14.gif)

* If your application is dead, Kubernetes will remove the Pod and start a new one to replace it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Probe Types

## HTTP Probes



## Command Probes

## TCP Probes
