---
layout: post
title: "Clojure building standalone jar with leiningen"
date: 2012-07-23 21:26
comments: true
categories: clojure leiningen jar
---
## 使用leiningen把clojure project打包成可以獨立執行的.jar檔

<!-- more -->

前陣子在使用 seesaw 寫 desktop app，遇到想把所有 source code build 成單一執行檔的需求，
使用 leiningen，可以輕鬆把你的 source 和其它的 dependencies 包成一個可單獨執行 standalone 的 jar。

* 在宣告ns時要加上 (:gen-class)，例如：

{% codeblock lang:clojure %}
(ns my-namespace.core
  (:import [java.util Calendar])
  (:use seesaw.core
        seesaw.graphics)
  (:gen-class))
{% endcodeblock %}

* 在project.clj裡加上 :main，例如：

{% codeblock lang:clojure %}
(defproject my-project "1.0.0-SNAPSHOT"
  :description "This is my clojure project"
  :dependencies [[org.clojure/clojure "1.3.0"]
                 [org.clojure/core.match "0.2.0-alpha9"]
                 [seesaw "1.2.2"]]
  :main my-namespace.core)
{% endcodeblock %}

* 使用 leiningen 產生 jar

     $ lein uberjar

* 執行

     $ java -jar my-project-1.0.0-SNAPSHOT-standalone.jar

