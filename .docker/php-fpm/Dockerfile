FROM php:7.0-fpm
LABEL maintainer="enumus@gmail.com"

RUN useradd -ms /bin/bash docker

RUN docker-php-ext-install pdo_mysql

RUN yes | pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" > /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_enable=on" >> /usr/local/etc/php/conf.d/xdebug.ini \
    && echo "xdebug.remote_autostart=off" >> /usr/local/etc/php/conf.d/xdebug.ini

RUN apt update && apt install -y nodejs npm

RUN npm cache clean -f \
    && npm install -g n \
    && n 9.2.0 \
    && npm install -g yarn

WORKDIR /app

#RUN yarn install

USER docker