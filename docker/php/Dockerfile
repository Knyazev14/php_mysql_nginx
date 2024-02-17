FROM php:8.2-fpm

RUN apt-get update \
    && apt-get install -y procps \
    && docker-php-ext-install mysqli \
    && groupadd -g 1001 mygroup \
    && useradd -u 1001 -g mygroup -m myuser \
    && usermod -aG sudo myuser \
    && echo 'myuser:password' | chpasswd \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

USER myuser
