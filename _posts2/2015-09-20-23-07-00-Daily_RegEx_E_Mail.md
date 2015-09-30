---
layout: post
category: "regex"
title: "Daily RegEx: E-mail"
tags: [RegEx]
summary: "Daily RegEx: E-mail"
---

	/^([A-Za-z0-9_\.-]+)@([\dA-Za-z\.-]+)\.([A-Za-z\.]{2,6})$/ 

###匹配示例:

	Meniny@qq.com

###错误示例:

	Meniny@qq.somethingtoolongohitssolong

