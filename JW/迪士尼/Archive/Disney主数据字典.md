#### 1、用户数据 userinfo

| 参数名称            | 类型          | 说明                                                         |
| ------------------- | ------------- | ------------------------------------------------------------ |
| id                  | int           | 自增id                                                       |
| uid                 | char(32)      | 用户ID                                                       |
| name                | varchar(50)   | 姓名                                                         |
| password            | char(32)      | 加密后的密码                                                 |
| email               | varchar(100)  | 邮箱                                                         |
| other_account       | varchar(100)  | 账号                                                         |
| employee_id         | varchar(100)  | 工号                                                         |
| pinyin              | varchar(50)   | 拼音                                                         |
| alias               | varchar(100)  | 别名                                                         |
| birth               | varchar(100)  | 生日                                                         |
| level_id            | char(32)      | 安全等级                                                     |
| logintime           | varchar(11)   | 最后一次登录时间                                             |
| gender              | varchar(5)    | 性别 female:女, male:男                                      |
| dept                | varchar(1024) | 所属部门 允许值 dept_id:团队id值、title_id：岗位，业务字典具体某个岗位的id值 |
| status              | tinyint(1)    | 用户状态 允许值0、正常 1、冻结 2、离职 5、未激活             |
| created_at          | int(10)       | 创建时间(UNIX时间戳，精确值：秒)                             |
| updated_at          | int(10)       | 更新时间(UNIX时间戳，精确值：秒)                             |
| firstname           | varchar(50)   | 姓                                                           |
| lastname            | varchar(50)   | 名                                                           |
| business_role       | varchar(500)  | 角色                                                         |
| contact             | varchar(1024) | 通讯录                                                       |
| virtual_reporter    | varchar(200)  | 虚线汇报人                                                   |
| direct_reporter     | varchar(200)  | 直线汇报人                                                   |
| supervisor_reporter | varchar(200)  | 汇报主管                                                     |
| education           | char(16)      | 学历                                                         |
| entry_date          | int(10)       | 入职日期(UNIX时间戳，精确值：秒)                             |
| monthlysalary_date  | int(10)       | 转月薪日期(UNIX时间戳，精确值：秒)                           |
| fulltime_date       | int(10)       | 转全职日期(UNIX时间戳，精确值：秒)                           |
| corporation         | varchar(200)  | 所属法人，具体某个法人的实体                                 |
| dict_attr           | varchar(1024) | 字典详情 允许值：user_category:用户类别、function_level:职能等级 |
| is_manully          | tinyint(1)    | 是否手动创建  1：是 0：否                                    |
| employee_number     | varchar(50)   | 编号                                                         |
| company_domain      | char(16)      | 企业域id                                                     |
| avatar_l            | varchar(100)  | 用户头像-大图                                                |
| avatar_s            | varchar(100)  | 用户头像-小图                                                |
| web_cover           | varchar(150)  | web端封面图                                                  |
| mobile_cover        | varchar(150)  | 移动端封面图                                                 |
| idcard_info         | varchar(255)  | 身份证信息                                                   |
| firstlogin          | int(10)       | 首次登录时间                                                 |
| initial             | varchar(20)   | 用户姓名的首字母                                             |
| sip_config          | varchar(500)  | sip电话配置项                                                |
| ext_flag            | tinyint(1)    | 内外部用户 0、内部， 1、外部                                 |

#### 2、团队数据 dept

| 参数名称            | 类型          | 说明                                                         |
| ------------------- | ------------- | ------------------------------------------------------------ |
| id                  | int(10)       | 自增id                                                       |
| dept_id             | char(16)      | 部门ID                                                       |
| name                | varchar(300)  | 部门名称-中文                                                |
| pinyin              | varchar(300)  | 部门名称pinyin                                               |
| en_name             | varchar(300)  | 部门名称-英文                                                |
| level               | int           | 部门等级                                                     |
| parent_id           | string        | 上级id                                                       |
| logo                | varchar(200)  | 部门logo                                                     |
| description         | string        | 描述                                                         |
| created_at          | int           | 创建时间                                                     |
| updated_at          | int           | 更新时间                                                     |
| category            | int           | 类别                                                         |
| code                | int           | 编码                                                         |
| detail_address      | object        | 详细地址允许值：longitude：横坐标、latitude：纵坐标、province：省份、city：市辖区、district、区/县、street：街道、location_name：定位地址 、location：定位名称 |
| tels                | array         | 电话                                                         |
| emails              | array         | 邮箱                                                         |
| ticket_info         | array         | 开票信息 eg（company：公司名称、taxpayer_numer：纳税人识别号、ticket_address：地址、ticket_tel：电话、open_bank：开户行、account：账号） |
| operating_at        | array         | 营业时间 eg（id可选值：mon：周一,tue ：周二,wen：周三,thu：周四,fri：周五,sat：周六,sun：周日、start_time：开始时间、end_time：结束时间） |
| corporation         | string        | 法人                                                         |
| is_manully          | int           | 是否手动创建                                                 |
| dict_attr           | object        | 字典属性 允许值：teamtype:部门类别、store_category:门店类别  |
| rid                 | string        | 部门负责人                                                   |
| deputys             | array         | 副职                                                         |
| admins              | array         | 管理员                                                       |
| region_code         | varchar(32)   | 区域code                                                     |
| ishide              | int(1)        | 是否隐藏本部门 0:否 1:是                                     |
| hide_exception      | text          | 隐藏本部门，例外人员仍可以看到本部门                         |
| isvisible           | int(1)        | 是否开启仅可见本部门 0:否 1:是                               |
| visible_exception   | text          | 仅可见本部门例外人员                                         |
| ext_flag            | tinyint(1)    | 内外部团队标识 1、内部 2、外部                               |
| top_time            | int(1)        | 系统管理使用的置顶时间                                       |
| superior_unsysuser  | varchar(255)  | 上级管理人员-非系统用户                                      |
| long                | varchar(30)   | 经度                                                         |
| lat                 | varchar(30)   | 纬度                                                         |
| position_img        | varchar(100)  | 部门所在位置图片-中文                                        |
| position_img_en     | varchar(100)  | 部门所在位置图片-英文                                        |
| background          | varchar(100)  | 背景图                                                       |
| business_code       | varchar(200)  | 业务编号                                                     |
| shifts              | varchar(1024) |                                                              |
| virtual_parent      | char(16)      | 虚线上级                                                     |
| store_switch_status | tinyint(1)    | 开关店状态 1、开店 2、关店                                   |
| ext_dept_flag       | tinyint(1)    | 团队是否允许删除 0、否 1、是                                 |
| initial             | varchar(255)  | 团队名称首字母                                               |

#### 3、团队与用户直属成员 group_mems

| 参数名称        | 类型         | 说明                                                         |
| --------------- | ------------ | ------------------------------------------------------------ |
| id              | int(11)      | 自增id                                                       |
| uid             | char(32)     | 用户id                                                       |
| gid             | char(16)     | 部门id/群组id                                                |
| gname           | varchar(255) | 部门名称/群组名称                                            |
| pinyin          | varchar(255) | 部门名称pinyin/群组名称pinyin                                |
| op_uid          | char(32)     | 操作人                                                       |
| type            | int(1)       | 数据类型 0、群组 1、部门                                     |
| role            | int(1)       | 成员身份 0、创建人  1、管理员 2、成员 4、关注人员 ，该参数仅群组使用 |
| join_at         | int(10)      | 加入时间                                                     |
| level_code      | int(1)       | 部门管理员身份-已废弃                                        |
| top_time        | int(10)      | 用户在系统管理中置顶时间                                     |
| order           | int(10)      | 排序值，作为在通讯录中用户排序使用                           |
| user_pinyin     | varchar(100) | 用户pinyin                                                   |
| is_dynamic_mems | tinyint(3)   | 群组成员的主关系是否为动态成员 1、是 2、否                   |

#### 4、角色数据 roles

| 参数名称   | 类型         | 说明                               |
| ---------- | ------------ | ---------------------------------- |
| id         | int(10)      | 自增id                             |
| role_id    | char(16)     | 角色id值，唯一标识                 |
| name       | varchar(255) | 角色名称                           |
| pinyin     | varchar(255) | 拼音                               |
| creator_id | char(16)     | 创建人                             |
| code       | varchar(32)  | 编码                               |
| created_at | int(10)      | 创建时间(UNIX时间戳，精确值：秒)   |
| updated_at | int(10)      | 更新时间(UNIX时间戳，精确值：秒)   |
| domain_id  | char(16)     | 企业域id                           |
| data       | varchar(500) | 已废弃                             |
| operation  | varchar(500) | 角色可操作项                       |
| apps       | varchar(500) | 已废弃                             |
| sync_flag  | tinyint(1)   | 是否开启同步模式 1、开启 2、未开启 |

#### 5、角色成员 role_users

| 参数名称    | 类型     | 说明                             |
| ----------- | -------- | -------------------------------- |
| id          | int(10)  | 自增id                           |
| role_id     | string   | 角色id值，角色唯一标识           |
| uid         | string   | 用户id值，用户唯一标识           |
| operator_id | string   | 操作人                           |
| created_at  | int      | 创建时间(UNIX时间戳，精确值：秒) |
| domain_id   | char(16) | 企业域id                         |

#### 6、字典数据 dictinfo

| 参数名称           | 类型         | 说明                                                         |
| ------------------ | ------------ | ------------------------------------------------------------ |
| id                 | int(10)      | 自增id                                                       |
| type               | varchar(100) | 字典类型 允许值：teamtype：团队类别、store_category：门店类别、user_category：用户类别、jobtype：岗位、function_level：职能等级 |
| zh_title           | varchar(100) | 标题-中文                                                    |
| en_title           | varchar(100) | 标题-英文                                                    |
| zh_desc            | varchar(500) | 描述 - 中文                                                  |
| en_desc            | varchar(500) | 描述 - 英文                                                  |
| apply_obj          | varchar(100) | 适用对象 允许值：user：用户、dept：部门、store：门店、org：组织 |
| word_strip_source  | tinyint(1)   | 词条来源模式 允许值 1、数据同步模式 2、手动管理模式 注：数据同步模式的字典不允许在系统管理中编辑 |
| is_self_edit       | tinyint(1)   | 是否允许自行编辑 允许值 0、不允许 1、允许                    |
| is_custom          | tinyint(1)   | 是否允许自定义 允许值 0、不允许 1、允许                      |
| is_default         | tinyint(1)   | 是否默认 允许值 0、否 1、是                                  |
| allow_modify_items | varchar(20)  | 允许修改模式 允许值多选：1、团队或用户为非同步模式 2、团队或用户为同步模式 |
| is_single_select   | tinyint(1)   | 单双选 允许值 1、单选 2、多选                                |
| ceator_id          | char(32)     | 创建人                                                       |
| created_at         | int(10)      | 创建时间(UNIX时间戳，精确值：秒)                             |
| updated_at         | int(10)      | 更新时间(UNIX时间戳，精确值：秒)                             |

#### 7、词条数据  dicts

| 参数名称   | 类型         | 说明                                                         |
| ---------- | ------------ | ------------------------------------------------------------ |
| id         | char(16)     | 字典id值，可作为词条唯一标识                                 |
| type       | varchar(20)  | 字典类型 允许值：teamtype：团队类别、store_category：门店类别、user_category：用户类别、jobtype：岗位、function_level：职能等级 |
| name       | varchar(255) | 字典名称 - 中文                                              |
| en_name    | varchar(255) | 字典名称 - 英文                                              |
| pinyin     | varchar(100) | 拼音                                                         |
| code       | varchar(40)  | 编码                                                         |
| desc       | archar(255)  | 描述 - 中文                                                  |
| en_desc    | varchar(255) | 描述 - 英文                                                  |
| region     | text         | 废弃                                                         |
| cid        | string       | 字典分组id值，具体某个字典分组的唯一值                       |
| domain_id  | char(16)     | 企业域id                                                     |
| creator_id | char(32)     | 创建人                                                       |
| parent_id  | char(16)     | 父级id                                                       |
| created_at | int(10)      | 创建时间                                                     |
| updated_at | int(10)      | 更新时间                                                     |
| dtype      | tinyint(1)   | 词条类型 允许值 1：分组 2： 词条（分组下可以有多个分组和词条，词条下只能有词条） |

#### 8、字典分组数据 dict_class

| 参数名称   | 类型          | 说明                                                         |
| ---------- | ------------- | ------------------------------------------------------------ |
| id         | char(16)      | 分组id，可作为字典分组唯一标识                               |
| type       | varchar(20)   | 字典类型 允许值：teamtype：团队类别、store_category：门店类别、user_category：用户类别、jobtype：岗位、function_level：职能等级 |
| name       | varchar(100)  | 分组名称                                                     |
| scope      | varchar(1024) | 分享范围                                                     |
| domain_id  | char(16)      | 企业域id                                                     |
| is_default | tinyint(1)    | 默认标识 允许值 1：是 0：否                                  |
| creator_id | char(32)      | 创建人                                                       |
| created_at | int(10)       | 创建时间(UNIX时间戳，精确值：秒)                             |

#### 9、字典与对象关系数据 dict_dept

| 参数名称 | 类型        | 说明                                                         |
| -------- | ----------- | ------------------------------------------------------------ |
| id       | int(10)     | 自增id                                                       |
| did      | char(16)    | 词条id，具体某个词条数据的唯一值                             |
| dtype    | varchar(50) | 字典类型 允许值：teamtype：团队类别、store_category：门店类别、user_category：用户类别、jobtype：岗位、function_level：职能等级 |
| oid      | char(32)    | 对象id，允许值：可以是部门id值，也可以是用户id值             |
| type     | tinyint(1)  | 对象类型 0：部门 1：用户                                     |
| category | tinyint(1)  | 允许值 1：直属关系 2：非直属关系                             |
