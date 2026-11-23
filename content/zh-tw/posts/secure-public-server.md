---
title: 如何保護一個在公網上面的伺服器！
subtitle: 每天都被嘗試但不會被登入！
date: 2026-11-23T10:58:25+08:00
lastmod: 2026-11-23T10:58:25+08:00
slug: 4112316
draft: false
author: 
  name: blusewill
  link: https://blusewill.top/
  email: owner@blusewill.top
  avatar: /img/pfp.webp
description:
keywords:
comment: true
weight: 0
tags:
  - Linux
  - 網路資訊
  - 工具
  - 紀錄
categories:
  - 安全性教學
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

我不知道你有沒有遇過這種請況，當你第一次買了 VPS 然後設定好了之後

某一天跑去看 ssh (遠端登入) 的請求，才發現有 20 幾萬個嘗試登入請求

![SSH Login Request Example](/zh-tw/img/secure-public-server/WindowsTerminal_0Q5KfLuR7T.webp)

至少我是這樣啦，某一天發現有 20 幾萬個登入請求也是神奇了

但是在這 20 萬次的登入請求中只有 42 個成功登入的紀錄！

![SSH Successful Login](/zh-tw/img/secure-public-server/WindowsTerminal_pej3rcfWeu.webp)

然後確定都是我的電腦沒有錯！因為我的 ssh 金鑰也就只有那幾個

所以今天就要來分享一下，如何以最基礎的方式來保護你的公網 VPS

## 登入方式

第一個最重要的是登入方式了！比起使用傳統的打密碼登入

使用 ssh 金鑰會是比較安全的方案！

什麼是 ssh 金鑰呢？你就想像他是一個你家的鑰匙

然後伺服器就像是一個門，你會需要拿你的鑰匙打開這道門！

那其他人如果想要進來你家的話，除非拿到鑰匙要不然他們是進不來的！

這就是 ssh 金鑰的作用！他會同時擁有兩個檔案

一個是私鑰（鑰匙）一個是公鑰（大門）

你會需要拿你的私鑰去開公鑰來進行登入！

### 生成一個新的公私鑰

在任何的終端機或是 Windows 下的 Powershell 輸入 ssh-keygen

然後輸入你想要的檔案名稱

然後 ssh 金鑰的密碼你可以考慮留空或輸入！

基本上輸入密碼會更安全不過留空也不會不安全到哪裡去喔！

![ssh-keygen](/zh-tw/img/secure-public-server/WindowsTerminal_XcTFXcggAV.webp)

之後你剛剛生成的金鑰應該就會在你目前的資料夾裡面了！

### 放進去伺服器裡面

如果是預設的話，那就是會在以下這兩種資料夾

Linux : `$HOME/.ssh`

Windows : `%USERPROFILE%\.ssh`

你要找到的檔案是後綴有 .pub 的檔案

像是我這邊就是 `test-key.pub`

用記事本打開它你就會看到類似這種東西

`ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIDus5CHyNJqPhww6D/GpW3b66wLCtr1ynMtXJ5+fcQyr blusewill@DESKTOP-DQSKFKA`

接下來你要做的事情就是登入你的 VPS

然後 `sudo nano $HOME/.ssh/authorized_keys`

將你剛剛複製好的那一行放進去！

![ssh-keygen](/zh-tw/img/secure-public-server/WindowsTerminal_Np43iJ9Ahu.webp)

然後按 Ctrl + O 之後按 Enter 存檔

然後 Ctrl + X 退出！

### 關閉密碼登入

接下來你要做的事情就是關閉密碼的登入

畢竟你都拿到了大門的鑰匙，你也不需要用到通關密語了吧對不對！

那要關閉這個"通關密語"的話我們就只要編輯一行就好了！

在終端機打下這個指令 `sudo nano /etc/sshd_config`

之後把這些東西把這些選項改成 No

> Ctrl + W 可以進行搜尋

```
ChallengeResponseAuthentication no
PasswordAuthentication no
UsePAM no
```

然後按 Ctrl + O 之後按 Enter 存檔

然後 Ctrl + X 退出！

這樣設定就可以將使用登入密碼關閉了！

## 安裝防火牆

雖說你只要設定好金鑰登入應該就沒有問題了！

但是為了避免有人會想要去突破你伺服器全部的端口，那這樣防火牆就會非常的重要！

那這邊用的就會是 ufw 你可以在任何的 Linux 系統上面安裝到！

Debian : `sudo apt install ufw`

Fedora / RHEL : `sudo dnf install ufw`

Arch Linux : `sudo pacman -S ufw`

那如果你是網頁伺服器的話，你通常只會用到

**80 (HTTP)** 與 **443 (HTTPS)** 跟 **22 (SSH)** 的端口

> Cloudflare Proxy 只會用到這些端口，不用擔心網頁端口在 8080 之類的！

> 只需要用 [Caddy](https://caddyserver.com/) 或是 [Nginx](https://nginx.org/) 這些工具轉發端口到網站就可以了！

然後我們要限制其他的端口

那這時候只需要輸入以下指令

```
sudo ufw limit 22/tcp  
sudo ufw allow 80/tcp  
sudo ufw allow 443/tcp
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
```

就可以限制只有這些端口了才可以上了！

那如果以後有需要開放其他端口的話，就只要輸入

`sudo ufw allow {端口}/{tcp/udp}`

就可以了！

那現在就要來測試我們的防火牆是否有在運作

輸入 `sudo ufw status` 就可以查看目前的運作狀態

如果是 `active` 的話表示他目前是啟用的！

如果是 `inactive` 的話那可能就是設定上出了一些問題，或是你可能沒有打到 `sudo ufw enable` 這行指令喔！

> 當然如果你像是我伺服器廠商有內建防火牆功能的話，那就不一定要透過 ufw 來阻擋連線喔！

![Akamai Cloud Firewall](/zh-tw/img/secure-public-server/librewolf_oGiOH8OaKW.webp)

## 更進階的方案

如果你設定好以上還覺得不夠安全的話！

你可以新增一個使用者，對他添加 sudo 權限

就可以將 ssh 的 Root 登入關掉了！

一樣 `sudo nano /etc/sshd_config`

找到 `PermitRootLogin yes` 把它改成 `PermitRootLogin no`

然後按 Ctrl + O 之後按 Enter 存檔

然後 Ctrl + X 退出！

就沒有辦法透過 ssh 登入 Root 帳號了！

那當然你也可以限制 ssh 登入的 IP

但因為這通常都是大公司的設定，如果是一般的伺服器的話不會用到這麼複雜！

所以就不多做說明了！

接下來就是不要讓這些機器人們有無限次的 ssh 登入嘗試

你可以安裝 fail2ban 這樣子如果他們嘗試到一定次數之後 IP 就會被 BAN 掉一天！

Debian : `sudo apt install fail2ban`

Fedora / RHEL : `sudo dnf install fail2ban`

Arch : `sudo pacman -S fail2ban`

之後將他啟動！

systemd : `sudo systemd enable fail2ban --now`

OpenRC : 

```
sudo rc-service fail2ban start
sudo rc-update add fail2ban default
```

這樣 SSH 的嘗試次數就會少一點！

那當然還有很多的方法，但是這樣子通常就可以擋下 90% 的攻擊了！

如果有更好的點子的話！可以在下面留言分享一下你們是怎麼防護伺服器的喔！

那這邊就是小品大大，我們下一篇文章見！
