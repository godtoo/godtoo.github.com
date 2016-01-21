---
layout: post
title: "基于GitHub搭建免费无限流量blog--使用GitHub Pages创建博客"
img: 201301/cblog/blog.jpg
category: 开发者手册
tags: [Github]
author: 大熊
description: "本篇GitHub pages将隆重登场，它是建立你的blog的核心功能。通过msysgit客户端与GitHub建立连接后，就可以方便的使用它提供的Pages服务。"
---

[《免费搭建无限流量博客--配置和使用github》](http://godtoo.com/blog/2013/01/12/install-msysgit.html)《[免费搭建无限流量博客--在github上创建代码仓库》](http://godtoo.com/blog/2013/01/13/create-repo.html),经过前面两篇文章的介绍，你已经知道如何创建github连接，如何创建代码仓库，如何上传和获取代码文件，这些都是建立blog的前奏，本篇GitHub pages将隆重登场，它是建立你的blog的核心功能。通过msysgit客户端与GitHub建立连接后，就可以方便的使用它提供的Pages服务，GitHub Pages分两种，一种是你的GitHub用户名建立的username.github.com这样的用户&组织页（站），另一种是依附项目的pages。


与GitHub建立好链接之后，就可以方便的使用它提供的Pages服务，GitHub Pages分两种，一种是你的GitHub用户名建立的username.github.com这样的用户&组织页（站），另一种是依附项目的pages。

###User & Organization Pages

想建立个人博客是用的第一种，形如fety.github.com这样的可访问的站，每个用户名下面只能建立一个，在[《免费搭建无限流量博客--在github上创建代码仓库》](http://godtoo.com/blog/2013/01/13/create-repo.html)中，我创建了"fety.github.com"代码仓库，创建好username.github.com项目之后，提交一个index.html文件，然后push到GitHub的master分支。第一次页面生效需要一些时间，大概10分钟左右。生效之后，访问username.github.com就可以看到你上传的页面了，[fety.github.com](http://www.godtoo.com/)就是我的blog

###项目pages

关于第二种项目pages，他和用户pages使用的后台程序是同一套，只不过它的目的是项目的帮助文档等跟项目绑定的内容，所以需要在项目的gh-pages分支上去提交相应的文件，GitHub会自动帮你生成项目pages。具体的使用帮助可以参考[Github Pages的官方文档](https://help.github.com/articles/user-organization-and-project-pages)，最终你可以建立想这样的pages目录[fety.github.com/godtoo](http://www.godtoo.com/)，[godtoo](http://www.godtoo.com/)是我创建的另一个代码仓库，且在该仓库下建立gh-pages分支，并把gh-pages设置为默认分支。

###自动生成Page页面

如果你觉得上面的方式太麻烦，github提供了傻瓜式操作生成page页面，按如下图所示步骤操作

####配置界面

![ALT '创建github blog'](/images/201301/cblog/github_repo_settings.jpg)
![ALT '创建github blog'](/images/201301/cblog/github_auto_create_blog.jpg)

####生成首页
![ALT '创建github blog'](/images/201301/cblog/github_auto_index.jpg)

####选择模板，并发布

![ALT '创建github blog'](/images/201301/cblog/github_auto_template.jpg)

要注意的是，该方式如果是在username.github.com命名的代码库进行,发布后即可通过"username.github.com"访问，例如我的[fety.github.com](http://www.godtoo.com/)，如果是像我上面在代码库[godtoo](http://www.godtoo.com/)下进行操作，还需按以下命令操作后，才能使用github pages功能，其实就是"项目pages"方式。

{% highlight bash %}
$ cd blog
$ git fetch origin
# remote: Counting objects: 92, done.
# remote: Compressing objects: 100% (63/63), done.
# remote: Total 68 (delta 41), reused 0 (delta 0)
# Unpacking objects: 100% (68/68), done.
# From https://github.com/user/repo.git
#  * [new branch]      gh-pages     -> origin/gh-pages

$ git checkout gh-pages
# Branch gh-pages set up to track remote branch gh-pages from origin.
# Switched to a new branch 'gh-pages'
{% endhighlight %}

至此，你已经知道如何创建一个简单的blog，这仅仅是开始，blog的界面如何配置？文章如何编写？将在下一篇文章介绍
