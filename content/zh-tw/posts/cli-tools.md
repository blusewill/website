---
title: 好用的終端機工具筆記 （持續更新中）
subtitle:
date: 2024-05-19T21:09:57+08:00
slug: 6adac2b
draft: false
author: 
  name: blusewill
  link: https://blusewill.us.to/
  email: blusewillstudio@protonmail.com
  avatar:
description:
keywords:
comment: true
weight: 0
tags:
  - Windows
  - Linux
  - CLI
  - 終端機
categories:
  - 小品的筆記簿
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRss: false
hiddenFromRelated: false
summary:
toc: true
repost:
  enable: false
  url:

# See details front matter: https://fixit.lruihao.cn/documentation/content-management/introduction/#front-matter
---

<!--more-->

Linux 一定不能跑離終端機，Windows 的 Powershell 也很強大。

但是就是有一些小小的工具，用文章寫不太出來。

這個筆記簿就是給我筆記用，也讓你們大概知道 Linux 中的一些小工具們

## duf 更好的 df

df 是大家有時候要查看自己容量的工具。

但是顯示的內容通常都是以 bytes 顯示

就算你是用 df -h 也很難說你剩下的容量

![上面是 df 下面是 df -h](../../img/Linux-cli-tools/df.png)

這時候 duf 就出現了，duf 可以顯示出彩色的樣式

加上幫你分出什麼是什麼分區等等的

![duf](../../img/Linux-cli-tools/duf.png)

對與查看系統空間還是很有用的！

duf 的 [GitHub](https://github.com/muesli/duf)

## ncdu / gdu 查看資料夾用量

用 Windows 的一定都聽過 WizTree 這個可以告訴你那裡是使用最多空間的地方

![WizTree](../../img/Linux-cli-tools/wiztree_treeviewwithmap3.jpg)

那今天你在 cli 也想要做一樣的事情，ncdu 跟 gdu 就可以幫忙到你了

ncdu 跟 gdu 功能都是一樣的，可以看出你的不同資料夾的大小

不同的就是，ncdu 不會有其他顏色

gdu 會分不同的顏色來區分內容

![ncdu](../../img/Linux-cli-tools/ncdu.png)

![gdu](../../img/Linux-cli-tools/gdu.png)

要刪除檔案就是按下 `d` 就可以刪除了

然後按下 `Esc` 退出

那就兩個都推薦給大家摟！

ncdu 的 [官網](https://dev.yorhel.nl/ncdu)

gdu 的 [GitHub](https://github.com/dundee/gdu)