FROM node:20.11.1-alpine3.18

WORKDIR /var/www/test_task

RUN set -xe; apk add --no-cache --virtual .temp shadow; \
    groupmod -o -g 1000 www-data; usermod -o -u 1000 -g www-data www-data; \
    chown -R www-data:www-data /var/www/test_task; apk del .temp; \
    rm -rf /tmp/* /var/tmp/* /var/cache/apk/* /usr/share/doc/* /usr/share/man/*;

USER www-data
