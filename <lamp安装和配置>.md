##安装apache2

* sudo apt-get install apache2
  * 在浏览器中输入localhost---

##安装php5,和apache2的php支持模块
* sudo apt-get install php5
* sudo pat-get install libapache2-mod-php5
  * 书写 phpinfo 文件进行测试
  `注意文件权限的改变`

##安装mysql-server mysql-client php5-mysql
* 编写mysql_phptest.php文件进行数据库测试

##安装php附加模块 php5-gd php5-curl php5-xdebug
  * sudo apt-get install php5-gd php5-curl php5-xdebug
  * sudo /etc/init.d/apache2 restart 重启apache2

