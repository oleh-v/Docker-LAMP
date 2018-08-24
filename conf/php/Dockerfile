FROM php:7.2.8-apache-stretch

##### LIBS, MONGO, GD
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        zlib1g-dev \
        libssl-dev \
    && pecl install mongodb \
    && echo "extension=mongodb.so" > /usr/local/etc/php/conf.d/ext-mongodb.ini \
    && echo "upload_max_filesize = 5M" > /usr/local/etc/php/conf.d/upload.ini \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

RUN docker-php-ext-enable gd

##### MCRYPT
RUN pecl install mcrypt-1.0.1
RUN docker-php-ext-enable mcrypt

##### MYSQLI
RUN docker-php-ext-install mysqli
RUN docker-php-ext-enable mysqli

##### OPCAHCE
RUN docker-php-ext-install opcache
RUN docker-php-ext-enable opcache

##### MEMCACHED
RUN apt-get install -y libz-dev libmemcached-dev
RUN pecl install memcached-3.0.4
RUN echo extension=memcached.so >> /usr/local/etc/php/conf.d/memcached.ini

##### IMAGICK
RUN apt-get install -y libmagickwand-dev --no-install-recommends
RUN pecl install imagick && docker-php-ext-enable imagick