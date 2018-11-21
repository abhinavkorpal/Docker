# Docker


## what is container ?

A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

Container images become containers at runtime and in the case of Docker containers - images become containers when they run on Docker Engine. Available for both Linux and Windows-based applications, containerized software will always run the same, regardless of the infrastructure. Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.

Docker containers that run on Docker Engine:

Standard: Docker created the industry standard for containers, so they could be portable anywhere
Lightweight: Containers share the machine’s OS system kernel and therefore do not require an OS per application, driving higher server efficiencies and reducing server and licensing costs
Secure: Applications are safer in containers and Docker provides the strongest default isolation capabilities in the industry

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
docker rmi -f $(docker images -a -q)
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

##### Clear any cached networks:

```shell
docker network prune
```
