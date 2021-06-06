Docker
======


Installation
------------

Docker installation for [Mac OS](https://docs.docker.com/docker-for-mac/install/)
Docker installation for [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)


Usage
-----

Show information about the installed `docker` service.

```bash
docker version
```

#### Image

Show all images that are cached locally.

```bash
docker image ls
```

Remove an image _(ID: f2a91732366c)_.

```bash
docker image rm f2a91732366c
```

#### Container

Show all containers that are running.

```bash
docker container ls
```

Show all containers that are cached locally.

```bash
docker container ls --all
```

Stop a container _(ID: 6d6ecf809b63)_.

```bash
docker container stop 6d6ecf809b63
```

Remove a container _(ID: 6d6ecf809b63)_.

```bash
docker container rm 6d6ecf809b63
```

Run a container in interactive mode. Name the container _helloworld_.

Options:  
`-i` Interactive  
`-t` TTY  

```bash
docker run -it --name helloworld ubuntu:16.04
```

Run a container and mount the current working directory inside the container.

```bash
docker run -it --rm --name example --mount type=bind,source="$(pwd)",target=/project --publish 8000:8000 python:3.7-alpine /bin/sh
```

Re-attach a container _(ID: 4c690aaba373)_, that was closed, back to the terminal.

```bash
docker start -i 4c690aaba373
```

Stop a running container _(ID: 4c690aaba373)_.

```bash
docker stop 4c690aaba373
```

Create an image from a `Dockerfile` in the current directory.

```bash
docker build --rm --tag myimage .
```

Create an image from a `Dockerfile` in a different directory.

```bash
docker build --rm --tag myimage --file /path/to/Dockerfile .
```

Execute a command against a running container.

```bash
docker exec -it mycontainer /bin/bash
```

Save a running container into a new image.

```bash
docker commit mycontainer mycontainer:latest
```

#### Volumes

Create a **named volume**.

```bash
docker volume create myvolume
```

Mount a **named volume**.

```bash
docker run -dp 8000:8000 -v myvolume:/etc/myvolume myapplication
```

Display **named volume** info.

```bash
docker volume inspect myvolume
```

Watch container logs.

```bash
docker logs -f myvolume
```

#### Networking

Create a network.

```bash
docker network create mynetwork
```

Attach the network.

```bash
docker run -d --name mydb --network mynetwork -v myvolume:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=abcdef mariadb:latest

# OR
docker run -d --name mydb --network mynetwork -v /path/to/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=abcdef mariadb:latest
```

Try connecting to the container.

```bash
docker exec -it mydb mysql -p
```

#### Logs

Display the logs of a container _(ID: 4c690aaba373)_.

```bash
docker logs 4c690aaba373
```


Docker Compose
==============

Installation
------------

```bash
pip install docker-compose
```

Usage
-----

```bash
docker-compose up
```