<h1 align="center"> Docker Swarm </h1>

Docker Swarm is a native clustering and orchestration tool for Docker containers. It allows you to create and manage a cluster of Docker nodes, which can be used to deploy and scale containerized applications.

## Features of Docker Swarm

Docker Swarm offers several features that make it a powerful tool for managing containerized applications:

- **High availability**: Docker Swarm ensures high availability by replicating containers across multiple nodes in the cluster.
- **Scalability**: Docker Swarm allows you to scale your applications by adding or removing nodes from the cluster.
- **Load balancing**: Docker Swarm provides built-in load balancing for distributing traffic across multiple containers running on different nodes.
- **Service discovery**: Docker Swarm includes a built-in DNS server for service discovery within the cluster.
- **Rolling updates**: Docker Swarm supports rolling updates, which allow you to update your applications without downtime by gradually updating containers across the cluster.

## Components of Docker Swarm

Docker Swarm consists of the following components:

- **Swarm manager**: The Swarm manager is responsible for managing the cluster and coordinating tasks across the nodes.
- **Swarm nodes**: The Swarm nodes are the individual Docker hosts that make up the cluster.
- **Service**: A service is a containerized application that is deployed and managed by Docker Swarm.
- **Task**: A task is a running instance of a service on a particular node.

## Working with Docker Swarm

To create and manage a Docker Swarm cluster, you can use the Docker CLI or a tool like Docker Compose. Here are some common Docker Swarm commands:

| Command                            | Description                                                  |
| ---------------------------------- | ------------------------------------------------------------ |
| `docker swarm init`                | # Initialize a new Swarm cluster                             |
| `docker swarm join`                | # Join a node to an existing Swarm cluster                   |
| `docker swarm leave`               | # Remove a node from a Swarm cluster                         |
| `docker stack deploy`              | # Deploy a stack to a Swarm cluster                          |
| `docker service create`            | # Creates a new service in the Swarm cluster                 |
| `docker service ls`                | # List all the services running in a Swarm cluster           |
| `docker service ls`                | # Lists all the services running in the Swarm cluster        |
| `docker service scale`             | # Scales a service up or down by adding or removing replicas |
| `docker service update`            | # Updates a service by changing its configuration            |
| `docker node ls`                   | # List all the nodes in a Swarm cluster                      |