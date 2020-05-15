<!-- PROJECT LOGO -->
<br />
<p align="center">
  <h1 align="center">Developer's Docker ✨</h1>

  <p align="center">
    <br />
    ·
    <a href="https://github.com/abhinavkorpal/Docker/issues">Report Bug</a>
    ·
    <a href="https://github.com/abhinavkorpal/Docker/issues">Request Feature</a>
  </p>
</p>

![GitHub contributors](https://img.shields.io/github/contributors/abhinavkorpal/Docker?color=ffcc66&style=for-the-badge)
![GitHub stars](https://img.shields.io/github/stars/abhinavkorpal/Docker?color=ffcc66&style=for-the-badge)
[![GitHub forks](https://img.shields.io/github/forks/abhinavkorpal/Docker?style=for-the-badge)](https://github.com/abhinavkorpal/star_book/network)
[![GitHub issues](https://img.shields.io/github/issues/abhinavkorpal/Docker?color=ffcc66&style=for-the-badge)](https://github.com/abhinavkorpal/star_book/issues)
[![GitHub license](https://img.shields.io/github/license/abhinavkorpal/Docker?style=for-the-badge)](https://github.com/abhinavkorpal/Docker/blob/master/LICENSE)
[![Twitter Follow](https://img.shields.io/twitter/follow/abhinavkorpal?color=ffcc66&logo=twitter&logoColor=ffffff&style=for-the-badge)](https://twitter.com/abhinavkorpal)


## what is container ?
A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another. A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.
Container images become containers at runtime and in the case of Docker containers - images become containers when they run on Docker Engine. Available for both Linux and Windows-based applications, containerized software will always run the same, regardless of the infrastructure. Containers isolate software from its environment and ensure that it works uniformly despite differences for instance between development and staging.
**Docker containers that run on Docker Engine:**
**Standard:** Docker created the industry standard for containers, so they could be portable anywhere
**Lightweight:** Containers share the machine’s OS system kernel and therefore do not require an OS per application, driving higher server efficiencies and reducing server and licensing costs
**Secure:** Applications are safer in containers and Docker provides the strongest default isolation capabilities in the industry
![](https://github.com/abhinavkorpal/Docker/blob/master/images/containerized_applications.png)
Docker container technology was launched in 2013 as an open source Docker Engine.
It leveraged existing computing concepts around containers and specifically in the Linux world, primitives known as cgroups and namespaces. Docker's technology is unique because it focuses on the requirements of developers and systems operators to separate application dependencies from infrastructure.
Success in the Linux world drove a partnership with Microsoft that brought Docker containers and its functionality to Windows Server.
Technology available from Docker and its open source project, Moby has been leveraged by all major data center vendors and cloud providers. Many of these providers are leveraging Docker for their container-native IaaS offerings. Additionally, the leading open source serverless frameworks utilize Docker container technology.
![](https://github.com/abhinavkorpal/Docker/blob/master/images/docker_today.png)
### Comparing Containers and Virtual Machines
Containers and virtual machines have similar resource isolation and allocation benefits, but function differently because containers virtualize the operating system instead of hardware. Containers are more portable and efficient.
### CONTAINERS
Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems.
### VIRTUAL MACHINES
Virtual machines (VMs) are an abstraction of physical hardware turning one server into many servers. The hypervisor allows multiple VMs to run on a single machine. Each VM includes a full copy of an operating system, the application, necessary binaries and libraries - taking up tens of GBs. VMs can also be slow to boot.
![](https://github.com/abhinavkorpal/Docker/blob/master/images/containerized.png)
### Containers and Virtual Machines Together
Containers and VMs used together provide a great deal of flexibility in deploying and managing app
Docker developed a Linux container technology - one that is portable, flexible and easy to deploy. Docker open sourced libcontainer and partnered with a worldwide community of contributors to further its development. In June 2015, Docker donated the container image specification and runtime code now known as runc, to the Open Container Initiative (OCI) to help establish standardization as the container ecosystem grows and matures.
Following this evolution, Docker continues to give back with the containerd project, which Docker donated to the Cloud Native Computing Foundation (CNCF) in 2017. containerd is an industry-standard container runtime that leverages runc and was created with an emphasis on simplicity, robustness and portability. containerd is the core container runtime of the Docker Engine.
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
##### you can create volume explicitly using the:
```shell
docker volume create
```
##### you can remove unused volume using:
```shell
docker volume prune
```
##### To we the approximate size of a running container, you can use the:
```shell
docker ps -s
```
If you build image from two Dockerfiles, you can use ```docker image ls``` and ```docker history``` commands to verify that the cryptographic IDs of the shared layers are the same.
##### List the contents of the local storage area:
```shell
$ sudo ls /var/lib/docker/containers
```
##### check out their sizes:
```shell
$ sudo du -sh /var/lib/docker/containers/*
```
##### Create a volume:
```shell
$ docker volume create my-vol
```
##### List volumes:
```shell
$ docker volume ls
```
##### Inspect a volume:
```shell
$ docker volume inspect my-vol[
    {
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/my-vol/_data",
        "Name": "my-vol",
        "Options": {},
        "Scope": "local"
    }
]
```
##### Remove a volume:
```shell
$ docker volume rm my-vol
```
##### List Docker CLI commands
```shell
docker
docker container --help
```

##### Display Docker version and info
```shell
docker --version
docker version
docker info
```

##### Execute Docker image
```shell
docker run hello-world
```

##### List Docker images
```shell
docker image ls
```

##### List Docker containers (running, all, all in quiet mode)
```shell
docker container ls
docker container ls --all
docker container ls -aq
```
### List of all the basic Docker commands:
```shell
docker build -t friendlyhello .  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello  # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello         # Same thing, but in detached mode
docker container ls                                # List all running containers
docker container ls -a             # List all containers, even those not running
docker container stop <hash>           # Gracefully stop the specified container
docker container kill <hash>         # Force shutdown of the specified container
docker container rm <hash>        # Remove specified container from this machine
docker container rm $(docker container ls -a -q)         # Remove all containers
docker image ls -a                             # List all images on this machine
docker image rm <image id>            # Remove specified image from this machine
docker image rm $(docker image ls -a -q)   # Remove all images from this machine
docker login             # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag  # Tag <image> for upload to registry
docker push username/repository:tag            # Upload tagged image to registry
docker run username/repository:tag                   # Run image from a registry
docker stack ls                                            # List stacks or apps
docker stack deploy -c <composefile> <appname>  # Run the specified Compose file
docker service ls                 # List running services associated with an app
docker service ps <service>                  # List tasks associated with an app
docker inspect <task or container>                   # Inspect task or container
docker container ls -q                                      # List container IDs
docker stack rm <appname>                             # Tear down an application
docker swarm leave --force      # Take down a single node swarm from the manager
```

# Docker - How to cleanup (unused) resources

Once in a while, you may need to cleanup resources (containers, volumes, images, networks) ...
    
## delete volumes
    
    // see: https://github.com/chadoe/docker-cleanup-volumes
    
    $ docker volume rm $(docker volume ls -qf dangling=true)
    $ docker volume ls -qf dangling=true | xargs -r docker volume rm
    
## delete networks

    $ docker network ls  
    $ docker network ls | grep "bridge"   
    $ docker network rm $(docker network ls | grep "bridge" | awk '/ / { print $1 }')
    
## remove docker images
    
    // see: http://stackoverflow.com/questions/32723111/how-to-remove-old-and-unused-docker-images
    
    $ docker images
    $ docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
    
    $ docker images | grep "none"
    $ docker rmi $(docker images | grep "none" | awk '/ / { print $3 }')

## remove docker containers

    // see: http://stackoverflow.com/questions/32723111/how-to-remove-old-and-unused-docker-images
    
    $ docker ps
    $ docker ps -a
    $ docker rm $(docker ps -qa --no-trunc --filter "status=exited")
    
## Resize disk space for docker vm
    
    $ docker-machine create --driver virtualbox --virtualbox-disk-size "40000" default
