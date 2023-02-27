<h1 align="center"> Docker Run </h1>

The docker run command is used to create and start a new container from an image. When you run this command, Docker will download the image (if it's not already available) and create a new container based on that image.

Here are some of the most commonly used options for the 'docker run' command:

| Option        | Description                                                       |
| ------------- | ----------------------------------------------------------------- |
| '-d'	        | Run the container in detached mode (i.e., in the background)      |
| -it:          | Run the container in interactive mode with a pseudo-TTY attached. |
| '-p'	        | Map a port from the container to the host                         |
| '-v'	        | Mount a volume from the host to the container                     |
| '-e'	        | Set an environment variable                                       |
| '--name'	    | Give the container a name                                         |
| '--rm'	    | Automatically remove the container when it stops                  |

**SYNTEX**
```bash
docker run <image_name>:<tag>                   # if the image is offical
docker run <repo_name>/<image_name>:<tag>       # if the image is not official
```

![Screenshot 2023-02-27 at 12 41 15 PM](https://user-images.githubusercontent.com/111651161/221498432-bac7c96d-7f67-493b-9128-d09e592542af.png)

First, Docker will check the local host machine to see if the image is already available; if not, it will pull the image from the registry (where images are deployed) and then Docker will create and start a new container based on that image.

<img src="https://user-images.githubusercontent.com/111651161/221502653-f4c50e7a-1269-40be-bdec-10970621aa33.png" height="600">

## List all the running containers

```bash
docker ps
or
docker container ls
```

## Running a container in interactive mode

```bash
docker run -it ubuntu
```

This will create a new contaier from the latest Ubuntu image, and opens up an interactive terminal session with that container.

## Giving the container a name

```bash
docker run --name <container_name> <image>
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