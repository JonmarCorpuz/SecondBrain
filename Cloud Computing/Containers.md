Containers are software packages that contain an application and all dependencies for the contained application to run

* Containers run on a containter engine
* Lightweight and includes only the dependencies that are required for the application to run
* Very portable (Ex: *Can boot up in milliseconds*, *Take up very little disk space*, *Can be run on nearly any container service*, *Uses much fewer CPU/RAM resources*, *etc.*)
* Doesn't require a Guest OS to run
* Provides isolation since they're all in their own independent environment (If the Host OS crashes, all containers running on it are effected)

# Container Components

| Container Components | Description |
| --- | --- |
| Container Engine | Software that allows you to create, manage, and run containers on a single Host OS |
| Containe Orchestrator | Software that allows you to automate the deployment, management, scaling, and networking of containers across multiple nodes |

## Container Engine

A container engine is software that allows you to create, manage, and run containers on a single Host OS (Ex: *Docker*, *Podman*)

* Runs on a Host OS
* Doesn't need a Guest OS to run

## Container Orchestrator 

A oontainer orchestrator is a software that allows you to automate the deployment, management, scaling, and networking of containers across multiple nodes (Ex: *Kubernetes*, *Docker Swarm*, *Apache Mesos*)

| Container Orchestrator Feature | Description |
| --- | --- |
| Autoscaling | Scale containers based on demand |
| Service Discovery | Help microservices find one another |
| Load Balancing | Distribute workload among multiple instances of a microservice |
| Self Healing | Do health checks and replace failing instances |
| Zero Downtime Deployment | Release new versions without downtime |
