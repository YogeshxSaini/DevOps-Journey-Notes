<h1 align="center"> Docker Run </h1>

This command is used to run a container.

- First, Docker will search for the requested image locally. If it is available, Docker will run the image and create a container from it.

```bash
docker run centos
Unable to find image 'centos:latest' locally
```
- If the requested image is not available locally, Docker will pull the image from the Docker registry and then run it.

```bash
docker run centos
Unable to find image 'centos:latest' locally
latest: Pulling from library/centos
```