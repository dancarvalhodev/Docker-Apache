FROM php:8.0-apache

# Disable apt interactive
ARG DEBIAN_FRONTEND=noninteractive

# Update
RUN apt update && apt -y dist-upgrade

# Essentials
RUN apt install -y build-essential wget curl git nano zip

# Libs
RUN apt install -y libzip4 libzip-dev libicu-dev

# MySQL
RUN docker-php-ext-install mysqli pdo pdo_mysql zip intl
RUN docker-php-ext-enable pdo_mysql zip intl

# Xdebug and Redis
RUN pecl install xdebug redis
RUN docker-php-ext-enable xdebug redis

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Cleanup
RUN apt autoremove -v && apt clean && rm -rf /usr/src/*  