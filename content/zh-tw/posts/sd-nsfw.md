---
title: Stable Diffusion 產出色圖筆記
subtitle: 密碼是 SD-NSFW-FURRY 轉成小寫
date: 2024-05-14T23:05:58+08:00
slug: 093cd2e
draft: false
author:
  name: blusewill
  link: https://blusewill.us.to/
  email: blusewillstuTotofox-shirtless.jpegdio@protonmail.com
  avatar:
description: 小品的瑟瑟 AI 筆記簿
keywords:
comment: true
weight: 0
tags:
  - Stable Diffusion
  - NSFW
  - Audlt Only
categories:
  - AI
  - Stable Diffusion
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRss: false
hiddenFromRelated: false
summary:
toc: true
repost:
  enable: false
  url:
password: sd-nsfw-furry

# See details front matter: https://fixit.lruihao.cn/documentation/content-management/introduction/#front-matter
---

<!--more-->

# 未滿 18 歲請離開現場，這邊是我的 Stable Diffusion 1.5 模型筆記。專門在講色圖我的產生方法，會介意的也請迴避摟！



最近重灌 Windows 過後，不知道看到空出來的 C 槽都會給我要把它填滿的想法 (這是什麼起怪的癖好....) 所以就打算來玩玩看 Stable Diffusion。

然而就這樣玩了一個禮拜，就被許多人說產的很不錯？(到底是為什麼

因此，我打算來寫筆記分享一下我的產圖方法！(當然因為網站會放到Github的原因，我就不放色圖了XDD)



## 一切都從準備開始

我自己用的模型是 [Indigo Furry mix - v115_anime | Stable Diffusion Checkpoint | Civitai](https://civitai.com/models/34469?modelVersionId=357362)

然後 UI 採用的是 [Easy Diffusion](https://easydiffusion.github.io/)

Easy Diffusion 預設安裝的時候會安裝很多預設的模型，設定起來會比 A111 還要簡單一些



## 如何脫衣服？

我自己脫衣服的時候我會打 Shirtless.

但是這個有時候產出來會有問題，像是我當時幫托托產生的這一張圖，就有要脫不脫的感覺。

![](../../img/SD/Totofox-shirtless.jpeg)



Prompt :

`Cat that looks like Fox, Fat, ((Full White Body)), blue khaki pants, happy, Short, solo, black ear, 2 White Tails, shirtless _hyaku`

Configuration :

**Seed:** 3777894087, 

**Dimensions:** 448x640, 

**Sampler:** euler, 

**Inference Steps:** 25, 

**Guidance Scale:** 7.5, 

**Model:** indigoFurryMix_v115Anime, 

**Negative Prompt:** nsfw, 

**Fix Faces:** GFPGANv1.4, 

**Upscale:** RealESRGAN_x4plus (4x)



但是最近發現只要打 Topless 就可以直接把衣服脫掉了，而且是全脫的那種



![](../../img/SD/Totofox-topless.jpeg)



Prompt :

`Cat that looks like Fox, Fat, ((Full White Body)), blue khaki pants, 
happy, Short, solo, black ear, 2 White Tails, topless _hyaku`



Configuration :

**Seed:** 3777894087, 

**Dimensions:** 448x640, 

**Sampler:** euler, 

**Inference Steps:** 25, 

**Guidance Scale:** 7.5, 

**Model:** indigoFurryMix_v115Anime, 

**Negative Prompt:** nsfw, 

**Fix Faces:** GFPGANv1.4, 

**Upscale:** RealESRGAN_x4plus (4x)



## 如何整隻肉棒塞進去！

這個就好玩了，到底要玩到什麼程度才會這樣呢？

這個比較特別的地方是要使用一個關鍵字，`deep throat`

那我不太會去說他的意思，有興趣自己去查看看。

那重要的第二點就是一定要打雙人，如果不打雙人的話很容易出來很神奇的成果。（因為我打文章測試的時候）就有出現神奇的結果。

那關於這個關鍵字我是建議越後面打越好，因為打在前面有可能會出事。
