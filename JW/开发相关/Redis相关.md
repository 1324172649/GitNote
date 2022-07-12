连接29
ssh root@192.168.2.29 -p22
redis-cli
127.0.0.1:6379> info //查看redis版本等信息
127.0.0.1:6379> smembers uid.sids:0ec597c200db8030b955343b41bbef6f（uid=>userinfo表）

hgetall user:b965192f2cbcb71d875a4a2ef9e30d29

查看linux上面是否有安装redis,以及redis的启动和关闭
1、检测是否有安装redis-cli和redis-server;
[root@localhost bin]# whereis redis-cli
redis-cli: /usr/bin/redis-cli

[root@localhost bin]# whereis redis-server
redis-server: /usr/bin/redis-server
显示如此，说明已经安装好了

2、启动redis:
加上`&`号使redis以后台程序方式运行
redis-server &

3、检测后台进程是否存在
ps -ef |grep redis

4、检测6379端口是否在监听
netstat -lntp | grep 6379

5、使用redis-cli客户端检测连接是否正常 / 如果更改了端口，使用redis-cli客户端连接时，也需要指定端口
redis-cli / redis-cli -p 6380
127.0.0.1:6379> keys *
(empty list or set)
127.0.0.1:6379> set key "hello world"
OK
127.0.0.1:6379> get key
"hello world"

6、停止redis:
redis-cli shutdown
因为Redis可以妥善处理SIGTERM信号，所以直接kill -9也是可以的
kill -9 PID

====================================
## redis geo
//获取指定定位的经纬度
geopos dept_geo FQA5x8p86kwtPqW3 [member ...] 
//获取距离某个经纬度指定范围内排序后的列表
georadius dept_geo 100 10 99999999999999 km withcoord withdist asc count 5 [WITHCOORD] [WITHDIST] [WITHHASH] [COUNT count] [ASC|DESC] [STORE key] [STOREDIST key]



set workplace.group.relation:997702067611283 Qnk7joykOvG514L1 //设置
get workplace.group.relation:997702067611283 //获取
del workplace.group.relation:997702067611283 //删除

SMEMBERS workplace.as:HNdgTCfya6fyE7ok //获取
srem workplace.as:HNdgTCfya6fyE7ok 365152309033748_369928595222786 //删某一个
sAdd workplace.as:HNdgTCfya6fyE7ok 365152309033748_369928595222786 //添加一个
del workplace.as:HNdgTCfya6fyE7ok //删除

keys workplace.user.relation:* //查看keys


set workplace.group.relation:997702067611283 "Navalink中Everyone群组ID"

set workplace.group.relation:365152309033748 "Navalink中R&D群组ID"

set workplace.user.relation:100074401674407 "Navalink中关联Marlin Doo的用户ID"