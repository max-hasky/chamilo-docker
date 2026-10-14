FROM php:8.4-fpm-alpine

# 1. Устанавливаем только системные пакеты разработки
RUN apk add --no-cache \
    curl \
    unzip \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    icu-dev \
    libzip-dev \
    openldap-dev \
    libxml2-dev \
    musl-locales \
    musl-locales-lang \
    icu-data-full

# 2. Компилируем расширения PHP, включая exif и скачивая apcu через встроенный pecl
RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) \
    gd \
    intl \
    pdo_mysql \
    zip \
    ldap \
    bcmath \
    soap \
    opcache \
    exif

# Ставим APCu проверенным для docker-php способом
RUN apk add --no-cache --virtual .build-deps $PHPIZE_DEPS \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && apk del .build-deps

# 3. Копируем кастомный php.ini
COPY ./php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www/chamilo

