---
layout: post
title: "同一台电脑，如何用SSH连接多个github帐号"
img: 201410/200101.jpg
description: "做为一个好程序员，没有几个github怎么说得过去。也许一个是个人所用，一个是为公司项目所用，也许个人就有好几个账号（搭建多个个人网站），但你配置好SSH连接后，一个公钥是不能给多个账号使用的，会提示你“Key is already in use”。那么我们可以生成另一个公钥不就可以了吗？"
keywords: github
category: 开发者手册
tags: [github]
author: 大熊
---

做为一个好程序员，没有几个github怎么说得过去。也许一个是个人所用，一个是为公司项目所用，也许个人就有好几个账号（搭建多个个人网站），但你配置好SSH连接后，一个公钥是不能给多个账号使用的，会提示你“Key is already in use”。那么我们可以生成另一个公钥不就可以了吗？

### 新建user2的SSH Key
{% highlight bash %}
$ cd ~/.ssh     #切换到C:\Users\你的用户名\.ssh
$ ssh-keygen -t rsa -C "yourname@email.com"  #user2 账号注册时的邮箱
#设置名称为id_rsa_work
Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa): id_rsa_work
#(注:如果不输，默认名称是id_rsa,必须与user1生成的文件名区分开来，否则会覆盖)
{% endhighlight %}

### 修改config文件
{% highlight bash %}
在~/.ssh目录下找到config文件，如果没有就创建：
touch config        # 创建config
{% endhighlight %}

然后修改如下：
{% highlight bash %}
# 该文件用于配置私钥对应的服务器
# Default github user(first@mail.com)
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa

# second user(second@mail.com)
# 建一个github别名，新建的帐号使用这个别名做克隆和更新
Host github2
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_work
{% endhighlight %}

其规则就是：从上至下读取config的内容，在每个Host下寻找对应的私钥。这里将GitHub SSH仓库地址中的git@github.com替换成新建的Host别名如：github2，那么原地址是：git@github.com:xiong/xiong.git，替换后应该是：github2:xiong/xiong.git.

### 添加密钥到GitHub后台

打开新生成的~/.ssh/id_rsa2.pub文件，将里面的内容添加到GitHub后台。


### 测试：
{% highlight bash %}
$ ssh -T github2
{% endhighlight %}


### 参考文章：

* 1）  [多github帐号的SSH key切换](http://www.cnblogs.com/BeginMan/p/3548139.html)
* 2）  [在GitHub多个帐号上添加SSH公钥](http://www.webmaster.me/uncategorized/add-multiple-ssh-keys-on-github.html)
* 3）  [BeginMan](https://gist.github.com/BeginMan/8969248)
