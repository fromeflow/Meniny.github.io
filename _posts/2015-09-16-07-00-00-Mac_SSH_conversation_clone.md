---
layout: post
category: "mac"
title:  "Mac SSH 克隆会话"
tags: [OS X,Mac,SSH]
summary: "Mac SSH 克隆会话"
---
`Terminal`的`SSH`是标准的`OpenSSH client`  
如果需要克隆会话功能，可以通过配置打开:

{% highlight console %}
$ cat .ssh/config 
Host *
    ControlMaster auto
    ControlPath ~/.ssh/%h-%p-%r
    ControlPersist yes
{% endhighlight %}

这样每连上一个服务器都会自动在`~/.ssh/`下创建一个`socket`文件，下次用相同用户名、端口、主机名进行连接就会自动复用

