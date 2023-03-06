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