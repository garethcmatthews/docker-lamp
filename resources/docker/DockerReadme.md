
# LAMP Docker Application

A LAMP based Docker application for use in development.

### Containers
> **lamp-apache**: Apache, PHP, curl, nano, composer  
> **lamp-mysql**: MySQL 8  
> **lamp-phpmyadmin**: phpMyadmin  

### PHP Versions
> PHP 7.4.33  
> PHP 8.0.30, 8.1.27, 8.2.15, PHP 8.3.2

### Setup
Copy the files 'docker.env' and 'docker-compose.yaml' from the required PHP versions folder to the project root.

> Example  
> Copy ./resources/docker/development/php-8.3.2/docker.env to ./  
> Copy ./resources/docker/development/php-8.3.2/docker-compose.yaml to ./

### Docker

#### Run Docker
> docker compose up -d

#### Rebuild containers after any config changes
> docker compose up -d --build 

#### Access PHP box...
> docker exec -it lamp-php /bin/bash 
#### Access MySQL box...
> docker exec -it lamp-mysql /bin/bash  
#### Access PHPMyAdmin box...
> docker exec -it lamp-phpmyadmin /bin/bash 

#### Browser
> http://localhost:8080

#### PHPmyadmin
> http://localhost:8888
