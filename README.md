# Dockerizing_Custom_Webserver
Dockerizing_Custom_Webserver Including a Plain HTML Page with Nginx

Objective:

The objective of this assignment is to familiarize yourself with Docker and containerization by Dockerizing a simple HTML page using Nginx as the web server.

Requirements:

I have used an EC2 instance for this task.

![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/6032a0fc-cc75-408c-b5a0-376678a76702)

Install Docker by running 

```
sudo apt install docker.io -y
```
![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/bca1ef14-d8c9-43d6-9237-95ab3c55cfc0)


Also, install nginx on this node

```
sudo apt install nginx -y
```
![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/56b629de-10fe-47bd-b7c5-cf4294788706)

Clone the repo on this node by running

```
sudo git clone https://github.com/adm077/Dockerizing_Custom_Webserver.git

```

![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/3fb69ced-5790-4828-8492-b763537308b3)


1. Basic HTML Page:

   - Create a plain HTML page named `index.html` with some content (e.g., "Hello, Docker!").

```
#------------------------------index.html----------------------------------#
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
```

2. Nginx Configuration:

   - Create an Nginx configuration file named `nginx.conf` that serves the `index.html` page.

   - Configure Nginx to listen on port 80.

```
#-----------------------------nginx.conf-------------------------#
events {}
http {
    server {
        listen 80;
        location / {
            root /usr/share/nginx/html;
            index index.html;
        }
    }
}
#----------------------------------------------------------------#
```

3. Dockerfile:

   - Create a `Dockerfile` to define the Docker image.

   - Use an official Nginx base image.

   - Copy the `index.html` and `nginx.conf` files into the appropriate location in the container.

   - Ensure that the Nginx server is started when the container is run.

```
#---------------------------Dockerfile----------------------#
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html
COPY nginx.conf /etc/nginx/nginx.conf
#-----------------------------------------------------------#
```

4. Building the Docker Image:

   - Build the Docker image using the `Dockerfile`.
```
docker build -t custom_webserver:v1 -f dockerfile .
```

5. Push the image on ECR

  - Make the public repository and push them on the ECR

![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/a5a41e28-85ea-4645-9d3a-d92750ca4a47)

![image](https://github.com/adm077/Dockerizing_Custom_Webserver/assets/139608052/088590fe-1385-4010-9c29-5fa945ef6c14)


