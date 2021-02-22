# LAMP (+Node/Angular) Docker Application

A LAMP based Docker application for use in development.

### Containers
* **lampserver-apache** - Apache, PHP7.4/8.0, composer
* **lampserver-mysql** - MySQL 8
* **lampserver-node** - Nodejs 14 and Angular
* **lamp-phpmyadmin** - phpMyadmin

### PHP version
To change the PHP version update the docker file located at ./docker/php/Dockerfile

### Scripts
* **docker/docker-cleanup.sh** Script to cleanup docker tmp folder (data and logs)

### URL's
* **Angular** - http://localhost:4200
* **PHP Application** - http://localhost:8080
* **PhpMyadmin** - http://localhost:8888

### Start LAMP
docker-compose up -d --build mysql php phpmyadmin 

### Bash
docker exec -it lampserver-php /bin/bash  
docker exec -it lampserver-phpmyadmin /bin/bash  
docker exec -it lampserver-mysql /bin/bash  

### Composer
docker-compose run --rm composer create-project mezzio/mezzio-skeleton ./application/skeleton  
**move files from skeleton subfolder to ./application-backend after download**  

docker-compose run --rm composer require laminas/laminas-config

### Angular/Node
docker-compose run --rm --publish 4200:4200 node bash

### ANGULAR
ng new hello-world --skip-git  
**move files from hello-world subfolder to ./application-frontend after download - exclude node_modules**  

npm install  
**node_nodules folder is retained on the container - slower builds/faster angular runs - npm update is run at startup**  

**Enable Angular file change watch**  

    "architect": {
        "build": {
            "options": {
                "poll": 1000,

**Run/Watch**  
docker-compose run --name lampserver-node --publish 4200:4200 node bash  
npm install (keeping this on the container results in faster builds)  
ng serve --host 0.0.0.0 --port 4200  

docker start lampserver-node  
docker exec -it lampserver-node /bin/bash  
