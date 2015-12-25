---
layout: post
title: "基于GitHub搭建blog免费无限流量--前期准备"
img: 201301/github/github.jpg
description: "首次在GitHub上搭建Blog，并不是一件轻松的事情。对于无IT背景，更确切的说是无代码编写经验的人，此方法不推荐使用。如果你是一个爱折腾的人，恭喜你，GitHub就是为你准备的。当你熟练地虐它千百遍后，那种满足感油然而生。此处，贡献虐它宝典。Git是一个分布式版本控制工具，GitHub基于git的类似google code的代码仓库服务提供商，既提供免费的代码仓库服务，也提供付费服务。更详细资料请百度、google代劳回答。"
category: Github
tags: [Github,Mygithub]
---

首次在GitHub上搭建Blog，并不是一件轻松的事情。对于无IT背景，更确切的说是无代码编写经验的人，此方法不推荐使用。如果你是一个爱折腾的人，恭喜你，GitHub就是为你准备的。当你熟练地虐它千百遍后，那种满足感油然而生。此处，贡献虐它宝典。Git是一个分布式版本控制工具，GitHub基于git的类似google code的代码仓库服务提供商，既提供免费的代码仓库服务，也提供付费服务。更详细资料请百度、google代劳回答。

## 一、注册GitHub账号

打开github首页https://github.com/，首页最右边就是注册框，注册及其方便快捷，10秒钟内可完成。
![Alt "注册github账号"](/images/201301/github/github_reg.jpg)

## 二、安装客户端

要使用Git，需要安装它的客户端，这里以Windows作为配置和使用环境。在Windows上安装git，一般为msysgit。Windows版的下载地址在这里：http://code.google.com/p/msysgit/downloads/list。

#### 1、下载:请下载最新版本。
![Alt "msysgit_download"](/images/201301/github/msysgit_download.jpg)

#### 2、安装：点击next，直到出现步骤三。
![Alt "msysgit_install"](/images/201301/github/msysgit_install.jpg)

#### 3、在Windows Explorer integration选项中将“Git Bash here”和“Git GUI here”打对勾。
![Alt "msysgit_install"](/images/201301/github/msysgit_install_ei.jpg)

#### 4、在“Adjusting your PATH environment”选项中，默认即可。
![Alt "msysgit_install"](/images/201301/github/msysgit_install_path.jpg)

#### 5、在“Configuring the line ending conversions”选项中，
在windows系统安装，默认选中第一个选项。
![Alt "msysgit_install"](/images/201301/github/msysgit_install_config.jpg)

#### 6、点击“Finish”，结束安装。
![Alt "msysgit_install"](/images/201301/github/msysgit_install_finish.jpg)


##三、配置GitHUb
上步成功安装客户端后，在电脑桌面上你会看到如图所示图标

![Alt "gitbash"](/images/201301/github/gitbash_ico.jpg)

双击gitbash图标，打开程序，界面如下图。

![Alt "gitbash"](/images/201301/github/gitbash_cmd.jpg)

以下步骤将在该命令窗口中完成。
####1、生成SSH Key
输入下面第1行代码，回车。后面几步按回车键即可。第3行代码是提示给key文件命名，回车后按默认名字命名。

{% highlight bash %}
1、$ ssh-keygen -t rsa -C "邮件地址@youremail.com" (注册github账户所使用的邮箱)
2、Generating public/private rsa key pair.
3、Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):<回车确认即可>
{% endhighlight %}

接下来要求你输入加密串，图省事的话，这两步按回车即可

{% highlight bash %}
1、Enter passphrase (empty for no passphrase):<输入加密串>
2、Enter same passphrase again:<再次输入加密串>
{% endhighlight %}

最后看到这样的界面，就成功设置ssh key了：
####2、添加SSH Key到GitHub
在本机生成SSH Key之后，需要添加到GitHub上，以完成SSH链接的设置。用文本编辑工具打开id_rsa.pub文件，该文件在C:\Users\（你的电脑用户名）\.ssh目下。如果看不到这个文件，你需要设置显示隐藏文件。

在GitHub的主页上点击设置按钮：
![Alt "msysgit_install"](/images/201301/github/github_setting.jpg)

选择SSH Keys项，把复制的内容粘贴进去，然后点击Add Key按钮即可：
![Alt "msysgit_install"](/images/201301/github/github_setting_sshkey.jpg)
![Alt "msysgit_install"](/images/201301/github/github_setting_addkey.jpg)

####3、测试连接
可以输入下面的命令，看看设置是否成功，git@github.com的部分不要修改：
{% highlight bash %}
$ ssh -T git@github.com
{% endhighlight %}
如果出现如下提示：
{% highlight bash %}
The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
{% endhighlight %}
输入yes后回车，然后会看到：
{% highlight bash %}
Hi <em>username</em>! You've successfully authenticated, but GitHub does not provide shell access.
{% endhighlight %}
####4、设置你的账号信息
现在我们已经可以通过SSH链接到GitHub了，还有一些个人信息需要完善。从电脑本地提交文件到github,Git会根据用户的名字和邮箱来记录提交,也就是说提交文件时需输入用户名等信息。GitHub也是用这些信息来做权限的处理，输入下面的代码进行个人信息的设置。
{% highlight bash %}
$ git config --global user.name "注册时的用户名"
$ git config --global user.email "your_email@youremail.com"
{% endhighlight %}
个人信息的设置，在目录C:\Users\{你的电脑用户名}下，生成文件名为{.gitconfig}的文件，用文本编辑器打开，里面的内容如下：
![Alt "msysgit_install"](/images/201301/github/github_setting_accout.jpg)

到此，你以成功的连接了github。恭喜你，可以休息下。
特别提醒：如果你想在另一台电脑上建立连接，除了不需要重新创建github账户外，其他步骤依次执行(关键是添加新的SSH Key)。