<h1 align="center"> Volume Mapping </h1>

Volume mapping, also known as data volumes or bind mounts, is the process of mapping a directory or file on the host system to a directory inside a Docker container. This enables the container to access and modify data stored on the host system, without the need to copy or move the data into the container's filesystem.

Volume mapping is necessary because by default, Docker containers have their own isolated filesystems, which are destroyed when the container is stopped or deleted. This means that any data stored inside the container will be lost when the container is removed or updated. Volume mapping provides a way to persist data outside the container, so that it can be shared and reused across multiple containers and host systems.

Here's an example of how volume mapping works in Docker:

Suppose you have a database application running inside a Docker container, and you want to persist the data stored in the database across multiple runs of the container. To achieve this, you can create a data volume on the host system, and map it to a directory inside the container where the database files are stored.

For example, you could use the docker run command with the -v option to map a directory on the host system to a directory inside the container:

```bash
docker run -v /my/host/data:/var/lib/mysql my-db-app
```

The above command is an old style, the new way to is to use '--mount' option 

```bash
docker run --mount type-bind,source=/location/on/host,target=/location/on/container mysql
```
In this example, /my/host/data is the path to the directory on the host system that will be used as the data volume, and /var/lib/mysql is the directory inside the container where the database files are stored. Once the container is running, any changes made to the database files inside the container will be persisted on the host system, and will be available to other containers that use the same data volume.

![Screenshot 2023-02-27 at 5 10 45 PM](https://user-images.githubusercontent.com/111651161/221555240-cfa84d86-53c9-422b-893a-a873091ee0c8.jpg)

![Screenshot 2023-02-27 at 5 14 25 PM](https://user-images.githubusercontent.com/111651161/221555763-956e171c-b41f-43d2-8084-8d319dc03e85.png)
