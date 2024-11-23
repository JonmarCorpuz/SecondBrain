# Probes Overview

Probes are periodic health checks performed by Kubernetes to determine the status of a container

* Allows Kubernetes to manage the lifecycle of containers by checking if they're healthy and ready to serve traffic

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Probe Types

## Startup Probe

The startup probe ensures that a container has started successfully

* If the startup probe fails, Kubernetes will kill the container and try to restart it

## Liveness Probe

The liveness probe checks if the container is still running

* If the liveness probe fails, Kubernetes will restart the container
* A failed liveness probe doesn't mean that the container has stopped
* Kubernetes will keep sending liveness probes throughout a container's whole lifecycle

## Readiness Probe

The readiness probe checks if the container is ready to accept traffic

* If the readiness probe fails, the container will be removed from the list of endpoints that receive traffic
* Kubernetes will keep sending readiness probes throughout a container's whole lifecycle
