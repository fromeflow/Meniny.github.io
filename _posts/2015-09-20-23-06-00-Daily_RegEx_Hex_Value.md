---
layout: post
category: "regex"
title: "Daily RegEx: Hex Value"
tags: [RegEx]
summary: "Daily RegEx: Hex Value"
---
###表达式:

	/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/
	
###构造描述:

* `^`  
* `?`  
* `#`  
* `(`  
* `{6}`  
* `[A-Fa-f0-9]`  
* `|`  
* `{3}`  
* `[A-Fa-f0-9]`  
* `)`  
* `$`  

###可以匹配:

	#a3c113

###不可匹配:

	#4d82h4

