---
title: 不要打開 "BitLocker"
subtitle: 就算有，也請現在把他去關掉
date: 2025-09-29T01:38:54+08:00
lastmod: 2025-09-29T01:38:54+08:00
slug: 168939e
draft: false
author: 
  name: blusewill
  link: https://blusewill.top/
  email: blusewillstudio@protonmail.com
  avatar:
description:
keywords:
comment: true
weight: 0
tags:
  - Windows
  - BitLocker
  - 資訊安全
  - 漏洞
  - 資料保護  
categories:
  - Windows 類別
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

## 如何關閉 BitLocker

先不囉唆，馬上教你怎麼關閉 BitLocker

第一步要先看的是你有沒有開啟 BitLocker

我們可以看硬碟的圖示，當你看到有一個鎖頭在你的硬碟上，就代表你目前有啟用 BitLocker 了！

![alt text](../../img/bitlocker/757722dc-2db0-4882-8d92-7b307dd0f3a1.png)

> 來源 https://www.asus.com/tw/support/faq/1044341/

首先，到**設定搜尋裝置加密設定** (或是在搜尋也可以)

然後**關閉裝置加密**之後應該會跑一段時間

![alt text](../../img/bitlocker/disable-encryption.png)

> 來源 https://www.asus.com/tw/support/faq/1044341/

跑完沒有看到鎖頭就表示 BitLocker 已經成功關閉了！

就不需要擔心了

## 什麼是 BitLocker 為什麼要關掉它？

BitLocker 是一個可以加密硬碟的程式，在近期新的筆電都會預設是開啟。

當你的硬碟或是電腦被竊取的時候，就可以幫你把你的資料保護的好好的！

但是，通常都不是電腦被竊取的請況居多，通常都是你自己的電腦系統壞掉

然後就把自己的資料鎖了起來，然後通常也很難做恢復。

就連外面的電腦店**也有可能沒有辦法幫你修復 BitLocker 鎖住的問題！**

第二個就是 BitLocker 很容易因為**更新而壞掉**，所以可能某一次更新會伴隨著你的資料一起說再見！

最後就是 BitLocker 這個加密軟體呢，也是**目前漏洞最多的軟體**。

![alt text](../../img/bitlocker/MSRC-bitlocker.png)

> 來源 https://msrc.microsoft.com/update-guide/vulnerability

以目前來看，從 2025 年初開始計算下來，已經有 11 起 BitLocker 相關的漏洞了。

況且大多數都是資料被解密，所以這個**加密軟體**也沒有成功的達成他的本分

## 那？我要怎麼加密我的硬碟

這邊我推薦一個軟體，叫做 [VeraCrypt](https://veracrypt.io/en/Home.html)

之後會特別幫他寫出一篇文章，但是這個軟體的優點也很多。

而且這個是真的可以加密你的硬碟了，跟 BitLocker 不一樣。

加上他也對雙開機的系統也很友善，如果你有 Linux 跟 Windows 一起裝在你的電腦的話，也不會有任何問題。

就推薦給如果你需要加密硬碟的你拉！那我們就下一篇文章見！


<!--more-->
