Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. 

Here is the format of the Dockerfile:

```bash
INSTRUCTION     arguments
```

eg. Dockerfile

```bash
# Use the official Python image as the base image
FROM python:3.9-slim-buster

# Set the working directory within the container
WORKDIR /app

# Copy the requirements.txt file from the host into the container
COPY requirements.txt .

# Install the required packages within the container
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code from the host into the container
COPY app.py .

# Set the command to run when the container starts
CMD ["python", "app.py"]

# Expose port 5000 for the application
EXPOSE 5000
```

This Dockerfile does the following:

1. Specifies the base image to use (`python:3.9-slim-buster`).
2. Sets the working directory within the container (`/app`).
3. Copies the `requirements.txt` file from the host into the container.
4. Installs the required packages within the container using `pip`.
5. Copies the `app.py` file from the host into the container.
6. Sets the command to run when the container starts (`python app.py`).
7. Exposes port 5000 for the application.


> The instruction is not case-sensitive. However, convention is for them to be UPPERCASE to distinguish them from arguments more easily.

Some **common arguments** that can be used in a Dockerfile:

| Argument | Description |
| ----------- | ---------- |
| FROM | Specifies the base image to use for the new image |
| MAINTAINER(Deprecated) | Specifies the author of the image |
| AUTHOR | Specifies the author of the image |
| RUN | Runs a command within the container |
| CMD | Specifies the command to run when the container is started |
| LABEL | Adds metadata to the image |
| EXPOSE | Specifies which ports the container will listen on |
| ENV | Sets an environment variable within the container |
| ADD | Copies a file or directory from the host machine into the container |
| COPY | Copies a file or directory from the host machine into the container |
| ENTRYPOINT | Specifies the command to run when the container is started |
| VOLUME | Creates a mount point for external storage |
| USER | Sets the user or UID to use when running the container |
| WORKDIR | Sets the working directory for the container |

[More INSTRUCTION here](https://docs.docker.com/engine/reference/builder/)

> MAINTAINER has been deprecated in favour of using the LABEL instruction.

## Notes

1. A Dockerfile begins with a base image, which is the starting point for building the new image. The base image is specified with the `FROM` instruction, which is always the first instruction in a Dockerfile.

2. Dockerfiles typically contain a series of instructions that are executed in order. Each instruction creates a new layer in the image, which allows for efficient reuse of common elements across multiple images.

3. Some common instructions in a Dockerfile include `RUN`, which executes a command within the container, COPY, which copies files from the host machine into the container, and `EXPOSE`, which specifies which ports the container will listen on.

4. Dockerfiles can also use variables and arguments, which can be passed in at build time to customize the image.

5. Once a Dockerfile is written, it can be built into an image using the docker build command. This command takes the Dockerfile as input and produces a new image as output.

```bash
docker build -t <image:tag> /path/of/Dockerfile
```

6. Dockerfiles are often versioned and stored alongside source code in a version control system like Git, which allows for easy collaboration and reproducibility across different environments.