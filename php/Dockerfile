FROM php:7.2-fpm

# Install libraries
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libzip-dev \
    zip \
    libjpeg-dev\
    libpng-dev\
    libfreetype6-dev \
    libpq-dev \
    libicu-dev g++

# Configure PHP extensions
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-configure zip --with-libzip

# Install PHP extensions
RUN docker-php-ext-install pdo pdo_mysql zip gd intl

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Setup php
COPY php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www

CMD ["php-fpm"]