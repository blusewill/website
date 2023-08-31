---
title: Minecraft伺服器架設懶人包
subtitle:
date: 2023-08-25T15:41:09+08:00
draft: true
author:
  name: blusewill
  link: https://buymeacoffee.com/blusewill
  email: blusewillstudio@pm.me
  avatar:
description:
keywords:
license:
comment: true
weight: 0
tags:
categories:
hiddenFromHomePage: true 
hiddenFromSearch: false
summary:
resources:
toc: true
math: false
lightgallery: false
password:
message:
share:
    enable: true
# See details front matter: https://fixit.lruihao.cn/documentation/content-management/introduction/#front-matter
---
你也想要開始架設你自己的Minecraft伺服器了嘛?

你也想要跟很多人一樣開24小時不關機的伺服器嗎?

那這樣你來對地方了！今天我要教你如何架設，原版，模組，跟插件伺服器！

# 一切都先從安裝Java開始
在Debian安裝Java非常簡單，我們就只要 
```
sudo apt install openjdk-17-jre
```
就可以下載到我們的Java17了，那當然不同的Minecraft也會有不同的Java版本

像是1.8的版本你可能需要 Java8

## 原版伺服器架設

原版伺服器架設其實是最簡單的一個，我們先到他的[下載伺服器](https://www.minecraft.net/en-us/download/server)頁面下載伺服器檔案server.jar

那在不同的情況會用到不同的方式來下載這個檔案

### SSH 上傳
你可以在你的電腦上使用scp來上傳你的伺服器檔案

你只需要在你的終端機輸入

`` scp <伺服器檔案> <伺服器使用者>@<伺服器IP>:<檔案地點>``

就可以透過SSH來上傳伺服器檔案

### FTP 伺服器上傳
如果你的伺服器廠商有FTP直接給你用的話，你可以直接使用一些工具像是[FileZilla](https://filezilla-project.org/)直接丟進去

但是如果沒有的話你就要自己架設一個FTP伺服器

#### FTP伺服器架設
在這一段我將會跟你講如何架設一個簡單的FTP伺服器，我們使用的範例是Debian 12所以可能對與其他的系統會有一些不同

我們先來安裝一下FTP伺服器軟體，我這邊用的是vsftpd

```
sudo apt install vsftpd
```
安裝完之後我們需要備份一下設定的檔案，避免出了任何差錯
```
sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.orig
```
之後我們編輯vsftpd.conf這個檔案 (我用的是vim但是你們也可以用簡單的文字編輯器像是nano)
```
sudo vim vsftpd.conf
```
之後我們要把`write_enable=YES`前面的#刪掉存檔，然後再來自啟動我們的FTP伺服器
```
sudo systemctl enable vsftpd --now
```
這樣你的FTP伺服器就可以架設好了
### 直接在伺服器下載檔案
這應該是簡單又最直接的方法，你就只要輸入
```
curl <Minecarft伺服器的下載網址> -o server.jar
```
就好了

之後我們要複製Minecraft官網下面給我們的直令

因為我們需要這個來啟動我們的Minecraft伺服器

我們新增一個server.sh的文件然後輸入

```
java -Xmx<給伺服器的最大記憶體容量> -Xms<給伺服器的最小記憶體容量> -jar <伺服器檔案> nogui
```
範例
```
java -Xmx1024M -Xms1024M -jar minecraft_server.1.20.1.jar nogui
```
之後輸入
`chmod +x server.sh`

然後打開這個文件

然後你就會看到以下內容

`[16:47:33] [ServerMain/INFO]: You need to agree to the EULA in order to run the server. Go to eula.txt for more info.`

我們接下來編輯Eula的文件，把`eula=false`改成`eula=true`

之後在啟動一次，你的原版伺服器就開始在啟動了，接下來看到

`[16:50:03] [Server thread/INFO]: Done (27.814s)! For help, type "help"`

就表示你可以進去玩摟！

## 模組伺服器架設
當然剛剛那個是原版的伺服器，現在來講大家都感興趣的模組伺服器！

### Forge伺服器
因為Forge是伺服器中最偏麻煩的一個，所以我打算從Forge開始

我們先到Forge的[官網](https://files.minecraftforge.net/net/minecraftforge/forge/)下載Installer

你可以透過我們剛剛講的 SSH,FTP,直線下載來下載

之後我們輸入
```
java -jar <Forge的檔案> --installServer
```
這時候它就會安裝到Forge伺服器到你自己的資料夾

之後你就可以打`./run.sh`同意Eula後就可以啟動你的Forge伺服器拉

但是他的預設是會有GUI的，所以你如果不想看到GUI的話你就要編輯`run.sh`

在`"$@"`的前面加上`nogui`就不會有GUI了

### Fabric伺服器
Fabric伺服器擁有最簡單的架設，跟原版幾乎一樣

我們先到Fabric下載伺服器的[網站](https://fabricmc.net/use/server/)

你就可以直接看到curl的直令

我們就複製那一行，然後輸入到我們的終端機裡面

接下來創建一個server.sh的文件

把下面的那一行JVM貼上

存檔過後輸入`chmod +x server.sh`

同意eula過後啟動伺服器，你就架設好Fabric的伺服器摟！

## 插件伺服器架設
好現在你想要做出一個Minecraft伺服器，裡面有非常多的小遊戲，但是你又不想要安裝模組？

這時候插件伺服器就來了，基本上有了插件伺服器你就可以跟你的朋友用原版Minecraft玩遊戲了！

但是因為插件伺服器有非常多的選擇，所以我今天只會講到一個現在最有名的[PaperMC](https://papermc.io/)

我們先來下載Paper伺服器，你可以透過SSH，FTP，直線下載來下載伺服器檔案

下載完之後呢我們要在開一個新的文件`server.sh`

輸入 `java -jar <伺服器檔案>`

之後`chmod +x server.sh`

之後同意Eula之後基本上就可以開始你的服主之旅了！

## 結語
很多人跟我說過安裝Minecraft伺服器很困難，其實並不會

真正困難的是你後續的維護，跟你的玩家族群。

這篇文章最後要告訴大家的是，如果你想要做出你想要的伺服器，就請不要讓你的玩家失望

要不然你會成為下一個[Housemaster](https://2b2t.org/update/)

謝謝大家看到這邊，我們下一篇文章見