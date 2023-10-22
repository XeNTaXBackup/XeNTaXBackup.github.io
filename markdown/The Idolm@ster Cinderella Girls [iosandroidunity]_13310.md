## Post #1
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-09-10T22:39:21+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

Hi all.
Who can help extract 3d data?
[Chipicao](http://forum.xentax.com/viewtopic.php?f=16&t=11095) max script not working.

Sample file: [https://yadi.sk/d/eRluO_-cizwvF](https://yadi.sk/d/eRluO_-cizwvF)
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-09-13T08:47:17+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

There are no any tools for Unity5 Engine 3D data.
Also, There are no 3D model data in BNEI0242.app\Data (iOS), only system data and images.
placed here: /var/mobile/Containers/Data/Application/
downloaded when frist runs
## Post #3
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-09-13T23:39:51+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

Sorry i checked your file. looking LZ4 lossless compression.
you can find more information here : [https://github.com/Cyan4973/lz4](https://github.com/Cyan4973/lz4)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-21T16:14:32+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

BMS script to decompress.
Use unityraw and unityEngine BMS scripts to unpack the results.

```

comtype "lz4"
get unk long
get SIZE long
get ZSIZE long
get unk long

savepos OFFSET
get NAME BASENAME

clog NAME OFFSET ZSIZE SIZE

```


I have a noesis plugin that loads unity models and it supports this as well (no skeleton), but I'll need more samples.
## Post #5
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-09-21T18:39:57+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

I think you need to get the address which the game downloads the big data pack from. It's being downloaded after you log in you namco account after the fast loading bar(the pic of 3 main idols with their bios written). I'm pretty sure its when the 3d data is downloaded cuz the game doesn't seem to download the stuff after you choose a song to play
## Post #6
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-09-21T21:52:04+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

Look pm   

> Reply from finale00
>
> BMS script to decompress.
Use unityraw and unityEngine BMS scripts to unpack the results.
Code: Select all# IdolM@ster Cinderella Girls uncompress

comtype "lz4"
get unk long
get SIZE long
get ZSIZE long
get unk long

savepos OFFSET
get NAME BASENAME

clog NAME OFFSET ZSIZE SIZE


I have a noesis plugin that loads unity models and it supports this as well (no skeleton), but I'll need more samples.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2015-09-21T22:19:52+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

You can try this on the decompressed archives. It sounds like it should load models properly.

[viewtopic.php?f=10&t=11807](http://forum.xentax.com/viewtopic.php?f=10&t=11807)
## Post #8
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-09-23T07:44:23+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

I hoped that S3BUtility would open the .unity3d file but it looks like iOS unity3d files arent supported ;-;
## Post #9
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-10-01T14:21:10+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

Makuchan has ripped a model from this game already, any idea how?
## Post #10
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-10-02T08:50:11+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from MarieRose1301
>
> 
Makuchan has ripped a model from this game already, any idea how?
Did he ever gave his tools? No! He miser.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-02T12:02:00+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

not too hard to get a mesh from an uncompressed lz4 model file:



chara_head_0134.JPG (89.43 KiB) Viewed 1126 times


edit: textures seem to be in the model file.
Search for tx_chr0134
## Post #12
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-10-02T12:27:52+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

Great!  
Textures?
## Post #13
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-10-02T19:57:03+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from Mrtest
>
> Great!  
Textures?

How did you get the original file you uploaded though?
I can't find any in the apk file e.e
## Post #14
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-10-02T20:13:04+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from MarieRose1301
>
> Mrtest wrote:Great!  
Textures?

How did you get the original file you uploaded though?
I can't find any in the apk file e.e
Most likely they are in the cache. But I downloaded the files directly from the game server...
I will share all the files, if someone will create import plugin.
## Post #15
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-10-02T20:26:07+00:00
- Post Title: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from Mrtest
>
> MarieRose1301 wrote:Mrtest wrote:Great!  
Textures?

How did you get the original file you uploaded though?
I can't find any in the apk file e.e
Most likely they are in the cache. But I downloaded the files directly from the game server...
I will share all the files, if someone will create import plugin.

Can you upload Ranko? I wanna try using hex2obj on her x3
## Post #16
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2015-10-02T20:26:42+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

More samples: [https://yadi.sk/d/xhH7U_V0jEd29](https://yadi.sk/d/xhH7U_V0jEd29)

 hex2obj - good utility. But for each file their individual hex values. : \
## Post #17
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2015-11-01T13:41:21+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

thanks
## Post #18
- Username: qxoda4
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Oct 31, 2012 7:13 pm
- Post datetime: 2015-11-05T00:30:05+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

Hello, Mrtest.

I'd like to participate in an analysis, too.
I'd like to advance work comfortably, so could you tell me the location of the model data or extracting method?
## Post #19
- Username: Gator
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 15, 2015 7:49 pm
- Post datetime: 2015-11-14T19:53:38+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

1447398700470.jpg (174.42 KiB) Viewed 690 times

Some anon on The iDOLM@STER General board on 4chan extracted Fumika's mesh (though it appears to be mirrored) and made it available here:
[https://dl.dropboxusercontent.com/u/219 ... omy2.blend](https://dl.dropboxusercontent.com/u/219331765/gloomy2.blend)

According to anon, he is getting the meshes out using a modified version of disunity 0.4 and he has done some of the others as well, but they all require manual fixing.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-15T14:47:30+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from Mrtest
>
> But for each file their individual hex values. : \yeah, they could be fetched using a MakeH2O project.
Sadly the unity3D files are too different, so only one (and a "half") of 3 checked models were extracted correctly:



body0001_3_0_1.jpg (164.25 KiB) Viewed 666 times


H2O files

body0001_3_0_1:
0xd050 20976
Vb1
24 99
0x43604 5645
020000
0x64748 12

3d_chara_head_0271:
0x4f160 12633
Vb1
24 99
0x6e588 3210
020000
0x8127C 12
## Post #21
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-12-06T16:02:40+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

So any news on models or animations?
It seems that Maku-chan has ported bones and(animations) or morphs somehow
## Post #22
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2015-12-25T17:20:42+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

I spoke to Maku-chan about the textures and here
The texture format is PVRTC2 and PVRTC4 (PowerVR Texture Compression 2bpp/4bpp)
All of the textures are inside the unity3d.lz4 files
This is the link explaining the format, it's in Japanese though: [http://www.webtech.co.jp/blog/optpix_labs/format/4930/](http://www.webtech.co.jp/blog/optpix_labs/format/4930/)
And this is the original email I got from him:

> こんにちは。
>
> キャラクターの胴体モデルに使用されているテクスチャデータは3d_tx_bodyから始まるunity3d.lz4ファイルに格納されています。
>
> 3Dモデルに使用されているテクスチャのピクセルフォーマットはPowerVR Texture Compression 2bpp/4bppのPVRTC2とPVRTC4で各アルファチャンネル有りと無しが使われいます。
>
> 
>
> 簡単な解説
>
> http://www.webtech.co.jp/blog/optpix_labs/format/4930/
>
> 
>
> 縦横サイズやフォーマットはヘッダ情報で判別することができます。
## Post #23
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-01-06T04:31:24+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]


## Post #24
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2016-02-27T13:22:25+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

disunity 5.0 now supports unity 5.0 ouo can it be used for that game?
[https://github.com/ata4/disunity/releases](https://github.com/ata4/disunity/releases)
## Post #25
- Username: TeridaxXD001
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 28, 2015 12:12 am
- Post datetime: 2016-05-08T21:37:33+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

How do you extract the models now that the old way is impossible?
## Post #26
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-01-22T02:20:57+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

Now it's encrypted. Do you know what to do?
## Post #27
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-22T14:13:47+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

You need to play on a real device and do url monitoring to grab the files.
I have not found any android emulators that have the 3d model mode enabled i think they blacklisted all emulators from loading 3d models in the app.
## Post #28
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-01-23T22:02:17+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

I think this file is a new encryption file.

[http://storage.game.starlight-stage.jp/ ... 0d9f9f79bb](http://storage.game.starlight-stage.jp/dl/resources/High/AssetBundles/Android/81c7c7d17671d28f2f49ab0d9f9f79bb)

[https://drive.google.com/file/d/0B1pwmi ... p=drivesdk](https://drive.google.com/file/d/0B1pwmicpHiFSVTh2OEczWkMyQTQ/view?usp=drivesdk)
Android APK ver 2.6.5

I know that it's still available in the Nox app player.
[https://www.yeshen.com/en](https://www.yeshen.com/en)
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-01-23T22:45:45+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

I can get it to play in any emulator it only does the 2d mode tho and blocks the 3d mode.
the url database is an sqlite3 database with a password on it.
If I got the 3d mode working in an emulator I could just dump it from ram.
## Post #30
- Username: LOZTPX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 04, 2017 10:52 pm
- Post datetime: 2017-02-04T15:06:17+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from chrrox
>
> I can get it to play in any emulator it only does the 2d mode tho and blocks the 3d mode.
the url database is an sqlite3 database with a password on it.
If I got the 3d mode working in an emulator I could just dump it from ram.
I suggest to install the GLtools.
[http://forum.xda-developers.com/android ... 9-t2828630](http://forum.xda-developers.com/android/apps-games/app-gltools-1-29-t2828630)

This app makes it possible to behave like using fake GPU and select 3d mode on emulator.
Launch, install, grant superuser access, choose CGSS, and config as below.
Enable custom settings for this app
Use fake GPU info
Use a template - Adreno 430
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-02-05T02:31:33+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

that worked great downloading the 19243 files right now.
## Post #32
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-02-06T00:13:57+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

May I ask what emulator you used? The one I've tried when I try to install that app, it says it isn't rooted and won't let me use it. ; ;
## Post #33
- Username: amai1990
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 07, 2017 7:23 am
- Post datetime: 2017-02-06T23:40:21+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from chrrox
>
> that worked great downloading the 19243 files right now.

Wow, that's awesome! could you please explain how to do it?
## Post #34
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-04-08T16:40:34+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

maybe use emulater
## Post #35
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-06-28T07:30:31+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

> Reply from chrrox
>
> that worked great downloading the 19243 files right now.

!! holy cow how did you manage that?
## Post #36
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2017-11-23T03:15:49+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

Hi chrrox,
It's great to see that you were able to import the models and play around with them.

I was able to import a head into 3DS Max, but I could not figure out how to put the texture map file on the head.
I went to Materials Editor > Diffuse > Bitmap > selected the texture file (you can see it in the Materials Editor)

However, the model just becomes a little brighter when I click the "Show Shaded Material in Viewport".
Could you give me a few tips on how to add the texture map?
Also, how were you able to get the bones? 

I'm still new to this stuff...still learning.
Thanks in advance for your help!
## Post #37
- Username: ervinrinos
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 04, 2018 3:05 pm
- Post datetime: 2018-01-04T07:21:39+00:00
- Post Title: Re: The Idolm@ster Cinderella Girls [ios/android/unity]

please make a tutorial and upload the file contents so we can use it also
