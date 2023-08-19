# Windows 11 完美安裝教學

安裝Windows 11可以是一件麻煩的事情，尤其是你後面安裝之後刪除很多你不會用到的程式，像是抖音,Netflix等等的程式。

![Screenshot of Windows 11 Start Menu](https://www.bleepstatic.com/images/news/Microsoft/windows-11/s/start-menu-classic/Windows-11-start-menu.jpg)

如果我們有辦法在安裝的時候直接把他刪掉會不會比較快呢?

## 安裝的一個小細節

我不知道大家打開Windows的安裝是第幾次了，但是你有沒有用過中間的那三個選單呢?

![Screenshot of Windows Installation CD](https://hipay0.com/wp-content/uploads/2022/10/10-Windows-11-installation-language.webp)

我想信大家都跟我一樣，會直接按下下一步的按鈕。

但是你知道嗎？只要把`時間與貨幣格式`改成`英文(世界)`他就不會有任何的垃圾App。

這是來自國外的[ctrl.blog](https://www.ctrl.blog/entry/windows-ooberegion-bloatware.html)的一篇文章。

但是最近因為國外YouTuber ThioJoe 的提及讓大部分的人都知道了這個技巧。

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Did you know you can install Windows 11 without any bloatware simply by selecting &quot;English (World)&quot; as the Time &amp; Currency format at the initial install? <a href="https://t.co/l5Mwr2pgmP">pic.twitter.com/l5Mwr2pgmP</a></p>&mdash; ThioJoe (@thiojoe) <a href="https://twitter.com/thiojoe/status/1686565269907636224?ref_src=twsrc%5Etfw">August 2, 2023</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

所以我們要把`世界與貨幣格式`改成`英文(世界)`這樣就可以減少你要刪除垃圾軟體的時間了。

Ps.還可以順便停用微軟商店，如果你不會用到的話可以繼續留在這個設定

## 但是這樣才剛剛開始

這樣解除安裝之後可能對大部分人來講已經夠了，但是我們才剛剛開始，現在我們基本上還是在很原本的Windows 11狀態。

所以我們現在要派出國外科技YouTuber [ChrisTitusTech](https://christitus.com) 的[Winutil](https://github.com/christitustech/winutil)工具箱

因為我們接下來要關閉的是可能會影響你的電腦效能的設定

現在按下`Win + X`用管理員打開Powershell (或是終端機)

然後輸入 `irm christitus.com/win | iex` 就可以叫出我們的工具箱

接下來我們到`Tweaks`畫面，上面已經有給你一些選項，像筆電就用Laptop，桌機就按Desktop。

之後按下`Run Tweaks` 他就會開始關閉一些影響效能的一些東西。

之後會有一個彈窗寫All Done代表已經跑完了全部的設定。

### 刪除那不好用的Edge (選用)

你的工具箱應該還是開著的吧？

如果是的話先到 `Install` 安裝你想要安裝的瀏覽器

安裝完之後在到`Tweaks`打勾`Remove Microsoft Edge`之後按Run

你的Edge就會消失不見了

我們的乾淨Windows 11也就這樣安裝完了！

有任何的問題也都可以在下面留言歐!

# 影片教學

{{< youtube E89MQjgMMxY >}}

