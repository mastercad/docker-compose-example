FROM php:7-fpm
MAINTAINER andreas kempe <andreas.kempe@byte-artist.de>

#RUN apt-get update && apt-get install php-mysql php-xdebug php-mail 
RUN echo 'deb http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list \
  && echo 'deb-src http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list \ 
  && apt-get update \
  && apt-get install -y --no-install-recommends wget \
  && cd /tmp \
  && wget https://www.dotdeb.org/dotdeb.gpg \
  && apt-key add dotdeb.gpg \
  && rm dotdeb.gpg \
  && apt-get update \
  && apt-get install -y --no-install-recommends php7.0-mysql php7.0-xml libpq-dev \
  && docker-php-ext-install mysqli pdo_pgsql pdo_mysql \
  && apt-get remove -y --purge wget
