# 10.How can we run 2 services in a single container like Apache and MySQL?
Create a file with the name of Dockerfile 

```sh
vi Dockerfile
```
And paste the content in the file
```sh
FROM ubuntu:latest
# Install Apache and MySQL
RUN apt-get update && apt-get install -y apache2 mysql-server
# Copy and set entrypoint script
COPY start.sh /start.sh
RUN chmod +x /start.sh
# Expose ports
EXPOSE 80 3306
CMD ["/start.sh"] 
```
Then create a file name of start.sh

```sh
vi start.sh
```
Paste this content in the file
```sh
#!/bin/bash
service apache2 start
service mysql start
tail -f /dev/null
```
Now we will build and run the container
```sh
docker build -t apache-mysql .
docker run -d -p 80:80 -p 3306:3306 apache-mysql
```
