# 重要声明
--------
此仓库fork来自theniceboy's [dwm](https://github.com/theniceboy/dwm)

 dwm 构建
============================
[English Ver.](./README_en.md)

dwm 是一个非常快速, 小巧并使用动态管理窗口的窗口管理器

要求
------------
构建 dwm 前, 你需要有 `Xlib` 头文件
In order to build dwm you need the Xlib header files.


安装
------------
编辑 `config.mk` 来匹配你的本地设置 (dwm 将默认安装在 /usr/local)

之后通过以下命令安装 dwm (必须使用 root 用户):

    make clean install

应用的自定义补丁
---------------
- [dwm-alpha-20180613-b69c870.diff](https://dwm.suckless.org/patches/alpha/)
- [dwm-autostart-20161205-bb3bd6f.diff](https://dwm.suckless.org/patches/autostart/)
- [dwm-awesomebar-20191003-80e2a76.diff](https://dwm.suckless.org/patches/awesomebar/)
- [dwm-fullscreen-6.2.diff](https://dwm.suckless.org/patches/fullscreen/)
- [dwm-hide-and-restore.diff](https://github.com/theniceboy/dwm-hide-and-restore-win.diff) (theniceboy写的自定义补丁)
- [dwm-hide_vacant_tags-6.2.diff](https://dwm.suckless.org/patches/hide_vacant_tags/)
- [dwm-noborder-6.2.diff](https://dwm.suckless.org/patches/noborder/)
- [dwm-pertag-20170513-ceac8c9.diff](https://dwm.suckless.org/patches/pertag/)
- [dwm-r1522-viewontag.diff](https://dwm.suckless.org/patches/viewontag/)
- [dwm-rotatestack-20161021-ab9571b.diff](https://dwm.suckless.org/patches/rotatestack/)
- [dwm-scratchpad-6.2.diff](https://dwm.suckless.org/patches/scratchpad/)
- [dwm-vanitygaps-20190508-6.2.diff](https://dwm.suckless.org/patches/vanitygaps/)


运行 dwm
-----------
将以下行添加到 .xinitrc 中来通过 `startx` 启动 dwm:

    exec dwm

如果你需要使用多显示器启动 dwm, 你需要设置屏幕变量, 以下是一个例子:

    DISPLAY=foo.bar:1 exec dwm

(这样将会启动 dwm 并显示在显示器一上)

如果你想自定义你的状态栏, 你可以在 .xinitrc 添加行, 以下是一个例子:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm



## 快捷键
|    主键   |       次键       |       功能       |                 说明                 |
|:---------:|:----------------:|:----------------:|:------------------------------------:|
|    mod    |         s        |     dmenucmd     |               打开dmenu              |
|    mod    |       enter      |      termcmd     |               打开终端               |
|    mod    |         c        |    browsercmd    |              打开浏览器              |
|    mod    |         p        |    touchpadcmd   |          打开或者关闭触摸板          |
| mod+shift |         w        |   setqwertycmd   |            设置qwerty键盘            |
| mod+shift |         m        |   setcolemakcmd  |            设置colemak键盘           |
| mod+shift |         p        |    suspendcmd    |                 熄屏                 |
|  mod+ctrl |         s        |    sktogglecmd   |             开关screenkey            |
|           | AudioLowerVolume |      downvol     |               降低声音               |
|           | AudioRaiseVolume |       upvol      |               升高声音               |
|           |     AudioMute    |      mutevol     |               关闭声音               |
|    mod    |    bracketleft   |      downvol     |               降低声音               |
|    mod    |   bracketright   |       upvol      |               升高声音               |
|    mod    |     backslash    |      mutevol     |               关闭声音               |
|    mod    |         b        |       wpcmd      |               切换壁纸               |
|           |       print      |   screenshotcmd  |                 截屏                 |
| mod+shift |         e        |   rotatestack+1  |        将当前窗口向前移动一格        |
| mod+shift |         u        |   rotatestack-1  |        将当前窗口向后移动一格        |
|    mod    |         e        |   focusstack+1   |         将焦点移到上一个窗口         |
|    mod    |         u        |   focusstack-1   |         将焦点移到下一个窗口         |
|    mod    |         n        |    viewtoleft    |           移到左边的Tab窗口          |
|    mod    |         i        |    viewtoright   |           移到右边的Tab窗口          |
| mod+shift |         n        |     tagtoleft    |      将当前窗口移到左边的Tab窗口     |
| mod+shift |         i        |    tagtoright    |      将当前窗口移到右边的Tab窗口     |
| mod+shift |         h        |    incnmaster    |         切换窗口水平垂直摆放         |
| mod+shift |         l        |    incnmaster    |         切换窗口水平垂直摆放         |
|    mod    |         h        |     setmfact     |         将当前窗口尺寸向左移
|    mod    |         l        |     setmfact     |         将当前窗口尺寸向右移         |
|    mod    |         k        |      hidewin     |             隐藏当前窗口             |
| mod+shift |         k        |    restorewin    |         打开上一个隐藏的窗口         |
|    mod    |         o        |   hideotherwins  |             隐藏其他窗口             |
| mod+shift |         o        | restoreotherwint |          打开隐藏的其他窗口          |
| mod+shift |       enter      |       zoom       |       将窗口与左边焦点窗口切换       |
|    mod    |        tab       |       view       | 在当前Tab窗口与下一个Tab窗口来回切换 |
| mod+shift |         q        |    killclient    |             关闭当前窗口             |
|    mod    |         t        |     setlayout    |      将堆叠窗口模式改为平铺模式      |
|    mod    |         m        |     setlayout    |      将平铺窗口模式改为堆叠模式      |
| mod+shift |         f        |    fullscreen    |             开关全屏模式             |
|    mod    |       space      |     setlayout    |     在平铺模式与堆叠模式之间切换     |
| mod+shift |       space      |  togglefloating  |   不改变当前窗口样式将其他窗口堆叠   |
|    mod    |    apostrophe    |   togglescratch  |       在屏幕中央开关一个小终端       |
|    mod    |         0        |       view       |             打开全视模式             |
| mod+shift |         0        |        tag       |  打开全视模式并将当前挂在每个Tab窗口 |
|    mod    |       comma      |     focusmon     |                                      |
|    mod    |      period      |     focusmon     |                                      |
| mod+shift |       comma      |      tagmon      |                                      |
| mod+shift |      period      |      tagmon      |                                      |
|    mod    |         1        |         0        |              打开0标签页             |
|    mod    |         2        |         1        |              打开1标签页             |
|    mod    |         3        |         2        |              打开2标签页             |
|    mod    |         4        |         3        |              打开3标签页             |
|    mod    |         5        |         4        |              打开4标签页             |
|    mod    |         6        |         5        |              打开5标签页             |
|    mod    |         7        |         6        |              打开6标签页             |
|    mod    |         8        |         7        |              打开7标签页             |
|    mod    |         9        |         8        |              打开8标签页             |
|  mod+ctrl |         q        |       quit       |                退出dwm               |


## 特别鸣谢
[theniceboy](https://github.com/theniceboy)


