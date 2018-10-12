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
