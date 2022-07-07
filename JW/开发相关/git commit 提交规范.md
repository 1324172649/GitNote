git commit 会车
kickoff链接：
SLA链接：
提测链接：





# Git commit日志基本规范
<type>(<scope>): <subject>
// 空一行
<body>
// 空一行
<footer>

Header部分只有一行，包括三个字段：type（必需）、scope（可选）和subject（必需）。

type代表某次提交的类型，比如是修复一个bug还是增加一个新的feature。
scope用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同。
subject是 commit 目的的简短描述，不超过50个字符。
- 以动词开头，使用第一人称现在时，比如change，而不是changed或changes
- 第一个字母小写
- 结尾不加句号（.）

Body 部分是对本次 commit 的详细描述
- 使用第一人称现在时，比如使用change而不是changed或changes。
- 应该说明代码变动的动机，以及与以前行为的对比。
- 如果要编写多行 请使用\n 换行 回车直接结束描述(注意为反斜杠)

Footer 部分只用于两种情况。
（1）不兼容变动
如果当前代码与上一个版本不兼容，则 Footer 部分以BREAKING CHANGE开头，后面是对变动的描述、以及变动理由和迁移方法。
例如：
BREAKING CHANGE: isolate scope bindings definition has changed.
To migrate the code follow the example below:
    Before:
    scope: {
      myAttr: 'attribute',
    }
    After:
    scope: {
      myAttr: '@',
    }
    The removed `inject` wasn't generaly useful for directives so there should be no code using it.
（2）关闭 Issue
如果当前 commit 针对某个issue，那么可以在 Footer 部分关闭这个 issue 。
例如：Closes #234
也可以一次关闭多个 issue 。
例如：Closes #123, #245, #992



所有的 type 类型如下：
feat： 新增 feature
fix: 修复 bug
docs: 仅仅修改了文档，比如 README, CHANGELOG, CONTRIBUTE等等
style: 仅仅修改了空格、格式缩进、逗号等等，不改变代码逻辑
refactor: 代码重构，没有加新功能或者修复 bug
build: 构造工具的或者外部依赖的改动，例如webpack，npm
perf: 优化相关，比如提升性能、体验
test: 测试用例，包括单元测试、集成测试等
chore: 改变构建流程、或者增加依赖库、工具等
revert: 回滚到上一个版本
ci: 与CI（持续集成服务）有关的改动
格式要求：

# 标题行：50个字符以内，描述主要变更内容
#
# 主体内容：更详细的说明文本，建议72个字符以内。 需要描述的信息包括:
#
# * 为什么这个变更是必须的? 它可能是用来修复一个bug，增加一个feature，提升性能、可靠性、稳定性等等
# * 他如何解决这个问题? 具体描述解决问题的步骤
# * 是否存在副作用、风险?
#
# 尾部：如果需要的化可以添加一个链接到issue地址或者其它文档，或者关闭某个issue。