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

7、