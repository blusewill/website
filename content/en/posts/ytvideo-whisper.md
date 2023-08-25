---
title: "Auto Subtitle Generator"
subtitle: ""
date: 2023-08-03T13:45:44+08:00
lastmod: 2023-08-03T13:45:44+08:00
draft: false
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
- Whisper
- AI
- Python
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
---
Tired of being type all of the subtitles by your self?

Well [ytvideo-whisper](https://github.com/blusewill/ytvideo-whisper) is here to help!

## Usage
There is Various of Different Usage Depends on your self

No matter you want to use Your own Server or Computer or the Google Colab Service

We all got you Covered!

### Google Colab

[Click This to Run in Google Colab](https://colab.research.google.com/github/blusewill/ytvideo-whisper/blob/master/ytvideo_whisper.ipynb)

First thing you want to select is your Download Method, We have 3 ways to let you download your srt file

You can use your favorite to Download it such as Google Drive | anonfiles | Direct Download (**NOT RECOMMENDED**)

![Download Method](/img/ytvideo-whisper/2023-07-20_19-01.png)

And the Next thing you want to do is change the Settings

![Settings](/img/ytvideo-whisper/2023-07-20_19-07.png)

Don't be panic when you see these options

It's Very Easy to Understand all of these options with the easy way to explain it.

---

`YouTube_Video_Link` You Have to Put your Video Link here.

`new_filename` The filename of the subtitle file.

`language` The language that is going to be Transcribe/Translate. If you want to Let it auto detect the Video language leave it blank.

`task` Do you want to Translate this Video or Transcribe this Video if you want to Translate `language` is a must option.

`Generate_Plain_Document` If will Generate a txt file along with the Subtitle File

`shutdown_after_complete` Shutdown the Google Colab Container After finishing Generating Subtitle

`model_user` The Model you are going to use. In my test I can use Medium in most of the time.

`enable_cookies` This will let you grab the Private Video in YouTube. You might have to use some tool like [EditThisCookie](https://chrome.google.com/webstore/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg) or [Cookie-Editor](https://addons.mozilla.org/en-US/firefox/addon/cookie-editor/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search)

**Not Recommended** to use your main account to do this. If you want to keep the Video Private Best way is set to **unlisted Video** instead of Private Video

---

After all of the Settings has been setup, next we are going to do is check your GPU in Google Colab is enabled or not.

Go to `Runtime` -> `Change Runtime type` to check your GPU is enabled or not.

![Runtime Type](content/en/img/ytvideo-whisper/2023-07-20_19-28.png)

Make sure change the GPU type to T4 to Enable it (Free Version)

And now click `Runtime` -> `Run All` to Finish the setup

And After a Moment your File Should be on `Google Drive` -> `Whisper` -> `Result` Folder

If is anonfile there will a link at `If Google Drive Gets Disabled` Section

### local Version

First because of Windows Version of Python can't use GPU (Haven't setup a conda setup process) So at here I will demo it by using Ubuntu Server 22.04

First what you have to do is Clone the ytvideo-whisper Projct by typing

```
git clone https://github.com/blusewill/ytvideo-whisper && cd ytvideo-whisper
```

And you have to install Python 3 

```
sudo apt install python3 python3-pip
```

Also install the Requirement Python Package by using pip

```
pip3 install -r requirement.txt
```

After all of the Package got installed you have to do is type this command
```
python3 start.py
```
Now Paste your YouTube Video! For Example ``https://youtu.be/-Iep2_q6cyo``

And you will need to use the arrow key to select your options

such as `model` `translate/transcribe` `language` and more!

And your file should be generated in Generated Folder!

# Walkthrough Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/-Iep2_q6cyo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
