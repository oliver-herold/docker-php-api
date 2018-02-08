FROM trafex/alpine-nginx-php7

RUN apk --no-cache --update add \
    bash \
    php7-pdo \
    php7-pdo_mysql

RUN rm -rf /var/cache/apk/*
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

RUN rm /var/www/html/index.php
RUN rm /var/www/html/test.html

COPY composer.json /var/www/html
COPY composer.lock /var/www/html

COPY index.php /var/www/html

RUN cd /var/www/html
RUN composer install
