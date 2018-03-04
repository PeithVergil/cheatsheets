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

Remove an image by its ID _(f2a91732366c)_.

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

Remove a container by its ID _(6d6ecf809b63)_.

```bash
docker rm 6d6ecf809b63
```