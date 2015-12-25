---
layout: post
title: "Sublime text 必备插件"
img: 201409/230201.jpg
description: "Sublime Text是一个代码编辑器也是HTML和散文先进的文本编辑器。漂亮的用户界面和非凡的功能，例如迷你地图，多选择，Python的插件，代码段，等等。完全可自定义键绑定，菜单和工具栏。Sublime Text的主要功能包括：拼写检查，书签，完整的Python API，Goto功能，即时项目切换，多选择，多窗口等等。 Sublime Text 是一个跨平台的编辑器，同时支持Windows、Linux、Mac OS X等操作系统。"
keywords: Sublime
category: 常用工具
tags: [Sublime]
---

Sublime Text是一个代码编辑器也是HTML和散文先进的文本编辑器。漂亮的用户界面和非凡的功能，例如迷你地图，多选择，Python的插件，代码段，等等。完全可自定义键绑定，菜单和工具栏。Sublime Text的主要功能包括：拼写检查，书签，完整的Python API，Goto功能，即时项目切换，多选择，多窗口等等。 Sublime Text 是一个跨平台的编辑器，同时支持Windows、Linux、Mac OS X等操作系统。

Sublime Text可以通过安装插件丰富其功能，打造一款完全适合自己的编辑器，在此收集了常用的插件。安装插件前，先要安装插件管理"Package Control"。

__自动安装：__

1. 通过快捷键 ctrl+` 或者 View < Show Console 菜单打开控制台
2. 粘贴对应版本的代码后回车安装

__适用于 Sublime Text 3：__
{% highlight bash %}
importurllib.request,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();urllib.request.install_opener(urllib.request.build_opener(urllib.request.ProxyHandler()));open(os.path.join(ipp,pf),'wb').write(urllib.request.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())
{% endhighlight %}

__适用于 Sublime Text 2：__
{% highlight bash %}
importurllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp)ifnotos.path.exists(ipp)elseNone;urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler()));open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read());print('Please restart Sublime Text to finish installation')
{% endhighlight %}

__手动安装：__

1. 点击 Preferences < Browse Packages… 菜单
2. 进入 Installed Packages/ 目录
3. 下载 Package Control.sublime-package，并复制文件到 Installed Packages/ 目录
4. 重启 Sublime Text

参考文章：[https://sublime.wbond.net/installation#st3](https://sublime.wbond.net/installation#st3)

###HTML-CSS-JS Prettify
HTML-CSS-JS Prettify是前端工程师必备插件

1. 插件介绍:[https://sublime.wbond.net/packages/HTML-CSS-JS%20Prettify](https://sublime.wbond.net/packages/HTML-CSS-JS%20Prettify)
2. 插件源码:[https://github.com/victorporof/Sublime-HTMLPrettify](https://github.com/victorporof/Sublime-HTMLPrettify)

__安装步骤__

* 在Sublime Text中，按下Ctrl+Shift+P调出命令面板;
* 输入install 调出 Install Package 选项并回车;
* 输入pretty，并在列表中选择HTML-CSS-JS Prettify后回车即可安装

HTML-CSS-JS Prettify，是基于nodejs处理格式化任务，所以必须安装nodejs，

>下载地址[http://nodejs.org/download/](http://nodejs.org/download/)。

下载安装后，需要配置插件指定node.exe的安装目录。如果nodejs是默认安装的化，这里的初始配置路径，一般是不需要更改，除非你安装在其他盘符。这里要注意路径的是反斜杠，与windows的路径反斜杠是不一样。

__右键点击__

![Alt "HTML-CSS-JS Prettify"](/images/201409/230202.jpg)

__配置文件__

![Alt "HTML-CSS-JS Prettify"](/images/201409/230203.jpg)

####HTML-CSS-JS Prettify使用
打开需要格式化的文件，按下快捷键：Ctrl+Shift+H。如果Ctrl+Shift+H不起作用，可能该快捷键被占用了。可以在配置文件中另指定快捷键。
{% highlight bash %}
{ "keys": ["super+shift+h"], "command": "htmlprettify" }
{% endhighlight %}

###IMESupport

如此强大的编辑器，对于中文用户来说，有一个致命的弱点：sublime Text 中文输入法不能跟随光标。神奇插件IMESupport，为你排忧解难。该插件是日本人开发的，对中文输入法也一样支持。效果不是很完美不过已经相当好了。支持ST2/3。

* 插件源码：[https://github.com/chikatoike/IMESupport](https://github.com/chikatoike/IMESupport)
* 插件介绍：[https://sublime.wbond.net/packages/IMESupport](https://sublime.wbond.net/packages/IMESupport)

__安装：__Ctrl+Shift+P →输入pci →输入IMESupport →回车

安装后，不需要任何配置，即可生效，如果不行，请先关闭重新打开sublime text。