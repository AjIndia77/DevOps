# 16.Create an image of nginx with the help of Dockerfile and application container run on 8087 port.
Create a directory name of
```plaintext
nginx-docker
```
```sh
mkdir nginx-docker
cd nginx-docker/
```
create a Dockerfile in nginx-docker
```sh
nano Dockerfile 
```
paste this content in the Dockerfile
```sh
# Use the official NGINX base image
FROM nginx:latest
# Copy a custom index.html to the container
COPY index.html /usr/share/nginx/html/index.html
# Expose port 80 inside the container
EXPOSE 80
# Start NGINX
CMD ["nginx", "-g", "daemon off;"]  
```
now create an 
```plaintext
index.html
```
file.
```sh
nano index.html 
```
and paste this content
```sh
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Welcome to NGINX</title>
</head>
<body>
<h1>Hello, this is a custom NGINX page!</h1>
</body>
</html>  
```
```sh
cd
docker build -t my-nginx .
docker run -d -p 8087:80 --name nginx-container my-nginx
curl -I http://localhost:8087
```
and you will see this output
```plaintext
HTTP/1.1 200 OK
```
