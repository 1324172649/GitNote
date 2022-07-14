@Git_分支管理  @朱晓娜(Hannah)  #提测申请# 

分支： liuxin_ent_sbux_sla_duty_suit_target_value_set_20220627
分支来源： ent_sbux

SLA相关链接：https://dogesoft.joywok.com/as/info?id=ifoVZFH5Y5DYJLBb
项目出处：@Starbucks PAPP

提测内容：
1、duty2.0套装下发的班次目标值变更；

涉及脚本：
1、清理班次目标缓存
cd /var/www/joywok/Sql/cmd
php del_duty_target_dirty_cache_20220627.php starbucks

涉及配置：无

涉及接口清单：
无

是否涉及Controller层改动：否

是否涉及model层改动：是
1、文件：joywok/library/models/duty/DutyTarget.php
方法：editTargetValue
影响点：套装下发的班次目标值变更

是否涉及Db层改动：否

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ的报文是否太大: 否

自测内容：
1、班次目标列表和详情展示正常✅ 
2、套装下发的班次目标值变更成功✅ 
3、套装下发的班次目标达成值提交成功✅ 

影响点：
1、duty2.0班次目标；

自测人： @柳鑫(Luna) 

cc @杨康(Conn) 

----------------------

上线内容补充：
是否涉及model层改动：是
1、文件：joywok/library/models/duty/DutyTarget.php
方法：editTargetValue、getTarget
影响点：套装下发的班次目标值变更、获取班次目标信息

2、文件：joywok/library/models/duty/ConsoleSuitPart.php
方法：updateTarget、deleteTarget
影响点：编辑和删除套装班次目标