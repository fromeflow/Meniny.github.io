---
layout: post
category: "php"
title:  "PHP 与 RegEx 浅析 002: preg_match()"
tags: [PHP,RegEx]
summary: "PHP 与 RegEx 浅析 002: preg_match()"
---
本文主要介绍函数 `preg_match()` 的语法、参数、返回值以及使用方法和范例。  
  
<table border="1" class="table table-bordered table-striped table-condensed">
<tr>
<th>格式</th>
<th colspan="2"><code>preg_match(pattern,  subjevt[, match[, flags [, offset]]])</code></th>
</tr>
<tr><th rowspan="5">参数</th>
<th>pattern</th><th>用分隔符包围的正则表达式，可能出现修饰符</th></tr>
<tr><th>subject</th><th>需要搜索的目标字符串</th></tr>
<tr><th>match</th><th>用来接收匹配数据，可省略</th></tr>
<tr><th>flags</th><th>只允许出现标志位 <code>PREG_OFFSET_CAPTURE</code>，可省略</th></tr>
<tr><th>offset</th><th>从 <code>0</code> 开始，表示匹配尝试的开始位置，可省略</th></tr>
<tr><th>返回</th><th colspan="2">如果找到匹配返回 <code>ture</code>，否则返回 <code>false</code></th></tr>
</table>


