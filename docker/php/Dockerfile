FROM php:8.0-fpm-buster

# 更换源
RUN sed -i "s/deb.debian.org/mirrors.aliyun.com/g" /etc/apt/sources.list 

RUN apt-get update && apt-get install -y \
    libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev libpng-dev \
    && apt-get install -y libmemcached-dev zlib1g-dev \

    && docker-php-ext-install -j$(nproc) iconv \

    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd \

    # PHP8必须装1.0.4  参考 https://bugs.php.net/bug.php?id=80459
    && pecl install mcrypt-1.0.4 \
    && docker-php-ext-enable mcrypt \

    && docker-php-ext-install mysqli \
    && docker-php-ext-install pdo pdo_mysql \

    && pecl install redis-5.3.2 \
    && docker-php-ext-enable redis \

    && docker-php-ext-install -j$(nproc) bcmath