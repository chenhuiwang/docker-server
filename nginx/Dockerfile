FROM nginx:alpine

COPY nginx.conf /etc/nginx/

WORKDIR /usr/share/nginx

VOLUME ["/usr/share/nginx", "/var/log/nginx", "/etc/nginx/conf.d"]

EXPOSE 80 443

CMD ["nginx", "-g", "daemon off;"]
