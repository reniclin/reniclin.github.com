---
layout: post
title: "Clojure proxy vs reify"
date: 2012-12-12 14:10
comments: true
categories: clojure
---
## Clojure的proxy和reify
<br />

<!-- more -->

這個問題是在用Clojure + awt/swing開發GUI程式時遇到的，

######（為什麼用awt/swing而不用 [seesaw](https://github.com/daveray/seesaw) ？因為我要用到SystemTray， seesaw沒有wrapper它，加上我的程式很小。）


用到像是```JButton```這種元件時，常會需要用```addActionListener```method 來 add```ActionListener```。

<br />
##### Java的寫法如下：

{% codeblock lang:java %}
myJButton.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent e) {
        // do something here
    }
});
{% endcodeblock %}

<br />
### 在Clojure中有兩種寫法，分別是用```proxy```和```reify```。

### proxy

{% codeblock lang:clojure %}
(.addActionListener my-jbutton
                    (proxy [ActionListener] []
                      (actionPerformed [evt]
                        ;; (do something here)
                        )))
{% endcodeblock %}

### reify

{% codeblock lang:clojure %}
(.addActionListener my-jbutton
                    (reify ActionListener
                      (actionPerformed [this evt]
                        ;; (do something here)
                        )))
{% endcodeblock %}

<br />

###### ```proxy```和```reify```一般都是用在實作interfaces，參考網路上的幾篇文章，講到平常大部份都使用時都用```reify```就好，

###### 除了一些特別的用途才用```proxy```。（ig. override base class methods）

#### 很大概的找一下資料，要再更深入研究一下```proxy```和```reify```的異同和主要用在哪些不一樣的地方。

<br />
### 參考
*  [Why should I use Reify instead of proxy in clojure?](http://stackoverflow.com/questions/5821892/why-should-i-use-reify-instead-of-proxy-in-clojure)
*  [How reify works, and how to write a custom type](http://pepijndevos.nl/how-reify-works-and-how-to-write-a-custom-typ/index.html)
