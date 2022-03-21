本地mac终端链接SFTP：
sftp luna@192.168.1.61
远程文件下载到本地制定目录下：
sftp> get -r ./* /Users/luna/Documents/GitNote/GitNote/test/shared

sftp> lcd /Users/luna/Documents/GitNote/GitNote/
sftp> put -r test/.