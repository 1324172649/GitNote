git 修改 commit 信息
执行：git rebase -i HEAD~3 // 查看最近三条提交信息
vi 模式下，找到需要修改的 commit 记录
将```pick``` 修改为 ```edit``` 或 ```e```，```:wq``` 保存退出
执行：git commit --amend  // 修改commit信息（可重复执行）
执行：git rebase --continue //修改commit信息结束后，提交修改

此时查看log就是修改后的信息：git log/git log --oneline 

# 中间也可跳过或退出 rebase 模式
$ git rebase --skip
$ git rebase --abort

# 从HEAD版本开始往过去数3个版本
$ git rebase -i HEAD~3

# 合并指定版本号（不包含此版本）
$ git rebase -i [commitid]


# 本地仓库没 push 到远程仓库的 commit 信息
$ git rebase -i

# 已经 push 到远程仓库的 commit 信息(某次提交之后的)
$ git rebase -i commitID

# 修改最近提交的 commit 信息
$ git commit --amend --message="modify message by daodaotest" --author="jiangliheng <jiang_liheng@163.com>"
$ git commit --amend 直接回车

-----------------------------------------




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

还有一种特殊情况，如果当前 commit 用于撤销以前的 commit，则必须以revert:开头，后面跟着被撤销 Commit 的 Header。

revert: feat(pencil): add 'graphiteWidth' option

This reverts commit 667ecc1654a317a13331b17617d973392f415f02.
1
2
3
Body部分的格式是固定的，必须写成This reverts commit &lt;hash>.，其中的hash是被撤销 commit 的 SHA 标识符。

如果当前 commit 与被撤销的 commit，在同一个发布（release）里面，那么它们都不会出现在 Change log 里面。如果两者在不同的发布，那么当前 commit，会出现在 Change log 的Reverts小标题下面。



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


1、查看远程仓库连接
git remote 查看所有远程仓库， git remote xxx 查看指定远程仓库地址

2、修改仓库地址
git remote set-url origin   http:/xxxx/john/git_test.git

3、删除仓库，添加新仓库
	a、git remote rm origin
​	b、git remote add origin http://xxx/john/git_test.git

4、 当“git merge”合并分支时遇到错误或者冲突，分支旁边会多出“|MERGING”这个东西，如果想先取消这次合并，使用“git merge --abort”命令

5、// 查看最近三次提交
$ git log --oneline -3
// 查看某个分支最近三次提交
$ git log branchname -3

6、git cherry-pick可以理解为"挑拣"提交，它会获取某一个分支的单笔提交，并作为一个新的提交引入到你当前分支上。 当我们需要在本地合入其他分支的提交时，如果我们不想对整个分支进行合并，而是只想将某一次提交合入到本地当前分支上，那么就要使用git cherry-pick了。

git cherry-pick [<options>] <commit-ish>...

常用options:
    --quit                退出当前的chery-pick序列
    --continue            继续当前的chery-pick序列
    --abort               取消当前的chery-pick序列，恢复当前分支
    -n, --no-commit       不自动提交
    -e, --edit            编辑提交信息

7、撤销文件修改
1. 使用 git checkout 撤销本地修改
即放弃对本地已修改但尚未提交的文件的修改，还原其到未修改前的状态。
注意： 已 add/ commit 的文件不适用个方法，应该用本文提到的第二种方法。

命令如下：

git checkout .      # 撤销对所有已修改但未提交的文件的修改，但不包括新增的文件
git checkout [filename]     # 撤销对指定文件的修改，[filename]为文件名
1
2


2. 使用 git reset 回退项目版本
可以回退到任意已经提交过的版本。已 add / commit 但未 push 的文件也适用。

命令如下：

git reset --hard [commit-hashcode]  
# [commit-hashcode]是某个 commit 的哈希值，可以用 git log 查看
1
2
因此一般用法是先用 git log 查看具体commit的哈希值，然后 reset 到那个版本。

git clean 删除未被跟踪文件及文件夹
git clean  -f
删除：未被跟踪的文件

git clean -fd
删除：未被跟踪的文件和文件夹

从某次commit 切分支
git checkout -b feature/master/f9f104e3/lx-workplacesync-20220705 f9f104e3