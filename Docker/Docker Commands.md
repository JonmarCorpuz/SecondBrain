

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
docker pull <IMAGE_NAME>[:<VERSION>]
```

Build a Docker image from a Dockerfile
```Bash
docker build -t <OUTPUT_IMAGE_NAME> <DOCKERFILE_PATH>
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
docker run -d <IMAGE_NAME> [-p <HOST_PORT>:<CONTAINER_PORT>]
```

List all running containers
```Bash
docker ps -a
```

```Bash
docker exec -it {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Stop a running container
```Bash
docker stop {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Remove a stopped container
```Bash
docker rm {<CONTAINER_NAME>|<CONTAINER_ID>}
```
