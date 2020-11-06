# php-fpm
FROM php:7.4-fpm

RUN mkdir /var/log/php

WORKDIR /var/www

# Copy files / Volumes
COPY . /var/www
COPY ./php.ini /usr/local/etc/php/conf.d/php.ini

# installing dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    libzip-dev


# clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# installing extensions
RUN docker-php-ext-install pdo_mysql zip

CMD ["php-fpm"]
EXPOSE 9000
