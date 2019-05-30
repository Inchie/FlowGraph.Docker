FROM php:7.2-apache

RUN apt-get update -qq && apt-get install -yqq \
    git && \
    a2enmod rewrite

RUN pecl install -o -f redis \
    &&  rm -rf /tmp/pear \
    &&  docker-php-ext-enable redis \
    && docker-php-ext-configure bcmath \
    && docker-php-ext-install bcmath pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

ARG apacheconfig
ADD $apacheconfig /etc/apache2/sites-available/000-default.conf








