FROM alpine:3.8

LABEL maintainer="Janosch Kocsis <jk@coloso.de>"

RUN apk add --update \
    php7-fpm \
    php7-apcu \
    php7-bcmath \
    php7-ctype \
    php7-curl \
    php7-dom \
    php7-gd \
    php7-iconv \
    php7-imagick \
    php7-json \
    php7-intl \
    php7-mcrypt \
    php7-fileinfo \
    php7-mbstring \
    php7-opcache \
    php7-openssl \
    php7-soap \
    php7-pdo \
    php7-pdo_mysql \
    php7-mysqli \
    php7-xml \
    php7-xsl \
    php7-xmlwriter \
    php7-zlib \
    php7-phar \
    php7-tokenizer \
    php7-session \
    php7-simplexml \
    php7-xdebug \
    php7-zip \
    curl \
    make

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/* && \
    curl --insecure https://getcomposer.org/composer.phar -o /usr/bin/composer && chmod +x /usr/bin/composer

ADD php-fpm.conf /etc/php7/php-fpm.d/
ADD php.ini /etc/php7/

RUN adduser -D -g 'www' www \
    && mkdir /var/www \
    && chown -R www:www /var/www

CMD ["php-fpm7", "-F"]

WORKDIR /var/www/magento
EXPOSE 9001