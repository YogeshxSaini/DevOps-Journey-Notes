<h1 align="center"> Port Mapping </h1>

Port publishing, also known as port mapping or port forwarding, is the process of exposing a container's network ports to the host system or to the external network. When you publish a container's ports, you can access the services running inside the container from outside the container, either on the host system or on the internet.

As we all know, containers are isolated system which means containers cannot communicate with the outside world. By publishing ports, you can make the container's services accessible to other containers or to external clients, such as web browsers or APIs.

Suppose you have a web application running inside a Docker container, and the application is listening for incoming HTTP requests on port 80. By default, the container's network is isolated, and the application cannot receive requests from outside the container.

To make the webapp accessible from outside the container, you can publish port of container to a port on the host system using the command below.

```bash
docker run -p <port_on_host>:<exposed_port_on_container> <image>
```

For eg. you can publish port 80 of the container to port 8080 on the host

```bash
docker run --name my-web-app -p 8080:80 kodekloud/simple-webapp
```

In this example, my-web-app is the name or ID of the container, and -p 8080:80 specifies that port 80 of the container should be mapped to port 8080 on the host system. Once the container is running, you can access the web application by navigating to http://localhost:8080 or http://127.0.0.1:8080 in a web browser.

```bash
$ docker run --name my-web-app -p 8080:80 kodekloud/simple-webapp
 This is a sample web application that displays a colored background.
 A color can be specified in two ways.

 1. As a command line argument with --color as the argument. Accepts one of red,green,blue,blue2,pink,darkblue
 2. As an Environment variable APP_COLOR. Accepts one of red,green,blue,blue2,pink,darkblue
 3. If none of the above then a random color is picked from the above list.
 Note: Command line argument precedes over environment variable.


No command line argument or environment variable. Picking a Random Color =red
 * Serving Flask app "app" (lazy loading)
 * Environment: production
   WARNING: Do not use the development server in a production environment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
172.17.0.1 - - [27/Feb/2023 11:07:11] "GET / HTTP/1.1" 200 -
172.17.0.1 - - [27/Feb/2023 11:07:11] "GET /favicon.ico HTTP/1.1" 404 -
```