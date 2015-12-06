###修改默认根目录

#### 第一步
在 /etc/apache2/sites-enabled/000-default.cnf中修改默认路径
并加入   
```	
<Directory />
	Options Indexes FollowSymLinks
	AllowOverride All
	Require all granted
</Directory>
```
#### 第二步
在/etc/apache2/apache2.conf中加入Included httpd.conf

#### 第三步
在/etc/apache2/目录下，新建文件httpd.conf, 内容是ServerName localhost
