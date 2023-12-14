# Dockerizing_Custom_Webserver
Dockerizing_Custom_Webserver Including a Plain HTML Page with Nginx

Objective:

The objective of this assignment is to familiarize yourself with Docker and containerization by Dockerizing a simple HTML page using Nginx as the web server.

Requirements:

1. Basic HTML Page:

   - Create a plain HTML page named `index.html` with some content (e.g., "Hello, Docker!").

'''

#------------------index.html---------------------------------------------#
<!DOCTYPE html>
<html>
<head>
    <title>Hello, Docker!</title>
</head>
<body>
    <h1>Hello, Docker!</h1>
    <p>This is a plain HTML page served by Nginx in a Docker container.</p>
</body>
</html>
#--------------------------------------------------------------------------#

'''

2. Nginx Configuration:

   - Create an Nginx configuration file named `nginx.conf` that serves the `index.html` page.

   - Configure Nginx to listen on port 80.

3. Dockerfile:

   - Create a `Dockerfile` to define the Docker image.

   - Use an official Nginx base image.

   - Copy the `index.html` and `nginx.conf` files into the appropriate location in the container.

   - Ensure that the Nginx server is started when the container is run.

4. Building the Docker Image:

   - Build the Docker image using the `Dockerfile`.

5. Push the image on ECR

  - Make the public repository and push them on the ECR
