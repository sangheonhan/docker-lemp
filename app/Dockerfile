FROM php:7.3-fpm-alpine AS php-fpm

COPY ./public/index.php /app/public/

CMD ["/usr/local/sbin/php-fpm", "--nodaemonize"]


FROM nginx:1.17-alpine AS nginx

COPY --from=php-fpm /app/ /app/
COPY default.conf /etc/nginx/conf.d/

CMD ["nginx", "-g", "daemon off;"]
