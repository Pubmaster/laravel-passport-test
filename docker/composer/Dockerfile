FROM php:7.2.8-alpine

RUN apk update && apk add \
    openssh \
    bash \
    postgresql-dev \
    zlib-dev

RUN docker-php-ext-install \
    zip \
    pdo \
    pdo_pgsql \
    mbstring

RUN curl -sS https://getcomposer.org/installer | php \
  && mv composer.phar /usr/local/bin/composer \
  && composer config -g github-oauth.github.com f13f56a541a3287caefa996bae1cf589b27e1f21

ENV COMPOSER_ALLOW_SUPERUSER 1

WORKDIR /var/www
