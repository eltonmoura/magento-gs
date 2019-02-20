FROM php:7.2-apache
MAINTAINER elton.ms@gmail.com

RUN apt-get update && apt-get install -y apt-utils libxml2-dev libpng-dev libcurl3-dev vim unzip \
	mysql-client openssl libxslt-dev libjpeg-dev libfreetype6-dev

# PHP extensions
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd
RUN docker-php-ext-configure mysqli --with-mysqli=mysqlnd
RUN docker-php-ext-install ctype curl dom gd intl mbstring hash mysqli pdo pdo_mysql xml simplexml soap zip iconv bcmath xsl

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- \
        --install-dir=/usr/local/bin \
        --filename=composer

RUN chmod 777 -R /var/www/html/
