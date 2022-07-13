mongo --port 27017 -u "root" -p "123456"

use joywok
db.starbucks_userinfo.find({"id": "4fd34eaecc7b5232afa14e745f869766"})

 db.starbucks_userinfo.update({"id": "4fd34eaecc7b5232afa14e745f869766"},{$set:{birth:'1995/06/22'}})

4fd34eaecc7b5232afa14e745f869766

ca7360d706299b9a9a6ab3aa00bee418

获取到生日周年庆的周期通知内容



【生日缓存】
 define("BIRTHDAY_UIDS","birthday.uids:");             // 当天生日人事件的uid
 
 SMEMBERS birthday.uids:{domain_id}
 SREM birthday.uids:SRSmV8AYGgz17BCW b550d296aa7b71c5bcd4fed1a2104bca 
 SMEMBERS birthday.uids:SRSmV8AYGgz17BCW
 
 #设置用户生日redis 
 hset user:ca7360d706299b9a9a6ab3aa00bee418 birth 1995/06/23

 # mongo 
 db.disneytest_userinfo.find({"id": "df949c98b907ee47e90199a2569e2133"})
 db.disneytest_userinfo.update({"id": "df949c98b907ee47e90199a2569e2133"},{$set:{birth:'2021/03/16'}})