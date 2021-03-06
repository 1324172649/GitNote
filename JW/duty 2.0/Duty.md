### 时间：2021年10月19号

### 主题：Duty2.0

---

### 一、需求梳理

#### 1、应用设置

1.1、权限配置：总管理员

1.2、高级设置：

- 门店更换或重置套装后清空生效日期及以后的门店自创建内容（开关，默认开启）（内容包括：任务、Todo、班次目标）
- 任务列表页面标题可编辑，默认为“任务”，星巴克为“领导”
- 允许门店在 Web 端管理中自创建任务时添加富文本详细介绍（开关，默认关闭）
- 允许门店自创建任务时添加表单（开关，默认关闭）
- 备忘录文本颜色

#### 2、总管理console

2.1、任务套装

2.1.1基本信息

| 展示     | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| 套装名称 | 限制 40 个字符，允许不同套装的名称一致                       |
| 套装说明 | 限制 1000 个字符                                             |
| 适用门店 | 可从“门店组”中设置的门店组，也可以选择门店类别               |
| 适用班次 | 可选择”无“和班次管理中开启的班次类型”一天两班“”一天三班“。若没有开启班次，则只有”无“一个选项 |

复制新建：基于当前套装新建，名称自动用被复制的套装名称后面加上“的副本”，其他所有的内容完全跟被复制的套装一致。如果此时点击了“取消”，则将复制出来的套装直接删除，如果点“保存”，则保存新的套装。

2.1.2、任务管理

编辑任务：点击编辑按钮弹，刷新当前页面为任务编辑的页面，标题为“编辑任务”，设置项同新建任务。编辑后保存时，提示管理员选择立即生效还是第二天生效，生效时，不管门店是否完成过或编辑过都会被覆盖为新编辑的任务内容；并可由管理员选择选择如果门店已经完成，是否变为未完成状态。此变更不影响已获得的星级班次。

2.1.3、班次目标

2.1.3.1、开关控制是否需要班次目标：默认开启。若不打开，则移动端不展示班次目标模块。若打开，可添加、编辑、删除班次目标。可定义班次目标进度条可选的颜色，默认为 Starbucks 绿色，也可以添加其他颜色，通过色盘组件选择并添加颜色。可定义班次目标卡片在移动端的布局模式，一行滑动模式/自动换行模式，二选一。

2.1.3.2、门店自定义班次目标权限管理

- 创建权限：可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。
- 编辑权限：创建人默认可编辑。其他可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。
- 删除权限：创建人默认可删除。其他可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

2.1.4、星级班次

2.1.4.1、开关控制此套装是否启用星级班次。若不开启，则任务设置项中没有“星级班次任务”一项开关控制此套装是否启用星级班次。若不开启，则任务设置项中没有“星级班次任务”一项。

2.1.4.2、口令库

| 设置       | 说明                            |
| ---------- | ------------------------------- |
| 口令库名称 | 限定 50 个字符                  |
| 口令内容   | 可添加多条，每条限定 100 字符数 |

2.1.5、常用文件

| 设置项 | 是否必填 | 说明                                                         |
| ------ | -------- | ------------------------------------------------------------ |
| 图标   | 是       | 300×300 px，jpg、png 格式                                    |
| 标题   | 是       | 限定 100 字符                                                |
| 文件   | 是       | 支持 PDF、图片和 MP4。仅可上传一个文件，上传后，文件处展示文件预览图标和文件名称（带格式后缀），且新增一个“更换”按钮 |

2.1.6、标签管理

| 标签种类   | 说明                           |
| ---------- | ------------------------------ |
| 任务标签   | 添加时出弹框，仅文字，支持两级 |
| Todo 标签  | 添加时出弹框，可设置图标和文字 |
| 备忘录标签 | 添加时出弹框，可设置图标和文字 |

2.1.7、常用功能

- 图标
- 名称
- 功能

| 功能项       | 说明                                                         |
| ------------ | ------------------------------------------------------------ |
| 表单         | 选择此项时，可配置要填写的表单（单选），这里只可以选择非任务表单。另外可设置谁可以编辑、删除所有提交的数据，以及允许编辑的时间为不限制，或仅提交的当天可以编辑 |
| 常用文件     |                                                              |
| 星级班次排行 |                                                              |
| 班次目标     |                                                              |
| 支援伙伴管理 |                                                              |
| 门店代理     |                                                              |
| 任务管理     |                                                              |
| 店经理检查   | 选择此项时，可继续设置 N 的数字是多少                        |
| 次级按钮     |                                                              |

- 权限

2.1.8、今日焦点

今日焦点关联的 H5 地址输入和保存。

2.2、表单管理

2.3、班次管理

总开关控制是否启用班次。

若开启，则在“一天两班”或“一天三班”类型中至少选择一个。

可自定义班次名称和图标，图标可定义未点亮和已点亮的两种图标。有默认的名称和图标，默认名称为：早班、中班、晚班，英文：AM、MID、PM。三个班次各有两种图标。 

上述开关默认开启，且默认勾选“一天两班”类型班次，不勾选“一天三班”类型班次。若不开启，则任务没有“所属班次”设置项，班次目标也没有是否分班次填写达成情况的设置。

2.4、门店组

类似系统管理 - IAM - 用户组的方式，创建门店组，只不过选择的条件都是门店的属性，比如门店类别、指定门店、所属区域、所在城市等。用于新版 Duty Roster 的各个选择门店范围的场景。

这里设定的门店组中包含的门店，默认为允许使用新版 Duty Roster 的门店。

2.5、人员组

同系统管理 - IAM - 用户组的方式创建自定义用户组，用于 新版 Duty Roster 的各个选择人员范围的场景。

2.6、权限管理

- 权限管理
  - 区域管理员
  - 门店管理组
- 观察员
  - 指定观察员
  - 区域观察员

- 任务权限

  - 分派权限

    可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 执行和完成权限

    可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

    如果任务已有执行人则仅可由执行人执行和完成（开关，默认关闭）

  - 任务逾期后的执行和完成权限

    可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。 

    如果任务已有执行人则仅可由执行人执行和完成（开关，默认关闭）

- To do权限

  - 创建

    可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 编辑

    创建人默认可编辑。其他可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 删除

    创建人默认可删除。其他可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

- 备忘录权限
  - 创建权限

    可多选：门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 编辑权限

    创建人默认可编辑。其他可多选：分享范围成员、门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 删除权限

    创建人默认可删除。其他可多选：分享范围成员、门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

  - 置顶权限

    可多选：创建人、分享范围成员、门店所有成员（含支援伙伴）、门店管理组（含代理）、区域管理员（含代理）、区域观察员、指定观察员、总管理员。

2.7、管理员与日志

2.8、DashBoard

#### 3、门店管理console

1. 初始套装
2. 任务管理
3. 数据报表

#### 4、移动端

1. 首页Nav Bar

2. 班次目标

3. Todo
   - todo 列表
   - 新建todo
   - 未完成的todo操作：查看、编辑、删除、完成
   - 已完成的todo操作：查看、取消完成
   
4. 任务

   - 星级班次未完成

     - 左侧展示今日未完成的任务总数，下面文字“今日任务还有 N 个未完成”；右侧展示当前靠前的一个尚未全部完成所有星级班次任务的班次的未完成的星级班次任务数量，下面文字“还剩 N 个任务即可达成 AM 星级班次”或“还剩 N 个任务即可达成 PM 星级班次”。

   - 星级班次完成

     值班主管：当某个班次的所有星级班次任务被完成，对应班次的值班主管打开此页面时可见到卡片右侧变为点亮的班次图标大小变化，文字“恭喜达成 AM 星级班次，点击领取”或“恭喜达成 PM 星级班次，点击领取”。点击弹出弹框，标题“达成星级班次”，正文展示星级班次口令中的随机一条，按钮“好的”

     此后，如果有下一个班次的星级班次任务待执行，则卡片右侧变为“恭喜达成星级班次，请回顾并做好班次交接”，再次打开此页面，变为下一个班次的未完成星级班次任务数。如果今日没有后续班次，或者后续班次没有星级班次任务，则右侧文字变为“恭喜达成了今日所有星级班次。请回顾并做好班次交接（文字具体内容待业务提供）”。

     其他伙伴：只能看到各个班次的剩余星级任务数，或“今日的所有星级班次任务都已完成”文字。

   - 任务列表

     - 不允许分派的任务：任务列表默认按照任务的创建时间倒序排列，任务完成时移动到此部分的底部，按照完成时间的倒序排列，但把自己完成的任务放在上面。任务完成时展示完成人的头像。
     - 允许分派的任务：最下的部分是允许分派的任务，默认按照任务的创建时间倒序排列，但需要把自己是执行人的任务排在上面。如果没有执行人则展示空头像占位图
     - 未设置具体执行日的周任务：如果是套装中的周循环任务，但是没有设定具体周几执行，这些任务不会出现在任务列表。需要管理组用户在常用功能-门店管理-任务管理中去设置周几执行才会出现在伙伴的任务列表中。
     - 过期任务：过了有效期的任务在新的日期及以后都消失，门店编辑过的也一样。过期的任务可以重新编辑有效时段再次生效。

5. 底部快捷入口
   - 今日焦点
   - 本周关键事项（备忘录）
   - 常用功能

6. 备忘录
   - 备忘录列表
   - 搜索备忘录
   - 新建备忘录
   - 查看/编辑备忘录
   - 过期时间：选择过期时间，可选择年月日时（整点）。过期时间后，备忘录自动进入“历史”，在历史中的备忘录仍可被编辑。若修改过期时间至更久，该备忘录仍会回到备忘录首页的列表。过期备忘录的列表排序也是按照修改时间倒序排，可点击查看和编辑，但是没有置顶功能，所以当一个置顶的备忘录过期进入到了历史备忘录列表，自动取消置顶状态。

7. 常用功能
   - 表单填写
     - 快速评估表
     - 下架登记表
   - 常用文件
   - 星级班次排行
   - 门店管理
     - 班次目标
     - 任务管理
     - 支援伙伴管理
     - 门店代理管理
   - 店经理检查

#### 5、表单

### 二、设计思路

##### 1、应用

应用相关设置存储到{domain}_app_config表中，创建应用时初始化相关设置

```
{
	"administrators":[], //管理员
	"change_suit_empty_content": 1, //门店更换或重置套装后清空生效日期及以后的门店自创建内容
	"add_task_form": 1, //允许门店自创建任务时添加表单
	"add_task_detail": 1,  //允许门店在 Web 端管理中自创建任务时添加富文本详细介绍
	"task_page_title": "领导", //任务列表页面标题可编辑，默认为“任务”，星巴克为“领导”
	"memo_colour": "000000"  //备忘录颜色
}
```

##### 2、任务套装

- 总管理后台新建套装，数据存入模板套装表，根据适用门店存入门店套装关系表
- 任务、班次目标跑批下发到门店
- 套装任务、班次目标更新后，第二天跑批将任务下发到门店

##### 3、表单管理

- {domain}_form表增加obj_id字段，为套装id，获取表单列表直接查询{domain}_form表
- 表单默认版本为0，编辑表单时，表单版本加1
- 提交任务表单时，变更{domain}_duty_task表中links的version字段，更新任务绑定的表单版本

##### 4、班次管理

数据存储到{domain}_app_config中，新建应用的时候将配置初始化进去

```
{
	"shift": {
		"status": 1,
		"twice": [
			{
				"id": "od3c5umjfkr9q2ie",
				"name": "早班",
				"normal_icon": "",
				"finish_icon": ""
			},
			{
				"id": "nxv9bskz3qqaeqqi",
				"name": "晚班",
				"normal_icon": "",
				"finish_icon": ""
			}
		],
		"thrice": []
	}
}
```

##### 5、权限管理

```
{
	"area_admins":[],   //区域营运管理员
	"dept_admins":[],  //门店管理组
	"area_watchers":{     //区域观察员
		"name": "汇报线观察员", 
		"scope": []
	}
	"designate_watchers":{  //指定观察员
		"name": "DM",    //名称
		"scope": [],	 //区域范围
		"user_scope":[]   //人员范围
	},
	"task_cfg": {
		"assign": [
			"all": 1,    //门店所有成员
			"dept_admins": 0,   //门店管理组
			"area_admins": 1,    //区域管理员
			"area_watchers": 0,  //区域观察员
			"designate_watchers": 1,  //指定观察员
			"admins": 1  //总管理员
		],
		"do_task": [   //执行任务
			"all": 1,    //门店所有成员
			"dept_admins": 0,   //门店管理组
			"area_admins": 1,    //区域管理员
			"area_watchers": 0,  //区域观察员
			"designate_watchers": 1,  //指定观察员
			"admins": 1  //总管理员
		],
		"do_due_task": [  //执行逾期任务
			
		]
	},
	"todo_cfg": {
		"add": [],
		"edit": [],
		"del": []
	},
	"memo_cfg":{
		"add":[],
		"edit":[],
		"del":[],
		"visible":[],
		"top":[]
	}
}
```

6、快速评估表绑定todo

### 三、设计目标

1. 功能上满足产品需求
2. 接口响应时间不超过500ms

### 四、库表设计

1、模板套装表 {domain}_duty_template_suit

| column              | type          | desc             |
| ------------------- | ------------- | ---------------- |
| id                  | int(11)       | 自增id           |
| suit_id             | char(16)      | 套装id           |
| name                | varchar(512)  | 套装名称         |
| desc                | varchar(2048) | 套装说明         |
| apply_store         | varchar(2048) | 适用门店         |
| shift_id            | char(16)      | 班次id           |
| shift_target_config | varchar(255)  | 班次目标设置     |
| star_shift_flag     | tinyint(1)    | 是否启用星级班次 |
| today_focus         | varchar(100)  | 每日焦点链接     |
| creator_id          | char(32)      | 创建人           |
| del_flag            | tinyint(1)    | 删除标识         |
| created_at          | int(11)       | 创建时间         |
| updated_at          | int(11)       | 更新时间         |

2、模板任务表 {domain}_duty_template_task

| column           | type          | desc         |
| ---------------- | ------------- | ------------ |
| id               | int(11)       | 自增id       |
| task_id          | char(16)      | 任务id       |
| suit_id          | char(16)      | 套装id       |
| name             | varchar(1024) | 任务名称     |
| pinyin           | varchar(100)  | 任务名称拼音 |
| desc             | varchar(512)  | 说明         |
| detail           | text          | 详细介绍     |
| attachment       | text          | 附件         |
| forms            | varchar(1024) | 表单         |
| shift_id         | char(16)      | 所属班次id   |
| tags             | varchar(100)  | 标签id       |
| end_at           | int(11)       | 截至时间     |
| start_at         | int(11)       | 生效时间     |
| lost_at          | int(11)       | 失效时间     |
| repeat           | varchar(255)  | 重复频率     |
| edit_auth_flag   | tinyint(1)    | 允许门店编辑 |
| del_auth_flag    | tinyint(1)    | 允许门店删除 |
| assign_auth_flag | tinyint(1)    | 允许分派     |
| star_shift_flag  | tinyint(1)    | 星级班次任务 |
| created_at       | int(11)       | 创建时间     |
| updated_at       | int(11)       | 更新时间     |

2、模板任务表 {domain}_duty_dept_template_task

| column           | type          | desc         |
| ---------------- | ------------- | ------------ |
| id               | int(11)       | 自增id       |
| task_id          | char(16)      | 任务id       |
| suit_id          | char(16)      | 套装id       |
| detp_id          | char(16)      | 门店id       |
| name             | varchar(1024) | 任务名称     |
| pinyin           | varchar(100)  | 任务名称拼音 |
| desc             | varchar(512)  | 说明         |
| detail           | text          | 详细介绍     |
| attachment       | text          | 附件         |
| forms            | varchar(1024) | 表单         |
| shift_id         | char(16)      | 所属班次id   |
| tags             | varchar(100)  | 标签id       |
| end_at           | int(11)       | 截至时间     |
| start_at         | int(11)       | 生效时间     |
| lost_at          | int(11)       | 失效时间     |
| repeat           | varchar(255)  | 重复频率     |
| edit_auth_flag   | tinyint(1)    | 允许门店编辑 |
| del_auth_flag    | tinyint(1)    | 允许门店删除 |
| assign_auth_flag | tinyint(1)    | 允许分派     |
| star_shift_flag  | tinyint(1)    | 星级班次任务 |
| template_flag   | tinyint(1)    | 模板任务标识 |
| update_flag     | tinyint(1)    | 任务修改标识 |
| del_flag        | tinyint(1)    | 任务删除标识 |
| created_at       | int(11)       | 创建时间     |
| updated_at       | int(11)       | 更新时间     |

3、班次目标表 {domain}_duty_template_target

| column            | type         | desc             |
| ----------------- | ------------ | ---------------- |
| id                | int(11)      | 自增id           |
| target_id         | char(16)     | 班次目标id       |
| suit_id           | char(16)     | 套装id           |
| name              | varchar(255) | 班次名称         |
| target_value_type | tinyint(1)   | 目标值类型       |
| unit              | varchar(10)  | 单位             |
| rate_flag         | tinyint(1)   | 达成值展示百分比 |
| rate_color        | char(6)      | 百分比进度条颜色 |
| reach_shift_flag  | tinyint(1)   | 达成值分班次填写 |
| creator_id        | char(32)     | 创建人           |
| created_at        | int(11)      | 创建时间         |
| updated_at        | int(11)      | 更新时间         |

4、星级班次表 {domain}_duty_template_star_shift

| column     | type          | desc     |
| ---------- | ------------- | -------- |
| id         | int(11)       | 自增id   |
| star_id    | char(16)      | 班次id   |
| suit_id    | char(16)      | 套装id   |
| name       | varchar(255)  | 名称     |
| content    | varchar(1024) | 内容     |
| creator_id | char(32)      | 创建人   |
| created_at | int(11)       | 创建时间 |
| updated_at | int(11)       | 更新时间 |

5、常用文件 {domain}_duty_file

| column     | type         | desc     |
| ---------- | ------------ | -------- |
| id         | int(11)      | 自增id   |
| f_id       | char(16)     | 文件id   |
| suit_id    | char(16)     | 套装id   |
| name       | varchar(255) | 名称     |
| icon       | varchar(255) | 图标     |
| file_id    | char(16)     | 文件id   |
| creator_id | char(32)     | 创建人   |
| created_at | int(11)      | 创建时间 |
| updated_at | int(11)      | 更新时间 |

6、标签 {domain}_duty_tag

| column     | type         | desc                                    |
| ---------- | ------------ | --------------------------------------- |
| id         | int(11)      | 自增id                                  |
| tag_id     | char(16)     | 标签id                                  |
| suit_id    | char(16)     | 套装id                                  |
| name       | varchar(255) | 名称                                    |
| icon       | varchar(255) | 图标                                    |
| parent_id  | char(16)     | 父级id                                  |
| creator_id | char(32)     | 创建人                                  |
| type       | tinyint(1)   | 类型，1任务标签，2todo标签，3备忘录标签 |
| del_flag   | tinyint(1)   | 删除标识                                |
| created_at | int(11)      | 创建时间                                |
| updated_at | int(11)      | 更新时间                                |

7、常用功能 {domain}_duty_shortcut

| column        | type         | desc         |
| ------------- | ------------ | ------------ |
| id            | int(11)      | 自增id       |
| fun_id        | char(16)     | 唯一id       |
| suit_id       | char(16)     | 套装id       |
| name          | varchar(255) | 名称         |
| icon          | varchar(255) | 图标         |
| relation_type | varchar(50)  | 关联对象类型 |
| relation_obj  | varchar(255) | 关联对象     |
| auth_config   | varchar(255) | 权限配置     |
| parent_id     | char(16)     | 父级id       |
| creator_id    | char(32)     | 创建人       |
| created_at    | int(11)      | 创建时间     |
| updated_at    | int(11)      | 更新时间     |

8、门店套装关系表 {domain}_dept_suit

| column     | type     | desc     |
| ---------- | -------- | -------- |
| id         | int(11)  | 自增id   |
| dept_id    | char(16) | 门店id   |
| suit_id    | char(16) | 套装id   |
| created_at | int(11)  | 创建时间 |
| updated_at | int(11)  | 更新时间 |

9、任务表 {domain}_duty_task

| column          | type          | desc         |
| --------------- | ------------- | ------------ |
| id              | int(11)       | 自增id       |
| task_id         | char(16)      | 任务id       |
| suit_id         | char(16)      | 套装id       |
| name            | varchar(1024) | 任务名称     |
| pinyin          | varchar(100)  | 任务名称拼音 |
| desc            | varchar(512)  | 说明         |
| detail          | text          | 详细介绍     |
| attachment      | text          | 附件         |
| forms           | varchar(1024) | 表单         |
| shift_id        | char(16)      | 所属班次id   |
| tags            | varchar(100)  | 标签id       |
| end_at          | int(11)       | 截至时间     |
| start_at        | int(11)       | 生效时间     |
| lost_at         | int(11)       | 失效时间     |
| repeat          | varchar(255)  | 重复频率     |
| star_shift_flag | tinyint(1)    | 星级班次任务 |
| new_flag        | tinyint(1)    | 新任务标识   |
| created_at      | int(11)       | 创建时间     |
| updated_at      | int(11)       | 更新时间     |

10、todo表 {domain}_duty_todo

| column     | type          | desc        |
| ---------- | ------------- | ----------- |
| id         | int(11)       | 自增id      |
| todo_id    | char(16)      | todo id     |
| dept_id    | char(16)      | 部门id      |
| tag_id     | char(16)      | todo 标签id |
| content    | varchar(2048) | 内容        |
| creator_id | char(32)      | 创建人id    |
| status     | tinyint(1)    | 状态        |
| created_at | int(11)       | 创建时间    |
| updated_at | int(11)       | 更新时间    |

11、班次目标表 {domain}_duty_target

| column            | type         | desc             |
| ----------------- | ------------ | ---------------- |
| id                | int(11)      | 自增id           |
| target_id         | char(16)     | 班次目标id       |
| dept_id           | char(16)     | 门店id           |
| name              | varchar(255) | 班次名称         |
| target_value_type | tinyint(1)   | 目标值类型       |
| unit              | varchar(10)  | 单位             |
| rate_flag         | tinyint(1)   | 达成值展示百分比 |
| rate_color        | char(6)      | 百分比进度条颜色 |
| reach_shift_flag  | tinyint(1)   | 达成值分班次填写 |
| data              | varchar(100) | 目标达成数据     |
| creator_id        | char(32)     | 创建人           |
| created_at        | int(11)      | 创建时间         |
| updated_at        | int(11)      | 更新时间         |

12、日志  {domain}_duty_admin_log

| column      | type        | desc     |
| ----------- | ----------- | -------- |
| id          | int(11)     | 自增id   |
| app_id      | char(32)    | 应用id   |
| oid         | char(16)    | 对象id   |
| modules     | varchar(50) | 模块     |
| sub_modules | varchar(50) | 操作项   |
| op_key      | varchar(10) | 操作类型 |
| ip          | varchar(30) | ip地址   |
| data        | text        | 数据     |
| creator_id  | char(32)    | 创建人   |
| created_at  | int(11)     | 创建时间 |

13、日志  {domain}_duty_log

| column      | type        | desc     |
| ----------- | ----------- | -------- |
| id          | int(11)     | 自增id   |
| app_id      | char(32)    | 应用id   |
| oid         | char(16)    | 对象id   |
| modules     | varchar(50) | 模块     |
| sub_modules | varchar(50) | 操作项   |
| op_key      | varchar(10) | 操作类型 |
| ip          | varchar(30) | ip地址   |
| data        | text        | 数据     |
| creator_id  | char(32)    | 创建人   |
| created_at  | int(11)     | 创建时间 |

14、代理表  {domain}_duty_agent

| column     | type       | desc                                  |
| ---------- | ---------- | ------------------------------------- |
| id         | int(11)    | 自增id                                |
| dept_id    | char(16)   | 门店/区域id                           |
| user_id    | char(32)   | 用户id                                |
| type       | tinyint(1) | 类型：1区域代理，2门店代理，3帮铺伙伴 |
| start_at   | int(11)    | 开始时间                              |
| end_at     | int(11)    | 结束时间                              |
| creator_id | char(32)   | 创建人id                              |
| created_at | int(11)    | 创建时间                              |

15、备忘录表 {domain}_duty_memo【过期时间和分享范围】

| column     | type         | desc     |
| ---------- | ------------ | -------- |
| id         | int(11)      | 自增id   |
| memo_id    | char(16)     | 备忘录id |
| dept_id    | char(16)     | 门店id   |
| title      | varchar(255) | 标题     |
| content    | text         | 正文     |
| top_flag   | tinyint(1)   | 置顶状态 |
| creator_id | char(32)     | 创建人id |
| created_at | int(11)      | 创建时间 |

16、备忘录记录表 {domain}_duty_memo_record

| column     | type     | desc     |
| ---------- | -------- | -------- |
| id         | int(11)  | 自增id   |
| momo_id    | char(16) | 备忘录id |
| creator_id | char(32) | 创建人   |
| data       | text     | 修改内容 |
| created_at | int(11)  | 创建时间 |

17、门店任务数据统计 {domain}_duty_task_stat

| column         | type     | desc              |
| -------------- | -------- | ----------------- |
| id             | int(11)  | 自增id            |
| dept_id        | char(16) | 门店id            |
| date_id        | int(11)  | 时间，0点的时间戳 |
| done_stat_num  | int(11)  | 星级班次完成数    |
| done_task_num  | int(11)  | 已完成数量        |
| total_task_num | int(11)  | 任务总数          |
| created_at     | int(11)  | 创建时间          |
| updated_at     | int(11)  | 更新时间          |

18、班次目标表 {domain}_duty_dept_template_target

| column            | type         | desc             |
| ----------------- | ------------ | ---------------- |
| id                | int(11)      | 自增id           |
| target_id         | char(16)     | 班次目标id       |
| suit_id           | char(16)     | 套装id           |
| dept_id           | char(16)     | 门店id           |
| name              | varchar(255) | 班次名称         |
| target_value_type | tinyint(1)   | 目标值类型       |
| unit              | varchar(10)  | 单位             |
| rate_flag         | tinyint(1)   | 达成值展示百分比 |
| rate_color        | char(6)      | 百分比进度条颜色 |
| reach_shift_flag  | tinyint(1)   | 达成值分班次填写 |
| template_flag     | tinyint(1)   | 模板添加标识     |
| creator_id        | char(32)     | 创建人           |
| created_at        | int(11)      | 创建时间         |
| updated_at        | int(11)      | 更新时间         |

### 五、涉及的接口

#### 移动端

##### 1、门店首页/详情页

- 获取区域/门店列表
- 搜索区域/门店
- 获取今日焦点/常用功能列表

##### 2、班次目标

- 获取班次目标列表
- 新建班次目标
- 编辑班次目标
- 编辑目标达成
- 删除班次目标

##### 3、Todo

- 获取todo列表
- 新增todo
- 获取todo分类
- 编辑todo
- 删除todo
- 完成/取消完成todo

##### 4、任务

- 今日任务完成概况
- 获取任务列表
- 任务筛选
- 获取任务标签
- 获取任务详情
- 完成/取消完成任务
- 分派任务
- 领取星级班次

##### 5、任务管理

- 获取任务列表
- 删除/恢复删除任务
- 编辑任务
- 新建任务
- 获取班次列表

##### 6、帮铺伙伴/门店代理

- 获取代理列表
- 添加/编辑代理
- 删除代理

##### 7、备忘录

- 获取备忘录列表
- 新建备忘录
- 编辑备忘录
- 置顶备忘录
- 获取修改历史
- 备忘录设置
- 删除备忘录
- 获取过期备忘录列表

##### 8、店经理检查获取任务完成情况

##### 9、星级班次排行

##### 10、快速评估表

- 快速评估表列表
- 新建快速评估表
- 删除快速评估表

##### 11、下架登记表

- 获取列表
- 新建下架等级表
- 删除

#### 总管理后台

##### 1、任务套装

- 任务套装列表
- 新建套装
- 删除套装
- 复制新建套装
- 编辑套装（套装详情、适用门店、班次目标设置、星级班次开关、今日焦点）

##### 2、任务管理

- 获取任务列表
- 新建任务
- 编辑任务
- 删除任务
- 复制任务到套装

##### 3、班次目标

- 添加班次目标
- 删除班次目标
- 编辑班次目标

##### 4、星级班次

- 添加星级班次
- 删除星级班次

##### 5、常用文件

- 常用文件列表
- 新建常用文件
- 删除常用文件

##### 6、标签管理

- 获取标签列表
- 添加标签
- 删除标签

##### 7、常用功能

- 常用功能列表
- 添加常用功能
- 删除常用功能

##### 8、表单管理

- 表单列表
- 导出数据
- 表单设置

##### 9、班次管理

- 编辑班次

##### 10、门店组

- 新建门店组分组
- 新建门店组
- 编辑门店组分组
- 编辑门店组

##### 11、人员组

- 新建人员组
- 编辑人员组

##### 12、权限管理

- 编辑权限配置
- 新建区域/指定观察员
- 编辑区域/指定观察员

##### 13、管理员日志

- 获取管理员日志列表
- 日志导出

##### 14、统计

#### 门店管理后台

##### 1、套装

- 获取已绑定的套装
- 套装预览
- 更换套装

##### 2、获取任务列表

- 编辑任务
- 删除任务
- 重置任务
- 获取任务/回收站任务列表+筛选

##### 3、数据报表

#### 应用管理

##### 1、编辑应用设置
