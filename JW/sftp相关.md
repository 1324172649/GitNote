本地mac终端链接SFTP：
sftp luna@192.168.1.61
远程文件下载到本地指定目录下：
sftp> get -r ./* /Users/luna/Documents/GitNote/GitNote/test/shared
切换到本地指定目录下：
sftp> lcd /Users/luna/Documents/GitNote/GitNote/
上传本地目录下所有文件到当前远程目录下：
sftp> put -r test/. OR put -r ～/test/
上传本地目录下所有文件到指定远程目录下：
sftp> put -r test/. /tmp/ OR put -r ～/test/ /tmp/