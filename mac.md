## mac电脑使用与配置

### 相关介绍
dock(程序坞) 桌面下方的一排图标，用来快速启动程序，Dock中间偏右侧有一条浅浅的分割线。分割线左侧是APP的图标，在运行的下面会有白色光点。
分割线右侧是堆栈，此图中堆栈中只有打开后最小化的APP窗口。再次单击后会恢复该窗口。最右侧是废纸篓，里面有文件的时候会是满的，没有文件就如上图是空的

finder(访达) 应用软件的访问入口，类似于开始菜单

触摸屏 是多点触控，支持多种手势，方便操作

### 键盘布局

键盘布局： Command键又称苹果键「Apple key」，作用等同于PC键盘上的Ctrl键，键盘左右各一个。option键，第二选择键。control键用的不多，
control+左键就是右键，但control键在终端下等同于ctrl键

Mac键盘符号和修饰键说明
⌘ Command
⇧ Shift
⌥ Option
⌃ Control
↩︎ Return/Enter
⌫ Delete
⌦ 向前删除键（Fn+Delete）
↑ 上箭头
↓ 下箭头
← 左箭头
→ 右箭头
⇞ Page Up（Fn+↑）
⇟ Page Down（Fn+↓）
Home Fn + ←
End Fn + →
⇥ 右制表符（Tab键）
⇤ 左制表符（Shift+Tab）
⎋ Escape (Esc)

### 基本操作
显示桌面： 五个手指我抓然后在面板上散开

开关机与睡眠： 点击左上角的苹果图标

左上角是菜单栏，苹果图标旁边是打开的应用名称，整个菜单栏会随着打开的应用而变化

触摸bar上会随着打开的应用及按键变化

系统设置： 齿轮图标，可以设置亮度，声音，触摸板，语言与输入法，可以直接添加中文和中文输入法

右键： 两个手指头点击一下触控板

### 快捷键

Spotlight是最最常用的东西，类似Windows开始菜单中的搜索。可以用来搜索文档，也可以搜索本机的程序。点击右上角的“放大镜”图标，或者快捷键： Command+Space

Mac中使用Activity monitor结束未响应的程序

全屏截图：Command+Shift+3,    使用快捷键后会马上截获当前的全屏。保存到桌面上
区域截图：Command+Shift +4,   使用快捷键后会出现带坐标的瞄准器， 拖拽选择要截图的区域。
程序窗口截图： Command+Shift+4+Space, 使用快捷键后会出现一个照相机的图标， 选择程序窗口，然后单击截图。

访问远程共享目录在Mac中，  先打开Finder,    command +K   打开共享目录 输入： smb://192.168.0.4/share

command键和+键增大显示

复制剪切粘贴文字： command+c/x/v
移动文件：选中目标文件，然后使用 Command+C 复制，然后用 Command +Option+V 将其移动到目标目录。

交换大小写键和control键： 系统设置设置-》键盘-》修饰键


跳到本行开头 – Command + 左方向键←
跳到本行末尾 – Command + 右方向键→
跳到当前单词的开头 – Option + 左方向键←
跳到当前单词的末尾 – Option + 右方向键→
选中当前位置到本行开头的文字 – Shift + Command + 左方向键←
选中当前位置到本行末尾的文字 – Shift + Command + 左方向键→

0 行首
$ (shift+4)行尾
gg 文首
G（shift+g） 文尾
A（Shift+a)文尾，并编辑
ctrl+f 向前翻页
ctrl+b 向后翻页
数字+gg，跳转到数字指定的行

网页刷新 cmd+r

### 触摸屏
双指点击唤起如win系统右键的菜单列表；双指滑动是浏览页面内容；三指向上滑是分块显示桌面上的应用，并显示当前是哪个桌面，你可以再添加多几个桌面；
三指向下是会回到应用应用，三指左右滑动是切换不同桌面；四指往手心一捉是显示电脑上所有的应用程序快捷图标。四指散开是快速到桌面

### iterm+zsh
iterm从官网下载安装 或者 brew cask install iterm2


将iTem2设置为默认终端，打开iTerm2-菜单栏中选择iTerm2 -> Make iTerm2 Default Term

bash的提示功能不够强大，界面也不够炫，并非理想工具。
而zsh的功能极其强大，只是配置过于复杂，起初只有极客才在用。后来，有个穷极无聊的程序员可能是实在看不下去广大猿友一直只能使用单调的bash, 
于是他创建了一个名为oh-my-zsh的开源项目

查看系统已有的bash  cat /etc/shells, Mac系统自带了zsh, 一般不是最新版，如果需要最新版可通过Homebrew来安装（

安装 oh-my-zsh sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"


### 软件安装
安装方式有： dmg,zip等安装文件下载，二进制安装文件，app store， brew安装


Mac系统的安装文件后缀名是.dmg,  双击打开后，会出现一个安装对话框， 把图标拖拽到Application中就可以了。
打开Finder, 到Application文件夹下，找到你要卸载的软件，右键，选择Move To Trash. 就卸载好了。

应用程序安装目录切换:
应用都统一安装在application目录，出现让你拖动图表到Application这个文件夹，一定要拖，这样所有软件都在一个文件夹了。
目的路径不在Application的，可以考虑卸载了再安装。下载到dmg文件其实是一个磁盘镜像，挂载磁盘镜像，然后把程序拷贝进application目录，
就可以把磁盘镜像推出。dmg文件是可以直接运行的，双击打开就是运行. 如果点击之后没有拖拽到application目录，可以在访达里面的位置点击这个应用，
右边会显示该应用与application目录同级，手动拖拽过去即可。


安装brew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"


默认没有python3，brew install python3即可

### 终端相关
禁止brew 每次安装都要更新 export HOMEBREW_NO_AUTO_UPDATE=true

vim 配置 https://github.com/amix/vimrc

### todo 
触摸板的使用
把苹果的系统自带的中文输入法，换成自己习惯的搜狗输入法。

默认的terminal并不好用，改用 iTerm，shell选择oh-my-zsh
iTerm2 + oh-my-zsh + solarized


### 不灵的点
锁屏快捷键 ctrl +shift + 开机键
三个指头切换应用
mac app store 登陆下载出错，提示：未能完成该操作。(com.apple.commerce.client 错误 500。)
defaults delete com.apple.appstore.commerce Storefront 方法无效
