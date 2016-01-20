---
layout: post
title: "为什么每次push都要输入账号密码？"
img: 201305/200101.jpg
description: "第一次使用github,每次push代码至github的时候，都要求输入用户名和密码，感觉很麻烦,原以为就是这样，但总觉得还是有其他方式，经过资料搜索，终于知道如何解决不需要每次输密码了。"
keywords: github,ssh,https,密钥
category: Github
tags: [Github]
author: 大熊
---

也许你每次push代码至github的时候，都要求输入用户名和密码，是不是感觉很麻烦！是什么原因导致的？客户端与github建立连接有两种方式：一种是https，另外一种是基于密钥的SSH连接。https方式每次提交都需要输入账号和密码进行认证；而SSH方式是在客户端所在的电脑生成密钥，同时把密钥部署到github服务器上，客户端与github服务器通过密钥进行认证。所以每次Push都要输入账号和密码，原因是使用了https方式push。

通过下面的命令添加项目连接，即为https方式。
{% highlight bash %}
$git remote add origin https://github.com/fety/fety.github.com.git
{% endhighlight %}

###如何查看当前连接方式？
在git bash命令窗口里输入
{% highlight bash %}
$git remote -v
{% endhighlight %}
返回结果
{% highlight bash %}
origin https://github.com/fety/fety.github.com.git (fetch)
origin https://github.com/fety/fety.github.com.git (push)
{% endhighlight %}

###如何把https换成ssh方式
通过下面的命令
{% highlight bash %}
1. git remote rm origin
2. git remote add origin git@github.com:fety/fety.github.com.git
3. git push origin
{% endhighlight %}

###什么是SSH?
Secure Shell（缩写为SSH），由IETF的网络工作小组（Network Working Group）所制定；SSH为一项创建在应用层和传输层基础上的安全协议，为计算机上的Shell（壳层）提供安全的传输和使用环境。

**优点：**

>1. SSH是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。
>2. 利用SSH协议可以有效防止远程管理过程中的信息泄露问题。
>3. 通过SSH可以对所有传输的数据进行加密，也能够防止DNS欺骗和IP欺骗。
>4. 其传输的数据可以是经过压缩的，所以可以加快传输的速度。

####在客户端来看，SSH提供两种级别的安全验证。
* 第一种级别（基于密码的安全验证），知道帐号和密码，就可以登录到远程主机，并且所有传输的数据都会被加密。但是，可能会有别的服务器在冒充真正的服务器，无法避免被“中间人”攻击。

* 第二种级别（基于密匙的安全验证），需要依靠密匙，也就是你必须为自己创建一对密匙，并把公有密匙放在需要访问的服务器上。客户端软件会向服务器发出请求，请求用你的密匙进行安全验证。服务器收到请求之后，先在你在该服务器的用户根目录下寻找你的公有密匙，然后把它和你发送过来的公有密匙进行比较。如果两个密匙一致，服务器就用公有密匙加密“质询”（challenge）并把它发送给客户端软件。从而避免被“中间人”攻击。

通过SSH连接github，正是基于第二种级别（基于密钥的安全验证）的验证方式。
github生成SSH密钥步骤，请参考[generating-ssh-keys](https://help.github.com/articles/generating-ssh-keys "generating-ssh-keys")，或者[使用Github Pages建独立博客](http://beiyuu.com/github-pages/)
