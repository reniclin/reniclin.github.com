---
layout: post
title: "Clojure Read a File as a Sequence of Lines"
date: 2012-12-11 09:04
comments: true
categories: clojure
---
## Clojure把檔案逐行讀成sequence

<!-- more -->

Clojure (Lisp) 常用到sequence，讀檔時也可以把檔案逐行讀成sequence：

{% codeblock lang:clojure %}
(line-seq (clojure.java.io/reader (clojure.java.io/file "file-path")))
{% endcodeblock %}

讀出來的東西類似像這樣：

{% codeblock lang:clojure %}
("line-1" "line-2" "line-3" "line-4" "line-4")
{% endcodeblock %}

讀成sequence之後就可以用doseq之類方便處裡sequence的macro來操作它，例如：
{% codeblock lang:clojure %}
(doseq [line (line-seq (clojure.java.io/reader (clojure.java.io/file "file-path")))]
  (println line))
{% endcodeblock %}