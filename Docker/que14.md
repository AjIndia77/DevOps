# 14.Create an N/W with 192.168.0.0/16 subnet and create 2 containers in default and created N/W respectively and make sure only these 2 containers can communicate.
```sh
docker network create --subnet=192.168.0.0/16 custom_network
docker run -itd --name default-cont ubuntu:latest
docker run -itd --name custom-cont --net custom_network ubuntu:latest
docker network connect custom_network default-cont
docker exec -it default-cont bash
```
```sh
ping --version
apt update && apt install -y iputils-ping
```
To get exit from the last command type
```plaintext
Ctrl+p+q 
```
```sh
docker exec -it default-cont ping -c 3 custom-cont
```
