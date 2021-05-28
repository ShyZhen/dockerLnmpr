# DockerLnmpr
php8+redis+mysql8+nginx 环境脚手架

### 修改配置
 - 最新docker-compose快捷创建php环境

 - 自己修改nginx/conf中的vhost配置

 - 需要调用php脚本的，比如laravel的php artisan，进入php的容器执行，同nginx一样，当前已经挂载了www目录

### 常用命令
```
docker-compose up -d
docker-compose down
docker images
docker ps
docker exec -it xxx /bin/sh
```
