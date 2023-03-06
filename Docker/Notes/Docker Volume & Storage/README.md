<h1 align="center"> Docker Storage </h1>

Docker storage provides a range of storage options for containerized applications. Docker containers have their own isolated file system, but they also need to be able to access persistent storage for data storage and sharing.

## Docker storage drivers

Docker storage drivers are responsible for managing the storage of Docker containers. Docker supports multiple storage drivers, including:

- overlay2: This is the default storage driver for Docker on most modern Linux distributions. It provides efficient storage and better performance than other drivers.
- aufs: This driver is an older storage driver that is no longer recommended for new deployments. It is still supported for legacy systems.
- btrfs, devicemapper, zfs: These drivers are available, but are less commonly used than overlay2.

## Docker volumes

Docker volumes provide a way to share data between containers and the host system. A volume is a directory that is stored outside of the container's file system and can be shared between multiple containers. Docker volumes can be created using the Docker CLI or the Docker API.

### Creating a Docker volume

To create a Docker volume, use the following command:

```bash
docker volume create <volume-name>
```

This will create a new Docker volume with the specified name. You can then use the volume with the docker run command:

```bash
docker run -v <volume-name>:/path/to/mount <container-image>
```

This will mount the Docker volume at the specified path inside the container.

### Managing Docker volumes

You can list all the Docker volumes on your system using the following command:

```bash
docker volume ls
```

You can inspect the details of a specific Docker volume using the following command:

```bash
docker volume inspect <volume-name>
```

You can remove a Docker volume using the following command:

```bash
docker volume rm <volume-name>
```

## Docker bind mounts

Docker bind mounts provide a way to mount a directory from the host system into a Docker container.  
This allows the container to access files and directories from the host system. Docker bind mounts are created using the `-v` option with the docker run command:

```
docker run -v /host/path:/container/path <container-name/id>
```

This will mount the directory at /host/path on the host system to /container/path inside the container.

## Conclusion

Docker storage provides a range of storage options for containerized applications, including storage drivers, volumes, and bind mounts. Docker volumes provide a way to share data between containers and the host system, while bind mounts allow containers to access files and directories from the host system. By leveraging Docker storage options, you can build and deploy containerized applications with efficient, scalable, and reliable storage.
