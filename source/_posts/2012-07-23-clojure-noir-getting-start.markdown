---
layout: post
title: "Clojure noir getting start"
date: 2012-07-23 21:37
comments: true
categories: clojure leiningen noir
---
## 使用leiningen建立新noir專案

<!-- more -->

noir是一套很好用的clojure web frameworks，紀錄一下安裝leiningen noir plugin的方法，
和如何使用leiningen建立一個新的noir專案，使用leiningen一樣簡單，不過leiningen 1.x
和leiningen 2.x 步驟有點不一樣，要注意一下。

### lein 1.x

* 安裝 leiningen noir plugin

{% codeblock lang:bash %}
$ lein plugin install lein-noir 1.2.1
{% endcodeblock %}

* 建立一個新的 noir 專案

{% codeblock lang:bash %}
$ lein noir new my-web
{% endcodeblock %}

* cd 到剛剛建出來的資料夾

{% codeblock lang:bash %}
$ cd my-web
{% endcodeblock %}

* 試跑一下

{% codeblock lang:bash %}
$ lein run
{% endcodeblock %}

* 成功跑起來之後可以用瀏覽器打開 http://localhost:8080 就可以看到歡迎畫面。


### lein 2.x 的步驟比較簡單，不用先裝 plugin

* 建立一個新的 noir 專案

{% codeblock lang:bash %}
$ lein new noir my-web
{% endcodeblock %}

* cd 到剛剛建出來的資料夾

{% codeblock lang:bash %}
$ cd my-web
{% endcodeblock %}

* 試跑一下

{% codeblock lang:bash %}
$ lein run
{% endcodeblock %}

* 成功跑起來之後可以用瀏覽器打開 http://localhost:8080 就可以看到歡迎畫面。
