# LAMP (+Node/Angular) Docker Application

A LAMP based Docker application for use in development.

### Containers
* **lampserver-apache** - Apache, PHP7.4/8.0, curl, nano, composer
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

### Bash
docker exec -it lampserver-php /bin/bash  
docker exec -it lampserver-phpmyadmin /bin/bash  
docker exec -it lampserver-mysql /bin/bash  

### Server Code
The apache server is setup to run from server/public  
The vendor folder is excluded from volumes for speed  

### Client Code
Angular should be run from client
The node_modules folder is excluded from volumes for speed  

**Enable Angular file change watch**  

    "architect": {
        "build": {
            "options": {
                "poll": 1000,

**Run/Watch**  
npm install (keeping this on the container results in faster builds)  
ng serve --host 0.0.0.0 --port 4200  
