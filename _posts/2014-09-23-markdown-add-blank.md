---
layout: post
title: "为markdown的超链接加上target='_blank'"
img: 201409/230101.jpg
description: "Markdown支持两种形式的链接语法：行内和参考两种形式，两种都是使用角括号来把文字转成连结。而不管是使用哪种形式，生成的超链接默认是在本窗口打开的。Markdown语法目前还不支持生成“_blank”属性。是不是就没有办法了呢？"
keywords: Markdown
category: Github
tags: [Markdown]
---

Markdown 支持两种形式的链接语法：行内和参考两种形式，两种都是使用角括号来把文字转成连结。

行内形式是直接在后面用括号直接接上链接： 
{% highlight bash %}
This is an [example link](http://example.com/). 
{% endhighlight %}
输出 HTML 为： 
{% highlight bash %}
This is an <a href="http://example.com/">example link</a>
{% endhighlight %}

你也可以选择性地加上 title 属性： 
{% highlight bash %}
This is an [example link](http://example.com/ "With a Title").
{% endhighlight %}
输出 HTML 为： 
{% highlight bash %}
This is an <a href="http://example.com/" title="With a Title">example link</a>.
{% endhighlight %}

正如你所见，生成的超链接默认是在本窗口打开的，为了有更好地阅读体验，我们往往是希望在新窗口中打开超链接，而并不影响阅读本文。markdown目前应该还不支持这种语法的，当然markdown是支持html的，你可以直接使用<code><a></a></code>标签来达到要求。

使用markdown的原因是简洁，为了这个简单的需求而使用臃肿的html就有点得不偿失了，如果这样，还倒不如选择接受markdown这种默认的超链接形式。而jekyll/Octopress可以很自由地定制需要的功能，使新窗口中打开链接变得很容易。

{% highlight bash %}
function addBlankTargetForLinks () {
  $('a[href^="http"]').each(function(){
      $(this).attr('target', '_blank');
  });
}
$(document).bind('DOMNodeInserted', function(event) {
  addBlankTargetForLinks();
});
{% endhighlight %}
代码来源 [https://gist.github.com/4523641](https://gist.github.com/4523641)
