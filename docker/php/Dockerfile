FROM php:8.4-fpm-alpine

RUN apk add --no-cache \
    postgresql-dev \
    libzip-dev \
    zip \
    unzip \
    php84-pecl-redis \
    && docker-php-ext-install pdo pdo_pgsql zip

RUN docker-php-ext-enable redis || true

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

WORKDIR /var/www/html

RUN chown -R www-data:www-data /var/www/html

USER www-data