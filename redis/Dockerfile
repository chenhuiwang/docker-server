FROM redis:5.0-alpine
# 复制配置文件到容器内，会自动创建路径
COPY redis.conf /usr/local/etc/redis/redis.conf
# 指定工作目录
WORKDIR /data
# 挂载为匿名卷
VOLUME ["/data"]
# 声明端口
EXPOSE 6379
# 容器启动命令
CMD ["redis-server", "/usr/local/etc/redis/redis.conf"]
