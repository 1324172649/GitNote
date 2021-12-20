root@joywok:/var/www# vim joywok/library/stomp-activemq/startmq.sh
mkdir -p /var/www/joywok/logs/activemq/
chmod  777  /var/www/joywok/logs/activemq/

RMQ 分支： lkm_rmq_0623

//虚拟机重启之后，执行一些服务的重启，其中一般包含activemq
cd /root
sh start.sh 

//单独重启activemq
cd /var/soft/apache-activemq-5.13.5/
sudo ./bin/activemq start

#cd /var/soft/apache-activemq-5.13.5/
#sudo ./bin/activemq start

//activemq单独启动一个队列，并在后台运行
php activemq_group.php 2> /dev/null &

//activemq单独关闭一个队列
ps -ef | grep activemq_group.php | awk '{ print $2 }' | sudo xargs kill -9


//rabbitmq单独启动一个队列，并在后台运行
php queues/group/group_dynamicmems.php 2> /tmp/rmq_group_dynamicmems.log &

//rabbitmq单独关闭一个队列
ps -ef | grep queues/group/group_dynamicmems.php | awk '{ print $2 }' | sudo xargs kill -9

activemq管理后台:
http://192.168.1.63:8161/admin/

rabbitmq管理后台:
http://192.168.2.14:15672/#/channels


//群组动态成员相关队列
activemq_push.php
activemq_as.php
activemq_usergroup.php
activemq_user_status.php
activemq_user.php
activemq_group.php