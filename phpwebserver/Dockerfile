FROM php:7.1-apache

MAINTAINER Gigatrappeur <gigatrappeur@gmail.com>

RUN apt-get update && apt-get install -y libjpeg62-turbo-dev libpng12-dev \
	&& docker-php-ext-configure gd --with-jpeg-dir=/usr/include/ \
	&& docker-php-ext-install mysqli gd


RUN a2enmod rewrite
RUN service apache2 restart

WORKDIR /var/www/html
VOLUME ["/var/www/html"]
CMD ["apache2-foreground"]