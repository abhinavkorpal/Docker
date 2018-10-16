# Docker

## Useful Docker Commands

##### docker build

Build an image from a Dockerfile.

```shell
docker build [DOCKERFILE PATH]
```

#### Example:
Build an image tagged my-org/my-image where the Dockerfile can be found at /tmp/Dockerfile.
```shell
docker build -t my-org:my-image -f /tmp/Dockerfile
```
#### Useful flags
```shell
--file -f Path where to find the Dockerfile.
--force-rm Always remove intermediate containers.
--no-cache Do not use cache when building the image.
--rm Remove intermediate containers after a successful build (this is true) by default.
--tag -t Name and optionally a tag in the ‘name:tag’ format.
```

#### Remove all images
All the Docker images on a system can be listed by adding -a to the docker images command. Once you're sure you want to delete them all, you can add the -q flag to pass the Image ID to docker rmi:

###### List:

```shell
docker images -a
```

###### Remove:

```shell
docker rmi $(docker images -a -q)
```

#### Stop and remove all containers

You can review the containers on your system with docker ps. Adding the -a flag will show all containers. When you're sure you want to delete them, you can add the -q flag to supply the IDs to the docker stop and docker rm commands:

##### List:

```shell
docker ps -a
```
Remove:

```shell
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
docker rm -f $(docker ps -aq)
```
