# DOCKER HUB: https://hub.docker.com/_/php/
FROM php:7.4.11-apache

# System
RUN apt-get update && \
    apt-get install --no-install-recommends --yes curl && \
    apt-get install --no-install-recommends --yes nano

# Apache
COPY ./apache-default-vhost.conf /etc/apache2/sites-available/000-default.conf
RUN a2enmod rewrite

# PHP: https://github.com/mlocati/docker-php-extension-installer
RUN apt-get install --no-install-recommends --yes libzip-dev && \
    apt-get install --no-install-recommends --yes unzip && \
    docker-php-ext-install opcache && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install zip

RUN cp /usr/local/etc/php/php.ini-development /usr/local/etc/php/php.ini && \
    sed -i "s|^;date.timezone =.*$|date.timezone = Europe/London|" /usr/local/etc/php/php.ini && \
    sed -i "s|display_startup_errors =.*$|display_startup_errors = On|" /usr/local/etc/php/php.ini && \
    sed -i "s|display_errors =.*$|display_errors = On|" /usr/local/etc/php/php.ini && \
    sed -i "s|^;error_log =.*$|error_log = /var/log/php/php-error.log|" /usr/local/etc/php/php.ini

# Composer
RUN cd ~ && \
    curl -sS https://getcomposer.org/installer -o composer-setup.php && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer

# NodeJS
#RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && \
#    apt-get install --no-install-recommends --yes nodejs

# Docker
EXPOSE 80
WORKDIR /var/www
