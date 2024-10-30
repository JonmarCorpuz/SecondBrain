#

```Bash
docker images
```

#

```Bash
docker pull <DOCKER_IMAGE>[:<IMAGE_VERSION>]
```

# 

```Bash
docker build <REPOSITORY>
```

# 

```Bash
docker create
```

# 

```Bash
docker start {<CONTAINER_ID>|<CONTAINER_NAME}
```

#

```Bash
docker run [OPTIONS] <DOCKER_IMAGE>
```

* A combination of `docker create` and `docker start`

```Bash
docker run -d <DOCKER_IMAGE>
```

```Bash
docker run -p <LOCAL_PORT>:<CONTAINER_PORT> <DOCKER_IMAGE>
```

```Bash
docker run --name <CONTAINER_NAME> <DOCKER_IMAGE>
```

# 

```Bash
docker ps
```

```Bash
docker ps -a
```

# 

```Bash
docker pause {<CONTAINER_ID>|<CONTAINER_NAME}
```

#

```Bash
docker stop {<CONTAINER_ID>|<CONTAINER_NAME}
```

# 

```Bash
docker rm {<CONTAINER_ID>|<CONTAINER_NAME}
```

#

```Bash
docker kill {<CONTAINER_ID>|<CONTAINER_NAME}
```

# 

```Bash
docker logs {<CONTAINER_ID>|<CONTAINER_NAME}
```

```Bash
docker logs -f {<CONTAINER_ID>|<CONTAINER_NAME}
```

# 

```Bash
docker exec -it {<CONTAINER_ID>|<CONTAINER_NAME} /bin/bash
```
