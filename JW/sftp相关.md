【安装OpenSSH服务器】
sudo apt-get install openssh-server
1、创建SFTP组
groupadd sftp-users
2、创建SFTP的用户
useradd -g sftp-use -s /bin/false mysftp 
passwd mysftp
3、新建目录，指定为SFTP的主目录
mkdir -p /sftp/mysftp
usermod -d /sftp/mysftp mysftp
4、编辑配置文件
vim /etc/ssh/sshd_config

# Subsystem      sftp    /usr/libexec/openssh/sftp-server   //注释这一行

//下面的内容添加到文件末尾
Subsystem       sftp    internal-sftp   
Match Group sftp  
ChrootDirectory /sftp/%u    
ForceCommand    internal-sftp    
AllowTcpForwarding no   
X11Forwarding no 
5、设置目录权限
chown root:sftp /sftp/mysftp  #文件夹所有者必须为root，用户组可以不是root
chmod 755 /sftp/mysftp   #权限不能超过755，否则会导致登录报错，可以是755
6、新建一个目录供stp用户mysftp上传文件，这个目录所有者为mysftp所有组为sftp，所有者有写入权限所有组无写入权限
mkdir /sftp/mysftp/upload  
chown mysftp:sftp /sftp/mysftp/upload  
chmod 755 /sftp/mysftp/upload 
7、重启ssh
service sshd restart
8、sftp登录
sftp mysftp@192.168.1.62


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