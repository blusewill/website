---
title: 我如何直播戶外台？
subtitle: 直播戶外台全部的方法，為什麼我不用了？現在的方法是什麼？
date: 2026-11-18T11:24:29+08:00
lastmod: 2026-11-18T11:24:29+08:00
slug: 785489e
draft: false
author: 
  name: blusewill
  link: https://blusewill.top/
  email: owner@blusewill.top
  avatar: 
description:
keywords:
comment: true
weight: 0
tags:
  - OBS
  - Streamer
  - IRL
  - 工具
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

你想要嘗試看看開戶外台嗎？

很好奇我的戶外直播後台是什麼樣子嗎？

歡迎來到小品大大全部目前從 2024 的戶外台到目前全部使用的工具！

從最簡單的開台，到把他跟 OBS 串接，到現在嘗試降低延遲

我是怎麼做到的？這些東西要怎麼架設？最後要花多少錢？

<!--more-->

## 價格

讓我先來說價格，當然這篇文章大部分理論都會是**免費**的

但是有些工具的部分會需要一些成本，不管是學習還是購買伺服器的成本

但沒有關係，價格的部分我也會跟你介紹花了我多少錢！

## 最基礎的開始

當然，如果要講到最基礎不用花到任何錢的方式

當然還是直接從你的手機開台！讓你的手機直接投到 Twitch 或是 YouTube 這些平臺！

那這邊我最推薦的直播軟體是 [IRL Pro](https://play.google.com/store/apps/details?id=app.irlpro.android&hl=zh_TW) 我自己平時都是使用這個直播工具開台！

![IRL Pro UI](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-103858.webp)

這個是目前 Android 市場裡面你可以找到功能最多也最沒有限制的直播軟體！

目前這個實況軟體他最好的是可以將很多的網路合起來製作出畫質提升！

還有在畫面顯示放上不同的 Overlay 還有很多等等的功能！

那當然如果你是 iPhone 的話可以嘗試看看 [Moblin](https://apps.apple.com/tw/app/moblin/id6466745933) 據說也有一樣的效果！

當然如果你只是臨時想要直播不想要設定這麼多麻煩的東西的話！

YouTube 跟 Twitch 都有內建直播的功能供你使用！

## 我想要認真了，但我沒有錢

好！接下來讓我們進入如果你想要認真的開戶外台了！

那接下來你就會想要將你的畫面接到 OBS 上面！

![OBS 範例畫面](/zh-tw/img/new-irl-streaming-announcement/Screenshot-2026-11-18-10-46-07.webp)

這樣子你就可以做到更多的事情，不管是 Overlay 的廣度

或是你會想要不會與 Twitch 跟 YouTube 斷線的畫面

那你會更想要這些東西！

那第一個是你家一定要有一個穩定的網路！這樣才可以一直直播

那第二個你會需要的是轉播程式了！

這邊最多人使用的是 [VDO.Ninja](https://vdo.ninja/) 

![VDO.Ninja 網站](/zh-tw/img/new-irl-streaming-announcement/vdo-ninja.webp)

第一個是因為他不用安裝任何程式，你只要做的是把他的網頁打開

然後在 OBS 上面使用瀏覽器瀏覽就好了！

![OBS Browser Source](/zh-tw/img/new-irl-streaming-announcement/obs64_9Yd8LpbG8Q.webp)

那如果你是直播會需要看 Twitch 聊天室的話！

不用擔心 VDO Ninja 的團隊早就幫你想好了！

只要到 https://vdo.ninja/twitch 就可以一邊直播一邊看聊天室了！

非常的簡單對吧！但這時候你就會遇到一個問題了

沒有畫面的時候要怎麼辦？我要怎麼在戶外操作我的 OBS

### 自己可以用的導播板！

沒錯！因為這問題我也都有遇到，所以我自己也會需要一個導播板！

這時候你就會用到 Streamer.bot 跟 Streamer.bot Decks

![Streamer.bot](/zh-tw/img/new-irl-streaming-announcement/Streamer.bot_d7PYXb1Ugs.webp)

那如果你平時就有在看我網站的話應該就會知道 Streamer.bot 這個東西了！

因為我為了他寫了很長很長的教學文章！甚至到今天我依舊在使用 Streamer.bot！

而我平時會用到的就是 Streamer.bot Decks

因為他可以控制我目前的直播畫面，相機特效，還有開關直播等東西！

![Streamer.bot Decks](/zh-tw/img/new-irl-streaming-announcement/librewolf_n1KUaRlV9W.webp)

而且這個東西是免費的！你只需要登入你的 Streamer.bot 帳號在你的 Streamer.bot 上面

這樣就可以透過第二台手機來遠端控制你的 OBS 了！

你看完之後想要去看看的話，可以點擊以下連接去看看喔！

https://blusewill.top/zh-tw/posts/ea7ec9c/

那當然如果你想要更技術一點的話，你也可以使用 [Tailscale](https://tailscale.com/) 或 [Headscale](https://headscale.net/stable/) 建置 VPN 的形式來連到家裡的 OBS Websocket

我這邊有用過的是 [OBS Controller](https://play.google.com/store/apps/details?id=se.erikfahlen.obscontroller)

可以透過手機來連線進入 OBS Websocket 來控制自己的 OBS

![OBS Controller](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-105546.webp)

兩種都是不錯的方法！

### 為什麼不用？

你會想說，我剛剛講了 VDO.Ninja 不是很好嗎？

為什麼還會有這一區？

那肯定是因為 VDO.Ninja 還是有一些我不喜歡的地方

1. 畫質太差了：

我有時候會用到 VDO.Ninja 來臨時當作我的鏡頭來用。

雖說他的延遲很低但是他的畫質也同時是最差的。

這你可以在我的 2026 獸無限影片回顧裡面看到

{{< youtube xGLNxBYR9YM >}}

其中就有拿 VDO.Ninja 拿來當鏡頭的後果！真的很糊！

2. 手動導播：

有時候其實是想要關掉畫面不想要手動換畫面的，或是可能手機沒電或忘記了！

那大家就會待在 IRL 的畫面裡面，不會被丟到掛機房

3. 難用的 UI

如果我不在網址裡面固定解析度的話，我都要手動調整解析度

但解析度不知道為什麼那個拉桿極度難調，有時候還會自己縮回去！

![VDO.Ninja Setting](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-110020.webp)

也就是因為以上這三點，讓我還是不用 VDO.Ninja 了

他只存活於兩次的 IRL 直播！

2025 台北的同志大遊行跟 2025 獸無限直播！

之後就改用其他方式了！

## 我想要認真了，且我有一點點錢

好，剛剛介紹完了不用錢的！那你們一定會好奇那如果我每個月課金一點點可以獲得什麼直播體驗？

那就歡迎來到第二章，轉播伺服器 + 全自動導播系統

我已經這樣開了一整年了！

今年 2026 全部的獸展，還有自己線下直播其實都是用他開的！

剛剛講了三個 VDO.Ninja 的缺點，那接下來我剛剛提到全部的問題在接下來都不會發生！

且這個是目前許多國外實況主採用的直播方式！那就是透過 SRTLA 伺服器轉發！

你一定會很好奇！很多人在用是哪些人在用？

讓我介紹一下使用這個架構直播的人：

[Elijah](https://www.twitch.tv/bocabola) 前 Linus Tech Tips 員工！去年的時候自己製作的同樣架構的直播背包！

[企鵝妹](https://www.twitch.tv/jinnytty) 韓國 IRL 實況主！採用現成的同樣架構 LiveU 背包方案

這些人都是採用類似的架構進行直播！

那你問我為什麼要這樣直播呢？因為這樣才可以提供最好的畫質給觀眾！

但這時候你就會發現，他們用的不是樹莓派就是超級貴的商業方案

而且你在整我吧，要我自己去製作一個背包然後往裡面放路由器？

這樣更本一點都不輕量！感覺超級重！

但是沒有關係，畢竟誰說一定要透過本地處理呢？

當然也是可以透過其他地方的伺服器處理的！

我自己目前是使用 [Akamai Cloud](https://www.linode.com/lp/refer/?r=ef32bcb648b281045da1a3a61da944a31a81761c) 的最便宜 5 美金的日本伺服器方案

也就是 150 塊錢台幣的價格！經濟有夠實惠了吧？

那當然如果你有自己的伺服器的話，也可以使用自己的伺服器架設省下這個成本！

之後你會需要自己架設一個 Belabox 的伺服器

那這邊你可以採用 IRLServer 提供的伺服器檔案！

https://github.com/datagutt/bbox-receiver

只需要將 Git Clone 下來，用裡面的 Docker Compose 檔案啟動就可以獲得 SRTLA 的伺服器！

當然，你還是會需要在 config.json 裡面進行設定密碼的動作！

這會非常重要！畢竟你應該不會想要讓任何人使用你自己的轉播伺服器吧？

> 如果你不想要設定伺服器的話，你也可以採用 Belabox Cloud 的方案！
> https://cloud.belabox.net/

那都架設好了之後你就可以設定直播軟體了！

這時候你就會需要找到一個可以直播 SRTLA 的，可以把網路連線聚合在一起的程式

沒錯！就是我們剛剛提到的 IRL Pro 跟 Moblin

他們一出生其實就是拿來直播這種架構了！所以直接無痛使用！

你只要在 Connection 的面板新增一個連線

輸入 srtla://<IP>:<端口>

下面就會有更多的選項！

這邊主要是要看的是 streamid

你這邊會需要輸入

live/<直播ID>?srtauth=<直播密碼>

![SRT IRL Pro](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-110248.webp)

這樣你的直播就設定完成了！

而且不會有任何的適應期！非常的棒！

那在 OBS 裡面，你會需要創建一個媒體來源

將上面的本機檔案取消勾選

將來源輸入 srt://<IP>:<端口>/?streamid=play/<直播ID>?srtauth=<直播密碼>

然後格式輸入 `mpegts` 就可以解決了！

![OBS SRT Setting](/zh-tw/img/new-irl-streaming-announcement/obs64_BeryxWg4Cg.webp)

### 自動化導播系統！

竟然都換到 SRTLA 直播了，怎麼能不談談他最好用的東西呢？

自動的導播系統！

因為這直播方式也已經夠成熟了，所以自然的就會有很多的系統

像是自動換場景這類的導播系統也是有的！

這時候最多人用的方案會是 [NOALBS](https://github.com/NOALBS/nginx-obs-automatic-low-bitrate-switching) 可以自動的切換場景！

![NOALBS](/zh-tw/img/new-irl-streaming-announcement/noalbs_heu3n567SZ.webp)

同時也可以在 Twitch 聊天室說明目前的場景切換，與使用聊天室指令切換場景！

但因為他的設定太過於麻煩，所以 IRLHosting 有做一個生成器可以去用看看！

https://irlhosting.com/noalbs/

### 為什麼不用了？

其實最更本的缺點只有一個，那其實就是延遲太高了

沒錯！延遲太高導致我要跟聊天室互動的時候更本無法互動

雖說延遲只有 0.5 ~ 1.5 秒的時間，不過還要在加上傳到 Twitch 與 YouTube 的時間

![SRT Latancy](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-110912.webp)

其實已經過了大約 3 ~ 4 秒，也就是說觀眾看到我的畫面其實已經是 3 ~ 4 秒前的畫面了

這樣其實是合格的，對於一般實況台來說延遲高觀眾也看不出來！

且 IRL 不一定是要跟觀眾互動，基本都是跟真人互動！

所以對於很多人來說沒有差別，但對我來說就有！

我的觀眾每次都會看到 IRL 的延遲過高然後超生氣 XD

都沒有辦法在獸展認親，讓觀眾們很難過！

所以為了迎合觀眾，就來到了現在，也就是這篇文章的核心

## 我需要測試員

沒錯！如果你是跟我一樣開 IRL 的實況主！

我最近正在研究 Media Over QUIC 簡稱 MoQ 的架構！

但這個架構目前還在 Beta 

OBS 本身也不支援，需要額外安裝插件

但這個架構經過測試看起來畫質雖說沒有比 SRT 還要好，但是比 WebRTC 好多了

目前想要找一些測試員來幫我測試這個新的直播工具！

他目前的延遲是毫秒級別，大概是 100ms 左右

![SRT Latancy](/zh-tw/img/new-irl-streaming-announcement/Screenshot-2026-11-18-10-11-00.webp)

如果想要看實際效果的話，可以看這個紀錄檔！

{{< youtube r-MkZSnCDzQ >}}

當然還有很多 BUG 會需要修復，所以最近可能會開很多 IRL 台？

像是聲音畫面不同步的問題阿，Audio Buffer 等等的問題都需要修復！

所以想要看 Live Action 的話可以到我的 [Twitch](https://twitch.tv/blusewill) 來看看

那如果你也想要測試的話，歡迎郵寄到我的 [Email](mailto:owner@blusewill.top) 來談看看合作的部分！

那你問我，要付錢嗎？

那為了不要讓我自己又進入不開心的時期，對不起我要收錢。

當然現在如果你想要嘗試看看 EA 的話，現在是最便宜的時機！

只需要 300 塊錢，你就可以把這個程式終生帶回家。

當然是只有這個程式，如果你有想要導播程式的話我寫好之後只需要 200 塊

我就可以把導播程式一起給你！

因為我不想要只有我自己在測試，這樣我完全會不知道這程式還有什麼問題

尤其是 Android 端，因為 Android 端是 AI 寫的，不是我自己寫的

![Android Client](/zh-tw/img/new-irl-streaming-announcement/Screenshot_20261118-111226.webp)

所以問題可能會很多，就只能請你們幫我測試啦！

那當然影像傳輸可以透過 [moq.pro](https://moq.pro/) 或是 Cloudflare 的 MoQ Relay 系統來轉發喔！

## 未来

那這就是我三年下來全部使用的工具了，你問我還會在換新嗎？

可能會，也有可能不會！

如果有更成熟的架構出來且可以有畫面好延遲低的方案

我也有可能會去研究看看！

那這就是小品大大！我們下一篇文章見啦！
