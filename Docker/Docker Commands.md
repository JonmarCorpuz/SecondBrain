# Install Docker

```Bash
sudo apt -y install docker.io
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Hub

tmp
```Bash
docker login
```

tmp
```Bash
docker search <IMAGE_NAME>
```

tmp
```Bash
docker images
```

Push an image to Docker Hub
```Bash
docker push <DOCKER_HUB_USERNAME>/<IMAGE_NAME>[:<TAG_NAME>]
```

tmp
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
docker run -d [--env-file "<VARIABLES_FILENAME>"] [--name <CONTAINER_NAME>] <IMAGE_NAME> [-p <HOST_PORT>:<CONTAINER_PORT>] [-f <DOCKERFILE_NAME>]
```

List all running containers
```Bash
docker ps -a
```

tmp
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

tmp
```Bash
docker history <DOCKER_IMAGE>
```

tmp
```Bash
docker logs <IMAGE_TAG>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Volumes

tmp
```Bash
docker volume ls [-f <VOLUME_NAME>]
```

tmp
```Bash
docker volume inspect {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Remove a volume from a container
```Bash
docker volume rm {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Create a named volume
```Bash
docker volume create <VOLUME_NAME>
```

tmp
```Bash
docker system prune
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Resource Limits

tmp
```Bash
docker stats
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Restart Policies

```Bash
--restart on-failure[:<RESTART_LIMIT>]
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Networking

View networks
```Bash
docker network ls
```

Inspect network
```Bash
docker network inspect <NETWORK_DRIVER>
```

Inspect a container's network
```Bash
docker inspect {<CONTAINER_NAME>|<CONTAINER_ID>}
```

Connect a container to a network
```Bash
docker network connect <NETWORK> <CONTAINER>
```

## Default Bridge Network

tmp
```Bash
sudo docker run -itd --rm [-p <host_port>:<container_port>] --name <container_name> <docker_image>[:<version>]
```

## User-Defined Bridge Network

tmp
```Bash
sudo docker network create <network_name>

sudo docker run -itd --rm [-p <host_port>:<container_port>] --network <network_name> --name <container_name> <docker_image>[:<version>]
```

## Host Network

tmp
```Bash
sudo docker run -itd --rm --network host --name <container_name> <docker_image>[:<version>]
```

## MACVLAN Bridge Network

tmp
```Bash
sudo docker network create {-d|--driver} macvlan --subnet <home_network_subnet> --gateway <home_network_gateway> [--ip-range <ip_range>] -o parent=<host_network_interface> <network_name>
```

```Bash
sudo docker run -itd --rm --network <network_name> --ip <ip_address> --name <container_name> <docker_image>[:<version>]

sudo ip link set <host_network_interface> promisc on
```

## MACVLAN 802.1q Network

tmp
```Bash
sudo docker network create {-d|--driver} macvlan --subnet <home_network_subnet> --gateway <home_network_gateway> [--ip-range <ip_range>] -o parent=<host_network_interface>.<subinterface> <network_name>

sudo docker run -itd --rm --network <network_name> --ip <ip_address> --name <container_name> <docker_image>[:<version>]
```

## IPVLAN L2 Network

tmp
```Bash
sudo docker network create {-d|--driver} ipvlan --subnet <home_network_subnet> --gateway <home_network_gateway> [--ip-range <ip_range>] -o parent=<host_network_interface>.<subinterface> <network_name>

sudo docker run -itd -rm -network <network_name> --ip <ip_address> --name <container_name> <container_image>[:<image_version>]
```

## IPVLAN L3 Network

tmp
```Bash
sudo docker network create {-d|--driver} ipvlan --subnet <home_network_subnet> -o parent=<host_network_interface> -o ipvlan_mode=l3 --subnet=<l3_network_subnet> <network_name>

sudo docker run -itd --rm --network <network_name> --ip <ip_address> --name <container_name> <container_image>[:<image_version>]
```

tmp
```Bash
sudo docker stop <container_name>

sudo docker exec -it <container_name> {bash|sh}
```

tmp
```Bash
sudo docker network ls

sudo docker inspect <network_name>

bridge link
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Compose


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Docker Compose Plugin
