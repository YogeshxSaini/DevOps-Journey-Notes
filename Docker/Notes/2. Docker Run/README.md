<h1 align="center"> Docker Run </h1>

The docker run command is used to create and start a new container from an image. When you run this command, Docker will download the image (if it's not already available) and create a new container based on that image.  
By default, the container is started in the foreground and attached to the current terminal.  
The docker run command can be customized with a variety of options to configure the container's runtime behavior.  

Here are some of the most commonly used options for the 'docker run' command:

| Option        | Description                                                       |
| ------------- | ----------------------------------------------------------------- |
| `-d`	        | Run the container in detached mode (i.e., in the background)      |
| `-it:`        | Run the container in interactive mode with a pseudo-TTY attached. |
| `-p`	        | Map a port from the container to the host                         |
| `-v`	        | Mount a volume from the host to the container                     |
| `-e`	        | Set an environment variable                                       |
| `--name`	    | Give the container a name                                         |
| `--rm`	    | Automatically remove the container when it stops                  |


> Use the --network option to specify the network to use for the container.
> Use the --restart option to specify the restart policy for the container.

```bash
docker run <image_name>:<tag>                   # if the image is offical
docker run <repo_name>/<image_name>:<tag>       # if the image is not official
```

First, Docker will check the local host machine to see if the image is already available; if not, it will pull the image from the registry (where images are deployed) and then Docker will create and start a new container based on that image.

<!-- <img src="https://user-images.githubusercontent.com/111651161/221502653-f4c50e7a-1269-40be-bdec-10970621aa33.png" height="600"> -->

```bash
$ docker run -d ubuntu

Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
8b150fd943bc: Already exists
Digest: sha256:9a0bdde4188b896a372804be2384015e90e3f84906b750c1a53539b585fbbe7f
Status: Downloaded newer image for ubuntu:latest
```

## List all the containers (including running, paused, stopped and exited)

```bash
docker ps -a         # docker container ls

CONTAINER ID   IMAGE     COMMAND       CREATED          STATUS                      PORTS     NAMES
ea1b9f3e6f88   ubuntu    "/bin/bash"   11 seconds ago   Exited (0) 10 seconds ago             pensive_pike
dd0fcbedc0f1   ubuntu    "/bin/bash"   59 seconds ago   Exited (0) 59 seconds ago             magical_ritchie
```

## Running a container in interactive mode

```bash
docker run -it ubuntu
```

This will create a new contaier from the latest Ubuntu image, and opens up an interactive terminal session with that container.

<img src="https://user-images.githubusercontent.com/111651161/221514839-de0f89d2-9c8e-46b0-b0c2-e798aec45c87.png" height="600">

## Giving the container a name

```bash
docker run --name <container_name> <image>
```

You can't change names of the container after using this command.


Rename a container  
```bash
docker rename <old_name> <new_name>
```

## Mapping a port from the container to the host

```bash
docker run -p <port_on_host>:<exposed_port_on_container> <image>
```

## Mounting a volume from the host to the container

```bash
docker run -v /path/on/host:/path/in/container <image>
```

## Setting an environment variable

```bash
docker run -e ENV_VARIABLE=value <image>
```

## Automatically remove the container when it stops

```bash
docker run --rm <image>
```
