---
title: Streamer.bot 筆記 (持續更新中)
subtitle:
date: 2025-06-21T01:59:00+08:00
lastmod: 2025-06-21T01:59:00+08:00
slug: ea7ec9c
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
  - YouTube
  - OBS
  - Streamer  
categories:
  - 直播工具教學
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

不知道你們想到 Twitch 或是 YouTube 上面的機器人你們會想到什麼。

是 Nightbot 還是像是 StreamElements 或 Streamlabs 會附送給你的機器人呢？

但是如果你要說最強的直播機器人的話，那還得是 Streamer.bot

因為他目前可以做的事情已經超過了這些機器人提供給你的資訊

在 2025 年的今天，現在我的直播全部是 Streamer.bot 驅動的

除了右上方的 Spotify 目前播放以外，還有現在的時間，這個有興趣在跟大家介紹。

剩下的都是 Streamer.bot 在我的電腦後台，監視著大家的訊息。

那我自己也是不太會用 Streamer.bot 所以乾脆做一個筆記跟大家分享我是怎麼使用的？

我後面又學會了什麼？

## 如何下載 Streamer.bot

你只要去到他們的官方網站 https://streamer.bot/

按下左手邊的 Streamer.bot v0.2.8

![streamer.bot 的網站](../../img/streamer-bot-configuration/Streamerbot_website.png)

之後你就會開始下載一個壓縮檔，我們把它節壓縮之後打開裡面的 `Streamer.bot.exe` 就會啟動你的 Streamer.bot 了。

這邊做一個小筆記，如果你像我一樣有養一隻狼的話，你也可以不同直播的 Streamer.bot 分成兩份，這樣你每次就不用重新登入 Twitch 跟 YouTube 的帳號了！

## 初次見面！Streamer.bot

當你第一次打開 Streamer.bot 的時候一定就會想說。

什麼！？這是目前市面上功能最多的機器人系統？

![Streamer.bot UI](../../img/streamer-bot-configuration/Streamer.bot.png)

對，你沒有看錯。

但是也不要慌張，它們最近也快要更新 UI 了！

換成 UWP 的樣式

![Streamer bot alpha](../../img/streamer-bot-configuration/Streamer.bot_alpha.png)

所以在期待一下，雖說這樣用 UWP 有可能會導致 Linux 無法透過 Wine 進行使用。

但是由於目前它們還在 Debug 所以可能還不會發布這個版本！

## 綁定 Twitch/YouTube 帳號

綁定這兩個帳號應該是最大的優勢，畢竟你需要在這些平台直播。

我們到上面的 Platforms 你就會看到三個平台

Twitch YouTube 跟 Trovo

### 綁定 Twitch 帳號

我們到 Twitch 之後按下 Accounts

![Twitch Accounts](../../img/streamer-bot-configuration/Twitch%20Accounts.png)

這時候你就會看到它分兩邊，左邊是你要拿來直播的帳號，右邊是拿來當機器人的帳號

> 你不一定要登入機器人的帳號，他會預設設定直播中的帳號為機器人帳號

這時候你就按下 Login 來登入這些帳號！

之後就會長這樣子！

![Logined Twitch Account](../../img/streamer-bot-configuration/Twitch_Loggedin.png)

就表示你的帳號已經登入了！

### 綁定 YouTube 帳號

YouTube 帳號就跟登入 Twitch 帳號一樣簡單

你只是你需要先同意條約

![YouTube streamer.bot ToS](../../img/streamer-bot-configuration/Streamer.bot_YouTube_ToS.png)

按下同意之後也是到上面的 Account

![YouTube Account](../../img/streamer-bot-configuration/sign%20in%20with%20Google.png)

然後按下 Sign in With Google 的按紐

選擇帳號這邊有很重要的一點

要記得勾選上面

之後就可以登入了！

但是等等！YouTube 不知道為什麼就不能跟 Twitch 一樣預設自動連接。

所以你需要按下右上的 Auto Connect 的按鈕才可以每次打開 Streamer.bot 的時候自動連接到 YouTube

![Auto Connect YouTube](../../img/streamer-bot-configuration/Auto%20Connect%20YouTube.png)

這樣子我們雙平台的帳號就都設定完成了！

## 綁定 OBS

沒錯！這個工具甚至可以綁定 OBS

所以這稱為最強機器人系統的原因是因為，它可以跟你的 OBS 連動！

而且不需要任何的插件，你只需要去 **OBS 上面的工具 > WebSocket 伺服器設定**

![OBS Websocket Setup](../../img/streamer-bot-configuration/obs-webscoket-setting-menu.png)

之後打勾第一個選項 **啟用 WebSocket 伺服器**

那下面還有一個選項叫做**啟用驗證**

如果你不想要設定密碼的話可以關閉，那你也可以設定密碼。

![OBS Websocket](../../img/streamer-bot-configuration/OBS%20Websocket%20Settings.png)

如果想要查看你的密碼的話，你可以按下下面的**顯示連線資訊**來查看密碼。

![OBS Show Connection Info](../../img/streamer-bot-configuration/OBS_Show_Connection_Info.png)

設定好之後按下確定，我們就可以回到 Streamer.bot

選擇上面的 Stream Apps 裡面的 OBS

![Stream Apps OBS Streamer.bots](../../img/streamer-bot-configuration/streamer-bot-obs.png)

然後對下面白白的視窗按下右鍵，按下 Add 

之後你就會看到這個畫面

![OBS Add Connection](../../img/streamer-bot-configuration/Add_OBS_Connection.png)

在 Name 幫你的 OBS 連線取名

如果有密碼的話，輸入 Websocket 的密碼

之後你會需要打勾下面的 Auto Connect on Startup

還有 Reconnect on Disconnect

這樣就可以保證你 Streamer.bot 打開的時候就會自動連接到 OBS 了喔！

如果有密碼的話，你需要在 Password 的地方輸入你的密碼！

如果沒有密碼的話，直接按下 OK 你的 OBS 就連線成功了！

### OBS 插件推薦

如果你不想要每次打開 OBS 都要等 Streamer.bot 的話

你可以使用一個叫做 [AutoStarter](https://obsproject.com/forum/resources/autostarter.2083/) 的插件

它會在 OBS 打開的時候詢問你是否要啟動這個設定檔的東西。

按下啟動就可以啟動你設定好的程式，當然你也可以設定關閉 OBS 的時候自動關閉，非常的方便！

## 簡易動作設定

當你打指令的時候當然聊天室要有動靜，而這個動靜就是動作了！(真不好的一個解釋方法)

總之，我們到上面的 Actions 也就是動作。

通常如果你是第一次用 Streamer.bot 基本上都是空的

![Empty Actions](../../img/streamer-bot-configuration/empty_acitons.png)

你會看到一個 Right click to add actions!

然後我們就對他按下右鍵，按下 Add

![Add Action](../../img/streamer-bot-configuration/Add_Action_Easy_Version.png)

你就會看到這裡的選項怎麼這麼多，那由於這邊還是簡易的設定，所以目前你不會動到 Group 以下的設定。

所以你不太需要太過緊張！

那這邊就簡單翻譯一下設定

`Name` (這個動作的名子)

`Group` (這個動作要放在哪一區)

`Enabled` (這個動作是否啟用)

然後按下 OK 我們就成功創件好一個動作了！

### 觸發方式

接下來我們看向右上角，也就是 Triggers

我們對他按下右鍵，你就會發現怎麼會有這麼多選項！？

![Trigger Options](../../img/streamer-bot-configuration/Trigger%20Options.png)

沒錯！記得我剛剛說他什麼都能做到嗎？

它也真的是什麼都可以觸發。

從最基本的指令觸發，到 Twitch 的忠誠點數，到你 OBS 按下開始直播的瞬間，都可以當作觸發的條件。

甚至，Twitch 的廣告開始的時候都可以當作一個觸發條件。

那我們現在就先從簡單的指令開始。

我們對 Triggers 按右鍵 Core > Commands > Command Triggered

它就會跳出這個視窗

![Command Triggered](../../img/streamer-bot-configuration/command_triggered.png)

你可以在中間選擇選你想要的指令，那想要新增新的指令就按下左下角的 Create Command

之後就會出現這個畫面

![Add Command](../../img/streamer-bot-configuration/Add%20Command.png)

這個就是添加指令的畫面。

我知道看起來很複雜，但是我們目標現在放向簡單的部份

我們目前只需要看到 Name, Command(s), Group, Source(s), Cooldown 還有右邊的 Permissions 就好了

首先要先幫我們的的這個指令取個名子，我們看到左上角的 Name

你可以取你任何想要的名子，像是我們這個是測試指令我們就叫它 test

然後取名之後我們看到下面 Commands 的部份，這邊代表的是你要使用什麼指令觸發。

像是我們在裡面打 `!test` 的話，在 Twitch 聊天室打 `!test` 就會觸發這個動作

那如果你想要有多個指令的話，你可以以分段的方式輸入

像是這樣

```text
!test
!test2
!test3
```

這樣你輸入以上這三個指令的時候都會觸發這個動作！

接下來我們看到 Sources 的部份，這個代表的是要在哪些地方觸發

像是你可以看到上面有 Twitch 聊天室，還有 YouTube 聊天室等等的東西

如果你想要兩個都要的話，你也可以複選，就可以同時在兩邊使用了。

然後接下來就是下面的 Cooldown (冷卻時間)

如果你不想要有人同時一直刷同一個指令的話，你就可以在下面的冷卻時間設定。

`Global Cooldown` 代表的是這個指令被使用後，**全部人**都要等多久才可以使用。

`User Cooldown` 代表的是這個指令被使用後，這個**使用人**要等多久才可以使用。

> **冷卻時間是以秒為單位，所以要記得換算分鐘或是小時變成秒**

那你也可以設定這個指令被使用後，全部人要等冷卻時間 10 秒，然後使用者要冷卻 120 秒

這樣就可以避免很多很多人一直在刷指令了！

接下來是右邊的 Permissions (權限設定)

我們看向上面的 Grant Type

你按下去就會看到 Allow 跟 Deny

那 Allow 就是誰可以使用這些指令。

然後 Deny 就是誰不能用這些指令

但是一般都是只會用到 Allow 而已拉。

但是還是想要讓一些會用到 Deny 的人知道 <i class="fa-regular fa-face-laugh-wink"></i>

接下來我們往下面看，你會看到權限。

Streamer.bot 很棒的地方就是他幫你分配成了兩類

`Group Permissions` 群組權限跟 `User Permissions` 使用者權限

那 Group Permissions 它這邊有 Mod (大劍們) 跟 Subscribers (訂閱者) 還有 VIPs

![user_permissions panel streamer.bot](../../img/streamer-bot-configuration/User_permissions_streamer.bot.png)

那 User Permissions 的意思就是你可以分派給不同的使用者，上面選擇 User Permissions 之後呢，按下下面的 Add User(s) 就可以選擇使用者

![Search User Permission](../../img/streamer-bot-configuration/user_permissions_search.png)

你可以在上面搜尋你要找的 ID 然後按兩下添加到權限裡面！

如果你有一些指令是你想要自己用的話，你可以透過這個方式來避免其他人使用！

最後我們來講 Groups

放到最後面講的原因是因為，它沒有很重要 XD

他是可以幫你在 Commands 的分頁幫你分類哪些指令是哪些。

像是這個樣子

![Commands 分頁](../../img/streamer-bot-configuration/Commands_Tab.png)

所以如果你想要分類的話，你可以透過 Groups

那不用擔心每一次添加新的指令都在打一次 Groups 的名稱

你可以按下右邊的下拉選單，就可以看到你目前有的 Groups 了！

最後呢！設定下來就會是這個樣子！

![Finished Add Command Settings](../../img/streamer-bot-configuration/finish_add_command_settings.png)

我這邊就設定這個在群組 `test group` 的指令 `test` 

觸發條件是：當**小品大大**在 Twitch 的聊天室輸入 `!test` 的時候就會進行觸發。

然後沒有冷卻時間

是不是很複雜呢？但其實設定起來簡單很多，如果你會看得懂一點英文的話，應該不到 5 分鐘就可以設定出一樣的畫面了！


### 觸發之後要做什麼？

你這時候一定在想，我已經設定好了指令

但是...我們還沒有說要讓他來幫我們做什麼啊！

![](../../img/streamer-bot-configuration/empty_acitons.png)

這時後我們就可以看右下角的 Sub-Actions

那邊就是我們的主要應該要做什麼了！

我們對 Sub-Actions 按下右鍵，你也可以看到跟 Triggers 一樣非常非常多的事情可以做。

![Sub Actions Context Menu](../../img/streamer-bot-configuration/Sub-Actions-context-menu.png)

那這邊就是可以讓你開始發揮創意的地方！

你可以從這邊讓觀眾操控你的 OBS 操控 Twitch 的全部東西！

我不知道你有沒有在某些台看過一些點數兌換像是 VIP 或是發送廣告等等的

有了這個！你的全部的東西都可以自動化。

就不用還要打開 Twitch 的後台等等的，就因為某人兌換了 VIP

有了 Streamer.bot 你全部的作業就都可以自動化了！

那我們因為現在還在簡單的部份，所以我們這邊先設定發送訊息到聊天室看看好了！

如果你是 YouTube 聊天室的話，會在 `Youtube > Send Message to Channel`

那是在 Twitch 聊天室的話，就會在 `Twitch > Chat > Send Message to Channel`

那我這邊先使用 Twitch 的當作示範，但是 YouTube 的應該也很類似。

![Send Message to Channel](../../img/streamer-bot-configuration/send_message_to_channel.png)

看到這個畫面之後呢，你就可以在上面打上任何你想要的訊息！

之後我們看到左下，如果你有設定機器人的話它就會用機器人帳號發送

如果沒有的話他就會回到你直播的帳號去！

### 測試

接下來我已經打好了內容，我們就可以去聊天室測試看看了！

非常剛好，Streamer.bot 集成了聊天室！

如果你正在尋找有什麼可以 YouTube 跟 Twitch 合在一起的聊天室軟體

你也可以考慮看看 Streamer.bot!

我們只要按下上面的 Chat

![Streamer.bot Chat Location](../../img/streamer-bot-configuration/streamer-bot-chat-open-location.png)

就可以打開 Streamer.bot 的聊天室了！

![Streamer.bot Chat](../../img/streamer-bot-configuration/streamer_bot_chat.png)

這時候我們就只要打上我剛剛的 `!test`

![streamer.bot test message](../../img/streamer-bot-configuration/test_message_streamer_bot.png)

你就可以看到我的測試訊息發送出去了！

那為了避免有人說這個聊天室可能只是測試用。

所以剛剛好我是一邊打這個文章一邊直播

所以我的 Twitch 有紀錄下來這個訊息！

![Twitch test message](../../img/streamer-bot-configuration/Twitch_test_command.png)

你看，就連機器人都知道要訂閱我的網站 RSS 了！

不考慮訂閱一下嗎？ XD

[按此訂閱](https://blusewill.us.to/zh-tw/index.xml)

**Streamer.bot 沒有自動存檔，所以記得做完之後要按下存檔**

好！到這邊我們的簡單設定就到這邊結束了！

接下來就是一些筆記的部份了！

## Raid 指令

/raid {使用者名稱} 大家都知道這是 Twitch 的 Raid 指令

但是你有沒有想過，先讓大家知道一些資訊嗎？

像是他在直播什麼之類等等的！

這時候，你會需要 `!raid` 指令

`!raid` 指令呢，它會讓你先顯示你要 Raid 的人的相關資訊。

然後因為我 YouTube 雙開的原因，所以它也會發送到 YouTube 那邊

如果有 YouTube 的人想要跳到 Twitch 去看的話也可以直接點擊連接！

訊息輸出像是這樣！

![Raid Command](../../img/streamer-bot-configuration/raid_example.png)

![Raid Command Twitch Example](../../img/streamer-bot-configuration/Raid_Exmaple_Twitch.png)

然後同時它也會開啟 Raid！

那要下載的方法很簡單！

```
U0JBRR+LCAAAAAAABADVV8+P3DQUviPxP4SRVlzq2fxwJklvZcSPSoBQW7igHhz7JWs1iYPjzMyqWqmICwKp1YoLh57gAgfaE6ISiL+ms9sb/wJOZjKTTJJqtcABaQ5jf8/Pz9/3/Pzy8M03DGOSgiKTm8bDaqCHGUlBDydhUhaw5EnydmHcW3JFT4w7hDNjLtKUZGxyY2tPSnUiZGfFDluALLjIKtCamlNzBzAoqOS52oJtZ+JOmd2iWyQrk6TBUp7xtEw/2/mswAo7qy0mjHTOQWofhZ75fDNjNFANc1ZtHIU0Aju0kI19D2GLUUQchhEOZiZgjH2gtAmuXvZFCSV0A6vnISNhApVPJUvoICualAzekyL9gBdKyFNtFJGkGLP6BDLGs3jIqtGmEqITVixFmfdUEyIpOmYkWZLTQhM85FxqVUW6o76HU5HRUkrI1BCqJI9jLU2b7wPOt17q9Lld028Hkeu7M4Zsh/gIh5aLiMUICoHOKI4ojfywfYCWcl5A/ciJKHJIMEPYdgIURsxBWszA90wnsE2vt1Sd5hV/2LQOkVH99uoUTTrdb6Nn+8H9DtX99BuioxClpHBvE5d9uO+CSF7F1b4jBzzMbBtTiBhygTGEGcYoZNhGM9Ohlmc5nmv3eVgCj08qGfWdHOHI7QFNjh2k/hXo4xmDVbVbh7gbr+NFZ7H8UMS8Lg9HisgY1Kd67mN9A45GqLD8ILSoGyKXRQRhL3SQzoIAeV7AbGw5jGH3elT8B1xYV+dCwaoKcPLq2XcXX5+vH52/fPHo1a+/rR//fvn0W/0zWvwcGeunPxknSuXFzeNjVdftqVocH1JovHzxzV9/fLl+9pX2d/nkT71q/eT5xffPL375Uf+/fPyzcRTXhuvzH7Rhjzcqkrrq96jRyr0j1MjpddlIQkIfjJFT60iJGwQedVBkeVpHn3o6pSPQw5AGFEICjn8dHW3n35fR/p/LmEuIQBd1dotSUdalvUdfKAVhlBSD4EYyzCKb+rYu3zNiasnARiSwLeRjXX9CbM+iyLmOZNjsl+p/Lppz9QL+frXZpup338IkIXkBrIU38NZhY79pGToumkdwtDnZvAq9x8McCTUHmXKlgFV50Q92B++DbXudfCQYSKI7k2IysgG/1ms93q7sZer1ETyrG6GBRioV9bTZ1WHTjOpN3pKHu0iIYfXuKk845WpOclVKGNoyEZRsm56Ocx5nQlbFbH83DmPamNzOFMiMJAMGedWtFmperQc5tPvWopLuNVb6+sFdyAqu+GLwEHEiQpLMdcvHxLJ3lLL2PowN9o7zJkO7liRT217FHEv3JYSFoA9A3QW5OEjHPThPuG4ku6DiaWPfauv33xDWphTobiwXUqdz1SxXcZtTe7p9EPofCTWqeyL9kTOd6fw++xuvGqY79QwAAA==
```

你需要把上面這一行複製起來，然後在 Streamer.bot 的上面按下 Import 的按紐

![Streamer.bot Import](../../img/streamer-bot-configuration/Streamer_bot_import.png)


然後將它貼上到上面的 Import Strings

![Import Commands](../../img/streamer-bot-configuration/Import%20Commands.png)

之後按下右下方 Import 的按紐，你就可以導入了！

那預設導入的指令都是停用的，所以你需要到上方的 Commands 找到 Raid

對他按下右鍵，然後按下 Enabled

![Enable Commands](../../img/streamer-bot-configuration/Enable%20Commands.png)

你就可以啟用這個指令了！

### 編輯訊息

如果你想要編輯訊息的話，你可以到 Actions 的 blusewill's Tools 裡面會有一個 Raid 的 Actions

之後我們要到右邊的 Sub-Actions 你就會看到 Twitch Announce 跟 YouTube Message！

那我這邊先將變數列出來，如果有人不小心刪掉的話可以補回去！

` %targetUser%` 要 Raid 的人的暱稱 (中文等語言)

`%targetUserName%` 要 Raid 的人的 ID

`%game%` 它們目前在玩什麼遊戲？

那如果你想要調整更多的話！你可以往上看看新手 Streamer.bot 教學！調整權限各類設定喔！

<!--more-->
