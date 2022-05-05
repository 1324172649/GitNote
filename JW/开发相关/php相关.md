1、查看php-fpm是否开启
root@joywok:/var/www# ps -ef | grep php
root        1827    1487  0 02:42 pts/0    00:00:00 grep --color=auto php
2、查看php-fpm的位置
root@joywok:/var/www# whereis php-fpm
php-fpm: /usr/sbin/php-fpm5.6
3、开启php-fpm
root@joywok:/var/www# /usr/sbin/php-fpm5.6
4、再次输入命令ps -ef|grep php，查看是否已经开启
root@joywok:/var/www# ps -ef | grep php
root        1830       1  0 02:43 ?        00:00:00 php-fpm: master process (/etc/php/5.6/fpm/php-fpm.conf)
www-data    1831    1830  0 02:43 ?        00:00:00 php-fpm: pool www
www-data    1832    1830  0 02:43 ?        00:00:00 php-fpm: pool www
root        1835    1487  0 02:43 pts/0    00:00:00 grep --color=auto php