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

## Docker mounts

In Docker, mounts allow you to share files and directories between the host machine and the Docker container. By using mounts, you can persist data across container restarts and share data between containers.

There are two ways we can mount the volume to docker container.

1.  `-v` option (deprecated)
2. `--mount` option

### `-v` option:

This is the older way of mounting volumes in Docker. With this option, you can specify the path to the host directory or file to be mounted, as well as the path inside the container where the directory or file should be mounted.  
For example, the following command mounts the host directory `/path/to/host/directory` to the container directory `/path/to/container/directory`:

```
docker run -v /path/to/host/directory:/path/to/container/directory myimage
```

### `--mount` option:

This is the newer way of mounting volumes in Docker. With this option, you can specify the same information as with the `-v` option, but you can also specify additional options such as the read-only flag or the volume driver. `--mount` is more explicit and verbose.
For example, the following command mounts the host directory `/path/to/host/directory` to the container directory `/path/to/container/directory` and sets it to read-only:

```
docker run --mount type=bind,source=/path/to/host/directory,target=/path/to/container/directory,readonly myimage
```

The deprecated way of mounting volumes in Docker is to use the `-v` option without specifying the type of mount. This is equivalent to using `--mount type=bind`, which is the recommended way of mounting volumes in Docker.

The new way of volume mounting using the `--mount` option provides more flexibility and options than the older `-v` option. You can use it to specify the type of mount (such as a bind mount or a volume mount), the source and target directories or files, and additional options such as the read-only flag or the volume driver.

## Types of docker mounts

### Docker bind mount

Bind mounts allow you to mount a file or directory on the host machine to a directory in the Docker container.
Docker bind mounts can be created using the `-v` option with the docker run command:

```
docker run -v /host/path:/container/path <image-name>
```

Or using the `--mount` option with the docker run command:

```
docker run --mount type=bind,source=/host/path,target=/container/path <image-name>
```

This will mount the directory at `/host/path` on the host system to `/container/path` inside the container.

### Docker volume mount

Volume mounts allow you to create a new volume or use an existing volume to store data that can be shared between containers. 
Volume mounts are stored in the Docker host's file system, but they can be managed by Docker and easily moved between hosts.

Volume mounts are created using the `-v` or `--mount` option and specifying the volume name and target directory.  
For example, the following command creates a new volume named `myvolume` and mounts it to the directory `/path/to/container/` directory in the container using `-v` option:

```
docker run -v myvolume:/path/to/container/directory myimage
```

If the volume `myvolume` does not exist, it will be created automatically (Only when using the `-v` option).

Or using `--mount` option:

```
docker run --mount type=volume,source=/path/to/host,target=/path/to/container myimage
```

When using the `--mount` option with `type=volume`, the source parameter specifies the name of the volume to use. If the specified volume does not exist, Docker will return an error message.

Thats why create the specified volume before running the above command.

## Conclusion

Docker storage provides a range of storage options for containerized applications, including storage drivers, volumes, and bind mounts. Docker volumes provide a way to share data between containers and the host system, while bind mounts allow containers to access files and directories from the host system. By leveraging Docker storage options, you can build and deploy containerized applications with efficient, scalable, and reliable storage.
