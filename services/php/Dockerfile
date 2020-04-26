FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        && docker-php-ext-configure gd --with-freetype --with-jpeg \
        && docker-php-ext-install -j$(nproc) gd \
RUN pecl install redis && docker-php-ext-enable redis \
	&& pecl install xdebug && docker-php-ext-enable xdebug

RUN echo "" >> /usr/local/etc/php/php.ini
RUN usermod -u 1000 www-data