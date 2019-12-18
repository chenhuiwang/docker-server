FROM php:7.3-fpm-alpine

COPY www.conf /usr/local/etc/php-fpm.d/www.conf
COPY php.ini /usr/local/etc/php/

RUN echo "https://mirrors.aliyun.com/alpine/v3.9/main/" > /etc/apk/repositories \
    && apk update \
    && apk upgrade  \
    && apk add $PHPIZE_DEPS \
    && docker-php-ext-install bcmath pdo_mysql opcache \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && mkdir -p /var/www \
    && chown -R www-data:www-data /var/www

WORKDIR /var/www

VOLUME ["/usr/local/var/log", "/var/www"]

EXPOSE 9000

CMD ["php-fpm"]
