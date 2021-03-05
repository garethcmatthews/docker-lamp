# LAMP Docker Application

A LAMP based Docker application for use in development.

### Containers
* **lampserver-apache** - Apache, PHP7.4/8.0, curl, nano, composer
* **lampserver-mysql** - MySQL 8
* **lamp-phpmyadmin** - phpMyadmin

### PHP version
To change the PHP version update the docker file located at ./docker/php/Dockerfile

### URL's
* **PHP Application** - http://localhost:8080
* **PhpMyadmin** - http://localhost:8888

### Bash
docker exec -it lampserver-php /bin/bash  
docker exec -it lampserver-phpmyadmin /bin/bash  
docker exec -it lampserver-mysql /bin/bash  

### Server Code
The apache server is setup to run from public  
