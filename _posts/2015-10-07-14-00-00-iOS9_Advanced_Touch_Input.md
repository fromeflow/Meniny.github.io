---
layout: post
title: "iOS 9 : Advanced Touch Input"
category: "ios"
tags: [iOS,iOS 9,Advanced Touch Input]
---
一直以来 iOS 的触摸输入操作的延迟都为人诟病，如果你常用绘图应用，你应该也有过类似的体验: 当你在屏幕上描绘线条，如果速度较快，那么线条就总是在手指触摸位置的后面一段距离追赶。在 iOS 9 中苹果针对这一问题做了改善，从手势的获取，到屏幕的显示，各个环节都做了性能优化来减少时间延迟。

> 关于其他 iOS 9 的特性与功能，有兴趣的朋友可以参考我在 ***iOS 9 适配*** 系列中提到的 [***URLSchemes***](http://www.meniny.cn/2015/09/18/23-08-00-iOS9_URLScheme/)、[***Bitcode***](http://www.meniny.cn/2015/09/18/23-07-00-iOS9_Bitcode/)、[***ATS***](http://www.meniny.cn/2015/09/18/23-06-00-iOS9_ATS/)、[***后台定位***](http://www.meniny.cn/2015/09/25/14-00-00-iOS9_Location/) 、[***StoryBoard Refrences***](http://www.meniny.cn/2015/09/25/15-00-00-iOS9_Stortboard_Refrences/)、[***SFSafariViewController***](http://www.meniny.cn/2015/09/21/12-00-00-iOS9_SFSafariViewController/) 以及 [***Search API***](http://www.meniny.cn/2015/10/07/12-00-00-iOS9_Search/)、[***Content Blocker***](http://www.meniny.cn/2015/10/07/13-00-00-iOS9_Content_Blocker/)。

### Low Latency 低延迟

对于低延迟的使用，苹果提供了这样的代码:

{% highlight swift %}
// For lowest latency (default):
layer.presentsWithTransaction = false;

// For synchronizing with CA:
layer.presentsWithTransaction = true
{% endhighlight %}
<br/>

也就是说，如果用 `OpenGL ES` 渲染，将 `CAEAGLLayer` 的 `presentsWithTransaction` 属性设值为 `false` 即可降低延迟，当然你也可以不设置，因为 `false` 是它的默认值；如果用 `Metal` 渲染则只需将 `MTKView` 的 `presentsWithTransaction` 属性设值为 `false`；如果你不知道我在说什么，请关闭浏览器。

除了 Core Animation 性能的增强外，苹果还引入 Touch Coalescing 和  Touch Prediction 来提升显示效果。

### Touch Coalescing 触控合并

在 iOS 9 之前，应用触摸扫描频率、渲染帧率、应用代码扫描频率均为 `60Hz`，而在 iPad Air 2 中，点扫描(Touch Scan)触摸扫描频率为 `120Hz`，也就是说有 iPad Air 2 中一半的点被丢弃了。而通过 Touch Coalescing，即可将没被直接响应的点合并到响应的触摸事件中。

{% highlight swift %}
for touch in touches {
  let line = lineForTouch(touch)
  for coalescedTouch in event.coalescedTouchesForTouch(touch) {
       addTouchSample(coalescedTouch, toLine: line)
  }
}
{% endhighlight %}
<br/>


### Touch Prediction 触控预测

Touch Prediction 的功能正如它的名字，也即预测后续触摸点的大致走向。

{% highlight swift %}
for touch in touches {
	let line = lineForTouch(touch)
	for predictedTouch in event.predictedTouchesForTouch(touch) {
	   addTouchSample(predictedTouch, toLine: line)
	}
}
{% endhighlight %}
<br/>

<center>Powered by Meniny</center>
<center>Contact <Meniny@qq.com></center>


