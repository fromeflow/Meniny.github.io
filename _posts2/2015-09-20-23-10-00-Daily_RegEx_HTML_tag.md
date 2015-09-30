---
layout: post
category: "regex"
title: "Daily RegEx: HTML Tag"
tags: [RegEx]
summary: "Daily RegEx: HTML Tag"
---

	/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/ 

###匹配示例:

	<a href="http://www.meniny.cn/">Meniny+</a>

###错误示例:

	<img src="img.jpg" alt="Some image>" />

