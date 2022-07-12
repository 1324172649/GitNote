//虚拟机重启之后，执行一些服务的重启，其中一般包含activemq
cd /root
sh start.sh 

start.sh 内容如下：
#!/bin/bash
service nginx restart;
service php5.6-fpm restart;
service mysql stop;
service redis-server stop;
/etc/init.d/postgresql stop;
/root/apache-activemq-5.15.8/bin/activemq start;
#sleep 30;
#cd /var/www/joywok/library/stomp-activemq/;./startmq.sh;