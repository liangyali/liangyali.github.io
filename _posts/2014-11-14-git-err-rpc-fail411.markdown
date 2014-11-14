---
layout: post
title:  "GitError"
date:   2014-11-14 15:03:18
categories: ruby
---

今天使用Git的过程中，遇到了下面的问题

{% highlight sh %}

Counting objects: 171, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (148/148), done.
error: RPC failed; result=22, HTTP code = 411
fatal: The remote end hung up unexpectedly
Writing objects: 100% (168/168), 2.26 MiB | 0 bytes/s, done.
Total 168 (delta 23), reused 0 (delta 0)
fatal: The remote end hung up unexpectedly
Everything up-to-date

{% endhighlight %}

问题产生原因：

默认git设置http post的缓存大小为1MB

问题解决方法：

{% highlight sh %}

git config http.postBuffer {Size}

{% endhighlight %}
