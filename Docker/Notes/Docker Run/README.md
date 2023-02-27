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
<!-- 
> Note that if the image is hosted on a private registry, you may need to authenticate with the registry using the docker login command before you can pull or run the image.

**SYNTEX**
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

- OPTIONS are optional parameters that modify the container's behavior. Some common options include:
    <ul>
        <li> -d: Run the container in the background (detached mode). </li>
        <li> -it: Run the container in interactive mode with a pseudo-TTY attached. </li>
        <li> --name: Assign a name to the container. </li>
        <li> -p: Map a container port to a host port. </li>
        <li> --rm: Remove the container automatically when it exits. </li>
        <li> -v: Mount a host directory or file as a data volume inside the container. </li>
    </ul>
- IMAGE is the name and tag of the Docker image to use as the basis for the container.
- COMMAND (optional) is the command to run inside the container.
- ARG (optional) is any additional arguments to pass to the command.


**NOTES**
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
``` -->
