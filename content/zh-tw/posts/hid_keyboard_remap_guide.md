---
title: 最平價 StreamDeck！拿數字鍵盤來當快捷鍵！
subtitle:
date: 2025-03-11T02:08:13+08:00
lastmod: 2025-03-11T02:08:13+08:00
slug: 4082c82
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
  - 工具
  - HID
categories:
  - 工具
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

你是不是想過買一個快捷鍵盤，上面可以自訂各種按鍵

現實確實是有這樣的方案，他的名子叫做 StreamDeck

![StreamDeck](../../img/hid_keyboard_remap_guide/StreamDeck_price.jpg)

但是你也可以看到 StreamDeck 的價格非常的高昂，那我們有什麼方法可以買到一個價格沒有這麼高昂的 StreamDeck 呢？

## 我...我買了一個數字鍵盤

![Numpad](../../img/hid_keyboard_remap_guide/Numpad.jpg)

先聽我說！

買這個數字鍵盤是‘有意義的，因為其實很多人都不知道，你其實可以拿隨便一個鍵盤當作快捷鍵來用。

當然大家都知道，但是這時候就有人會想說

這樣不是會跟現有的鍵盤造成衝突嗎？

其實並不會，因為鍵盤都是透過一個叫做 HID (Human Interface Device) 這個東西下去跟電腦說我現在在使用哪一個鍵盤操作！

所以都會有一個特殊的 ID 來跟電腦說，這個應該是哪個按鍵。

有趣的地方就在這裡了，我們完全可以把一個數字鍵盤當作分開的按鍵來設定

今天這篇文章就會實際教你應該要怎麼做！

## 安裝需要的程式

這次會需要的程式有以下這些

[AutoHotkey](https://autohotkey.com/) 來設定你的鍵位

[Interception](https://github.com/oblitum/Interception/releases) 來讓 AutoHotKey 可以跟據裝置來重新指定鍵位

[KeyTik](https://keytik.com) 來輔助你重新設定你的鍵位


## 如何安裝

安裝 AutoHotKey 的方法很簡單，只要去網站然後下載 v2.0 的版本安裝

![AutoHotKey_Website](../../img/hid_keyboard_remap_guide/AHK_Download.jpg)

> 免則聲明：安裝驅動程式可能會讓你的電腦不穩定，也有可能讓你無法正常使用電腦，請慎入

然後安裝 Interception 會比較麻煩一點，你會先需要解壓縮，然後打開你的終端機

之後呢要把終端機指定到 `command line installer` 這個地方

然後打上 `.\install-interception.exe /install` 就可以安裝 Interception 驅動程式了

![Interception](../../img/hid_keyboard_remap_guide/Interception_driver_install.jpg)

安裝完過後要重新開機，讓驅動程式成功載入進去就可以下載 KeyTik 了

## KeyTik 使用方法

首先我們可以先把 KeyTik 打開，它就會跳出兩個畫面，第一個是謝謝下載 KeyTik 還有這個程式可能會被防毒軟體誤判

之後呢我們按下右下角的以後不要在顯示，之後就可以看到預設很多的腳本

![KeyTik](../../img/hid_keyboard_remap_guide/KeyTik%20main%20menu.jpg)

但這些都不重要，我們要做的是按下下方的 Create New Profile

![KeyTik_New_profile](../../img/hid_keyboard_remap_guide/KeyTik_New_Profile.jpg)

然後你就可以看到最上面 Profile Name 就是這個設定檔的名子要叫什麼

再來就是這個只能在哪個程式觸發，那這個我是不建議設定，因為設定過後會需要讓視窗指定是那個畫面才能用

除非是遊戲，要不然就算了。

再來是你的裝置，我們就在右邊按下 Select Device 就可以選裝置了

![KeyTik_Select_Device](../../img/hid_keyboard_remap_guide/KeyTik_Select_Device.jpg)

但是你看這些你還是不知道什麼是什麼阿，所以我們要在按下右下角的 Open AHI Monitor To Test Device

![KeyTik_Select_Device](../../img/hid_keyboard_remap_guide/AHI_Monitor.jpg)

先看上面左邊是鍵盤，右邊是滑鼠，那因為我們這次是鍵盤，所以我們就一個一個打勾，當下面出現訊息的時候你就知道是什麼鍵盤了

這時候回到 Select Device 選擇跟 VID/PID 還有 Handle 一樣的選項

接下來我們就可以在下面選擇按鍵，然後要改到什麼按鍵

這邊的話我就把 Numpad1 改成 F13

![KeyTik_Remap](../../img/hid_keyboard_remap_guide/Key_remap.jpg)

那當然，因為在 Windows 上面呢 F13 是很少會用到的按鍵，你在 MacOS 上面會比較常看到。

所以這個時候我們就可以將按鍵都設定成 F13 就可以設定在其他地方了！

然後如果你要在添加的話，就可以按下面的 Add Remap Row 就可以繼續添加下去

## 我會寫 AHK 腳本的話我應該要怎麼編輯檔案

這時候你就要到 KeyTik 資料夾裡面的 `\_internal\Data\Active` 就可以找到了

![AHK_Data_Path](../../img/hid_keyboard_remap_guide/AHK_datapath.jpg)

## 開機自動啟動

你要開機自動啟動這個 AHK 的腳本可以按下右邊的 Startup

![KeyTik_Startup](../../img/hid_keyboard_remap_guide/KeyTik_Startup.jpg)

它就會自動開機，當然在點擊一下 Unstart 就會取消

要確定的話可以按下 <i class="fa-brands fa-windows"></i>+R 打上 `shell:startup` 就可以看到你剛剛的 AHK 腳本了！

## 結語

那以上就是如何將你的第二把鍵盤設定成快捷鍵盤，希望以上的內容有幫助到你。

那我們就下一篇文章見拉！

## 影片教學

{{< youtube VVQtG1IRhLU >}}

<!--more-->
