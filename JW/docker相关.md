//查看activemq_group相关进程
ps -ef | grep activemq_group

//查看dcker进程
docker ps

//进入docker
docker exec -it e8da09a94531 /bin/bash

cd /var/www/joywok/library/stomp-activemq

php activemq_group.php