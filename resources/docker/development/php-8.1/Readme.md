
# LAMP Docker Application

A LAMP based Docker application for use in development.

### Containers
> **lamp-apache**: Apache, PHP 8.1.27 , curl, nano, composer  
> **lamp-mysql**: MySQL 8.3.0
> **lamp-phpmyadmin**: phpMyadmin  

### Setup
Copy the file 'docker-compose.yaml' to the project root.

> Example  
> Copy ./resources/docker/php-8.1/development/docker-compose.yaml to ./

### Docker

#### Run Docker
> docker compose up -d

#### Rebuild containers after any config changes
> docker compose up -d --build 

#### Access PHP box...
> docker exec -it php /bin/bash 

#### Access MySQL box...
> docker exec -it mysql /bin/bash  

#### Access PHPMyAdmin box...
> docker exec -it phpmyadmin /bin/bash 

#### Browser
> http://localhost:8080

#### PHPmyadmin
> http://localhost:8888
