---
title: "這是最棒的音樂播放器"
subtitle: ""
date: 2022-11-28T23:49:14+08:00
lastmod: 2022-11-28T23:49:14+08:00
draft: false
author: "blusewill"
authorLink: "https://www.buymeacoffee.com/blusewill"
description: ""
license: ""
images: []

tags: [mpd,music,setup]
categories: []

featuredImage: ""
featuredImagePreview: ""

hiddenFromHomePage: true
hiddenFromSearch: false
twemoji: false
lightgallery: false
ruby: false
fraction: false
fontawesome: true
linkToMarkdown: false
rssFullText: true

toc: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: []
  # ...
---
說到音樂播放，相信大家都會想到VLC，MPC-HC，Amberoi，mpv等等的多媒體播放器</p>
但是我告訴你，有一個音樂播放器非常的好用，它可以在自己的電腦播放，可以音樂串流，甚至可以聽音樂電台</p>
沒錯這個東西就是我們今天的主角**mpd**。
# 為什麼mpd是最好用的音樂播放器
當時接觸mpd是因為一個基於Arch Linux的系統[Archcraft](https://archcraft.io/)它上面有一個音樂播放器，我想說這個是什麼音樂播放器可以把目前播放的音樂寫在上面，最後竟然發現是mpd播放器就讓我如此的好奇想要讓我研究一番，最後到今天我用了mpd一個月，我可以跟大家說mpd是一個有無限潛力的音樂播放器，它可以讓你想不到音樂播放器有如此多的用途，也是我決的mpd是最好用的音樂播放器之一。
# 我目前的設定
我現在是用[myMPD](https://github.com/jcorporation/myMPD)當做我目前的音樂播放界面，那當然不只有myMPD，mpd的音樂播放界面還有很多，以下是一些例子</p>

可以客製化到很恐怖的地步的終端機音樂播放界面的 : [ncmpcpp](https://github.com/ncmpcpp/ncmpcpp)
![ncmpcpp](https://arcolinux.com/wp-content/uploads/2018/01/mpd-ncmpcpp.jpg)
</p>

跟間單好用的 : [mpdevil](https://github.com/SoongNoonien/mpdevil)


![mpddevil](https://github.com/SoongNoonien/mpdevil/raw/master/screenshots/mainwindow_1.9.0.png)
# mpd安裝
Debian / Ubuntu (Nix) **建議**
```
nix-env -iA nixpkgs.mpd
```
Arch Linux
```
sudo pacman -Sy mpd
```
Fedora **(建議也使用nix)**
```
sudo dnf install mpd
```
# mpd設定
我的mpd設定長這個樣子
```
## Copyright (C) 2020-2021 Aditya Shakya <adi1090x@gmail.com>
## Everyone is permitted to copy and distribute copies of this file under GNU-GPL3

music_directory "~/music"
playlist_directory "~/.mpd/playlists"
db_file "~/.mpd/mpd.db"
log_file "~/.mpd/mpd.log"
pid_file "~/.mpd/mpd.pid"
state_file "~/.mpd/mpdstate"

audio_output {
        type "pulse"
        name "pulse audio"
}

audio_output {
	type                    "fifo"
	name                    "my_fifo"
	path                    "/tmp/mpd.fifo"
	format                  "44100:16:2"
}

audio_output {
    type        "httpd"
    name        "HTTP Stream"
    encoder     "lame" #to support safari on ios
    port        "8000"
    bitrate     "128"
    format      "44100:16:1"
    always_on   "yes"
    tags        "yes"
}

bind_to_address "127.0.0.1"
port "6600"
```
但是我建議大家去下載[原本的檔案](https://raw.githubusercontent.com/andrewrk/mpd/master/doc/mpdconf.example)，這樣才比較穩定歐</p>
或是直接在這裡複製
```
# An example configuration file for MPD
# See the mpd.conf man page for a more detailed description of each parameter.


# Files and directories #######################################################
#
# This setting controls the top directory which MPD will search to discover the
# available audio files and add them to the daemon's online database. This 
# setting defaults to the XDG directory, otherwise the music directory will be
# be disabled and audio files will only be accepted over ipc socket (using
# file:// protocol) or streaming files over an accepted protocol.
#
#music_directory		"~/music"
#
# This setting sets the MPD internal playlist directory. The purpose of this
# directory is storage for playlists created by MPD. The server will use 
# playlist files not created by the server but only if they are in the MPD
# format. This setting defaults to playlist saving being disabled.
#
#playlist_directory		"~/.mpd/playlists"
#
# This setting sets the location of the MPD database. This file is used to
# load the database at server start up and store the database while the 
# server is not up. This setting defaults to disabled which will allow
# MPD to accept files over ipc socket (using file:// protocol) or streaming
# files over an accepted protocol.
#
#db_file			"~/.mpd/database"
# 
# These settings are the locations for the daemon log files for the daemon.
# These logs are great for troubleshooting, depending on your log_level
# settings.
#
# The special value "syslog" makes MPD use the local syslog daemon. This
# setting defaults to logging to syslog, otherwise logging is disabled.
#
#log_file			"~/.mpd/log"
#
# This setting sets the location of the file which stores the process ID
# for use of mpd --kill and some init scripts. This setting is disabled by
# default and the pid file will not be stored.
#
#pid_file			"~/.mpd/pid"
#
# This setting sets the location of the file which contains information about
# most variables to get MPD back into the same general shape it was in before
# it was brought down. This setting is disabled by default and the server 
# state will be reset on server start up.
#
#state_file			"~/.mpd/state"
#
# The location of the sticker database.  This is a database which
# manages dynamic information attached to songs.
#
#sticker_file			"~/.mpd/sticker.sql"
#
###############################################################################


# General music daemon options ################################################
#
# This setting specifies the user that MPD will run as. MPD should never run as
# root and you may use this setting to make MPD change its user ID after
# initialization. This setting is disabled by default and MPD is run as the
# current user.
#
#user				"nobody"
#
# This setting specifies the group that MPD will run as. If not specified
# primary group of user specified with "user" setting will be used (if set).
# This is useful if MPD needs to be a member of group such as "audio" to
# have permission to use sound card.
#
#group				"nogroup"
#
# This setting sets the address for the daemon to listen on. Careful attention
# should be paid if this is assigned to anything other then the default, any.
# This setting can deny access to control of the daemon.
#
# For network
#bind_to_address		"any"
#
# And for Unix Socket
#bind_to_address		"~/.mpd/socket"
#
# This setting is the TCP port that is desired for the daemon to get assigned
# to.
#
#port				"6600"
#
# This setting controls the type of information which is logged. Available 
# setting arguments are "default", "secure" or "verbose". The "verbose" setting
# argument is recommended for troubleshooting, though can quickly stretch
# available resources on limited hardware storage.
#
#log_level			"default"
#
# If you have a problem with your MP3s ending abruptly it is recommended that 
# you set this argument to "no" to attempt to fix the problem. If this solves
# the problem, it is highly recommended to fix the MP3 files with vbrfix
# (available from <http://www.willwap.co.uk/Programs/vbrfix.php>), at which
# point gapless MP3 playback can be enabled.
#
#gapless_mp3_playback			"yes"
#
# Setting "restore_paused" to "yes" puts MPD into pause mode instead
# of starting playback after startup.
#
#restore_paused "no"
#
# This setting enables MPD to create playlists in a format usable by other
# music players.
#
#save_absolute_paths_in_playlists	"no"
#
# This setting defines a list of tag types that will be extracted during the 
# audio file discovery process. Optionally, 'comment' can be added to this
# list.
#
#metadata_to_use	"artist,album,title,track,name,genre,date,composer,performer,disc"
#
# This setting enables automatic update of MPD's database when files in 
# music_directory are changed.
#
#auto_update	"yes"
#
# Limit the depth of the directories being watched, 0 means only watch
# the music directory itself.  There is no limit by default.
#
#auto_update_depth "3"
#
###############################################################################


# Symbolic link behavior ######################################################
#
# If this setting is set to "yes", MPD will discover audio files by following 
# symbolic links outside of the configured music_directory.
#
#follow_outside_symlinks	"yes"
#
# If this setting is set to "yes", MPD will discover audio files by following
# symbolic links inside of the configured music_directory.
#
#follow_inside_symlinks		"yes"
#
###############################################################################


# Zeroconf / Avahi Service Discovery ##########################################
#
# If this setting is set to "yes", service information will be published with
# Zeroconf / Avahi.
#
#zeroconf_enabled		"yes"
#
# The argument to this setting will be the Zeroconf / Avahi unique name for
# this MPD server on the network.
#
#zeroconf_name			"Music Player"
#
###############################################################################


# Permissions #################################################################
#
# If this setting is set, MPD will require password authorization. The password
# can setting can be specified multiple times for different password profiles.
#
#password                        "password@read,add,control,admin"
#
# This setting specifies the permissions a user has who has not yet logged in. 
#
#default_permissions             "read,add,control,admin"
#
###############################################################################


# Input #######################################################################
#

input {
        plugin "curl"
#       proxy "proxy.isp.com:8080"
#       proxy_user "user"
#       proxy_password "password"
}

#
###############################################################################

# Audio Output ################################################################
#
# MPD supports various audio output types, as well as playing through multiple 
# audio outputs at the same time, through multiple audio_output settings 
# blocks. Setting this block is optional, though the server will only attempt
# autodetection for one sound card.
#
# See <http://mpd.wikia.com/wiki/Configuration#Audio_Outputs> for examples of 
# other audio outputs.
#
# An example of an ALSA output:
#
#audio_output {
#	type		"alsa"
#	name		"My ALSA Device"
##	device		"hw:0,0"	# optional
##	format		"44100:16:2"	# optional
##	mixer_type      "hardware"	# optional
##	mixer_device	"default"	# optional
##	mixer_control	"PCM"		# optional
##	mixer_index	"0"		# optional
#}
#
# An example of an OSS output:
#
#audio_output {
#	type		"oss"
#	name		"My OSS Device"
##	device		"/dev/dsp"	# optional
##	format		"44100:16:2"	# optional
##	mixer_type      "hardware"	# optional
##	mixer_device	"/dev/mixer"	# optional
##	mixer_control	"PCM"		# optional
#}
#
# An example of a shout output (for streaming to Icecast):
#
#audio_output {
#	type		"shout"
#	encoding	"ogg"			# optional
#	name		"My Shout Stream"
#	host		"localhost"
#	port		"8000"
#	mount		"/mpd.ogg"
#	password	"hackme"
#	quality		"5.0"
#	bitrate		"128"
#	format		"44100:16:1"
##	protocol	"icecast2"		# optional
##	user		"source"		# optional
##	description	"My Stream Description"	# optional
##	url		"http://example.com"	# optional
##	genre		"jazz"			# optional
##	public		"no"			# optional
##	timeout		"2"			# optional
##	mixer_type      "software"		# optional
#}
#
# An example of a recorder output:
#
#audio_output {
#	type		"recorder"
#	name		"My recorder"
#	encoder		"vorbis"		# optional, vorbis or lame
#	path		"/var/lib/mpd/recorder/mpd.ogg"
##	quality		"5.0"			# do not define if bitrate is defined
#	bitrate		"128"			# do not define if quality is defined
#	format		"44100:16:1"
#}
#
# An example of a httpd output (built-in HTTP streaming server):
#
#audio_output {
#	type		"httpd"
#	name		"My HTTP Stream"
#	encoder		"vorbis"		# optional, vorbis or lame
#	port		"8000"
#	bind_to_address	"0.0.0.0"		# optional, IPv4 or IPv6
##	quality		"5.0"			# do not define if bitrate is defined
#	bitrate		"128"			# do not define if quality is defined
#	format		"44100:16:1"
#	max_clients	"0"			# optional 0=no limit
#}
#
# An example of a pulseaudio output (streaming to a remote pulseaudio server)
#
#audio_output {
#	type		"pulse"
#	name		"My Pulse Output"
##	server		"remote_server"		# optional
##	sink		"remote_server_sink"	# optional
#}
#
## Example "pipe" output:
#
#audio_output {
#	type		"pipe"
#	name		"my pipe"
#	command		"aplay -f cd 2>/dev/null"
## Or if you're want to use AudioCompress
#	command		"AudioCompress -m | aplay -f cd 2>/dev/null"
## Or to send raw PCM stream through PCM:
#	command		"nc example.org 8765"
#	format		"44100:16:2"
#}
#
## An example of a null output (for no audio output):
#
#audio_output {
#	type		"null"
#	name		"My Null Output"
#	mixer_type      "none"			# optional
#}
#
# This setting will change all decoded audio to be converted to the specified
# format before being passed to the audio outputs. By default, this setting is
# disabled.
#
#audio_output_format		"44100:16:2"
#
# If MPD has been compiled with libsamplerate support, this setting specifies 
# the sample rate converter to use.  Possible values can be found in the 
# mpd.conf man page or the libsamplerate documentation. By default, this is
# setting is disabled.
#
#samplerate_converter		"Fastest Sinc Interpolator"
#
###############################################################################


# Normalization automatic volume adjustments ##################################
#
# This setting specifies the type of ReplayGain to use. This setting can have
# the argument "off", "album" or "track". See <http://www.replaygain.org>
# for more details. This setting is off by default.
#
#replaygain			"album"
#
# This setting sets the pre-amp used for files that have ReplayGain tags. By
# default this setting is disabled.
#
#replaygain_preamp		"0"
#
# This setting enables on-the-fly normalization volume adjustment. This will
# result in the volume of all playing audio to be adjusted so the output has 
# equal "loudness". This setting is disabled by default.
#
#volume_normalization		"no"
#
###############################################################################


# MPD Internal Buffering ######################################################
#
# This setting adjusts the size of internal decoded audio buffering. Changing
# this may have undesired effects. Don't change this if you don't know what you
# are doing.
#
#audio_buffer_size		"2048"
#
# This setting controls the percentage of the buffer which is filled before 
# beginning to play. Increasing this reduces the chance of audio file skipping, 
# at the cost of increased time prior to audio playback.
#
#buffer_before_play		"10%"
#
###############################################################################


# Resource Limitations ########################################################
#
# These settings are various limitations to prevent MPD from using too many
# resources. Generally, these settings should be minimized to prevent security
# risks, depending on the operating resources.
#
#connection_timeout		"60"
#max_connections		"10"
#max_playlist_length		"16384"
#max_command_list_size		"2048"
#max_output_buffer_size		"8192"
#
###############################################################################


# Character Encoding ##########################################################
#
# If file or directory names do not display correctly for your locale then you 
# may need to modify this setting.
#
#filesystem_charset		"UTF-8"
#
# This setting controls the encoding that ID3v1 tags should be converted from.
#
#id3v1_encoding			"ISO-8859-1"
#
###############################################################################


# SIDPlay decoder #############################################################
#
# songlength_database:
#  Location of your songlengths file, as distributed with the HVSC.
#  The sidplay plugin checks this for matching MD5 fingerprints.
#  See http://www.c64.org/HVSC/DOCUMENTS/Songlengths.faq
#
# default_songlength:
#  This is the default playing time in seconds for songs not in the
#  songlength database, or in case you're not using a database.
#  A value of 0 means play indefinitely.
#
# filter:
#  Turns the SID filter emulation on or off.
#
#decoder {
#	plugin			"sidplay"
#	songlength_database	"/media/C64Music/DOCUMENTS/Songlengths.txt"
#	default_songlength	"120"
#	filter "true"
#}
#
###############################################################################
```
由於我對這謝設定沒有非常多的認識，所以我只會講一些基礎的設定</p>

`music_directory` 你的音樂資料夾</p>
`playlist_directory` 你的播放清單放置處</p>
`db_file` 你的資料庫檔案</p>
`log_file` 你的紀錄檔案</p>
`pid_file` mpd的執行代號 （在關閉mpd的時候會用到）</p>
`state_file` 音樂播放紀錄</p>
`bind_to_address` 指定IP位置</p>
`port` 指定端口

---
## 音訊輸出部份
`audio_output` 音訊輸出</p>
`type` 輸出種類如 (pulseaudio , pipewire, httpd)</p>
`name` 輸出的名子</p>

---
那其他的你可以自己去研究，我在這裡就不多做說明

# myMPD架設

那myMPD架設的方式其實非常的多，以下是安裝的直令，根據系統會有些不同</p>

Debian/Ubuntu :
```
curl http://download.opensuse.org/repositories/home:/jcorporation/Debian_11/Release.key | gpg --no-default-keyring --keyring /usr/share/keyrings/jcorporation.github.io.gpg --import ;

gpg --no-default-keyring --keyring /usr/share/keyrings/jcorporation.github.io.gpg --fingerprint ;

source /etc/os-release ;
echo $VERSION_ID ;

apt update ;
apt install mympd ;

```
Arch : 
`` sudo pacman -Sy mympd`` </p>
你也可以用Docker架設

Docker Compose:

```
---
version: "3.x"
services:
  mympd:
    image: ghcr.io/jcorporation/mympd/mympd
    container_name: mympd
    network_mode: "host"
    environment:
      - TZ=Europe/London
      - UMASK_SET=022 #optional
      - MYMPD_SSL=false
    volumes:
      - /path/to/mpd/socket:/run/mpd/socket #optional, use if you connect to mpd using sockets
      - /path/to/mympd/docker/dir:/var/lib/mympd/
      - /path/to/music/dir/:/music/:ro
      - /path/to/playlists/dir/:/playlists/:ro
    restart: unless-stopped
```
Docker CLI:

```
docker run -d \
  --name=mympd \
  --net="host" \
  -e TZ=Europe/London \
  -e UMASK_SET=022 \
  -e MYMPD_SSL=false \
  -v /path/to/mpd/socket:/run/mpd/socket \
  -v /path/to/mympd/docker/dir:/var/lib/mympd/ \
  -v /path/to/music/dir/:/music/:ro \
  -v /path/to/playlists/dir/:/playlists/:ro \
  --restart unless-stopped \
  ghcr.io/jcorporation/mympd/mympd
```

## 開機自啟動

你可以設定myMPD開機啟動用

``systemctl enable mympd`` 
或是利用直令mympd開啟

之後你就可以在網址列打localhost就可以直接到myMPD的畫面摟

## myMPD附加啟動
`-u, --user <使用者名稱>` 啟動的使用者名</p>
`-w, --workdir <資料夾>` 更改預設資料夾</p>
`-a, --cachedir <資料夾>` 更改緩存資料夾

## myMPD設定
myMPD的預設設定資料夾是在 `/var/lib/mympd/config/`
然後裡面有一些設定我們可以來調整的這邊就講一些基礎的</p>
`http_host` 伺服器ip位置</p>
`http_port` 伺服器端口</p>
`ssl` 啟動ssl，或關閉</p>
`ssl_port` ssl端口</p>

# 音樂串流
我知道你在想什麼，我們都架了一個mpd網頁伺服器了，那可不可以做到**音樂串流**了呢?

答案是可以的，我們首先要在mpd的設定添加一個輸出選項
```
audio_output {
    type        "httpd"
    name        "HTTP Stream"
    encoder     "lame" #to support safari on ios
    port        "8000"
    bitrate     "128"
    format      "44100:16:1"
    always_on   "yes"
    tags        "yes"
}
```
之後我們到myMPD的設定，的Features
 
![](https://i.imgur.com/AyBO4V4.png)

然後打開 `Local playback`

然後設定`Streamport` (預設8000)

之後我們就可以在右下看到Local playback的選項，點進去按播放就可以串流音樂了

![](https://i.imgur.com/sLbFUtP.png)

*PS.你也可以打開Autoplay來按下播放鍵自動連接服務*

# 總結

這就是我平常怎麼播音樂的，雖說架起來麻煩但是用起來是真的好用的

那mpd也可以做到很多事，像是可以跟一個OBS的插件Tuna用在一起，就可以在上面看到正在播放的音樂，我這還只是簡單用用而已，還不是非常進階的用法，如果你們有非常進階的mpd使用方法也可以在Twitter上面@bluesewill讓我知道拉，這邊是blusewill_Guide我們下次再見 :D
