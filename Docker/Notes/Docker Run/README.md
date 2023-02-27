<h1 align="center"> Docker Run </h1>

This command is used to run a container.

**SIMPLE SYNTEX**
```bash
docker run <image_name>:<tag>       # if the image is offical
docker run <repo_name>/<image_name>:<tag>       # if the image is not official
```

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
```

<h2> Docker Images Commands</h2>
```bash
docker images               # List all the available images
docker pull <image>         # Pull an image from the registry
docker push <image>         # Push an image to the registry
docker rmi <image>          # Remove an image from the local machine
```

<h2> Docker Container Commands</h2>
```bash
docker ps                   # List all running containers
docker ps -a                # List all containers (including stopped ones)
docker create <image>       # Create a new container from an image
docker start <container>    # Start a stopped container
docker stop <container>     # Stop a running container
docker rm <container>       # Remove a container
docker logs <container>     # Show the logs of a container
docker exec <container>     # Execute a command inside a container
```

<h2> Docker Network Commands</h2>
```bash
docker network create <network>    # Create a new network
docker network ls                  # List all networks
docker network inspect <network>   # Show detailed information about a network
docker network connect <network> <container> # Connect a container to a network
docker network disconnect <network> <container> # Disconnect a container from a network
```

<h2> Docker Volume Commands</h2>
```bash
docker volume create <volume>  # Create a new volume
docker volume ls              # List all volumes
docker volume inspect <volume> # Show detailed information about a volume
docker volume rm <volume>     # Remove a volume
```

<h2> Docker Compose Commands</h2>
```bash
docker-compose up              # Start all the services defined in a Compose file
docker-compose down            # Stop all the services defined in a Compose file
docker-compose ps              # List all the containers managed by a Compose file
docker-compose logs            # Show the logs of all the containers managed by a Compose file
```

<h2> Docker Swarm Commands</h2>
```bash
docker swarm init              # Initialize a new Swarm cluster
docker swarm join              # Join a node to an existing Swarm cluster
docker swarm leave             # Remove a node from a Swarm cluster
docker swarm deploy            # Deploy a stack to a Swarm cluster
docker swarm services          # List all the services running in a Swarm cluster
docker swarm nodes             # List all the nodes in a Swarm cluster
```