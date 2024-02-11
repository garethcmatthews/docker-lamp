
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

### Running PHP7 and PHP8 together
if you have a project that requires PHP7 and 8 running then select the PHP8 project you want and copy the files.

> Example  
> Copy ./resources/docker/development/php-8.3.2/docker.env to ./  
> Copy ./resources/docker/development/php-8.3.2/docker-compose.yaml to ./

Edit docker-compose.yaml and edit as follows...

> PHP7  
> Copy php section from php-7.4.33 docker-compose.yaml  
> Name service php7  
> Change container name from lamp-php to lamp-php7  
> PHP8  
> Change container name from lamp-php to lamp-php8  
> Change ports from 8080:80 to 8088:80  

example

```
services:
    php7:
        # DOCKER HUB: https://hub.docker.com/_/php/
        build: ./resources/docker/development/php-7.4.33/apache-php
        container_name: lamp-php7
        depends_on:
            mysql:
                condition: service_healthy
        env_file:
            - 'docker.env'
        networks:
            - backend
            - frontend
        ports:
            - 8080:80
        volumes:
            - ./:/var/www/html
            - /var/www/html/vendor
    php8:
        # DOCKER HUB: https://hub.docker.com/_/php/
        build: ./resources/docker/development/php-8.3.2/apache-php
        container_name: lamp-php8
        depends_on:
            mysql:
                condition: service_healthy
        env_file:
            - 'docker.env'
        networks:
            - backend
            - frontend
        ports:
            - 8088:80
        volumes:
            - ./:/var/www/html
            - /var/www/html/vendor
```
