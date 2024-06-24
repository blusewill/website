---
title: Twitch 實況主必學！將音樂從 VOD 分開！
subtitle:
date: 2024-06-23T00:49:40+08:00
slug: 6e86ed2
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
  - Twitch
  - OBS
  - Streamer
categories:
  - 直播工具教學
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

有時候有沒有想說在 Twitch 直播的時候播放音樂，但是直播結束之後整個片段都被靜音了呢？

我非常的討厭這件事情，所以今天我要教你如何設定 VOD Track 將音樂從 VOD 中分開！

## 前製作業 (分軌)

首先要做的事情就是把我們的聲音分開拉！

不用擔心，這對大部份人來講都不會太難

### Windows

首先第一件事情，我們要先下載一個 OBS 插件叫做 [win-capture-audio](https://obsproject.com/forum/resources/win-capture-audio.1338/) 那當然你也可以用內建的音效擷取，但是我習慣使用這個了。

安裝完成之後打開我們的 OBS 添加一個叫做 **"應用程式輸出擷取"** 的來源

![應用程式輸出擷取](../../img/vod-track/add-source-windows.png)

之後我們就可以在下面選擇我們的程式，然後讓它輸出到音軌裡面

![應用程式輸出擷取設定](../../img/vod-track/audio-capture-config.png)

那就這樣創建不同的音軌，之後去設定把桌面音效調整成無

![桌面音效調整成無](../../img/vod-track/desktop-audio-null-win.png)

這樣我們的分軌就設定好了！

### MacOS

我這邊沒有 MacOS 的裝置，但是基本上大同小異

這邊給予兩個程式給有 MacOS 的人研究 [BlackHole 2ch](https://rogueamoeba.com/loopback/) 還有 [Loopback](https://existential.audio/blackhole/)

### Linux

那如果你是 Linux 的話，PulseAudio 可以幫你做出分軌，可以點擊這個連結看一下我設定的腳本

https://github.com/blusewill/bash-script/blob/main/Streamaudio/audio-setup.sh

之後我們就可以在音效設定要分配到那一個分軌，我這邊是用 PulseAudio Volume Control `pavucontrol`

![pavucontrol](../../img/vod-track/pavucontrol.png)

之後我們在新增擷取音效輸出分別給不同的分軌就可以成功分軌了！

![新增擷取音效輸出](../../img/vod-track/audio-capture-linux.png)

那接下來就是一樣，去設定把桌面音效設定成無！

![Linux OBS 音效設定](../../img/vod-track/audio-setting-linux.png)

Linux 這邊的分軌也就設定好了歐，是時候來設定 VOD 分軌了！

## VOD Track 設定

那這個東西是 **僅限 Twitch 平台** YouTube 等等平台都沒有支援。

我們要到設定裡面的輸出，然後將輸出模式改成進階

之後你會看到一個 **Twitch 視訊點播軌道** 這就是我們的 VOD Track 把它打勾之後就可以確定了

![輸出視訊範例圖](../../img/vod-track/obs-output-setting.png)

之後我們到音效混音器這邊，按下左下角的進階音訊屬性

![左下角的進階音訊屬性](../../img/vod-track/advanced-audio-config.png)

之後我們要到後面的音軌，然後如果你有不要的音軌的話，把音軌二的勾勾關掉，直播中就不會出現了！

![進階音訊屬性設定](../../img/vod-track/advanced-audio.png)

像是我這邊設定成 Music 不要在 VOD 中出現，我就把 Music 後面的音軌二關掉，這樣只有直播的時候會有聲音，然後在 VOD 的時候刪除這個分軌的所有聲音！

那這樣子就完全設定好拉！你現在直播應該是不會在被消音了呢！

希望這篇文章對 Twitch 直播主有所幫助，我們就下一篇文章見拉！

## VOD 有分軌的直播紀錄檔範例

你可以看到右上角有在播放音樂，但是影片卻非常的安靜，但是直播的時候是有音樂的

這個就是所謂的 VOD Track

{{< youtube _PDOtWpAWdQ >}}