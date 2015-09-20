---
layout: post
category: "regex"
title: "Daily RegEx: E-mail"
tags: [RegEx]
summary: "Daily RegEx: E-mail"
---
###表达式:

	/^([A-Za-z0-9_\.-]+)@([\dA-Za-z\.-]+)\.([A-Za-z\.]{2,6})$/ 

###可以匹配:

	Meniny@qq.com

###不可匹配:

	Meniny@qq.somethingtoolongohitssolong

