apidoc安装方式：
https://note.youdao.com/ynoteshare1/index.html?id=899009317c030623d9df3d8c207b8940&type=note

apidoc分支：
jw_apidoc

//更新生成文档
git pull
cd /var/www
sh apidoc.sh

//1.30更新文档
apidoc -i /var/www/joywok/application/modules/api/controllers/ -f EvaluateController.php -o /var/www/apidoc/

