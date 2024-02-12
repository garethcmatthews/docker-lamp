
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

### Running PHP7 and PHP8 side by side
Copy the files 'docker.env' and 'docker-compose.yaml' from the 'php-dual' folder to the project root.

> Copy ./resources/docker/development/php-dual/docker.env to ./  
> Copy ./resources/docker/development/php-dual/docker-compose.yaml to ./

To edit the php version update ./docker-compose.yaml to the version folder that is required

Example: for PHP 8.1.27  
```
    php8:  
        # DOCKER HUB: https://hub.docker.com/_/php/  
        build: ./resources/docker/development/php-8.1.27/apache-php  
```

#### Access Dual PHP box...
> docker exec -it lamp-php7 /bin/bash  
> docker exec -it lamp-php8 /bin/bash  
#### Access MySQL box...
> docker exec -it lamp-mysql /bin/bash  
#### Access PHPMyAdmin box...
> docker exec -it lamp-phpmyadmin /bin/bash  

#### Browser
> http://localhost:8080  
> http://localhost:8088  
#### PHPmyadmin
> http://localhost:8888  
