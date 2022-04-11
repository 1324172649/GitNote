@Git 分支管理 @朱晓娜(Hannah) #提测申请# 

分支： liuxin_master_duty2_slow_api_20220329
分支来源： master

相关链接：
https://dogesoft.joywok.com/as/info?id=OdMMdB8FWzqnbtKc
项目出处：@Starbucks Partner APP 

提测内容：
1、duty2.0慢接口优化;

涉及脚本：
1、{domain}_duty_target_custom表索引优化、{domain}_duty_target_data表索引优化、{domain}_duty_target_value表索引优化
cd /var/www/joywok/Sql/cmd/
php create_table_func.php create_index_for_duty2_slow_api_20220329

涉及配置：无

涉及接口清单：
1、GET /api/duty/shifttargets 	【班次目标列表】
2、GET /api/duty/shifttarget 	【班次目标详情】
3、GET /api/duty/memos 		【备忘录列表】
4、GET /api/duty/depttasks	【任务管理列表】

是否涉及Controller层改动：否

是否涉及model层改动：是
1、文件：joywok/library/models/memo/Memo.php
方法：_handleReturnList、_handleData、getMemoAuth、getMemoList、getMemo、addMemo、editMemo、delMemo
影响点：处理返回值、优化权限查询

2、文件：joywok/library/models/duty/DutyTarget.php
方法：_initFieldData、_handleDataArr、getTargetList、getTarget、editCustomTarget、delCustomTarget、editTargetData、editTargetValue、delDeptCustomTargetFromDateId
影响点：处理数据结构、优化班次查询、班次目标详情逻辑修改和写入缓存、修改删除门店自定义班次目标删除缓存、修改班次目标达成值删除缓存、修改套装下发班次目标值删除缓存、删除某个日期之后的门店自定义班次目标删除缓存【供console端使用】

3、文件：joywok/library/models/duty/ConsoleSuitPart.php
方法：getTagByIds
影响点：获取标签

4、文件：joywok/library/models/duty/StoreManage.php
方法：_handleTaskListReturn
影响点：处理返回结构

是否涉及DB 层改动：是
1、文件：joywok/library/DB/db_duty2.php
方法：getTagList、_combineTargetCustomParam、delDeptCustomTargetFromDateId
影响点：标签列表查询sql优化、门店自定义班次目标查询sql优化、门店自定义班次目标删除(某个日期及以后)

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ 的报文是否太大: 否

自测内容：
1、备忘录列表、详情、添加、编辑、删除✅
2、班次目标列表、详情、添加、编辑、删除、目标值变更、达成值变更✅
3、任务列表、详情✅

影响点：
1、备忘录、班次目标、任务管理；

自测人： @柳鑫(Luna) 

cc @杨康(Conn) 