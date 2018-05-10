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

Show all images that are cached locally.

```bash
docker image ls
```

Remove an image _(ID: f2a91732366c)_.

```bash
docker rmi f2a91732366c
```

Show all containers that are running.

```bash
docker container ls
```

Show all containers that are cached locally.

```bash
docker container ls --all
```

Remove a container _(ID: 6d6ecf809b63)_.

```bash
docker rm 6d6ecf809b63
```

Run a container in interactive mode. Name the container _helloworld_.

```bash
docker run -i -t --name helloworld ubuntu:16.04
```

Re-attach a container _(ID: 4c690aaba373)_, that was closed, back to the terminal.

```bash
docker start -i 4c690aaba373
```

Stop a running container _(ID: 4c690aaba373)_.

```bash
docker stop 4c690aaba373
```

Create an image from a `Dockerfile`.

```bash
docker build -t myimage .
```