# Docker-Networking-Project
## How to connect two container within Networks.
## Mysql and two-tier-flask-app 
### Commands:-
* sudo apt-get update -y
* sudo apt- get install docker.io && docker compose-v2
* docker --version
### For Giving Permisions
* sudo usermod -aG docker $USER
* newgrp docker
### shows docker images
* docker images
### show docker container
* docker ps
## Create mysql images and make container.
### Command is
* docker pull mysql
* docker images
### Make container of mysql from images
* docker run -d -e MYSQL_ROOT_PASSWORD=root "image-name"
* docker ps

## Take "Two-teir-flask-app" from github repository and make images and Container
* git clone "HTTPS link of github paste-here"

### Create Image From Docker file command is:-
* docker build -t "image-name" .
* docker images

### Create Container from docker images command is:-
* docker run -d -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=root -e MYSQL_DB=mydb -p 5000:5000 "images-name:latest"
* docker ps

### Stop And Delete both container and first Create your own Networks on Bridge type.
### Command is:-
* docker stop "container_id"
* docker rm "container_id"

### If this is not running lets Create our own network and network attached to container.
### Command is:-
* docker network ls
* docker network create two-tier -d bridge
* docker network ls

## Now Make both Container Within Network Command is
### Create Mysql Container command is:-
* docker run -d --name mysql --network two-tier -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=devops mysql:latest
## Now Make Two-Tier-Flask-App within network Command is:-
* docker run -d -p 5000:5000 --network two-tier -e MYSQL_HOST=mysql -e MYSQL_USER=root -e MYSQL_PASSWORD=root -e MYSQL_DB=devops flasks-backend-app:latest
### Now both Containers Are Running Within Networks you can check on "public_ip_add:5000"
