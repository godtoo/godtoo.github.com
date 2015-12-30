---
layout: post
title: "Sublime text 快捷键汇总"
img: 201410/160101.jpg
description: "Sublime Text 的快捷键还支持双重组合，譬如默认情况下，将选中的文字改成大写的热键是“Ctrl+K, Ctrl+U”，意思是当你先按下 Ctrl+K 之后迅速再按 Ctrl+U 进行触发（只按下Ctrl+K是没有作用的），这样可以避免很多热键冲突，也可以更灵活更多选择地进行热键自定义。不过在这里就不打算教大家怎样修改各种配置或修改热键了，这恐怕能出一个手册的。"
keywords: sublime
category: 常用工具
tags: [sublime]
author: 大熊
---

这个例子里我在 Key Bindings - User 里面的第一行：{ "keys": ["alt+up"], "command": "swap_line_up" }, 意思就是按 Alt+方向键上时将当前选择的那一行向上移（与上一行交换位置），如果语法神马的没问题，保存好这个文件之后马上就可以使用这个快捷键了。
Sublime Text 2 的快捷键还支持双重组合，譬如默认情况下，将选中的文字改成大写的热键是“Ctrl+K, Ctrl+U”，意思是当你先按下 Ctrl+K 之后迅速再按 Ctrl+U 进行触发（只按下Ctrl+K是没有作用的），这样可以避免很多热键冲突，也可以更灵活更多选择地进行热键自定义。不过在这里就不打算教大家怎样修改各种配置或修改热键了，这恐怕能出一个手册的。

####强大的多行选择和多行编辑：

在写代码的过程中，我们经常需要同时编辑多行代码或者多个变量。在 Sublime Text 中拥有非常实用的多行操作技巧，灵活运用可以大大提高编辑速度哟！相信日后你可能会这样问自己：“当年没有这种方式的编辑器时我究竟是怎么活过来的？！”

###下面是一些我所了解的多行编辑方法：
鼠标选中多行，按下 Ctrl+Shift+L (Command+Shift+L) 即可同时编辑这些行；

鼠标选中文本，反复按 CTRL+D (Command+D) 即可继续向下同时选中下一个相同的文本进行同时编辑；

鼠标选中文本，按下 Alt+F3 (Win) 或 Ctrl+Command+G(Mac) 即可一次性选择全部的相同文本进行同时编辑；

Shift+鼠标右键 (Win) 或 Option+鼠标左键 (Mac) 或使用鼠标中键可以用鼠标进行竖向多行选择；

Ctrl+鼠标左键(Win) 或 Command+鼠标左键(Mac) 可以手动选择同时要编辑的多处文本

类似的技巧还有很多，求大家补充……

###快捷键：
ctrl+/、ctrl+shift+/：代码注释功能，分别未行注释和块注释，再按一下就能去掉注释，ST3能够自动识别是html、css还是js文件，给出不同类型的注释。

* Ctrl+L  选择整行(按住-继续选择下行)
* Ctrl+KK 从光标处删除至行尾
* Ctrl+Shift+K    删除整行
* Ctrl+Shift+D    复制光标所在整行，插入在该行之前
* Ctrl+J  合并行(已选择需要合并的多行时)
* Ctrl+KU 改为大写
* Ctrl+KL 改为小写
* Ctrl+D  选词(按住-继续选择下个相同的字符串)
* Ctrl+M  光标移动至括号内开始或结束的位置
* Ctrl+Shift+M    选择括号内的内容(按住-继续选择父括号)
* Ctrl+/  注释整行(如已选择内容，同“Ctrl+Shift+/”效果)
* Ctrl+Shift+/    注释已选择内容
* Ctrl+Space  自动完成(win与系统快捷键冲突，需修改)
* Ctrl+Z  撤销
* Ctrl+Y  恢复撤销
* Ctrl+Shift+V    粘贴并自动缩进(其它兄弟写的，实测win系统自动缩进无效)
* Ctrl+M  光标跳至对应的括号
* Alt+.   闭合当前标签
* Ctrl+Shift+A    选择光标位置父标签对儿
* Ctrl+Shift+[    折叠代码
* Ctrl+Shift+]    展开代码
* Ctrl+KT 折叠属性
* Ctrl+K0 展开所有
* Ctrl+U  软撤销
* Ctrl+T  词互换
* Ctrl+Enter  插入行后
* Ctrl+Shift Enter    插入行前
* Ctrl+K Backspace    从光标处删除至行首
* Ctrl+Shift+UP   与上行互换
* Ctrl+Shift+DOWN 与下行互换
* Shift+Tab   去除缩进
* Tab 缩进
* F9  行排序(按a-z)
