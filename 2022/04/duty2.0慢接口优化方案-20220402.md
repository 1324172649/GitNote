- [ ]班次目标列表接口
	1.iphoto_duty_target_custom表索引优化：
        	a.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_custom;
        	b.创建索引：CREATE INDEX deptid_dateid_index on iphoto_duty_target_custom(dept_id,date_id);
    	2.iphoto_duty_target_data表索引优化：
        	a.删除索引：DROP INDEX date_id_inx on iphoto_duty_target_data;
        	b.删除索引：DROP INDEX target_id_inx on iphoto_duty_target_data;
        	c.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_data;
        	d.创建索引：CREATE INDEX deptid_dateid_targetid_idx on iphoto_duty_target_data(dept_id,date_id,target_id);
    	3.iphoto_duty_target_value表索引优化：
        	a.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_value;
        	b.创建索引：CREATE INDEX deptid_startat_idx on iphoto_duty_target_value(dept_id,start_at);
- [ ] 班次目标详情接口
    	1.使用的表索引和列表接口一致
    	2.详情信息记入缓存duty_target:
- [ ] 备忘录列表接口
    	1.列表不必要字段不予处理和返回，share_scope、remind_users、content
    	2.权限查询次数优化
- [ ] 任务管理获取任务列表
	- 未开始
- [ ] 新建任务
	- 未开始