

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Hub

```Bash
docker login
```

```Bash
docker search <IMAGE_NAME>
```

```Bash
docker images
```

Push an image to Docker Hub
```Bash
docker push <DOCKER_HUB_USERNAME>/<IMAGE_NAME>[:<TAG_NAME>]
```

```Bash
docker pull <IMAGE_NAME>[:<TAG_NAME>]
```

Build a Docker image from a Dockerfile
```Bash
docker build -t <IMAGE_TAG> <DOCKERFILE_PATH>
```

Forcefully remove an image
```Bash
docker rmi -f {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Forcefully remove all images
```Bash
docker rmi -f $(docker images -q)
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Containers

Deploy a Docker container
```Bash
docker run -d [--name <CONTAINER_NAME>] <IMAGE_NAME> [-p <HOST_PORT>:<CONTAINER_PORT>]
```

List all running containers
```Bash
docker ps -a
```

```Bash
docker exec -it {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Pause a running container
```Bash
docker pause {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Unpause a paused container
```Bash
docker unpause {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Stop a running container
```Bash
docker stop {<CONTAINER_NAME>|<CONTAINER_ID>}
```
```Bash
docker kill {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Stop all running containers
```Bash
docker stop $(docker ps -q)
```

Start a stopped container
```Bash
docker start {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Remove a stopped container
```Bash
docker rm {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Remove all stopped containers
```Bash
docker rm $(docker ps -aq)
```

```Bash
docker history <DOCKER_IMAGE>
```
