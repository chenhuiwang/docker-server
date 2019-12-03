FROM php:7.3-fpm-alpine

COPY www.conf /usr/local/etc/php-fpm.d/www.conf
COPY php.ini /usr/local/etc/php/

RUN mkdir -p /usr/share/nginx \
    && docker-php-ext-install bcmath pdo_mysql opcache \
    && pecl install redis \
    && docker-php-ext-enable redis

WORKDIR /usr/share/nginx

VOLUME ["/usr/local/var/log", "/usr/share/nginx"]

EXPOSE 9000

CMD ["php-fpm"]
