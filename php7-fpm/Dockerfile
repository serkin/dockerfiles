FROM php:fpm

MAINTAINER serkin.alexander@gmail.com

RUN apt-get update && apt-get install -y git libssl-dev

RUN   docker-php-ext-install zip \
	 && docker-php-ext-install mbstring

ENV COMPOSER_VERSION 1.0.0-alpha10

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=${COMPOSER_VERSION}
