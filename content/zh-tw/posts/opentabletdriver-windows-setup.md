---
title: 在 Windows 上面設定 OpenTabletDriver
subtitle:
date: 2024-11-27T01:54:16+08:00
lastmod: 2024-11-27T01:54:16+08:00
0slug: 7cbfed0
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
  - 電繪
  - 驅動程式  
categories:
  - 開源驅動程式 
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

我在去年年初購入了一個便宜的 Wacom 電繪板，然後我就開始安裝了 Wacom 的驅動程式。

之後呢換到 Linux 發現到一個致命的錯誤，我不應該要用 Wacom 的驅動程式的。

因為 Linux 上面 Wacom 的驅動程式是沒有 GUI 的，除非你是使用像是 KDE 或是 Gnome 這些桌面環境，要不然都是要透過 CLI 進行設定。

所以我就開始尋找了替代方案，我就看到了 OpenTabletDriver 這個驅動程式。

雖說這個驅動程式通常是拿來打 osu! 居多，但是我還是想要嘗試看看繪圖。

在 Linux 上面 OpenTabletDriver 有良好的相容性，有內建 Artist Mode 還有 Systemd 自動啟動。

加上本身就內建 GUI 就不需要調整半天，這就讓 OpenTabletDriver 變成是 Linux 上面最好用的電繪板驅動。

雖說在 Windows 上面也可以使用 OpenTabletDriver 但是就沒有剛剛的 Linux 版本這麼好用。

像是沒有開機自動啟動，沒有壓力等等的。

雖說最好用的功能就是它可以輸出設定到另外一個 OpenTabletDriver 上，但是也就只有這樣是遠遠不夠的。

所以今天我要來教大家如何安裝 OpenTabletDriver 到你的 Windows 系統上，不管你是繪師還是 osu! 玩家都可以看這一篇文章學習！

## 第一步：解除安裝原廠的驅動程式

當然，非常殘酷的是原廠的驅動程式不能跟 OpenTabletDriver 共存，所以我們需要先解除安裝原廠的驅動程式。

首先我們到 : https://github.com/X9VoiD/TabletDriverCleanup/releases/latest

下載 `tabletdrivercleanup.zip`

解壓縮之後你就會看到以下檔案

![tabletdrivercleanup](../../img/opentabletdriver-win/tabletdrivercleanup.png)

以 **系統管理員** 執行 tablerdrivercleanup.exe

![清理驅動程式](../../img/opentabletdriver-win/drivercleanup.png)

然後看到有跟你的電繪板相關的驅動程式，就按下 Y

> 因為我這邊是 OpenTabletDriver 的驅動程式，所以沒有按下 Y

## 第二步：安裝 OpenTabletDriver

首先你會需要安裝 [.NET 6 Desktop Runtime x64](https://aka.ms/dotnet/6.0/windowsdesktop-runtime-win-x64.exe) 來使用 OpenTabletDriver

安裝完之後就可以下載 [OpenTabletDriver](https://github.com/OpenTabletDriver/OpenTabletDriver/releases/latest/download/OpenTabletDriver.win-x64.zip) 了。

下載之後，你可以解壓縮到你想要的資料夾，那教學是建議放在使用者資料夾裡面。

那我這邊因為不想要動到太多，所以我是放在 C:\

下載過後你會看到以下這些檔案

![OpenTabletDriver資料夾](../../img/opentabletdriver-win/opentabletdriver-folder.png)

### 製作成可攜式程式

如果你想要把這個資料夾放在 USB 裡面的話，你可以按下 `convert_to_portable.bat` 它就會幫你生成一個 userdata 的資料夾。

你就可以走到哪裡就可以用這個驅動程式摟！

## 第三步：設定壓力功能

首先我們要先安裝一個叫做 [VMulti](https://github.com/X9VoiD/vmulti-bin/releases/latest) 的驅動程式

下載 VMulti.Driver.zip 之後解壓縮會長的像這個樣子

![VMulti資料夾](../../img/opentabletdriver-win/VMulti%20Folder.png)

以**系統管理員**執行 `install_hiddriver.bat` 這個腳本，就會自行安裝這個驅動程式了！

![VMulti安裝](../../img/opentabletdriver-win/VMulti-install.png)

然後我們就可以把 `OpenTabletDriver.UX.Wpf.exe` 打開，在上面選擇 Plugins

![](../../img/opentabletdriver-win/opentabletdriver-wpf-plugin-manager-topbar.png)

然後按下 Open Plugin Manager

然後找到 Windows Ink 插件

![](../../img/opentabletdriver-win/opentabletdriver-plugin-manager.png)

之後按下右邊的 Install 按鈕，就可以安裝此插件了！

之後我們到 Output 這個地方，把右下角改成 Windows Ink Absolute Mode

![](../../img/opentabletdriver-win/opentabletdriver-windows-ink-abolute-mode.png)

在換到 Pen Settings 在 Tip Binding 的右邊有三個點，我們把它按下去

![](../../img/opentabletdriver-win/opentabletdriver-tip-settings.png)

我們把 Type 換成 Windows Ink 然後 Button 改成 Pen Tip

![](../../img/opentabletdriver-win/opentabletdriver-advanced-binding-editor.png)

然後這時候打開支援 Windows Ink 的軟體，像是 Krita 或是 Clip Studio Paint 等等繪圖軟體

![](../../img/opentabletdriver-win/krita-pressure-test.png)

你就可以看到，現在檢測的到壓力了！

> Krita 要在電繪板設定裡面調整成 Windows Ink 才可以使用

## 第四步：自動啟動

首先我們先按下 Windows 鍵 + R 然後打上 `shell:startup` 打開自啟動資料夾。

然後我們按住 Alt 然後把 `OpenTabletDriver.UX.Wpf.exe` 丟過去它就會建立一個捷徑

然後我們對它按右鍵，關於

然後把執行改成最小化

![](../../img/opentabletdriver-win/opentabletdriver-shortcut-propertys.png)

這樣子我們的 OpenTabletDriver 就算設定成功拉！

希望這篇文章可以幫助很常跨系統畫畫的人！

那我們就下一篇文章再見拉。
