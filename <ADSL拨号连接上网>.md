###拨号连接上网

使用pppoeconf 进行拨号连接
* 启用拨号连接   
```sudo pppoeconf```

>一个基于文本菜单的程序会指导你进行下面的步骤：

1. 确认以太网卡已被检测到。

2. 输入你的用户名（由ISP所提供 注意：输入时请先清除输入框中的“username“，否则可能造成验证错误）。

3. 输入你的密码（由ISP所提供）。

4. 如果你已经配置了一个PPPoE的连接，会通知你这个连接将会被修改。

5. 弹出一个选项:你被询问是否需要'noauth'和'defaultroute'选项和去掉'nodetach',这里选择"Yes"。

6. Use peer DNS - 选择 "Yes".

7. Limited MSS problem - 选择 "Yes".

8. 当你被询问是否在需要在进入系统的时候自动连接，你可以选择"Yes"。

9. 最后，你会被询问是否马上建立连接。

> 在需要的时候启动ADSL连接，可以在终端中输入：   
```sudo pon dsl-provider```   
> 断开ADSL连接，可以在终端中输入:  
```sudo poff```

###使用pppoeconf拨号后，Network Manager显示设备未托管的解决办法：

> 在终端中输入以下命令，来配置网络连接管理文件：

> sudo gedit /etc/NetworkManager/nm-system-settings.conf 打开后
> 找到 [ifupdown] managed=false 修改成： [ifupdown] managed=true
> 终端运行sudo gedit /etc/network/interfaces 只保留auto lo iface lo inet loopback
> 删除dns设置 sudo mv /etc/resolv.conf /etc/resolv.conf_backup
  ``` 我在这里没有这样做，这样做域名解析失败```    
  
> 之后重启 network-manager服务： sudo service network-manager restart
