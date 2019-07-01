FROM lenderhomepage/php:fpm-nginx-latest

RUN apk --update --upgrade --no-cache add \
    autoconf \
    g++ \
    make \
    && pecl channel-update pecl.php.net \
    && pecl install mongodb \
    && apk del --purge autoconf g++ make
