---
title: Linux 入門教學
subtitle: 從入門，到長期使用
date: 2025-04-08T22:27:57+08:00
lastmod: 2025-04-08T22:27:57+08:00
slug: eb38ca4
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
  - Linux
  - 入門
categories:
  - 網站獨占系列
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

歡迎來到獨占系列，這邊的內容都不會製作成 YouTube 影片。

但是會教導比 YouTube 影片知識還要多的內容

如果以後對這些文章有興趣的話，歡迎透過 RSS 來訂閱我的文章！

第一時間收到最新文章喔！[點我訂閱](https://blusewill.us.to/zh-tw/index.xml)

---

今天要來跟大家玩玩 Linux 要怎麼去入門他

應該要從哪裡開始？

我們會先從什麼確定不能在 Linux 上面使用

再到選擇你的第一個系統，還有系統安裝

最後再跟大家分享想要用 Windows 的程式還有學會這些東西可以做什麼

那廢話就不多說了，我們就進入文章吧！

## 學會斷捨離

到了 Linux 之後會有很多東西是原本不能用的

像是 Microsoft Office

Adobe 系列產品

有些遊戲的防外掛系統，你可以透過 https://protondb.com 來查看支援度

所以如果你是 Adobe 大粉絲，那你應該不適合純 Linux 系統

可能製作一個雙開機系統，比較適合你。

## 千萬不要聽信你朋友的亂配！

第一件事情要非常殘忍的跟大家說，你朋友有時候幫你推薦 Linux 系統的順序

很多時候其實都不太對，像是有一些像是不懂的就會說

> 喔！Ubuntu 好棒，很多廠商都是用 Ubuntu 呢！

> 用 Arch 拉！ Arch 是 Linux 的神耶！

> 用 Kail Linux 拉！在職場看起來你會是最酷的！

<del>如果上述這些朋友推薦給你這些東西，請你給他看[這部影片](https://youtu.be/korOpibkm6g)</del>

雖說各自都有自己的想法，但是我的順序是這樣的

1. 安裝一個簡單的系統，學會一些基礎終端機操作

1. 最後嘗試自己安裝出一個系統，不靠任何的界面安裝

1. 加大難度，嘗試在文字界面設計出自己的系統

那這三個順序也代表的是，三個系統

我接下來也會一個一個帶你們來看，除了使用這些系統。

安裝有什麼要注意的？

還有這個階段應該要學習什麼好？

## 接觸前，應該要做什麼準備

如果你是初次接觸 Linux 我建議你可以先從虛擬機或是你的備用電腦，或是有一些人可能會用樹莓派，來開始你的旅程。

這是為了要讓你可以了解 Linux 的最基礎的核心，終端機操作。

當然這個階段你也是玩玩，也沒有要到很進階！

<iframe title="一部影片內，學會用 Mac/Linux 的終端機！" width="560" height="315" src="https://wiwi.video/videos/embed/16ede971-369a-42ea-ae04-36e320a56e85" frameborder="0" allowfullscreen="" sandbox="allow-same-origin allow-scripts allow-popups allow-forms"></iframe>

那你也可以配合這部影片進行學習基礎的終端機！

## 選擇一個系統

接下來我們來講講應該要選擇什麼系統。

Linux 目前的系統有分以下兩種模式

1. Stable Release（穩定版）同時也叫 LTS（長期支援版本）

    那這種系統通常會非常的穩定，不會有一天自己因為而更新壞掉了

    代表系統：
    
    Fedora: 6 個月一次更新週期 
    
    對與想要穩定又不想要太老的系統，可以選擇此系統
    
    Debian: 24 個月一次更新週期 
    
    目前最常見到的 Linux 發行版，也是最穩定的，最建議安裝
    
    Red Hat (Rocky Linux): 10 年支援週期 
        
    比較多請況會在企業環境看到，因為套件非常的舊，所以適合不會更動的系統

1. Rolling Release (滾動發行版) 白話一點就是什麼都是最新的！

    那這種系統呢，更新的時候要特別注意，因為可能更新下去，電腦再也開不了機了，需要進行修復

    代表系統：
    
    Arch Linux

    OpenSUSE Tumbleweed

什麼！？看到這邊還沒有決定出來嗎...？

那我直接來幫你選吧！

**那就安裝 [Debian](https://debian.org)**

這是目前最穩定且最多教學的系統，最適合初學者了

之後我們在來安裝 [Arch Linux](https://archlinux.org)

這個雖說沒有到很穩定，但是他在 Linux 界因為套件支援度的原因，所以很知名！

那你說，**其他成千上百的 Linux 系統呢！？**

**我朋友跟我說他用 Arco Linux 耶？**

我這邊就要分享一個 Linux 的魅力，不管你今天用的是什麼系統

像是 Ubuntu 或是 Arco Linux 或是 Mint

其實就跟人一樣，有各種一樣的器官，只是包了不同的皮。

你可以看我當初製作救援密碼影片的時候就可以看到

我用 Arch Linux 的 ISO 更改了我在 Linux Mint 的帳號密碼

有興趣的可以去看看

{{< youtube CdRbjA8d4V4 >}}

## 初學者安裝

好選好了系統我們就要把他下載下來。

在寫文章的當下，我使用的版本是 debian-12.10.0

你可以到這裡來下載 Debian 的 ISO

https://www.debian.org/download.zh-tw.html

然後我們開機到 ISO 選擇安裝

### 安裝設定

![Debian Installer Language](../../img/Linux-Guide-2025/Debian-installer-language.png)

第一個步驟就是選擇語言，你選擇一個你偏好的語言就好。

我這邊為了教學使用中文

之後選擇你的地區

![Debian Installer Location](../../img/Linux-Guide-2025/Debian-installer-location.png) 

再來設定你的鍵盤，基本上都是預設就好

![Debian Installer Keyboard Layout](../../img/Linux-Guide-2025/Debian-installer-keyboard-layout.png)

之後他就會開始跑設定，就等等他一下！

再來設定你的主機名稱

![Debian installer Hostname](../../img/Linux-Guide-2025/Debian-installer-hostname.png)

然後網域名稱留空，日常使用不會用到

![Debian Installer Root Account](../../img/Linux-Guide-2025/Debian-installer-root.png)

### 使用者設定

之後我們就要來設定 Root 帳號的密碼，那這個就看人。

如果不設定的話就會直接停用，對安全性來說會比較好！

那我這邊就不設定了

![Debian Account Setup](../../img/Linux-Guide-2025/Debian-installation-account-setup.png)

之後我們來設定使用者，這邊他會要你填寫全名

那我的習慣就是兩個都設定一樣的

那 Debian 也很好的幫你把全名跟使用者名稱都設定成一樣的，直接按下一步就好

![Debian Account Password](../../img/Linux-Guide-2025/Debian-installer-password.png)

之後到了設定密碼，這個地方很重要！

Linux 系統**一定**要設定密碼，要不然你會沒有辦法使用很多東西。

你可以設定很簡單的密碼，也可以很複雜，你記的起來就好

### 磁碟分割

![Debian Installer Disk Utilty](../../img/Linux-Guide-2025/Debian-installer-disk-utilty.png)

之後我們就到了分割的部份，那你可以看到他這邊有導引，算是一個不錯的功能

那我們這邊就使用整顆硬碟 **注意：這會把你的所有資料都格式化掉**

![Debian Installer Select Hard Drive](../../img/Linux-Guide-2025/Debian-installer-select-harddrive.png)

選擇我們的硬碟之後按繼續，你就會發現一些神奇的選項

![Debian Installer Split Partition](../../img/Linux-Guide-2025/Debian-split-partition.png)

其實 Linux 可以把其中一個資料夾變成硬碟，不像是 Windows 有分 C:\ D:\

所以你其實可以把系統放在 128 GB 的 SSD 然後自己的 /home 放在 1TB 的 SSD

這樣可以做到空間最大化，重灌也會比較方便

那當然今天我們只有用一顆硬碟，所以我們就選最上面的不要獨立。

![Debian Installer Partition Confirm](../../img/Linux-Guide-2025/Debian-installer-partition-end.png)

之後我們就可以結束並且寫到磁碟中了！

### 真的在安裝系統了拉

之後他還會問一些小問題，像是設定 apt 或是熱門度測試

那 apt 的部份就選預設，除非你知道哪裡更快

熱門度測試就開心就好！

最重要的是，你要安裝什麼界面

會在這個畫面顯示出來

![Debian Installer Tasksel](../../img/Linux-Guide-2025/Debian-installer-tasksel.png)

那這就是其他上千個系統為什麼都長的不一樣的地方

有些人用的是 Mate 有些人用的是 KDE Plasma 有些人用的是 GNOME

那這邊就是推薦如果你是 Windows 使用者的話，建議用 KDE Plasma 會比較順手

如果你是用 MacOS 的話，用 GNOME 會對你來說比較順手！

給你們看一下他們兩個的樣子

![KDE Plasma](https://kde.org/announcements/plasma/6/6.3.0/fullscreen_with_apps.png)

> 來源 https://kde.org/

![GNOME Desktop](https://i0.wp.com/9to5linux.com/wp-content/uploads/2021/04/gnome41.jpg?fit=1920%2C1080&ssl=1)

> 來源 https://9to5linux.com

那當然也不是說其他桌面環境不好，但是這兩個是最常看到的桌面環境。

那他這邊預設是 GNOME 就安裝 GNOME 吧

![Debian Installation Complete](../../img/Linux-Guide-2025/Debian-installer-install-complete.png)

然後我們就安裝完成了！可以重開了

## 進入系統

![GDM](../../img/Linux-Guide-2025/GDM-login.png)

之後你就會看到鎖定畫面，依照你安裝的不同系統，會有不同的樣式

這個叫做 GDM (GNOME Display Manager)

如果你是安裝 KDE 你會看到 SDDM

![SDDM](https://preview.redd.it/i-tweaked-the-default-plasma-sddm-theme-to-make-the-clock-v0-y4rvm703qyla1.png?width=1920&format=png&auto=webp&s=6cf44de9951bdd931a06987fc5a9c0b80e5f92bc)

那一樣就是使用密碼登入，你就可以登入了！

## 認識安裝包管理器

每個系統的安裝包管理器都不一樣

我們安裝的系統是 Debian 用的是 `apt`

安裝指令是這樣

`sudo apt install {包名}`

這邊也配上其他系統會用到的安裝包

Pacman (Arch Linux)

`sudo pacman -S {包名}`

dnf (Fedora / RHEL)

`sudo dnf install {包名}`

## 進階版本

想必你已經看完上面的版本，就可以進入進階版本了

那這時候就是要派出 Arch Linux 的時候了！

這邊的話就不說 Arch Linux 要怎麼安裝了，如果有興趣的話

我可以在發一篇文章，現在的話你可以透過 ArchWiki 來看安裝教學

https://wiki.archlinux.org/title/Installation_guide_(%E6%AD%A3%E9%AB%94%E4%B8%AD%E6%96%87)

> Arch Wiki 是非常有用的參考資源，就算你不是用 Arch Linux 也可以看看

這時候你可以問一個問題，我想要用 DE 還是用 WM

DE (Desktop Enviroment) 代表的是**桌面環境**，也就是剛剛提到的 KDE Plasma 或是 GNOME

WM (Window Manager) 代表的是**視窗管理器**，有像是 Hyprland, bspwm, i3, 等等的選擇，通常視窗化管理器需要使用大量快捷鍵進行操作！

這個是 Hyprland 的樣子

![hyprland example](../../img/Linux-Guide-2025/WM-Exmaple.png)

你可以看到他會自動並排，這算是 WM 的特點，加上因為都使用快捷鍵的原因

可以在不同程式間快速切換！

## 我想要用 Windows 的程式...怎麼辦？

這不用擔心，在 Linux 上有可以轉譯 Windows 程式的插件

叫做 [Wine](https://winehq.org)

但是我還是比較建議，可以簡易管理的 [Bottles](https://usebottles.com/)

可以透過 Flatpak 來進行安裝

那當然 Steam 裡面也有 Proton 的選項

啟用之後可以在 Linux 上面遊玩 Linux 的遊戲


## 最後，我學會了 Linux 我可以做甚麼事情?

學會 Linux 之後，除了能在工作上更具競爭力外

你也會在過程中學到許多關於電腦系統的知識

比方說，你可以更有效率地管理硬碟空間。

很多人會將 Home 分區與 Root 分區分開，這樣就算 Root 所在的硬碟壞掉了，Home 分區的資料也能安全保留

還有像是 Linux 的 LUKS 硬碟加密功能，可以幫你加密筆電上的資料。

這樣如果筆電遺失，也不用太擔心個人資料外洩的風險。

如果你對虛擬化技術有興趣，Linux 的 [QEMU](https://www.qemu.org/) 是目前效能表現最強的虛擬機工具之一。

不僅可以安裝各種不同的系統，還能將顯示卡（GPU）直通到虛擬機中，讓效能幾乎等同於另一台電腦

有些人會利用這個特性，讓 Windows 在虛擬機中執行大型遊戲或創作軟體

再搭配 [Looking Glass](https://looking-glass.io/) 技術來取得幾乎無延遲的操作體驗。

所以說，學會 Linux 除了可以讓你變得更專業以外。

還能讓你探索許多新奇有趣的玩法，甚至是你從沒想過的可能性都能在這個系統上實現。

## 結語

以上就是 Linux 的入門教學，這是一個需要很多時間來入門的領域

也有很多人在中途放棄，但是在這個學習的路上，是很好玩的！

也希望大家可以用 Linux 用的開心

那我們下一篇文章見拉！掰掰！


<!--more-->
