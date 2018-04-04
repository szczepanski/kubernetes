# microservices, docker and kubernetes


# Docker
It is a packaging format that includes an application(s), its dependencies and runtime information / variables required to run it.  
Used to create, distribute and run containers on a server machine. 
- Cretae GCP VM 

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


```
