## windows下相关开发环境配置

### git&github
```angular2
下载git安装包 https://git-scm.com/download/win
配置ssh-keygen, git安装之后自带ssh-keygen工具，目录是在git/usr/bin目录下,将目录添加的系统环境变量
打开git bash工具，ssh-keygen -t rsa -C "yourEmail@xinlang.com"， 如果仍然找不到就是用绝对路径
在C盘你自己的用户下面，找到.ssh文件夹，在里边找到 id_rsa.pub文件，用记事本打开，复制其中的全部内容,添加到github。
pycharm 在settings->version control->git中设置git路径，在terminal里面才能使用
```


