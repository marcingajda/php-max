FROM php:7.4-fpm

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install libcurl3-dev libmcrypt-dev libxml2-dev libicu-dev libbz2-dev -y
RUN apt-get install libfreetype6-dev libpng-dev libwebp-dev libjpeg62-turbo-dev libzip-dev -y

RUN docker-php-ext-configure gd \
        --with-freetype=/usr/include/freetype \
        --with-jpeg=/usr/include/ \
        --with-webp=/usr/include/

RUN docker-php-ext-install curl json gd pdo_mysql mysqli xmlrpc opcache intl bz2 xml zip exif

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
