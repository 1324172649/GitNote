@Git_分支管理  @朱晓娜(Hannah)  #提测申请# 

分支： liuxin_master_sla_duty_target_20220509
分支来源： master

相关链接：
https://dogesoft.joywok.com/as/info?id=AnJgRsTO9lu16bqH
项目出处： @Starbucks PAPP  

提测内容：
1、duty2.0班次目标SLA；

涉及脚本：
1、根据门店ID清理对应网络下自2022-05-08零点到目前的班次目标脏数据；
cd /var/www/joywok/Sql/cmd
php del_duty_target_dirty_data_and_cache_20220510.php starbucks 门店ID（需找柳鑫提供）

涉及配置：无

涉及接口清单：
1、GET /api2/users/userinfo	【用户主页】
2、GET /api2/users/favoriteobjs	【通讯录首页】
3、GET /api/myteams/teamusers	【组织架构】
4、GET /api2/users/getreport	【直线汇报人】
5、PUT /api/user/auth		【新增API - 用户认证设置（美妆秀B级认证）】

是否涉及Controller层改动：否

是否涉及model层改动：是
1、文件：joywok/library/models/user/user.php
方法：_handleUserCommonInfo
影响点：增加auth返回值的数据结构处理

2、文件：joywok/library/models/model_suggestion.php
方法：_getUsers、combineUser
影响点：批量获取用户信息的字段增加auth、增加auth返回值的数据结构处理

3、文件：joywok/library/models/model_user.php
方法：combineUser、getReport
影响点：增加auth返回值的数据结构处理、增加auth返回值的数据结构处理

是否涉及DB 层改动：是
1、文件：joywok/library/DB/mongo/user/user.php
方法：_handleUserinfoToDB
影响点：增加auth参数的数据结构处理

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ 的报文是否太大: 否

自测内容：
1、用户认证设置接口调用✅
2、用户主页接口调用✅
3、通讯录首页接口调用✅
4、组织架构接口调用✅
5、直线汇报人接口调用✅

影响点：
1、用户主页、通讯录；

自测人： @柳鑫(Luna) 

cc @杨康(Conn) 