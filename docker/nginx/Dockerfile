FROM alpine:3.8

LABEL maintainer="Janosch Kocsis <jk@coloso.de>"

RUN apk add --update nginx
RUN rm -rf /var/cache/apk/* && rm -rf /tmp/*

ADD nginx.conf /etc/nginx/
ADD default.conf /etc/nginx/conf.d/
RUN echo "upstream php-upstream { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

RUN adduser -D -g 'www' www \
    && chown -R www:www /var/www

EXPOSE 80