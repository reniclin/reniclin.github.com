---
layout: post
title: "ClojureScript method call and property access syntax"
date: 2012-08-17 21:35
comments: true
categories: clojurescript
---
## ClojureScript 呼叫物件 method 和存取物件 property 語法

<!-- more -->

ClojureScript 呼叫物件method和存取物件property的語法有點特別，做個紀錄備忘一下。

### Calling a method

{% codeblock lang:clojure %}
(. js-object method)
{% endcodeblock %}

{% codeblock lang:clojure %}
(. js-object method args)
{% endcodeblock %}

or

{% codeblock lang:clojure %}
(.method js-object)
{% endcodeblock %}

{% codeblock lang:clojure %}
(.method js-object args)
{% endcodeblock %}

### Accessing a property

{% codeblock lang:clojure %}
(. js-object -property)
{% endcodeblock %}

or

{% codeblock lang:clojure %}
(.-property js-object)
{% endcodeblock %}

#### 比較需要記住的是 property 名字前面需要加一個 - 號。
