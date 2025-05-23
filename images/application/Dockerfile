FROM php:8.2-fpm

RUN apt-get update && apt-get install -y \
    libicu-dev \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \
    libonig-dev \
    unzip \
    curl \
    gnupg \
    ca-certificates \
    && docker-php-ext-install pdo pdo_mysql intl gd bcmath opcache

RUN pecl install mongodb && docker-php-ext-enable mongodb
RUN pecl install xdebug && docker-php-ext-enable xdebug

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash && \
    apt-get install -y symfony-cli

ENV XDEBUGINI_PATH=/usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html

CMD ["php-fpm"]