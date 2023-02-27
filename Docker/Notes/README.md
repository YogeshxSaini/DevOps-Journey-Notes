<h2> Docker Images Commands</h2>

```bash
docker images                   # List all the available images
docker pull <image:tag>         # Pull an image from the registry
docker push <image:tag>         # Push an image to the registry
docker rmi <image:tag>          # Remove an image from the local machine
```

<h2> Docker Container Commands</h2>

```bash
docker run <image:tag>                              # Run a new container from an image
docker ps                                           # List all running containers
docker ps -a                                        # List all containers (including running, paused, created and stopped ones)
docker create <image:tag>                           # Create a new container from an image
docker start <container_name_or_id>                 # Start a stopped container
docker stop <container_name_or_id>                  # Stop a running container
docker rm <container_name_or_id>                    # Remove a container
docker logs <container_name_or_id>                  # Show the logs of a container
docker exec <container_name_or_id> <command>        # Execute a command inside a container
```

<h2> Docker Network Commands</h2>

```bash
docker network create <network>                             # Create a new network
docker network ls                                           # List all networks
docker network inspect <network>                            # Show detailed information about a network
docker network connect <network> <container_name_or_id>     # Connect a container to a network
docker network disconnect <network> <container_name_or_id>  # Disconnect a container from a network
```

<h2> Docker Volume Commands</h2>

```bash
docker volume create <volume>   # Create a new volume
docker volume ls                # List all volumes
docker volume inspect <volume>  # Show detailed information about a volume
docker volume rm <volume>       # Remove a volume
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
