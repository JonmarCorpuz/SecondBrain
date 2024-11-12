# Docker Volumes Overview

Docker Volumes enable you to persist data outside the container lifecycle

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/More%20Assets/Screenshot%202024-11-10%20173536.png)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Types of Docker Volumes

## Bind Mounts 

A [bind mount](https://docs.docker.com/engine/storage/bind-mounts/) directly links your host's directories or files to your container

* The file or directory on the host machine is mounted into a container and is referenced by its absolute path on the host machine
* Has limited functionality compared to volumes
* The mounted file or directory doesn't need to exist on the Docker host already, rather it's created on demand if it doesn't yet exist
* Very performant but relies on the host machine's filesystem having a specific directory structure available
* Ideal for real-time development updates

## Named Volumes

[Named volumes](https://docs.docker.com/engine/storage/volumes/) are the preferred mechanism for persisting data generated by and used by Docker containers


* Using a volume creates a new directory within Docker's storage directory on the host machine, and Docker manages that directory's contents
* Acts as a managed directory or file that's separate from the container's file system, which allows you to ensure that your data remains safe and accessible
* Allows you to share data between containers by sharing the same volume

## Anonymous Volumes


* Often used for temporary data that doesn't need to persist