15.Create a private Registry server and push any images to that and create a container from pushed images.
--> root@ip-172-31-15-80:~# docker run -d -p 5000:5000 --name private-registry registry:2
    root@ip-172-31-15-80:~# docker tag ambikaaj/my-apache-mysql:latest localhost:5000/my-apache-mysql
    root@ip-172-31-15-80:~# docker image ls
             localhost:5000/my-apache-mysql   latest    9b940b094473 
    root@ip-172-31-15-80:~# docker push localhost:5000/my-apache-mysql
    root@ip-172-31-15-80:~# curl -X GET http://localhost:5000/v2/_catalog
             {"repositories":["my-apache-mysql"]}
    root@ip-172-31-15-80:~# docker run -d -p 8080:80 localhost:5000/my-apache-mysql
    root@ip-172-31-15-80:~# curl -I http://localhost:8080
            HTTP/1.1 200 OK
