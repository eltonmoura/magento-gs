FROM php:7.2-fpm-alpine
MAINTAINER elton.ms@gmail.com

# RUN apt-get update && apt-get install -y libpng-dev libxml2-dev libcurl3-dev vim
RUN apk update && apk add --update --no-cache autoconf vim

# PHP extensions
RUN docker-php-ext-install ctype curl dom gd intl mbstring hash openssl pdo pdo_mysql xml simplexml soap zip iconv
