# Base image on
ARG PHP_VERSION=$PHP_VERSION
FROM php:${PHP_VERSION}-fpm-alpine
ARG USER_ID=$USER_ID

#install
RUN apk upgrade --update --no-cache \
    && apk add \
        curl \
        nginx \
        freetype-dev \
        icu-dev \
        jpeg-dev \
        libzip-dev \
        libxslt-dev \
        libpng-dev \
        libxml2-dev \
        shadow \
        gettext \
        php-mysqli \
        libgcrypt-dev \
        libjpeg-turbo-dev \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-configure pdo_mysql --with-pdo-mysql=mysqlnd \
    && docker-php-ext-configure mysqli --with-mysqli=mysqlnd \
    && docker-php-ext-install \
        xsl \
        intl \
        mysqli \
        pdo \
        pdo_mysql \
        bcmath \
        soap \
        zip \
        gd

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

RUN usermod -u $USER_ID www-data && \
    groupmod -g $USER_ID www-data

CMD ["php-fpm", "-F"]