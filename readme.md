## mac iterm zsh tmx
Iterm是用来替换mac自带的终端，配置更方便，功能多些，iTerm2 是配置完毕开箱即用的 tmux
Oh-my-zsh是替换自带的bash, 配置文件.zshrc也是只对zsh生效，即如果系统用的是zsh就会使用默认的主题，如果用的是bash，就还是系统原来的配置。
可以只用iterm, 也可以只用oh-my-zsh，也可以结合起来。

echo $SHELL查看当前使用的shell， chsh -s /bin/bash将系统shell切回为bashs

iterm垂直分屏是cmd+d， 水平分屏是cmd+shift+d, 关闭分屏就是把tab重新关掉，新建的屏是新的tab，也是新的session，而不是与原来屏公用session。
在不同的tab切换是cmd+]， 在同一个tab下不同的屏切换是cmd+option+].  

## bash配置

终端命令提示符内容显示通过PS1变量设置，包括显示的内容与颜色，默认最基本的配置export PS1='[\u@\h\w]\$'， 显示"用户名@主机名 当前所在目录的完整名称""

颜色设置复杂一点

    PS1="\[\e[31m\]\D{%c}\[\e[0m\]\[\e[36m\]\w\[\e[0m\]\n[\[\e[1;43m\]\u\[\e[0m\]@\H]$ "
    \[..\] ：表示一些非打印字符
    \e[.. ：转义字符，后面的跟着的特定的转义字符串在终端中表示颜色或者其他意思
    31m ：表示红色字体（41m 表示是红色背景）
    36m ：表示是青蓝色字体
    1;43m ：表示黄色字体（1;33m 表示黄色字体）
    [\e[0m]] ：它在最后将颜色恢复成系统终端默认颜色
    
    
    
## tmux配置

tmux的主要目的不是分屏，iterm或者自带的终端也能分屏，但iterm每新建一个屏都会新建一个ssh连接，消耗服务端资源。
重要的是ssh连接状态不能保存， 比如ssh到服务操作，到周末电脑要关机了，但是服务端操作现场要保留， 如果只用ssh的话就会断开，
用tmux就能实现这一需求，关闭ssh，但是操作仍然在。 

原理就是tmux是个cs模型，会在运行tmux指令的地方起一个tmux server作为代理，其他电脑连过去是连到这个server,发送的命令由这个server在服务器上执行。

tmux使用C/S模型构建，主要包括以下单元模块：
    
    一个tmux命令执行后启动一个tmux服务
    一个tmux服务可以拥有多个session，一个session可以看作是tmux管理下的伪终端的一个集合
    一个session可能会有多个window与之关联，每个window都是一个伪终端，会占据整个屏幕
    一个window可以被分割成多个pane
    
掘金上搜tmux的使用，讲的比较全