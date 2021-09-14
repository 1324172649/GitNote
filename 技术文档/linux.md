查看虚拟机安装的ubuntu的版本号：

root@ubuntu:/# cat /proc/version
Linux version 3.19.0-80-generic (buildd@lcy01-33) (gcc version 4.8.4 (Ubuntu 4.8.4-2ubuntu1~14.04.3) ) #88~14.04.1-Ubuntu SMP Fri Jan 13 14:54:07 UTC 2017
————————————————————————————————————————————————————————————————————————————————————————————————
Linux version 4.10.0-28-generic (buildd@lgw01-12) //linux内核版本号

gcc version 5.4.0 //gcc编译器版本号

Ubuntu 5.4.0-6ubuntu1 //Ubuntu版本号
————————————————————————————————————————————————————————————————————————————————————————————————

root@ubuntu:/# uname -a
Linux ubuntu 3.19.0-80-generic #88~14.04.1-Ubuntu SMP Fri Jan 13 14:54:07 UTC 2017 x86_64 x86_64 x86_64 GNU/Linux
————————————————————————————————————————————————————————————————————————————————————————————————
显示linux的内核版本和系统是多少位的：X86_64代表系统是64位的
————————————————————————————————————————————————————————————————————————————————————————————————
root@ubuntu:/# lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 14.04.5 LTS
Release:	14.04
Codename:	trusty
————————————————————————————————————————————————————————————————————————————————————————————————
Distributor ID: Ubuntu //类别是ubuntu

Description:  Ubuntu 16.04.3 LTS //16年3月发布的稳定版本，LTS是Long Term Support：长时间支持版本，支持周期长达三至五年

Release:    16.04 //发行日期或者是发行版本号

Codename:   xenial //ubuntu的代号名称
————————————————————————————————————————————————————————————————————————————————————————————————

查看磁盘空间
df -hl
