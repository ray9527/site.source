---
title: "brew command not found"
date: 2018-05-28T23:26:52+08:00
draft: true
---

brew command not found 问题记录：

<!--more-->
  本来安装好了brew和hugo，刚装好的时候命令使用都是正常的。这两天莫名其妙的都报“command not found ”,搜了下网上的内容，大致记录下：

* 查看 `.bash_profile` 文件中是否保存了brew命令的路径

> vim ~/.bash_profile 

如果报 permission denied 可以用 **sudo vim ~/.bash_profile** ，sudo 命令需要管理员密码

* 查看配置文件发现没有如下命令

> #brew <br>
export PATH=$PATH:/usr/local/bin

如果没有即将上述路径添加到.bash_profile文件中。
**其中有个小的注意点，如果你的文件中已经有其他Path添加路径，需要将新添加的路径放在其后面；否则的话上述的命令要改为以下命令，是将其作为首路径**

> #brew <br/>
export PATH=/usr/local/bin:$PATH

* 修改完成后需要重启.bash_profile

> source ~/.bash_profile

