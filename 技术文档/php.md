-----------------------------------------------------------------------------------

// 将在CLI中显示当前加载的ini文件，在其中搜索扩展名，其路径不正确。
php -r "echo php_ini_loaded_file();"

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