FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
        git \
        curl \
        wget \
        zip \
		unzip \
		mc
	
RUN apt-get install -y \		
		libpq-dev \
		&& docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
		&& docker-php-ext-install pdo pdo_pgsql
		
RUN apt-get install -y \
		libicu-dev \
		&& docker-php-ext-configure intl \
		&& docker-php-ext-install intl		

RUN apt-get install -y \
		libfreetype6-dev libjpeg62-turbo-dev libpng-dev \
		&& docker-php-ext-configure gd --with-freetype=/usr/include/ --with-jpeg=/usr/include/ \
		&& docker-php-ext-install gd

#RUN apt-get install -y \
#	libldap2-dev \
#	&& rm -rf /var/lib/apt/lists/* \
#	&& docker-php-ext-configure ldap --with-libdir=lib/x86_64-linux-gnu/ \
#	&& docker-php-ext-install ldap

RUN pecl install --force redis && docker-php-ext-enable redis

RUN docker-php-ext-install sockets pcntl

#RUN docker-php-ext-install zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

EXPOSE 9000
CMD ["php-fpm"]