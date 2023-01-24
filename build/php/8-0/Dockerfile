FROM php:8.0.27-fpm-alpine

######## Composer.phar ########
RUN curl -s https://getcomposer.org/installer | php \
  # move composer into a bin directory you control:
  && mv composer.phar /usr/local/bin/composer \
  # double check composer works
  && composer about

RUN php -m && echo "============================================="

RUN apk add --no-cache --update \
  icu-dev

RUN docker-php-ext-install \
  mysqli \
  opcache \
  intl \
  sockets

RUN rm -rf /tmp/* /var/cache/apk/* \
  && echo "=============================================" \
  && php -m