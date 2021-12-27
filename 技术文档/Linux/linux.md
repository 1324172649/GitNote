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

【linux将文件前面100行导出,linux中，使用cat、head、tail命令显示文件指定行】

小文件可以用cat(也可以用head、tail)

显示文件最后20行：cat err.log | tail -n 20

显示文件前面20行：cat err.log | head -n 20

从20行开始显示，显示20行以后的所有行：cat err.log | tail -n +100

显示100行到500行：cat err.log | head -n 500 | tail -n +100

cat err.log | tail -n +100 | head -n 401

sed -n '100,500p' err.log

大文件最好用head、tail

当被查看的文件很大，不要用cat，直接用head，tail

head -n 20 err.log

tail -n 20 err.log

显示100行到500行：head -n500 test.txt | tail -n +100

tail -n +100 test.txt| head -n 401

-----------------------------------------------------------------------------------

php站点访问502，查看错误日志显示
connect() to unix:/var/run/php/php5.6-fpm.sock failed 

查看php-fpm的进程
ps -ef | grep php-fpm
显示为
root       23733   23372  0 02:01 pts/0    00:00:00 grep --color=auto php-fpm

确实没有启动

查看php-fpm的位置
whereis php-fpm
启动php-fpm
/usr/sbin/php-fpm5.6

再次查看php-fpm的进程
ps -ef | grep php-fpm
显示为
root       23695       1  0 01:55 ?        00:00:00 php-fpm: master process (/etc/php/5.6/fpm/php-fpm.conf)
www-data   23697   23695  0 01:55 ?        00:00:00 php-fpm: pool www
www-data   23706   23695  0 01:55 ?        00:00:00 php-fpm: pool www
www-data   23724   23695  0 01:56 ?        00:00:00 php-fpm: pool www
root       23733   23372  0 02:01 pts/0    00:00:00 grep --color=auto php-fpm

此时页面访问正常

-----------------------------------------------------------------------------------