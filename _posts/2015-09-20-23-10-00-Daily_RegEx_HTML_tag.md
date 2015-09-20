---
layout: post
category: "regex"
title: "Daily RegEx: HTML Tag"
tags: [RegEx]
summary: "Daily RegEx: HTML Tag"
---
###表达式:

	/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/ 

###可以匹配:

	<a href="http://www.meniny.cn/">Meniny+</a>

###不可匹配:

	<img src="img.jpg" alt="Some image>" />

