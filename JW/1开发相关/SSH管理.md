//ssh每隔一段时间断连
终端在链接上服务器的时候过一段时间之后就无法再次操作了，输入内容的时候过一点时间会提示已经断开ssh连接了,解决方法是让本地隔一段时间就像服务器发一次请求
在本地打开配置文件：
sudo vim /etc/ssh/ssh_config
在文件中添加下面的参数：
ServerAliveInterval 60 #每隔60秒就向服务器发送一个请求
ServerAliveCountMax 3  #允许超时的次数，一般都会响应

//ssh连接
ssh 远程链接，用户名：root      密码： Dogesoft!@#
ssh root@192.168.1.63 -p22

//远程连接快捷免密登陆
cd /Users/luna/.ssh
vim config
ssh-copy-id -i ~/.ssh/id_rsa.pub -p 22 root@192.168.1.30

//staging环境
在证书当前目录下执行
cd /Users/luna/Downloads
ssh -i StagingBastion.pem ubuntu@ec2-52-83-143-151.cn-northwest-1.compute.amazonaws.com.cn
进入之后的目录是/home/ubuntu
查看当前目录下
./mysql.sh   //主库
./mysqlread.sh     //读库
control+R 搜索执行过的命令
输入ssh 自动搜索到 ssh -i pems/staging.pem ubuntu@172.0.1.231  为staging环境代码
可以临时在这上边修改文件，但是要尽快复原
本地最终修改之后提交到分支上，在staging环境git pull拉一下代码

星巴克uat是54和59两台轮流请求,59上有mq
迪士尼uat是51,mq是71改为72
丝芙兰uat是49 mq是48
dogesoftuat是56
staging是231,mq是56

看config.ini里的配置：可查看MQ地址
ActiveMQ="tcp://172.0.1.56:61613" 

./redis1.sh  //redis库
hgetall user:b965192f2cbcb71d875a4a2ef9e30d29

查看队列积压情况：
ubuntu@ip-172-0-1-59:/var/www$ sudo -i rabbitmqctl list_queues | grep duty



