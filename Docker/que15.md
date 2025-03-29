# 15.Create a private Registry server and push any images to that and create a container from pushed images.

```sh
docker run -d -p 5000:5000 --name private-registry registry:2
docker tag <your_DokerHub_Login_id>/my-apache-mysql:latest localhost:5000/my-apache-mysql
docker image ls
```
You can see this image which we done in que11
```sh
localhost:5000/my-apache-mysql   latest    9b940b094473
```
```sh
docker push localhost:5000/my-apache-mysql
curl -X GET http://localhost:5000/v2/_catalog
```
See this as a output
```sh
{"repositories":["my-apache-mysql"]}
```
```sh
docker run -d -p 8080:80 localhost:5000/my-apache-mysql
curl -I http://localhost:8080
```
It will give you like HTTP/1.1 200 OK

