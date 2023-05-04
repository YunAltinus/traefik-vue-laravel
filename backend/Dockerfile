FROM php:8.2-fpm

WORKDIR /var/www/html

RUN apt-get update -y
RUN apt-get install -y unzip libpq-dev libcurl4-gnutls-dev
RUN docker-php-ext-install pdo pdo_mysql bcmath

COPY --from=composer:2.3.5 /usr/bin/composer /usr/bin/composer

COPY composer.* ./

RUN composer -n install --no-scripts --ignore-platform-reqs --no-dev

# COPY ./ ./

EXPOSE 8000

CMD ["/usr/local/bin/php", "artisan", "serve", "--host=0.0.0.0"]