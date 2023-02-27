<h1 align="center"> Docker Container </h1>

| Command                                          | Description                                    |
| ------------------------------------------------ | ---------------------------------------------- |
| `docker run <image>`                             | # Run a new container from an image            |
| `docker ps`                                      | # List all running                             |
| `docker ps -a`                                   | # List all containers (including stopped ones) |
| `docker create <image>`                          | # Create a new container from an image         |
| `docker pause <container_name_or_id>`            | # Pause a running container                    |
| `docker start <container_name_or_id>`            | # Start a stopped container                    |
| `docker stop <container_name_or_id>`             | # Stop a running container                     |
| `docker rm <container_name_or_id>`               | # Remove a container                           |
| `docker logs <container_name_or_id>`             | # Show the logs of a container                 |
| `docker exec <container_name_or_id> <command>`   | # Execute a command inside a container         |
| `docker inspect <container_name_or_id>`          | # Display detailed information about container |


**Notes**

1. We can't remove a paused container by `docker rm <container_name_or_id>` command. Unpause and then stop the container before attempting removal or force remove.  
    `docker rm -f`
2. The command started using `docker exec` only runs while the container’s primary process (PID 1) is running, and it is not restarted if the container is restarted.   [More here](https://docs.docker.com/engine/reference/commandline/exec/)


**Tips**

1. Remove a running container without stopping it.  
    `docker rm -f <container_name_or_id>`

    ```bash
    $ docker ps -aq
    b957616beef3
    c4d4a9308cbf
    a92c37487e5d
    e8b1345bd330
    75e751751500
    ea1b9f3e6f88
    dd0fcbedc0f1
    ```

2. List all the containers IDs only.  
    `docker ps -aq`

3. Delete all the containers (including running, paused, stopped, exited).  
    `docker rm -f $(docker ps -aq)`

4. Remove multi-container at once.  
    `docker rm <container1> <container2> <container3> <container4> <container5> ...`