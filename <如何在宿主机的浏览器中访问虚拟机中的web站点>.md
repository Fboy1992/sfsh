###基本情况

* 宿主机可以ping通 虚拟机
* 虚拟机可以ping通 宿主机
* 虚拟机可以访问到宿主机的web站点
---

* 但是宿主机不能通过浏览器访问到虚拟机站点
* telnet ip port 得到 端口不可用
---

###解决办法

####1

1.修改防火墙设置：在Shell下输入命令 /sbin/iptables -I INPUT -p tcp --dport 80 -j ACCEPT

2.保存上面的设置：/etc/rc.d/init.d/iptables saved

3.重启防火墙：/etc/init.d/iptables restart

####2
最直接的 打开iptables  
gedit /etc/sysconfig/iptables  

在里面添加下面的（增加80）
-A INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT
service iptables restart 重启

