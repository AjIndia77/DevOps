# 13. Restart the docker service and now remove all the stopped containers without using the 'rm' command.
By 
```plaintext
prune
``` 
command we can remove all stopped containers
```sh
systemctl restart docker
docker container prune
```
