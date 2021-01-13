FROM php:7.3-fpm-alpine

RUN echo 'http://dl-4.alpinelinux.org/alpine/edge/community/' >> /etc/apk/repositories

RUN apk update \
    && apk add \
        --no-cache $PHPIZE_DEPS \
        icu \
        icu-dev \
        libintl \
        libjpeg-turbo-dev \
        libpng-dev \
        libwebp-dev \
        libzip-dev \
        php7-intl \
        unzip \
        zip \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

RUN docker-php-ext-configure zip --with-libzip
RUN docker-php-ext-configure gd --with-webp-dir=/usr/include/  --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install \
    bcmath \
    ctype \
    gd \
    intl \
    json \
    opcache \
    pcntl \
    pdo_mysql \
    zip

RUN curl --silent --show-error https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer

COPY ./conf/php-fpm.conf /usr/local/etc/php-fpm.conf
COPY ./conf/www.conf /usr/local/etc/php-fpm.d/www.conf

EXPOSE 9000

CMD ["php-fpm"]
