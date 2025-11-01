# Docker-Networking-Project
## How to connect two container within Metworks.
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
