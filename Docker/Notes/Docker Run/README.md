<h1 align="center"> Docker Run </h1>

This command is used to run a container.

** SIMPLE SYNTEX **
```bash
docker run <image_name>:<tag>       # if the image is offical
docker run <repo_name>/<image_name>:<tag>       # if the image is not official
```

> Note that if the image is hosted on a private registry, you may need to authenticate with the registry using the docker login command before you can pull or run the image.

** SYNTEX **
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

- OPTIONS are optional parameters that modify the container's behavior. Some common options include:
    -d: Run the container in the background (detached mode).
    -it: Run the container in interactive mode with a pseudo-TTY attached.
    --name: Assign a name to the container.
    -p: Map a container port to a host port.
    --rm: Remove the container automatically when it exits.
    -v: Mount a host directory or file as a data volume inside the container.
- IMAGE is the name and tag of the Docker image to use as the basis for the container.
- COMMAND (optional) is the command to run inside the container.
- ARG (optional) is any additional arguments to pass to the command.



1. First, Docker will search for the requested image locally. If it is available, Docker will run the image and create a container from it.

```bash
$ docker run centos
> Unable to find image 'centos:latest' locally
```
2. If the requested image is not available locally, Docker will pull the image from the Docker registry and then run it.

```bash
$ docker run centos
> Unable to find image 'centos:latest' locally
> latest: Pulling from library/centos
```