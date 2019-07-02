FROM richarvey/nginx-php-fpm:1.7.3

RUN apk add --upgrade --update --no-cache \
    autoconf \
    g++ \
    imagemagick-dev \
    libtool \
    make \
    pcre-dev \
    gettext-dev \
    freetype freetype-dev \
    libpng libpng-dev \
    libjpeg-turbo libjpeg-turbo-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-png-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) gd \
    && docker-php-ext-install gettext bcmath \
    && pecl channel-update pecl.php.net \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && apk del --no-cache autoconf g++ libtool make pcre-dev freetype-dev libpng-dev libjpeg-turbo-dev \
    && docker-php-ext-install sockets \
    && docker-php-ext-install pcntl
    
# ----------------------------------------------------------------------------------------------------------------------
# fluentd + logz.io
# ----------------------------------------------------------------------------------------------------------------------    

RUN apk add --upgrade --update --no-cache vim busybox-extras

RUN apk add --upgrade --update --no-cache ruby ruby-bundler ruby-dev ruby-irb ruby-rdoc ruby-webrick gcc build-base \
    && gem install fluentd \
    && gem install fluent-plugin-logzio \
    && fluentd --setup /etc/fluentd \
    && mkdir /etc/fluentd/conf.d \
    && echo include conf.d/*.conf >> /etc/fluentd/fluent.conf

# ----------------------------------------------------------------------------------------------------------------------