<h1 align="center"> Dockerfile </h1>

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

## Some **common arguments** that can be used in a Dockerfile:

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


## Tips

1. Use a small base image: Choose a base image that is as small as possible to reduce the overall size of the image.

2. Keep the Dockerfile simple: Keep the Dockerfile as simple as possible by breaking it up into logical sections and minimizing the number of steps.

3. Use caching: Use Docker's layer caching mechanism to speed up the build process.

4. Avoid unnecessary software: Avoid installing unnecessary software and packages in the image to keep it lightweight.

5. Minimize the number of layers: Minimize the number of layers in the image by combining multiple commands into a single RUN instruction.

6. Use environment variables: Use environment variables to parameterize the Dockerfile and make it more flexible.

7. Use labels: Use labels to add metadata to the image, such as the version number or the author.

8. Clean up after yourself: Remove any temporary files or artifacts created during the build process to keep the image size small.

## Things to always remember:

1. Always specify a base image in the `FROM` instruction.

2. Use the `WORKDIR` instruction to set the working directory within the container.

3. Use the `COPY` instruction to copy files from the host machine into the container.

4. Use the `RUN` instruction to execute commands within the container.

5. Use the `CMD` instruction to specify the command to run when the container is started.

6. Use the `EXPOSE` instruction to specify which ports the container will listen on.

7. Test the image: Test the image thoroughly to ensure that it works as expected before using it in production.

8. Keep the Dockerfile versioned: Keep the Dockerfile versioned along with the application source code to ensure that the image can be reproduced at any time.