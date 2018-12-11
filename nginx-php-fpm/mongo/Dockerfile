FROM lenderhub/nginx-php-fpm:latest

RUN apk --update --upgrade --no-cache add \
    autoconf \
    openssl-dev \
    g++ \
    make \
    && pecl channel-update pecl.php.net \
    && pecl install mongodb \
    && apk del --purge autoconf openssl-dev g++ make
