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
docker create
```

# 

```Bash
docker start <CONTAINER_ID>
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

# 

```Bash
docker pause <CONTAINER_NAME>
```

#

```Bash
docker stop <CONTAINER_NAME>
```

# 

```Bash
docker rm <CONTAINER_ID>
```

#

```Bash
docker kill <CONTAINER_NAME>
```
