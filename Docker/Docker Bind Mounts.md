# Docker Bind Mounts Overview

A [bind mount](https://docs.docker.com/engine/storage/bind-mounts/) is a shared directory from the host's filesystem into the container

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-10%20173536.png)

* The file or directory on the host machine is mounted into a container and is referenced by its absolute path on the host machine
* Has limited functionality compared to volumes
* The mounted file or directory doesn't need to exist on the Docker host already, rather it's created on demand if it doesn't yet exist
* Very performant but relies on the host machine's filesystem having a specific directory structure available
