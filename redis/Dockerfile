FROM redis:5.0-alpine

COPY redis.conf /usr/local/etc/redis/redis.conf

WORKDIR /data

VOLUME ["/data"]

EXPOSE 6379

CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]
