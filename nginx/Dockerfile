FROM alpine:3.10

LABEL maintainer="Duan Le <duanvnc@gmail.com>"

RUN apk add --update --no-cache nginx

COPY nginx.conf /etc/nginx/
COPY wsq-czytest.savour.local.conf /etc/nginx/conf.d/
COPY user.czytest.savour.local.conf  /etc/nginx/conf.d/
COPY colourhome-czytest.savour.local.conf  /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:9001; }" > /etc/nginx/conf.d/upstream.conf

RUN adduser -D -g '' -G www-data www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443
