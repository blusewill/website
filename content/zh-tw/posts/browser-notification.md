---
title: 網頁通知，一個被濫用的功能
subtitle: 
date: 2025-04-14T22:56:33+08:00
lastmod: 2025-04-14T22:56:33+08:00
slug: a3beafc
draft: true
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
  - 瀏覽器
  - Chrome
  - Firefox
  - Edge  
categories:
  - 影片不能全部提到的內容
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

今天讓我們來聊聊網頁通知！

這個時常被拿來濫用的功能。他到底是怎麼運作的。

那當然，一個 Shorts 不能解釋這麼多內容，所以如果以後想要第一時間觀看這些內容的話

歡迎訂閱我的 RSS 電子報來看更多有趣的文章 [點我訂閱](https://blusewill.us.to/zh-tw/index.xml)

好！廢話說到這邊，現在這邊就來跟你介紹網頁通知是怎麼被濫用的吧！

---

網頁通知可能很少有人知道是什麼，但是我只要放出一張圖片你就會知道是什麼東西了！

![Browser Notification](../../img/Browser-notification/Browser-Notification-Example.png)

沒錯，如果你有曾經按過允許的話，我相信你現在被通知所困擾。

我說的不是那種新聞電子報，我說的是類似這樣的東西

![](../../img/Browser-notification/Screenshot_win11-test_2025-04-14_01_13_38.png)

雖說他原本的利益是要取代 RSS 但是後面被變到這種地步，好像也不是好事

所以，這次想要教你如何永久刪除這些通知，加上他的原理是什麼

還有有一些網頁甚至能檢測你按了允許還是拒絕！？

這些都會在我們這次的文章節答！

## 如何移除

要移除這個很簡單，是 Chrome/Opera/Edge 的話就只要去以下連接

`about://serviceworker-internals/`

![](../../img/Browser-notification/ServiceWorker.png)

按下下面的 Unregister 直到這個畫面為空！

![](../../img/Browser-notification/ServiceWorker-0.png)

就刪除成功全部的通知了！

那如果你是手機板的話，你也可以這樣做！

手機一樣也有這個畫面！

![](../../img/Browser-notification/Android-google.png)

> 如果有刪不掉的話。可能是第三方擴充功能！

> 這時候就是要去，右上角清單、擴充功能、管理擴充功能進行刪除

那如果你是用 Firefox 的話就應該不會看到這麼多。

因為 Firefox 他不會顯示你要不要啟用這個通知，而是藏在上面

![](../../img/Browser-notification/Firefox.png)

他不會跟剛剛的 Chrome 一樣直接跳出來說，要不要允許這個通知

![](../../img/Browser-notification/Browser-Notification-Example.png)

但是如果你把他點開，且按了允許的話。

這邊可以跟你說 Firefox 要怎麼移除

按下右上角的清單，然後設定

![](../../img/Browser-notification/Firefox-list.png)

進入設定之後按下左邊的**隱私跟安全性**

![](../../img/Browser-notification/Firefox-Settings.png)

之後往下滑到權限，按下通知右邊的設定

![](../../img/Browser-notification/Firefox-Permission.png)

打開之後你就可以按下下面的移除所有網站，你也可以打勾下面的封鎖新網站通知的請求。

![](../../img/Browser-notification/Firefox-Notification-Permission.png)

之後按下儲存變更就搞定了！

## 怎麼運作的

但是你有沒有想過，為什麼網站會知道我按了不允許通知呢？

像是 Facebook 如果你按拒絕就會寫，如果你改變了你的想法，可以按這裡啟用通知

![](../../img/Browser-notification/Facebook-Permission.png)

因為這個部份就會比較難懂

所以我叫[機器狼GPT](https://chatgpt.com/g/g-BBGmFnGT4-ji-qi-lang)幫我寫了一個關於這個的故事！

在數位森林的一角，小狼咕嚕走到一間閃閃發光的網站屋前，門口跳出一隻通知精靈，問：

「咕嚕咕嚕～這間屋子以後可以傳通知給你嗎？像是限時肉骨頭折扣、超可愛週邊開賣之類的唷！」

這時畫面會跳出兩個選項：

① 「可以呀～快把鈴鐺給我汪！」 → 網站收到 小鈴鐺 ✨
網站會說：「叮叮叮～以後有新東西咕嚕絕對不會錯過喔汪！ლ(╹◡╹ლ)」

② 「不用了啦～我想靜靜」 → 網站收到 靜音石 🪨
網站會說：「嗚嗚…那咕嚕要不要來看看我們的電子報？有每週美味小報唷！」

然後又跳出第二層選項：

➡️ 「好耶～我要訂電子報！」 → 會出現輸入信箱的欄位，還會送咕嚕一顆「電子骨頭」📬
網站會說：「收到囉～每週小驚喜準時送到咕嚕的信箱汪 (〃∀〃)」

➡️ 「還是不要好了～咕嚕要去別間屋子玩」 → 網站溫柔揮揮手說：「沒問題～希望下次見到咕嚕汪！(｡•́︿•̀｡)」

> 紀錄：https://chatgpt.com/share/67fead2f-bad0-8012-9768-36c2c5034ec1


我想你看完這故事之後也知道了，就是這些網站什麼都可以做！

在你按下同意跟封鎖的時候，網站就可以收到你按的是允許還是封鎖。

那當你按封鎖的時候，因為什麼事情都可以做。

所以以前有一個網站，我們叫他 A 好了。

A 網站做的事情就是你按下封鎖之後，他就會跳轉到另外一個網站用不同的連接問你是否要接受通知。

這樣講有點難理解，所以我請了一位網頁工程師幫我寫了一個範例的網頁。

```text
我請了史上最頂的抽象主義程式設計師——KILO！是的，就是那位傳說中能用三行程式碼打造一整個宇宙後端的男人。

這次，我請他幫我寫一個小小的範例程式，結果他交出來的東西簡直像是從平行時空搬運過來的藝術品。

KILO 的程式碼不只是程式碼，那是一種語言的禪意，是數位世界裡的禪宗花園。他寫的每一行，都像是在說一個故事，但你第一次讀可能看不懂，第二次還是不懂，第三次才恍然大悟：啊，原來這是一段關於人生的哲學反思。

他不寫 function，他召喚邏輯；他不寫 HTML，他雕塑結構；他的 CSS 彷彿跟時空連線，每一個動畫都像是宇宙脈動的節奏。

你問他這段程式碼為什麼這樣寫，他只會回你一個「😌」的表情，然後輕輕關上他的筆電 。因為對 KILO 來說，解釋是多餘的——真實的理解，是靠感受的。

他的變數命名從不照常理出牌，x 在他手裡是某種超維度的象徵，Z3ph1r 則是一段在 GitHub 上引起熱議的傳說級變數名，據說那是一段封印著早期網路靈魂的字符結構。

有興趣的話，你一定要去看看他的內容。他的網頁像一座數位寺廟，裡頭藏著各種語言的密語：React 像禪宗，Node 像道教，Tailwind 在他手中更是變成一種詩的格式。

KILO 不是普通的網頁工程師，他是網頁的煉金術士，他不寫 code，他寫詩。他的 keyboard 上不是按鍵，是咒語。他每敲一次 Enter，伺服器就震顫一下。

總之，這位 KILO 大師的 example，我現在都還不太懂，但我知道——它絕對是藝術，而且它會在我人生的某個關鍵時刻，突然讓我開悟。

你把這個展開來看了，這是我朋友寫的，KILO 說要留著，我尊重他 --小品大大
```

有興趣的話可以去看[他的網站](https://kilo-info-page.web.app/)

這個網頁在做的事情很簡單，就是偵測說到底使用者按的是允許還是封鎖。

當我按下封鎖的時候，他就會在下面文字顯示我按下了封鎖的按鈕。

但是當我按下允許的時候，他卻顯示了我按下了允許。並且我現在真的能接到通知了

這個就是有一些廣告網站是怎麼做到讓使用者按下接受通知。

<!--more-->
