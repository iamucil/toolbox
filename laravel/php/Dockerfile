FROM php:8.0-fpm-alpine

RUN apk add --update --no-cache \
    oniguruma-dev zlib-dev libpng-dev libxml2-dev \
    && docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

WORKDIR /usr/share/nginx/html