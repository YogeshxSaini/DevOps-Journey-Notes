<h1 align="center"> Docker Engine</h1>

Docker engine includes three main components:

1. Docker Daemon
2. Docker REST API
3. Docker CLI

![Alt text](../../../../../../Downloads/Picture1-15.png)

## Docker Daemon

Docker Daemon which is also know as `dockerd`, listens for API requests in background and manages the Docker objects such as images, containers, networks and volumes.
A daemon can also communicate with other daemons to manage Docker services.

## Docker REST API

Its an API interface used by applications to interact with the Docker daemon and give instructions to Docker daemon. It can be accessed by an HTTP client.

## Docker CLI

Its a tool that allows users to interact with the Docker engine and manage Docker container and images using the command line.
Docker CLI used the REST API to interact with the Docker Daemon.

Fundamentally, both the Docker client and daemon can run on the same system. We can also connect a Docker client to a remote Docker daemon.

```
docker -H=remote-docker-engine:2375
```

In addition, by using a REST API, the Docker client and daemon, communicate, over UNIX sockets or a network interface.