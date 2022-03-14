@Git_分支管理  @朱晓娜(Hannah) #提测申请# 

分支： liuxin_duty2_todo_op_record_20220303
分支来源： jwbackend_master_duty2_20211027

相关需求链接：
https://dogesoft.joywok.com/as/info?id=yMQe8TqgRChe1h8q
项目出处：@Starbucks Partner APP

提测内容：
1、duty2.0今日Todo操作记录;

涉及脚本：
1、{domain}_duty_log表新增索引、{domain}_duty_todo表新增字段
cd /var/www/joywok/Sql/cmd
php create_table_func.php create_index_for_duty_log_20220311

涉及配置：无


涉及接口清单：
1、GET /api/duty/todorecord	【今日Todo操作记录列表（新增API）】
2、DELETE /api/duty/todoinfo	【今日Todo删除】
3、GET /api/duty/todolist	【今日Todo列表】

是否涉及Controller层改动：否

是否涉及model层改动：是
1、文件：joywok/library/models/duty/DutyTodo.php
方法：getTodoList、delTodo
影响点：今日Todo列表、今日Todo删除

是否涉及DB 层改动：是
1、文件：joywok/library/DB/db_duty2.php
方法：_combineTodoParam
影响点：今日Todo列表查询条件拼接

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ 的报文是否太大: 否

自测内容：
1、今日Todo新增、编辑内容、修改完成状态、删除✅
2、今日Todo列表✅
3、今日Todo操作记录列表✅

影响点：
1、今日Todo模块；

自测人： @柳鑫(Luna)

cc @杨康(Conn)
