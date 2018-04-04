Piotr Szczepanski

# microservices, docker and kubernetes
<br>
References:

https://classroom.udacity.com/courses/ud615

# Microservies



# Docker
It is a packaging format that includes an application(s), its dependencies and runtime information / variables required to run it.  
Used to create, distribute and run containers on a server machine. 

## Cretae GCP VM run instal run and stop manually nginx

```shell
gcloud compute instances create ubuntu --image-project ubuntu-os-cloud --image ubuntu-1604-xenial-v20160429
gcloud compute ssh ubuntu
sudo apt-get update
sudo apt-get install nginx
nginx -v
sudo systemctl start nginx
sudo systemctl status nginx
curl http://127.0.0.1 
sudo ps aux | grep nginx
sudo systemctl stop nginx
sudo ps aux | grep nginx
```
Native OS are good when it comes to installing, starting and stopping applications. 
When it comes to running multiple instances of one application or running different versions of the application, required configuration becomes complex.  

## install docker and two preconfigured images(versions) of nginx 
```shell 
sudo apt-get install docker.io 
sudo docker images

# download nginx (image and all its dependencies)
sudo docker pull nginx:1.10.0
sudo docker images

# run docker nginx
sudo docker run -d nginx:1.10.0
sudo docker ps

# install (pull) and run older nginx version
sudo docker run -d nginx:1.9.3
sudo docker ps
```

## Communication with docker containers
```shell
# copy specific docker container id
sudo docker ps
# check docker information including its IPv4
sudo docker inspect 43263f45699c
curl 172.17.0.4
```
## cleanup 
```shell
# get docker containers IDs
sudo docker ps
sudo docker stop 43263f45699c bf84cfdfa4c1 4809bdf9e792top 

# remove docker containers and any files
sudo docker rm 43263f45699c bf84cfdfa4c1 4809bdf9e792top
sudo docker ps
```

## Building own docker images - Dockerfile
As best practice an application is not build with Docker. 
Instead binaries are used that could've come from continuous integration pipeline. 
Dockerfile - text document containg series of necessary steps for building and image from CLI.

### Basic Dockerfile Format:
```shell
# From - tells docker which base image to build new image on top of, 
# here most popular Linux Apline 3.1. - small, contains package management and production debugging 
# default for officila docker images (5Mb size)
# maintainer - author 
# ADD - takes file or directory from host OS and add it to the container file system specified location
# ENTRYPOINT - let container to r

From Alpine:3.1
MAINTAINER ptr.szczepanski@gmail.com
ADD hello /usr/bin/hello
ENTRYPOINT ["hello"]
```

