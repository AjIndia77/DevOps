6.When you restart the docker service, all your container goes down, so how you will overcome this problem?
--> root@ip-172-31-15-80:~# docker run --restart always -d httpd
                            docker container inspect <container-id>
