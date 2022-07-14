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
1、GET /api/duty/shifttarget 	【班次目标详情】
2、PUT /api/duty/targetdata 	【班次目标达成值修改】

是否涉及Controller层改动：否

是否涉及model层改动：是
1、文件：joywok/library/models/duty/DutyTarget.php
方法：getTarget、addCustomTarget、editTargetData
影响点：班次目标详情、修改班次目标达成值

是否涉及DB 层改动：是
1、文件：joywok/library/DB/db_duty2.php
方法：getTargetData、getTargetDataInfo
影响点：增加查询排序条件

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ 的报文是否太大: 否

自测内容：
1、班次目标列表、详情、达成值修改、门店自定义班次目标新增和编辑、接口调用✅

影响点：
1、班次目标；

自测人： @柳鑫(Luna) 

cc @杨康(Conn) 


【提测内容补充】
是否涉及model层改动：是
2、joywok/library/models/memo/Memo.php
方法：getSimpleUserByids
影响点：获取用户简单信息

自测内容：
2、备忘录操作记录列表和备忘录添加分享范围消息通知接口调用✅

影响点：
2、备忘录；