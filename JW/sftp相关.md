1. 常用命令
本地mac终端链接SFTP：
sftp -P 22 luna@192.168.1.61

远程文件下载到本地指定目录下：
sftp> get -r ./* /Users/luna/Documents/GitNote/GitNote/test/shared

切换到本地指定目录下：
sftp> lcd /Users/luna/Documents/GitNote/GitNote/

上传本地目录下指定文件到当前远程目录下：
sftp> put ～/test.c
上传本地目录下指定文件到指定远程目录下：
sftp> put ～/test.c /tmp/

上传本地目录下所有文件到当前远程目录下：
sftp> put -r test/. OR put -r ～/test/
上传本地目录下所有文件到指定远程目录下：
sftp> put -r test/. /tmp/ OR put -r ～/test/ /tmp/

2. 服务器目录显示/操作命令
pwd 打印服务器当前目录

cd 切换服务器当前目录

ls 列出服务器当前目录下的文件

mkdir 为服务器创建目录

3. 本机目录显示/操作命令
比服务器目录操作命令多了一个"l"(Local)

lpwd 打印本机当前目录

lcd 切换本机当前目录

lls 列出本机当前目录下的文件

lmkdir 为本机创建目录