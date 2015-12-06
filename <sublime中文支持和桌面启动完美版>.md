####环境
ubuntu14.04
sublime_text_2

#### 支持中文字体

* 从知乎下载libsublime-imfix.so文件
* 放入/opt/sublime_text目录下
* 设定脚本 /usr/bin/subl   
```
#!/bin/bash
LD_PRELOAD=/opt/sublime_text/libsublime-imfix.so exec /opt/sublime_text/sublime_text $@
```
#### 桌面完美启动

* 在~/.local/share/applications/目录下
修改 两个 .desktop文件
* 不仅仅是/usr/share/applications/目录下的.desktop文件
