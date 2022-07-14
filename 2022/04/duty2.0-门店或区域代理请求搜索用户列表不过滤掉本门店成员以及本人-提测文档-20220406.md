@Git_分支管理  @朱晓娜(Hannah) #提测申请# 

分支： liuxin_master_duty2_agent_can_select_dept_members_20220402
分支来源： master

相关链接：
https://dogesoft.joywok.com/as/info?id=288B3SkQVMuDKoyj
项目出处：@Starbucks_Partner_APP 

提测内容：
1、duty2.0-门店/区域代理请求搜索用户列表不过滤掉本门店成员以及本人；

涉及脚本：无

涉及配置：无

涉及接口清单：
1、GET /api2/users/searchnewobjs 【搜索用户列表】

是否涉及Controller层改动：是
1、文件：joywok/application/modules/api2/controllers/UsersController.php
方法：searchnewobjsAction
影响点：新增type参数类型（jw_n_agentusers【门店代理/区域代理】）

是否涉及model层改动：是
1、文件：joywok/library/models/model_suggestion.php
方法：getSupportMems、SearchObjs
影响点：搜索和过滤用户成员

是否涉及DB 层改动：否

返回报文是否太大、是否有冗余报文: 否
发送到xmpp的报文是否太大: 否
发送到MQ 的报文是否太大: 否

自测内容：
1、接口调用展示搜索用户列表正确✅

影响点：无

自测人： @柳鑫(Luna) 

cc @杨康(Conn) 
