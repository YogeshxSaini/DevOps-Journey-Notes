<h1 align="center"> Docker Images </h1>

| Command                                                  | Description                                |
| -------------------------------------------------------- | ------------------------------------------ |
| `docker images`                                          | # List all the available images            |
| `docker pull <image:tag>`                                | # Pull an image from the registry          |
| `docker push <image:tag>`                                | # Push an image to the registry            |
| `docker rmi <image:tag>`                                 | # Remove an image from the local machine   |
| `docker inspect <image:tag>`                             | # Display detailed information about image |
| `docker build -t "name_image:tag" </path/of/Dockerfile>` | # Build an image from Dockerfile           |


**Note**

1. We can't remove a image, if one or more containers are running from it. Stop and remove the containers before removing the image.
2. If no tag is given in command, then 'latest' tag will be used.


**Tips**

1. Delete all the images
    `docker rmi $(docker images -q)`

    ```bash
    $ docker rmi $(docker images -q)

    Untagged: redis:latest
    Untagged: redis@sha256:eff56acc5fc7b909183da93236ba09d3b8cb7d6db31d5b25e9a46dac9b5e699b
    Deleted: sha256:ccee4cdf984f11952441cbab30146dae792c8d9fb668e762c78a49e7db858082
    Deleted: sha256:a4f3d68d06ee9aec1862695818528930f0e889f5c892da8be4c06759dc2e8f86
    Deleted: sha256:02c22c39334cefb22054330d3be804a3046286d7f0a47d83f5f25be13f4e635e
    Deleted: sha256:2d01997f1c500789fc369f5440ea810257641af6fbb1d4eaeb9558d94ea8879d
    Deleted: sha256:f448a5cc1367794bb2f15d887438c8b43f2324ee3523f5d95c15997685cc816d
    Deleted: sha256:e481db33c0c73ee7de5ecda57c21fcfb7eeeff7d22fcc4ad0166b0bf64a63a32
    Untagged: ubuntu:latest
    Untagged: ubuntu@sha256:cf31af331f38d1d7158470e095b132acd126a7180a54f263d386da88eb681d93
    Deleted: sha256:7e0aa2d69a153215c790488ed1fcec162015e973e49962d438e18249d16fa9bd
    Deleted: sha256:3dd8c8d4fd5b59d543c8f75a67cdfaab30aef5a6d99aea3fe74d8cc69d4e7bf2
    Deleted: sha256:8d8dceacec7085abcab1f93ac1128765bc6cf0caac334c821e01546bd96eb741
    Deleted: sha256:ccdbb80308cc5ef43b605ac28fac29c6a597f89f5a169bbedbb8dec29c987439
    ```