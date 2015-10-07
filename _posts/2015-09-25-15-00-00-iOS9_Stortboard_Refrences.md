---
layout: post
category: "ios"
title:  "iOS 9 : StoryBoard Refrences"
tags: [iOS,StoryBoard Refrences,StoryBoard]
---
除了前面 ***iOS 9 适配*** 系列中提到的 [***URLSchemes***](http://www.meniny.cn/2015/09/18/23-08-00-iOS9_URLScheme/)、[***Bitcode***](http://www.meniny.cn/2015/09/18/23-07-00-iOS9_Bitcode/)、[***ATS***](http://www.meniny.cn/2015/09/18/23-06-00-iOS9_ATS/) 和 [***后台定位***](http://www.meniny.cn/2015/09/25/14-00-00-iOS9_Location/) 之外，iOS 9 还对另外一个常用的工具——`StoryBoard` 做了一些改进。

在 iOS 9 之前，苹果虽然大力推广 `StoryBoard`，但在实际使用过程中还是有不少的坑。从 iOS 9 开始，苹果引入了 `StoryBoard Refrences` 概念为我们填坑，希望 `StoryBoard` 能扮演更重要的角色。

### 什么是 StoryBoard Refrences

在没有这个概念之前，如果你在 `StoryBoard` 中创建较为复杂的界面或数量众多的控制器，你很快就会发现它变得越来越难以管理，于是很多人选择创建多个 `StoryBoard`，但这也意味着要额外写很多代码。`StoryBoard Refrences` 概念的引入，意味着你可以从 `segue` 中引用其他 `StoryBoard` 中的控制器，带来的开发和管理效率的提升不言而喻。

### 旧的 StoryBoard 如何适配

如果你已经有了一个使用 `StoryBoard` 的项目，而且你希望使用 `StoryBoard Refrences`，那么你只需要在旧的 `StoryBoard` 中选中你想要提取(到其他 `StoryBoard`) 的控制器，在菜单栏中依次选择 `Editor` => `Refactor to Storyboard`，按提示输入目标 `StoryBoard` 的名称并确认保存即可，新的 `StoryBoard` 会自动创建并导入项目，而旧的 `StoryBoard` 中指向该控制器的箭头将指向一个 `StoryBoard` 标识。

![sbr](http://cc.cocimg.com/api/uploads/20150916/1442385811578426.png)

### 如何指向另一个 StoryBoard 中的控制器

事实上如果你细心，你会发现 `StoryBoard Refrences` 就在 Xcode 右侧 `Utilities` => `Object Library` 中。

使用起来也很简单:

* 打开目标控制器所在的 `Storyboard` 

* 在目标控制器的 `Attributes Inspector` 中设置其 `Storyboard ID`  

* 拖动一个 `StoryBoard Refrences` 到已有的 `StoryBoard` 中  

* 选中该 `StoryBoard Refrences` 并进入 `Attributes Inspector` 一栏  

* 将 `StoryBoard` 属性设置为目标控制器所在的 `StoryBoard`

* 将 `Referenced ID` 属性设置为目标控制器的 `Storyboard ID`  

* 连线到 `StoryBoard Refrences`


### 参考资料

更多相关内容可以参考 [***WWDC 视频***](https://developer.apple.com/videos/wwdc/2015/?id=215)

