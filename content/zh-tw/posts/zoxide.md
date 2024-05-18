---
title: zoxide 一個可以在終端機快速移動資料夾的工具
subtitle:
date: 2024-05-19T00:06:12+08:00
slug: 8ce0a21
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
  - Windows
  - 終端機  
categories:
  - 終端機工具
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

你有沒有想過，怎麼在終端機裡面怎麼快速移動呢？

我們通常都是會慢慢的 `cd` 進去我們想要的資料夾

想是我今天要進去 `$HOME/.tmp` 資料夾就要打 `cd $HOME/.tmp`

那當然，這速度太慢了，尤其如果你要打更長的路徑的話你會打到崩潰。

## 所以今天的主角 zoxide 就出來了

你可以想像 zoxide 是一位管家，他會看你平常的習慣。

之後你就可以跟他說，我要去二樓就會直接帶你去二樓。

zoxide 就是那位幫助你快速移動的管家，你就只要動動嘴巴就好！

![左邊是沒有使用 zoxide 右邊是使用了 zoxide](../../img/zoxide/preview.png)

那知道對 Linux 很熟悉的人就知道，這不就是 autojump 嗎？

確實，但是 zoxide 比 autojump 還有很多優點

## zoxide 的優點

**可以在不同的 shell 使用** : 基本上你可以想像到的，像是 Powershell, bash, zsh, fish 都可以使用 zoxide

**用方向鍵來選擇資料夾** : 你可以使用 `zi` 他會調用 `fzf` 來給你進行選擇你要去哪一個資料夾。

![zi command](../../img/zoxide/zi.png)

**安裝相當簡單** : 不管你是用 Windows / Mac / Linux 都可以非常間單的安裝 zoxide

## zoxide 基礎指令

**z {資料夾名稱}** : 跳到最常打開的相近名稱的資料夾，你不一定要打出全名也可以。 

**z {資料夾路徑}** : 就跟 cd 一樣，可以到你想要的資料夾

**z ..** : 回到上一層目錄

範例

`/home/blusewill/.local/bin`

`z ..`

`/home/blusewill/.local/`

**z -** 回到上一個目錄

範例

`/home/blusewill/.local`

`z git`

`/home/blusewill/Documents/GitHub/`

`z -`

`/home/blusewill/.local`

## 安裝 zoxide

那 Linux 他們是建議透過以下腳本安裝

`curl -sSfL https://raw.githubusercontent.com/ajeetdsouza/zoxide/main/install.sh | sh`

Windows 可以透過 winget 進行安裝

`winget install ajeetdsouza.zoxide`

### 設定 shell

那不同的 shell 有不同的方式，我這邊舉例最常用到的 bash 跟 powershell

Bash : ~/.bashrc

`eval "$(zoxide init bash)"`

Powershell : $PROFILE **(要加在最後面)**

`Invoke-Expression (& { (zoxide init powershell | Out-String) })`

最後就是安裝 fzf (如果你要用 zi 指令的話)

[點我前往 fzf 的安裝教學](https://github.com/junegunn/fzf#installation)

那我也有一些沒有列出來的，就請去他們的 GitHub 看摟！

[點我看更多安裝 zoxide 的方法](https://github.com/ajeetdsouza/zoxide#installation)


## 結語

總之 zoxide 是一個你應該要用的終端機工具，他可以省下你在終端機裡面 cd 的時間

也希望這工具有幫助到大家！

那我們就下一篇文章見了，掰掰！
