# streamsets管道：
查询数据库（偏移量字段为首选为updated_at，不存在该字段则为created_at，如果updated_at字段存在为0的情况，则特殊处理该数据）
->js整理和过滤字段（json类型的name拆分中英文两个字段、时间戳格式转换为日期时间格式、不需要的字段删除、保留主键ID）
->写入本地存储（按照每条数据的更新/创建日期，追加写入到本地对应日期目录下的，以数据表名称命名的，以.csv后缀命名的文件中）



53、应用统计数据 disney_s_tenant_apps_data
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将查询数据库的SQL条件的偏移量设置为主键ID
->首次上线需要设置起始偏移量为数据库中该表最新一条数据的主键ID
->读取到数据即写入day字段对应的目录下

54、客户端统计数据 disney_s_tenant_client_data
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将查询数据库的SQL条件的偏移量设置为主键ID
->首次上线需要设置起始偏移量为数据库中该表最新一条数据的主键ID
->读取到数据即写入day字段对应的目录下

56、应用访问统计数据 disney_apps_action_all
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将查询数据库的SQL条件的偏移量设置为主键ID
->首次上线需要设置起始偏移量为数据库中该表最新一条数据的主键ID
->读取到数据即写入day字段对应的目录下

57、应用数据统计数据 disney_apps_data_all
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将查询数据库的SQL条件的偏移量设置为主键ID
->首次上线需要设置起始偏移量为数据库中该表最新一条数据的主键ID
->读取到数据即写入day字段对应的目录下

60、抽奖事件数据 disney_raffle_event
updated_at存在0的情况

61、奖品数据 disney_raffle_award
updated_at存在0的情况

62、抽奖声明模版数据 disney_raffle_state_template
updated_at存在0的情况

63、抽奖与对象关系数据 disney_raffle_obj_rel
没有updated_at视为不会发生更新操作

64、抽奖形式模版数据 disney_raffle_game_template
updated_at存在0的情况

65、抽奖形式数据 disney_raffle_game
updated_at存在0的情况

66、抽奖事件与抽奖人记录数据 disney_raffle_times_record
没有updated_at视为不会发生更新操作
数据字典要求的下两个字段不存在
| start_at | int  | 抽奖开始时间 |
| -------- | ---- | ------------ |
| end_at   | int  | 抽奖结束时间 |
需要查询【抽奖事件数据 disney_raffle_event】

67、抽奖人总的抽奖次数数据 disney_raffle_total_times_record
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将查询数据库的SQL条件的偏移量设置为主键ID
->首次上线需要设置起始偏移量为数据库中该表最新一条数据的主键ID
->读取到数据即写入当前日期对应的目录下

68、抽奖记录数据 disney_raffle_record
没有updated_at视为不会发生更新操作

69、抽奖操作日志数据 disney_raffle_log
表中不存在created_at，也不存在updated_at，使用op_time。

70、抽奖用户范围数据 disney_raffle_userscope
updated_at存在0的情况








