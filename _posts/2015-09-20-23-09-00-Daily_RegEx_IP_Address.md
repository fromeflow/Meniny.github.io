---
layout: post
category: "regex"
title: "Daily RegEx: IP Address"
tags: [RegEx]
summary: "Daily RegEx: IP Address"
---
###表达式:

	/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/ 

###可以匹配:

	123.45.67.89

###不可匹配:

	256.45.67.89

