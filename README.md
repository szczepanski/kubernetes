# microservices, docker and kubernetes


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

## install docker
```shell 
sudo apt-get install docker.io 
sudo docker images
# download nginx img and its dependencies
sudo docker pull nginx:1.10.0
```
