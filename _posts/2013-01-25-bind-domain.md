---
layout: post
title: "基于GitHub搭建免费无限流量blog--绑定域名"
img: 201301/domain/github_domain.jpg
description: "历尽千辛万苦，终于把blog建立起来了，但是fety.github.com域名还是向广大人们宣示github的身份。你一定想要一个自己的域名，完全属于自己的地盘。OK！没问题，只需注册申请一个域名，稍加配置即可，你的地盘你做主。"
category: Github
tags: [Github]
author: 大熊
---


历尽千辛万苦，终于把blog建立起来了，但是[fety.github.com](http://www.godtoo.com)域名还是向广大人们宣示github的身份。你一定想要一个自己的域名，完全属于自己的地盘。OK，没问题，只要你申请注册一个域名，稍加配置，你的地盘你做主。

###绑定域名

要想让username.github.com能通过你自己的域名来访问，需要在项目的根目录下新建一个名为CNAME的文件，文件内容形如:[godtoo.com](http://www.godtoo.com)。需要注意的是，我还没弄清楚CNAME文件是什么类型文件，当初我创建的是一个txt文件，一直域名映射不成功，后来clone别人的CNAME文件修改后，才成功。你可以下载我的，再做修改。

你也可以绑定在二级域名上:[blog.godtoo.com](http://www.godtoo.com)需要提醒的一点是，如果你使用形如[godtoo.com](http://www.godtoo.com)这样的一级域名的话，需要在DNS处设置A记录（什么是A记录下一步会讲到）到207.97.227.245（此处每个人的地址都不同，需要根据Github提供的地址自行修改,如何查看IP，请看下图），而不是在DNS处设置为CNAME的形式，设置成功后，根据DNS的情况，最长可能需要一天才能生效，耐心等待吧。要注意的是，配置文件_config.yml中的baseurl是指向根目录，也就是baseurl这项值可以配置（从文件中删除即可）。

![Alt "查询github pages ip"](/images/201301/domain/github_fety_ip.jpg)

###购买、绑定独立域名

域名的购买网站很多，选择一家知名度高、服务好、优惠的服务商购买，

我们选择[DNSPod](https://www.dnspod.cn/)的服务，他们的产品做得不错，易用、免费，收费版有更高端的功能，暂不需要。注册登录之后，按照DNSPod的说法，只需三步（我们插入一步）：

* 首先添加域名记录，可参考DNSPod的帮助文档：[https://www.dnspod.cn/Support](https://www.dnspod.cn/Support)
* 在DNSPod自己的域名下添加一条[A记录](http://baike.baidu.com/view/65575.htm)，地址就是Github Pages的服务IP地址：204.232.175.78
* 在域名注册商处修改DNS服务:f1g1ns1.dnspod.net、f1g1ns2.dnspod.net。如果你不明白在哪里修改，可以在[DNSPod帮助文档](https://www.dnspod.cn/Support)找到对应的说明，如果还是不明白，可以找域名注册商的客服MM。
* 等待域名解析生效

下图是我的DNS配置
![Alt "查询github pages DNS"](/images/201301/domain/github_blog_dns.jpg)
域名的配置部分完成，等待生效。
