FROM php:8.3.3-fpm-alpine3.18

WORKDIR /var/www/test_task

RUN set -xe; apk add --no-cache --virtual .temp $PHPIZE_DEPS linux-headers shadow libpq-dev; \
    apk add --no-cache libpq; \
    docker-php-ext-install -j$(nproc) pdo_pgsql opcache; \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer; \
    groupmod -o -g 1000 www-data; usermod -o -u 1000 -g www-data www-data; \
    chown -R www-data:www-data /var/www/test_task; docker-php-source delete; apk del .temp; \
    rm -rf /tmp/* /var/tmp/* /var/cache/apk/* /usr/share/doc/* /usr/share/man/* /var/www/html;

USER www-data
