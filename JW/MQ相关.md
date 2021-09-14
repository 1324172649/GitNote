RMQ 分支： lkm_rmq_0623

//虚拟机重启之后，执行一些服务的重启，其中一般包含activemq
cd /root
sh start.sh 

//单独重启activemq
cd /var/soft/apache-activemq-5.13.5/
sudo ./bin/activemq start

//activemq单独启动一个队列，并在后台运行
php activemq_group.php 2> /dev/null &

//rabbitmq单独启动一个队列，并在后台运行
php queues/group/group_dynamicmems.php 2> /tmp/rmq_group_dynamicmems.log &

activemq管理后台:
http://192.168.1.63:8161/admin/

rabbitmq管理后台:
http://192.168.2.14:15672/#/channels