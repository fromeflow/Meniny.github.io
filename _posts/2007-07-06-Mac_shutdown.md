---
layout: post
category: "mac"
title:  "Mac: 终端关机重启"
tags: [Mac]
summary: "Mac: 终端关机重启"
---
收集了一些 Mac OS X 的终端关机/重启指令:

* 立即关机

{% highlight console %}
sudo halt
{% endhighlight %}

* 立即关机

{% highlight console %}
sudo shutdown -h now
{% endhighlight %}

* 某段时间后关机(这里是十分钟)

{% highlight console %}
sudo shutdown -h +10
{% endhighlight %}

* 某个时间点关机(这里是20:00)

{% highlight console %}
sudo shutdown -h 20:00
{% endhighlight %}

* 立即重启

{% highlight console %}
sudo reboot 
{% endhighlight %}
		
* 立即重启

{% highlight console %}
sudo shutdown -r now
{% endhighlight %}


