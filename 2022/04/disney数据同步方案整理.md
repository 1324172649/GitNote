# streamsets管道：
查询数据库（偏移量字段为首选为updated_at，不存在该字段则为created_at，如果updated_at字段存在为0的情况，则特殊处理该数据）
->js整理和过滤字段（json类型的name拆分中英文两个字段、时间戳格式转换为日期时间格式、不需要的字段删除、保留主键ID）
->写入本地存储（按照每条数据的更新/创建日期，追加写入到本地对应日期目录下的，以数据表名称命名的，以.csv后缀命名的文件中）

67、抽奖人总的抽奖次数数据 disney_raffle_total_times_record
表中不存在created_at，也不存在updated_at，如何判断新增和更新条件？
首先将偏移量设置为主键ID

