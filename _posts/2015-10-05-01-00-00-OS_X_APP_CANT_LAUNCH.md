---
layout: post
title: "OS X : 应用程序不能打开"
category: "mac"
tags: [Mac]
---
如果在启动应用/游戏时遇到 "`应用程序 XXX.app 不能打开`" 的问题，通常可能是执行文件的权限有误，可以尝试进入 `/Applications/XXX.app/Contents/MacOS/` 路径，修改其中的与应用/游戏同名的 `Unix executable` 文件的权限为 `755` 后再次运行。

{% highlight sh %}
chmod 755 /Applications/XXX.app/Contents/MacOS/XXX
{% endhighlight %}

<center>Powered by Meniny</center>
<center>Contact <Meniny@qq.com></center>


