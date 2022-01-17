# Docker and Kubernetes

<p align="center">
  <img src="utils/docker-logo.png">
</p>

## **What is Docker?**

* Docker is a tool for running applications in an isolated Enviroment.
* Similar to Virtual Machine
* App run in same enviroment
* Standard for Software Deployment.

### ⬇️ Install a specific Images.

I am using Nginx but you can choose any there are multiple options like alpine,mongo and many more.

`docker run --name nginx -d nginx` or `docker run postgres:9.6` or `docker run nginx:latest`

-d : detach mode

### 🏃‍♂️ Run an Image in interactive mode.

docker run -it ubuntu bash

### 🏃‍♂️ Run Docker Container

`docker container run --publish 80:80 --detach --name webhost nginx`

or 

Exposing One Container to Different Ports 🔌:

`docker container run -d -p 8080:80 -p 3000:80 nginx:latest`

### 📝 List all Docker Containers

`docker container ls -a` or `docker container ps -a`

### ✔️ Checks logs

`docker container logs webhost`

### ✔️ Check Inner Docker Working

`docker container top webhost`

### Remove Docker Container

`docker container rm [Container_Id]` or `docker rm $(docker ps -aq)`


## 🔨 Building a Custom Image with Docker
### Steps involved
```
1 apt-get update
2 apt-get install -y python3
3 apt-get install -y python3-pip
4 pip3 install flask
5 cd opt/
6 apt install vim
7 apt install curl
8 vi app.py
9 python3 app.py

#### Finally Run the below command

docker build . -t imagename

```

## To run the docker file with Enviroment variable
### First you have create a .env file
#### .env file content
```
MY_USER=dibyaranjan
MY_PASSWORD=12345
```
### 📙 Use below command to pass the environment details
```
docker run --env-file=.env envvar
```

## 📌 To PUSH your image
```
docker login
docker build . -t  dibyaranjan/calciapp
docker push dibyaranjan/calciapp
```




 
















