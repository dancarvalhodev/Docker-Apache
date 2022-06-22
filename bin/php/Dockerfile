FROM php:8-fpm-bullseye

# Basic
RUN DEBIAN_FRONTEND=noninteractive
WORKDIR /usr/local/apache2/htdocs

# Update
RUN apt update && apt dist-upgrade -y

# Essentials
RUN apt update && apt install -y build-essential zip git nano vim

# Libs
RUN apt update && apt install -y libzip4 libzip-dev libicu-dev

# MySQL
RUN docker-php-ext-install mysqli pdo pdo_mysql zip intl
RUN docker-php-ext-enable pdo_mysql mysqli zip intl

# XDEBUG and Redis
RUN pecl install xdebug redis
RUN docker-php-ext-enable xdebug redis

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
