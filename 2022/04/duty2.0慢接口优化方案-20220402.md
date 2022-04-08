# 班次目标列表接口
## 1.iphoto_duty_target_custom表索引优化：
a.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_custom;
b.创建索引：CREATE INDEX deptid_dateid_index on iphoto_duty_target_custom(dept_id,date_id);
## 2.iphoto_duty_target_data表索引优化：
a.删除索引：DROP INDEX date_id_inx on iphoto_duty_target_data;
b.删除索引：DROP INDEX target_id_inx on iphoto_duty_target_data;
c.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_data;
d.创建索引：CREATE INDEX deptid_dateid_targetid_idx on iphoto_duty_target_data(dept_id,date_id,target_id);
## 3.iphoto_duty_target_value表索引优化：
a.删除索引：DROP INDEX dept_id_inx on iphoto_duty_target_value;
b.创建索引：CREATE INDEX deptid_startat_idx on iphoto_duty_target_value(dept_id,start_at);
## 4.重复查询优化
# 班次目标详情接口
## 1.使用的表索引和列表接口一致
## 2.详情信息优先读取缓存，duty_target:$deptId:$targetId:$dateId
a.存储缓存：
	获取详情缓存，查询不到缓存则查询数据库拼接数据，存储缓存，并返回
b.删除缓存：
	门店自定义班次目标编辑；
	门店自定义班次目标删除；
	门店自定义班次目标删除(某个日期开始到之后的所有)【供console端使用】；
	门店班次目标达成值变更；
	套装下发班次目标值变更；
# 备忘录列表接口
## 1.列表不必要字段不予处理和返回，share_scope、remind_users、content
## 2.权限查询重复查询次数优化
# 任务管理获取任务列表
未开始
# 新建任务
未开始


# **索引优化脚本**
joywok/Sql/cmd/create_index_for_duty2_slow_api_20220329.php
执行步骤：
cd /var/www/joywok/Sql/cmd/
php create_table_func.php create_index_for_duty2_slow_api_20220329