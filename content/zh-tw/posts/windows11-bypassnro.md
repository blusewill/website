---
title: Windows 11 消除了 BypassNRO！？
subtitle: 別擔心，這邊教你最快繞過方法
date: 2025-04-06T17:56:50+08:00
lastmod: 2025-10-11T17:56:50+08:00
slug: 6d193ae
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

最近外國媒體在測試 24H2 的 Insider （內測） 版本的時候發現到一個恐怖的事情

就是 Windows 裡面的一個腳本 `C:\Windows\System32\oobe\bypassNRO.cmd` 在內測版本中消失，也就代表以後 "家用版" 的 Windows 11 跑不了要連網的命運。

那當然，你現在都來到了小品大大的網站，比起我要拍 10 分鐘以上的 YouTube 影片還要剪輯，講實話你也會變得沒有耐心，看完好幾分鐘的影片吧？

該不如我在這邊直接把所有你可以繞過的方法直接告訴你。

這樣我也省下許多時間，不用在影片裡面提到。

加上寫一篇文章也比肝一部 YouTube 影片還要簡單，如果想要看更多的話我懶惰做影片的文章的話

歡迎訂閱我的 RSS 電子報來看更多有趣的文章 [點我訂閱](https://blusewill.us.to/zh-tw/index.xml)

好廢話說到這邊，我們就開始教你如何跳過吧！

## 直接在 OOBE 帶入設定檔

下面的繞過即將要無效了，所以目前最新的方法就是直接載入 autounattend.xml 進入這個安裝階段裡面。

那這個文件的運作方式我在下面也解釋的很清楚了，如果有興趣設定自己的設定檔的話可以[按這裡看更多](./#使用-autounattendxml-安裝)

那因為這現在是未來唯一的方法，所以我幫大家設計好了一個設定檔！

https://github.com/blusewill/bypassnro

那這個設定檔呢會直接讓你跳過全部的設定畫面，直接進入桌面。

那如果你還是想要設定一些像是輸入法等等的東西之類

可以使用原作者 Chris Titus Tech 所製作的版本

https://github.com/ChrisTitusTech/bypassnro

那當你決定好你的版本之後呢，你就可以按下 `Shift + F10`

叫出命令提示字元

之後以你想要使用的版本打上不同的指令

我的版本：
`curl -L blusewill.top/oobe -o skip.cmd && skip.cmd`

Chris Titus Tech 的版本：
`curl -L christitus.com/bypass -o skip.cmd && skip.cmd`

![](../../img/BypassNRO/inject-xml-file.png)

之後按下 Enter 讓他跑一下之後 Windows 會自動重新開機

如果是使用我的版本的話，基本上不會在回到 OOBE 的畫面了

會直接登入 Windows 系統

但是如果你是用 ChrisTitusTech 的腳本的話，你就可以手動設定國家跟輸入法！

![](../../img/BypassNRO/bypassed-oobe.png)

缺點就是，這種腳本目前還**無法設定自訂使用者名稱** （除非自行更改 xml 檔案）

希望以後會開發出可以自訂使用者名稱的腳本吧

## 最簡單一行指令做法 (即將在未來版本失效)

首先在 OOBE 也就是設定國家的那個畫面按下 `Shift + F10`

打上 `start ms-cxh:localonly`

![start ms-cxh:localonly](../../img/BypassNRO/localonly-oobe.png)

你就會看到他會出現創建一個使用者，然後你就可以打上帳號名稱跟密碼

![create_user](../../img/BypassNRO/localonly-create-user.png)

按下下一步之後就可以只接跳過全部的設定，直接登入！

這是目前比執行 `bypassNRO.cmd` 還要快的方法！

> 2025/10/11 號更新，微軟真不愧是你，在最新的內測版本將這個東西修掉了！
> 不知道什麼時候會發布到最新的穩定版本，所以大家現在能用就用吧，或是參考上面最新的方案

## 改註冊表

我自己都沒有想到，媒體最多報導的是這一個方法

那這是為什麼呢？因為如果我們看 `bypassNRO.cmd` 裡面的內文

是長這樣的

```cmd
@echo off
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE /v BypassNRO /t REG_DWORD /d 1 /f
shutdown /r /t 0
```

### 這些指令代表什麼含意？

那我就來簡單介紹一下這個腳本做了什麼事情。

首先 `@echo off` 就是關閉顯示命令本身的輸出，讓螢幕只顯示執行結果，而不是顯示每行指令

<del>基本上這個是問 ChatGPT 的，因為我沒有什麼在寫 cmd 或是 bat 腳本，我也不懂 XD</del>

但是下一個我就可以幫你稍微解析一下了

`reg add` 代表的是在登入檔（註冊表）加入一個值

那加到 `HKLM` 是什麼東西？我打開登入檔也從來沒有看過 `HKLM` 這個資料夾阿

其實你看到 GUI 的登入檔，他其實是用全名展示出來。

其實在寫這種腳本的時候，可以使用縮寫的方式才不用打太多字

所以 `HKLM` 代表的是 `HKEY_LOCAL_MACHINE`

那當然的 `HKCU` 代表的是 `HKEY_CURRENT_USER`

`/v` 代表的是這一個值的名稱

你可以看到，完全沒有變！還是 BypassNRO

`/t` 代表的是哪一個類型的值

在這邊可以看到他是 `REG_DWORD`

也就是 `DWORD（32-位元）值`

`/d` 代表的是這個值的資料，也就是 1 啟用

那當然有時候不一定會是 1 這是看程式不同，有些程式會看 2 或 3 切換到不同的模式

這會在電腦病毒上面會很常見到。

`/f` 代表的是不詢問使用者要不要添加，強制添加這個值

這邊 `reg add` 的指令就介紹完了！

最後一個指令是 `shutdown /r /t 0`

簡單翻譯過來是0秒後重新開機！

### 所以應該要怎麼手動設定呢？

第一步是按下 `Shift + F10` 打上 `regedit` 打開登錄檔

![Example of Regedit](../../img/BypassNRO/regedit.png)

之後找到`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE` 的機碼

![Regedit Path Example](../../img/BypassNRO/regedit_path_example.png)

裡面在右鍵新增一個 `DWORD（32-位元）` 的值，然後取名叫做 BypassNRO

之後點開來，設定為 1

![Regedit BypassNRO Value](../../img/BypassNRO/BypassNRO_value.png)

之後回到 `cmd` 輸入 `shutdown /r /t 0` 把電腦重新開機就可以設定好了！

![Shutdown Command Exmaple](../../img/BypassNRO/shutdown_command_example.png)

<del>講實話的，為什麼不要直接打一開始的指令就好了</del>

## 使用 autounattend.xml 安裝

接下來如果你是很常安裝 Windows 的人，你應該要這樣設定你的 ISO 檔案

因為這樣不僅可以繞過 Windows 的 OOBE

還可以幾乎完全不用動手，就可以設定好電腦！

但是因為他的設定比較複雜，這邊會教你兩種方法進行使用

### WinUtil

[WinUtil](https://github.com/christitustech/winutil) 應該是我在 Windows 裡面剛安裝就會開始使用的工具箱了。

裡面有很多好用的功能，其中一個叫做 MicroWin

MicroWin 除了可以幫你減輕 Windows 的重量，其實他還可以幫你創建使用者

你只要把 ISO 丟上去，就會看到設定使用者的帳號密碼

![MicoWin Custom User Settings Captured From ChrisTitusTech's Video](../../img/BypassNRO/WinUtil_MicroWin_User.png)

設定之後按下下面的 Start the Process 就可以生成好一個沒有 OOBE 的 ISO 了！

### 手動設定

如果你要手動製作一個 xml 檔案的話。

那你可能會有一些辛苦。

因為基本上所有的生成網站，都是英文的

所以我這邊先簡易的先設定好了一個 xml 檔案

你可以依照這個下去做修改

[點我開啟](https://schneegans.de/windows/unattend-generator/?LanguageMode=Interactive&ProcessorArchitecture=amd64&BypassRequirementsCheck=true&BypassNetworkCheck=true&ComputerNameMode=Random&CompactOsMode=Default&TimeZoneMode=Implicit&PartitionMode=Interactive&DiskAssertionMode=Skip&WindowsEditionMode=Interactive&UserAccountMode=Unattended&AccountName0=User&AccountDisplayName0=User&AccountPassword0=&AccountGroup0=Administrators&AccountName1=&AccountName2=&AccountName3=&AutoLogonMode=Own&PasswordExpirationMode=Unlimited&LockoutMode=Default&HideFiles=HiddenSystem&ShowFileExtensions=true&TaskbarSearch=Hide&TaskbarIconsMode=Default&DisableWidgets=true&LeftTaskbar=true&DisableBingResults=true&StartTilesMode=Default&StartPinsMode=Empty&DisableFastStartup=true&PreventAutomaticReboot=true&PreventDeviceEncryption=true&HideEdgeFre=true&EffectsMode=Default&DesktopIconsMode=Custom&IconThisPC=true&WifiMode=Interactive&ExpressSettings=Interactive&KeysMode=Skip&ColorMode=Default&WallpaperMode=Default&WdacMode=Skip)

你需要滑到的是 User Accounts

![User Accounts on the Generator](../../img/BypassNRO/autoattended_xml_User_accounts.png)

更改最上面的選項，輸入 Account Name （使用者名稱） 跟 Display Name （顯示名稱）

然後如果要設定 Password （密碼）的話就建議打勾下面的

`Obscure all account passwords in your autounattend.xml file with Base64`

這會把你的密碼在這個 xml 裡面加密成 base64 的格式，但是我個人不建議，建議是自己創了一個帳號之後在設定密碼比較好

之後滑到最下面按下 `Download .xml file`

然後把這個 xml 檔案丟到 Windows 的安裝資料夾就好了（有 setup.exe 的地方）

那以上就是三種教你如何繞過得方法，雖說 Microsoft 應該以後就會把 BypassNRO 的註冊表全部刪除，但是第一種方法應該還可以用一陣子

如果你喜歡這種文章的話，記得在文章下面留言告訴我！

我們就下一篇文章見拉！

## 影片教學

{{< youtube VTjF-IBmOLM >}}

<!--more-->
