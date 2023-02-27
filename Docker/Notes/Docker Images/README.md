<h1 align="center"> Docker Images </h1>

| Command                        | Description                                |
| ------------------------------ | ------------------------------------------ |
| `docker images`                | # List all the available images            |
| `docker pull <image:tag>`      | # Pull an image from the registry          |
| `docker push <image:tag>`      | # Push an image to the registry            |
| `docker rmi <image:tag>`       | # Remove an image from the local machine   |
| `docker inspect <image:tag>`   | # Display detailed information about image |


**Note**

1. We can't remove a image, if one or more containers are running from it. Stop and remove the containers before removing the image.
2. If no tag is given in command, then 'latest' tag will be used.


**Tips**

1. Delete all the images
    `docker rmi -f $(docker images -q)`