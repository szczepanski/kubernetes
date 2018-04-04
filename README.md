Piotr Szczepanski

# microservices, docker and kubernetes
<br>
References:

https://classroom.udacity.com/courses/ud615



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

## install docke and two preconfigured images of nginx versions
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

## Building own docker images - lesson 10
