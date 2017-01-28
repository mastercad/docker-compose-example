FROM php7_normal
MAINTAINER andreas kempe <andreas.kempe@byte-artist.de>

RUN pecl install xdebug \
  && docker-php-ext-enable xdebug

COPY ./xdebug.ini /usr/local/etc/php/conf.d/ 

RUN curl https://getcomposer.org/download/1.2.0/composer.phar > /tmp/composer.phar \
    && chmod +x /tmp/composer.phar \
    && mv /tmp/composer.phar /usr/local/bin/composer

CMD ["php-fpm"]

EXPOSE 9000