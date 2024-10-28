FROM php:8.3-fpm

RUN apt-get update && apt-get install -y \
        git \
        curl \
        wget \
        zip \
	mc \
	nodejs \
	npm

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

EXPOSE 9000
CMD ["php-fpm"]