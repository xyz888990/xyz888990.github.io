---
layout: post
title:  "WhaleCTF之栅栏加密Writeup!"
date:   2018-11-11 17:30:54
categories: CTF WhaleCTF
tags: CTF 栅栏 加密
excerpt: 我家篱笆旁的栅栏被捣乱了！第一根和第二根都被换了位置····
---

# WhaleCTF 之栅栏加密


## 题目：

>我家篱笆旁的栅栏被捣乱了！第一根和第二根都被换了位置····
>只有第三根还能站在那，却也短了一截了。
>变成了这样：
>udJZml2VYVuWkdxXXs2Ne1DV5V9XEs2ZdZ7WlSNbVrm9eNDSlaFXG91F
>
>谁能帮我修好呢？ flag格式： venusCTF{xxx}

## 题解：
（我觉得这题出的不好，最后再讨论怎么不好）

按照提示，这是一道栅栏加密的题目，而且是三道栅栏

* 每三个一组，列出栅栏
```
udJ
Zml
2VY
VuW
kdx
XXs
2Ne
1DV
5V9
XEs
2Zd
Z7W
lSN
bVr
m9e
NDS
laF
XG9
1F
```

* 第一列与第二列互换（第三列正好短1，与题目相符），一列一列的摘取还原原文，重新拼接得到：
>dmVudXNDVEZ7SV9DaGFuZ2VkX215X2ZlbmNlX1JlYWxseV9sdWNreSF9

* [base64解密](http://ctf.ssleye.com/base64.html)得到flag:
>venusCTF{I_Changed_my_fence_Really_lucky!}

## 疑问

好了，说说为什么不合理，一家之言，大家讨论。
假如字串为：
>I am the King of the World

按照[栅栏加密](https://en.wikipedia.org/wiki/Rail_fence_cipher)原理：
```
I.......h.......n.......t.......o.......     
..a...t...e...i...g...f...h...W...r...d.
....m.......K.......o.......e.......l...
```
三个栅栏，分别是

>Ihnto<br>
>ateighfWrd<br>
>mKoel    

明显第二个栅栏要长于另外两个。

所以，我认为此题有些许不妥，或者表述不准确。

## 引申
在线栅栏解密：
[http://ctf.ssleye.com/railfence.html](http://ctf.ssleye.com/railfence.html)


