FROM nginx:latest
LABEL maintainer="enumus@gmail.com"

ARG NGINX_HOST

COPY symfony.conf.tpl /etc/nginx/conf.d/symfony.conf.tpl

RUN sed 's/localhost/'"${NGINX_HOST:-localhost}"'/' /etc/nginx/conf.d/symfony.conf.tpl > /etc/nginx/conf.d/symfony.conf
RUN rm -rf /etc/nginx/conf.d/symfony.conf.tpl
