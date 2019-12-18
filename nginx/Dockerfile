FROM nginx:alpine

COPY nginx.conf /etc/nginx/

WORKDIR /var/www

VOLUME ["/var/www", "/var/log/nginx", "/etc/nginx/conf.d"]

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
