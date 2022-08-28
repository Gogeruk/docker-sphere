FROM php:7.4-fpm

# PHP extensions
RUN apt update \
    && apt install -y \
        zlib1g-dev \
        libicu-dev \
        libffi-dev \
        librabbitmq-dev \
        libssh-dev \
        libgmp-dev \
        libssl-dev \
        libzip-dev \
        curl \
        g++ \
        git \
        gnupg\
        wget \
        zip \
        vim \
        cmake \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip \
    && docker-php-ext-install intl \
    && docker-php-ext-install opcache \
    && docker-php-ext-install pdo \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install sockets \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && pecl install amqp \
    && docker-php-ext-enable amqp \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug


# Set the working directory
WORKDIR /var/www/glows


# install yarn
RUN apt-get install -y apt-transport-https ca-certificates
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get install -y yarn


# install nodejs
RUN curl -sL https://deb.nodesource.com/setup_12.x | bash
RUN apt-get install -y nodejs


# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer