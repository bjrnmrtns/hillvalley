FROM alpine:3.16

RUN apk add --no-cache nginx
RUN adduser -D -g 'www' www && \
    mkdir /www && \
    chown -R www:www /var/lib/nginx && \
    chown -R www:www /www

COPY fs/etc/nginx/nginx.conf /etc/nginx/nginx.conf
COPY fs/www/index.html /www/index.html

CMD ["nginx", "-g", "daemon off;"]
