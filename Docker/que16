16.Create an image of nginx with the help of Dockerfile and application container run on 8087 port.
--> root@ip-172-31-15-80:~# mkdir nginx-docker
    root@ip-172-31-15-80:~# cd nginx-docker/
    root@ip-172-31-15-80:~/nginx-docker# nano Dockerfile [ # Use the official NGINX base image
                                                          FROM nginx:latest
                                                          # Copy a custom index.html to the container
                                                          COPY index.html /usr/share/nginx/html/index.html
                                                          # Expose port 80 inside the container
                                                          EXPOSE 80
                                                          # Start NGINX
                                                          CMD ["nginx", "-g", "daemon off;"]  ]
    root@ip-172-31-15-80:~/nginx-docker# nano index.html [ <!DOCTYPE html>
                                                           <html lang="en">
                                                           <head>
                                                              <meta charset="UTF-8">
                                                              <meta name="viewport" content="width=device-width, initial-scale=1.0">
                                                              <title>Welcome to NGINX</title>
                                                           </head>
                                                           <body>
                                                              <h1>Hello, this is a custom NGINX page!</h1>
                                                           </body>
                                                           </html>  ]
    root@ip-172-31-15-80:~/nginx-docker# cd
    root@ip-172-31-15-80:~# docker build -t my-nginx .
    root@ip-172-31-15-80:~# docker run -d -p 8087:80 --name nginx-container my-nginx
    root@ip-172-31-15-80:~# curl -I http://localhost:8087
               HTTP/1.1 200 OK
