FROM php:8.2-fpm

#move
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

#update packages
RUN apt-get update --allow-releaseinfo-change

# development packages
RUN apt-get install -y \
    git \
    zip \
    sudo \
    nano \
    unzip \
    libzip-dev  \
    libicu-dev \
    libbz2-dev \
    libpng-dev \
    libjpeg-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libreadline-dev \
    libfreetype6-dev \
    libgd-dev \
    jpegoptim optipng pngquant gifsicle \
    libonig-dev \
    libxml2-dev \
    g++

# install xdebug
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug

RUN apt-get install -y libmagickwand-dev --no-install-recommends && pecl install imagick && docker-php-ext-enable imagick

#extensions
RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg
RUN docker-php-ext-install gd
RUN docker-php-ext-install zip

#Composer
RUN apt-get install -y curl
RUN curl -sS https://getcomposer.org/installer -o composer-setup.php
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer

# Node.js
RUN curl -sL https://deb.nodesource.com/setup_18.x -o node_setup.sh
RUN bash node_setup.sh
RUN apt-get install -y nodejs
RUN npm install npm -g n
