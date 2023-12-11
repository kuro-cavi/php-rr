FROM php:8.3

RUN apt-get update && \
  apt-get install -y libzip-dev libxslt-dev libicu-dev libonig-dev && \
  docker-php-ext-install opcache zip xsl dom exif intl pcntl bcmath sockets

COPY --from=composer:2.6 /usr/bin/composer /usr/bin/composer
COPY --from=ghcr.io/roadrunner-server/roadrunner:2023.3 /usr/bin/rr /usr/local/bin/rr

WORKDIR /var/www/webserver
