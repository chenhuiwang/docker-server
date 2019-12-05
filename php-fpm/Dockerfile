FROM php:7.3-fpm-alpine

COPY www.conf /usr/local/etc/php-fpm.d/www.conf
COPY php.ini /usr/local/etc/php/

RUN echo "https://mirrors.aliyun.com/alpine/v3.9/main/" > /etc/apk/repositories \
    && apk update \
    && apk upgrade  \
    && docker-php-ext-install bcmath pdo_mysql opcache \
    && pecl install redis \
    && docker-php-ext-enable redis \
    && mkdir -p /usr/share/nginx \
    && chown -R www-data:www-data /usr/share/nginx

WORKDIR /usr/share/nginx

VOLUME ["/usr/local/var/log", "/usr/share/nginx"]

EXPOSE 9000

CMD ["php-fpm"]
