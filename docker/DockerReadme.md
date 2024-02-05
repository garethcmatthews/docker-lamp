# LAMP Docker Application

A LAMP based Docker application for use in development.

### Containers
* **lampserver-apache**: Apache, PHP, curl, nano, composer
* **lampserver-mysql**: MySQL 8
* **lamp-phpmyadmin**: phpMyadmin

### PHP Versions
* PHP 7.4.33
* PHP 8.0.30
* PHP 8.1.27
* PHP 8.2.15
* PHP 8.3.2

### Change PHP version
To change the PHP version update the php build folder in the docker compose file
```
php:
    # DOCKER HUB: https://hub.docker.com/_/php/
    build: ./resources/docker/development/php/php-8.1.30
```

### URL's
* **PHP Application** - http://localhost:8080
* **PhpMyadmin** - http://localhost:8888

#### Access PHP box...
> docker exec -it lampserver-php /bin/bash 
#### Access MySQL box...
> docker exec -it lampserver-mysql /bin/bash  
#### Access PHPMyAdmin box...
>docker exec -it lampserver-phpmyadmin /bin/bash  

#### Run Docker
> docker compose --file docker-compose.dev.yml up -d

#### To Rebuild Dev Box (After config changes)
> docker compose --file docker-compose.dev.yml up -d --build  
