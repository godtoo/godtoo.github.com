---
layout: post
title: "基于GitHub搭建免费无限流量blog--在GitHub上创建代码仓库"
img: 201301/repo/git_songshu.jpg
description: "上一篇介绍了如何在GitHub创建账户，并通过msysgit客户端与GitHub建立连接。本篇将介绍如何在GitHub上创建代码仓库，以及如何上传本地项目文件至代码仓库，如何获取代码仓库文件至本地电脑。熟练这两步，是后续创建和发布blog的基础。"
category: Github
tags: [Github]
author: 大熊
---

上一篇[《免费搭建无限流量博客--配置和使用github》](http://gudoor.com/github/2013/01/12/build-blog-by-github-install-msysgit.html)，介绍了如何在GitHub创建账户，并通过msysgit客户端与GitHub建立连接。本篇将介绍如何在GitHub上建立Blog，与GitHub建立好链接之后，就可以方便的使用它提供的Pages服务，GitHub Pages分两种，一种是你的GitHub用户名建立的username.github.com这样的用户&组织页（站），另一种是依附项目的pages。介绍GitHub Pages功能前，先介绍如何在github上创建代码仓库。

###一、在github上创建代码仓库

打开github首页https://github.com/，登陆成功后，创建代码仓库的按钮在页面的右上角，如下图：

![ALT '创建github代码仓库'](/images/201301/repo/github_create_repo.jpg)

点击创建按钮后,按如下图所示填写信息，确认后，即创建成功

![ALT '创建github代码仓库'](/images/201301/repo/github_create_repo_desc.jpg)

 如图所示，我创建了名为"fety.github.com"的代码仓库。

###二、获取和上传代码仓库文件


###创建项目文件目录

在你的电脑上，建立一个目录，作为项目的主目录。命名为"blog"。你可以在windows系统目录“C:\Users\{你的电脑用户名}”下点击右键创建名称为"blog"的文件夹；你也可以在Git Bash命令窗口下创建，如下图所示，所创建文件夹默认就是在“C:\Users\{你的电脑用户名}”。

![ALT '创建github代码仓库'](/images/201301/repo/github_mkdir.jpg)

###git初始化项目目录。

{% highlight bash %}
$ cd blog
$ git init
{% endhighlight %}

###创建index.html文件

{% highlight bash %}
$ echo "My GitHub Page" > index.html (创建文件index.html,写入内容“My GitHub Page")
$ git add .   (把文件添加到本地代码库)
$ git commit -a -m "First page commit" (提交代码文件)
{% endhighlight %}

###推送内容至github代码库中

在第一步，我们创建了代码库"fety.github.com",并在本地电脑创建了项目文件夹和文件，这里介绍如果把本地项目文件推送到代码库"fety.github.com"。

{% highlight bash %}
$ git remote add origin https://github.com/fety{fety是我们的用户名}/fety.github.com.git
$ git push -u origin master
{% endhighlight %}

 上传成功之后，等10分钟左右，访问http://fety.github.com,就可以看到index.html页面内容"My GitHub Page"。

###三、克隆代码库

如果你觉得某人的blog主题很漂亮，如何来获取心仪的模板文件呢？按以下步骤，你的愿望即将实现

{% highlight bash %}
$ git clone https://github.com/fety/fety.github.com.git mysite{存放在本地的文件夹}
$ cd mysite
$ rm -rf .git （删除.git）
$ git init
$ git add -A
$ git commit -m 'initial template based on https://github.com/fety/fety.github.com'
$ git remote add origin git@github.com:username/reponame.git
$ git push -u origin master
{% endhighlight %}
