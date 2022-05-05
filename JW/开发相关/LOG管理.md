192.168.2.14 log位置
/var/log/nginx

/var/docker/php6/etc

/var/www/joywok/logs

//查看access.log文件中某个关键字的相关log记录
cat access.log | grep /api/...

//查看某个日志文件中，某个请求的上下五个请求并显示行号
cat access.log | grep -n '/api/app/web/config' -C 5