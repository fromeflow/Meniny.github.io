---
layout: post
category: "scheme"
title:  "Scheme 字符串操作总结"
tags: [Scheme]
summary: "Scheme 字符串操作总结"
---
字符串操作是任何一门编程语言中最常用的操作之一，Scheme 也提供了一系列 `procudure` 来操作字符串。

1、字符串的比较，分别有`string=?`、`string>?`、`string<?`、`string>=?`、`string<=?`。

这与其他语言中对 `string` 的比较并无不同，比较字符和长度。

例子:

{% highlight scm %}
(string=? "mom" "mom") <graphic> #t
(string<? "mom" "mommy") <graphic> #t
(string>? "Dad" "Dad") <graphic> #f
(string=? "Mom and Dad" "mom and dad") <graphic> #f
(string<? "a" "b" "c") <graphic> #t
{% endhighlight %}

注意这些比较操作是大小写敏感。相应的，大小写不敏感的版本:

{% highlight scm %}
procedure: (string-ci=? string1 string2 string3 ...) 
procedure: (string-ci<? string1 string2 string3 ...) 
procedure: (string-ci>? string1 string2 string3 ...) 
procedure: (string-ci<=? string1 string2 string3 ...) 
procedure: (string-ci>=? string1 string2 string3 ...) 
{% endhighlight %}
	
###2、从字符构造字符串，使用string过程

{% highlight scm %}
(string #\a)  => "a"
(string #\a #\b #\c)  => "abc"
{% endhighlight %}

注意换行字符是`#\newline` ,回车字符是`#\return`

###3、重复N个字符构造字符串
	
{% highlight scm %}
(make-string)  => ""
(make-string 4 #\a)  =>"aaaa")
{% endhighlight %}

###4、字符串长度 string-length

{% highlight scm %}
(string-length "") =>0
(string-length "dennis") => 6
{% endhighlight %}

###5、取第N个字符，相当于java中的charAt

{% highlight scm %}
(string-ref "hi there" 0) <graphic> #\h
(string-ref "hi there" 5) <graphic> #\e
{% endhighlight %}

###6、修改字符串的第N个字符

{% highlight scm %}
(string-Setter! "hello" 0 #\H) => "Hello"
{% endhighlight %}

###7、拷贝字符串

{% highlight scm %}
(let ((str "abc"))
  (eq? str (string-copy str)))  => #f
(let ((str "abc"))
  (equal? str (string-copy str)))  => #t
{% endhighlight %}

###8、拼接字符串，string-append

{% highlight scm %}
(string-append) => ""
(string-append "abc" "defg") => "abcdefg"
{% endhighlight %}

###9、截取子串

{% highlight scm %}
(substring "hi there" 0 1) <graphic> "h"
(substring "hi there" 3 6) <graphic> "the"
(substring "hi there" 5 5) <graphic> "" 
{% endhighlight %}

###10、填充字符串

{% highlight scm %}
(let ((str (string-copy "sleepy")))
  (string-fill! str #\Z)
  str) <graphic> "ZZZZZZ"
{% endhighlight %}

###11、与list的相互转换

{% highlight scm %}
(string->list "") <graphic> ()
(string->list "abc") <graphic> (#\a #\b #\c)
	
(list->string '()) <graphic> ""
(list->string '(#\a #\b #\c)) <graphic> "abc"
(list->string
  (map char-upcase
       (string->list "abc"))) <graphic> "ABC"
{% endhighlight %}


