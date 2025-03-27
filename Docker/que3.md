3.Can you explain the different volume mount types available in Docker?
--> 2 types of volume mount :- 1. Bind mount [ root@ip-172-31-15-80:~# mkdir bind
                                               root@ip-172-31-15-80:~# cd bind
                                               root@ip-172-31-15-80:~/bind# vi index.html
                                               root@ip-172-31-15-80:~/bind# cd
                                               root@ip-172-31-15-80:~# docker container run -d -p 80:80 -v /root/bind/:/usr/local/apache2/htdocs --name bind-cont httpd ]
                               2. local mount [ root@ip-172-31-15-80:~# docker container run -d -p 80:80 -v local:/usr/local/apache2/htdocs --name local-cont httpd
                                                root@ip-172-31-15-80:~# cd /var/lib/docker/volumes/local/_data/
                                                root@ip-172-31-15-80:/var/lib/docker/volumes/local/_data# ls
                                                        index.html
                                                root@ip-172-31-15-80:/var/lib/docker/volumes/local/_data# cat index.html
                                                       <html><body><h1>It works!</h1></body></html> ]

