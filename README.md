# docker-server
使用 docker 构建 web 环境，练习...

## 目录
```
nginx
    - Dockerfile
    - nginx.conf
    - conf.d
        - default.conf
    - logs
php-fpm
    - Dockerfile
    - php.ini
    - www.conf
```

## 单个构建
在项目目录下，也就是 docker-server

### 构建 php-fpm
```
docker build -t php-fpm:v1 php-fpm

docker run -d -p 9000:9000 \
-v "$PWD"/www:/usr/share/nginx \
-v "$PWD"/php-fpm/logs:/usr/local/var/log \
--name php-fpm \
php-fpm:v1
```

### 构建 nginx
```
docker build -t nginx:v1 nginx

docker run -d -p 8001:80 \
--link php-fpm \
-v "$PWD"/www:/usr/share/nginx \
-v "$PWD"/nginx/conf.d:/etc/nginx/conf.d  \
-v "$PWD"/nginx/logs:/var/log/nginx \
--name nginx \
nginx:v1
```
