## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-04T15:03:20+00:00
- Post Title: Asphalt 8 .pig

Has anyone tried looking into this model format? I'm interested in ripping models from this game because it has some unique vehicles. I've tried looking through the files and I was only able to find face indices and dummy floats. The vertex data seems like it's there but it's suspiciously small and doesn't give any proper meshes. It could be compressed in some way (or I'm looking at it incorrectly)

Samples:
[http://www53.zippyshare.com/v/70121626/file.html](http://www53.zippyshare.com/v/70121626/file.html)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-04-04T17:54:37+00:00
- Post Title: Asphalt 8 .pig

Vertices are in short integer format.
XYZ / factor

eg: car_aston_martin_zagato.pig @ 0x1D70
1st vertex => [4281,-7359,-3373] / 32767
[a.jpg](https://xentaxbackup.github.io/file/7175_a.jpg)
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-04-26T07:05:37+00:00
- Post Title: Asphalt 8 .pig

Any progress on this format?
## Post #4
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-26T12:40:15+00:00
- Post Title: Asphalt 8 .pig

I'm working on a maxscript, but I still have some things to figure out before it's finished.

[](http://www.imagebam.com/image/30cf32322938246) [](http://www.imagebam.com/image/62d733322938271)
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-26T12:46:11+00:00
- Post Title: Asphalt 8 .pig

I wanted to make a MaxScript for this format, but I didn't get around to it yet. Nice work Chipicao
## Post #6
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-26T22:00:08+00:00
- Post Title: Asphalt 8 .pig

> Reply from barti
>
> Has anyone tried looking into this model format? I'm interested in ripping models from this game because it has some unique vehicles. I've tried looking through the files and I was only able to find face indices and dummy floats. The vertex data seems like it's there but it's suspiciously small and doesn't give any proper meshes. It could be compressed in some way (or I'm looking at it incorrectly)

Samples:
http://www53.zippyshare.com/v/70121626/file.html

where I find that pig files in android system? in sdcard0/Android/data, there I dont find car files
## Post #7
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-26T22:30:48+00:00
- Post Title: Asphalt 8 .pig

Just go to sdcard0\Android\obb\com.gameloft.android.ANMP.GloftA8HM - there will be an .obb file, change the extension to .zip and extract or open it in any ZIP viewer. There will be a "models" folder and inside will be all models (.pig) and textures (.pvr in my case) from the game (car models have the "car_" prefix in the name)
## Post #8
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-27T03:52:22+00:00
- Post Title: Asphalt 8 .pig

GT Racing 2 also has obb file com.gameloft.android.ANMP.GloftRAHM but I cannot extract it. it has models with interiors
## Post #9
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-27T06:46:50+00:00
- Post Title: Asphalt 8 .pig

> Reply from TomWin
>
> GT Racing 2 also has obb file com.gameloft.android.ANMP.GloftRAHM but I cannot extract it. it has models with interiors
How do you extract those gla files?
## Post #10
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-27T12:03:45+00:00
- Post Title: Asphalt 8 .pig

I dont have pvr files but tga, I cannot open them. i tried real racing 3 script for convert that tga files to pvr format but it doesnt work
URUS TEXTURES: [http://www.mediafire.com/download/tzc2tgr4t2k2hhq](http://www.mediafire.com/download/tzc2tgr4t2k2hhq)

these obb files are in sdcard0\Android\obb\
## Post #11
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-27T12:35:52+00:00
- Post Title: Asphalt 8 .pig

> Reply from TomWin
>
> I dont have pvr files but tga, I cannot open them. i tried real racing 3 script for convert that tga files to pvr format but it doesnt work
URUS TEXTURES: http://www.mediafire.com/download/tzc2tgr4t2k2hhq

these obb files are in sdcard0\Android\obb\

My bad, they're pvr files, only with tga extension. [PVRTexTool](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp) can open them. If it doesn't work, change extension from .tga to .pvr and it should work.

I tried opening the GT Racing 2 files a while ago, but I couldn't open the .obb and I needed space on my SD Card so I deleted it.
## Post #12
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-27T12:44:26+00:00
- Post Title: Asphalt 8 .pig

> Reply from barti
>
> TomWin wrote:I dont have pvr files but tga, I cannot open them. i tried real racing 3 script for convert that tga files to pvr format but it doesnt work
URUS TEXTURES: http://www.mediafire.com/download/tzc2tgr4t2k2hhq

these obb files are in sdcard0\Android\obb\

My bad, they're pvr files, only with tga extension. PVRTexTool can open them. If it doesn't work, change extension from .tga to .pvr and it should work.

I tried opening the GT Racing 2 files a while ago, but I couldn't open the .obb and I needed space on my SD Card so I deleted it.

it doesnt work in PVRTexTool v3.20. I get this error message:
File open failed:
Texture appears empty: file may be corrupt, If data appears to be intact, you could try wrapping as Raw data (Ctrl-D)
If file data is valid you could try to wrap it as RAW data.

that RAW thing doesnt work
## Post #13
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-04-27T12:58:42+00:00
- Post Title: Asphalt 8 .pig

I just installed the latest version from the link I gave before, and it loads all of your samples perfectly
## Post #14
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-27T13:14:30+00:00
- Post Title: Asphalt 8 .pig

Yes, the extension just needs to be changed from tga to pvr.

> Reply from TomWin
>
> these obb files are in sdcard0\Android\obb\Unfortunately I don't have  smartphone 
Does anyone know a way to extract gla files?
## Post #15
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-27T14:31:16+00:00
- Post Title: Asphalt 8 .pig

> Reply from barti
>
> I just installed the latest version from the link I gave before, and it loads all of your samples perfectly

thanks a lot, this new one worked, looks like previous version couldnt read them only
## Post #16
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-04-28T08:19:06+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> Yes, the extension just needs to be changed from tga to pvr.
TomWin wrote:these obb files are in sdcard0\Android\obb\Unfortunately I don't have  smartphone 
Does anyone know a way to extract gla files?

You can try it on a cheap but fairly-powerful smartphone or tablet. 

As for the models themselves, have you guys found any dummies, bones or whatever parts Gameloft used to string the car parts together?
## Post #17
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-28T08:55:59+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from huckleberrypie
>
> You can try it on a cheap but fairly-powerful smartphone or tablet.
I managed to install Android on a VMware virtual machine. Unfortunately I misunderstood; I thought .obb were model files extracted from .gla archives, but it's the other way around. So we're still stuck. But I heard GMMan is working on an update for his Gameloft CustomPak Extractor, so let's be patient.

> Reply from huckleberrypie
>
> As for the models themselves, have you guys found any dummies, bones or whatever parts Gameloft used to string the car parts together?I did, but I'm still having some issues with transformations to get them all in the right place.

Actually, it's not the dummies that are used to put all parts together. There are additional position and scale vectors for each mesh, and with them you'll get correct positions for everything except wheels..
## Post #18
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-28T12:42:09+00:00
- Post Title: Re: Asphalt 8 .pig

any idea how to extract that obb files from android version?
## Post #19
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-04-28T12:49:37+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> huckleberrypie wrote:You can try it on a cheap but fairly-powerful smartphone or tablet. 
I managed to install Android on a VMware virtual machine. Unfortunately I misunderstood; I thought .obb were model files extracted from .gla archives, but it's the other way around. So we're still stuck. But I heard GMMan is working on an update for his Gameloft CustomPak Extractor, so let's be patient.
huckleberrypie wrote:As for the models themselves, have you guys found any dummies, bones or whatever parts Gameloft used to string the car parts together?I did, but I'm still having some issues with transformations to get them all in the right place.

Actually, it's not the dummies that are used to put all parts together. There are additional position and scale vectors for each mesh, and with them you'll get correct positions for everything except wheels..

(OBBs are merely zip archives afaik) - That applies to most Android game packages i.e. the GTA games. Seems like some developers are either encrypting or just plain borked up the OBBs with a different format.

As for parts positions, provided that we gather enough info on the file format, would it be possible to shove in a custom vehicle model back into the game?
## Post #20
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-04-28T16:32:19+00:00
- Post Title: Re: Asphalt 8 .pig

It doesn't look like a zip file, at least not one that I'm familiar with.
I've made a quickbms script to extract it: [viewtopic.php?f=10&t=11462](http://forum.xentax.com/viewtopic.php?f=10&t=11462)

Regarding getting vehicles back in-game, anything is possible, but I'm not sure how easy it would be.
## Post #21
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-04-28T18:39:01+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> It doesn't look like a zip file, at least not one that I'm familiar with.
I've made a quickbms script to extract it: viewtopic.php?f=10&t=11462

Regarding getting vehicles back in-game, anything is possible, but I'm not sure how easy it would be.

works great, thanks a lot. now we gotta wait only for gla extractor.
how's going with asphalt 8 models?

is that LaFerrari from iOS or android version?
## Post #22
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2014-04-30T06:09:20+00:00
- Post Title: Re: Asphalt 8 .pig

The Minion Rush game on iOS also uses the .pig format, and I've been trying to get models from that game for quite some time. Would it be possible to configure the maxscript so that it will work with these files and preferably with the rigging in-tact?

Here's some samples to give you an idea: [https://www.mediafire.com/?sjse65615h7v5hb](https://www.mediafire.com/?sjse65615h7v5hb)

Thanks!
## Post #23
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-02T17:55:07+00:00
- Post Title: Re: Asphalt 8 .pig

The script is almost ready, I'm just putting in some final touches.
I know about Minion Rush and I already have it. The script should work with any .pig mesh file.

Does anybody know the name of this game engine?
## Post #24
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2014-05-03T02:47:07+00:00
- Post Title: Re: Asphalt 8 .pig

The .pig format seems to be fairly common in Gameloft games, so I'd probably name it based on that for now.
## Post #25
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-03T07:50:09+00:00
- Post Title: Re: Asphalt 8 .pig

Could you please name a few other games?
## Post #26
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-05-03T09:37:56+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from MisterPrawn
>
> The .pig format seems to be fairly common in Gameloft games, so I'd probably name it based on that for now.

The Pig Engine? 

Previous Gameloft titles used .BDAE as the primary model format, if I'm not mistaken.
## Post #27
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-03T12:18:39+00:00
- Post Title: Re: Asphalt 8 .pig

Hehe I guess Pig Engine will have to do for now.

Script released: [viewtopic.php?f=16&t=11095&p=91256#p91256](http://forum.xentax.com/viewtopic.php?f=16&t=11095&p=91256#p91256)
[](http://www.imagebam.com/image/bff015324346109) [](http://www.imagebam.com/image/8e2eab324346116) [](http://www.imagebam.com/image/624296324346129) [](http://www.imagebam.com/image/0997c1324346139) [](http://www.imagebam.com/image/5830ea324346154)
## Post #28
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-05-03T13:55:32+00:00
- Post Title: Re: Asphalt 8 .pig

Great work thanks a lot Chipicao!!!

hmm it doesnt load windows and glass parts of some models

how is going with GT Racing 2 extractor?
## Post #29
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-03T15:08:05+00:00
- Post Title: Re: Asphalt 8 .pig

Some models only have LOD3 glass, that's how they are.
## Post #30
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-05-05T07:42:02+00:00
- Post Title: Re: Asphalt 8 .pig

'Swell work with the importer dude! Now all we need is an exporter for maximum lulz.
## Post #31
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-05-11T19:38:00+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from huckleberrypie
>
> Now all we need is an exporter for maximum lulz.will never happen I believe.
## Post #32
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-05-19T01:49:47+00:00
- Post Title: Re: Asphalt 8 .pig

Does anyone know where the window glass meshes are located? Couldn't seem to find them for some reason.
## Post #33
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-19T05:42:06+00:00
- Post Title: Re: Asphalt 8 .pig

Some cars only have LOD2 or LOD3 windows.
## Post #34
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-05-19T09:48:13+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> Some cars only have LOD2 or LOD3 windows.

Noted. Might as well convert one of them cars to either The Sims 3, GTA IV or Need for Speed.
## Post #35
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-05-20T05:26:04+00:00
- Post Title: Re: Asphalt 8 .pig

I updated the script with a few fixes related to track models and added an option to import all .pig files within a folder. Use it with caution, you don't wanna load all game files by accident.
## Post #36
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2014-09-13T07:38:48+00:00
- Post Title: Re: Asphalt 8 .pig

Sorry, how to import/view .pig file?
## Post #37
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-09-13T11:27:41+00:00
- Post Title: Re: Asphalt 8 .pig

4th script on this page: [viewtopic.php?f=16&t=11095](http://forum.xentax.com/viewtopic.php?f=16&t=11095)
## Post #38
- Username: clang7775
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 29, 2014 2:31 am
- Post datetime: 2014-09-28T19:08:16+00:00
- Post Title: Re: Asphalt 8 .pig

I can't seem to extract the .obb file - I've tried the custom pak extractor and the zip unscrambler but no luck 

I have the android .obb - do i need the iOS one or..?
## Post #39
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-09-29T10:08:54+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from clang7775
>
> I can't seem to extract the .obb file - I've tried the custom pak extractor and the zip unscrambler but no luck 

I have the android .obb - do i need the iOS one or..?

rename OBB with ZIP and open it with Winrar or Winzip
## Post #40
- Username: clang7775
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Sep 29, 2014 2:31 am
- Post datetime: 2014-09-29T15:50:33+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from hermit
>
> 
rename OBB with ZIP and open it with Winrar or Winzip

I tried that but it says its an invalid archive
## Post #41
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-09-29T21:08:47+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from clang7775
>
> hermit wrote:
rename OBB with ZIP and open it with Winrar or Winzip

I tried that but it says its an invalid archive

I used Winrar 5.10
## Post #42
- Username: hermit
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Aug 10, 2014 9:13 pm
- Post datetime: 2014-09-30T18:22:39+00:00
- Post Title: Re: Asphalt 8 .pig

I have this problem 
[](http://www.imagebam.com/image/528e8b354769548)
## Post #43
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2014-10-01T11:42:01+00:00
- Post Title: Re: Asphalt 8 .pig

The script doesn't works on lastest "Metal Update" 1.6.1 
(Peugeot onyx,Agear one:1)

Error screen

[](http://www.imagebam.com/image/631340354913721) 

can you please fix it? 

UPDATE:

Textures also turn into mess  
[](http://www.imagebam.com/image/6fe21d354924116)
## Post #44
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-10-01T12:42:38+00:00
- Post Title: Re: Asphalt 8 .pig

The new version has vertex and index buffers compressed with lz4, textures as well.

Unfortunately it's impossible to use maxscript for decompression. I will see if I can make a standalone tool to export models as FBX or OBJ.
## Post #45
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-10-05T19:25:49+00:00
- Post Title: Re: Asphalt 8 .pig

Work in progress

[](http://www.imagebam.com/image/ac61d3355798073)
## Post #46
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-10-05T23:13:49+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> Work in progress

Superb! like always, thanks chipi for making that tool. Will it work with Overdrive pig files too?
## Post #47
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-10-06T05:21:30+00:00
- Post Title: Re: Asphalt 8 .pig

Not at first. Overdrive will require more research.
## Post #48
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2014-11-10T22:32:08+00:00
- Post Title: Re: Asphalt 8 .pig

Any more progress Chipi?
## Post #49
- Username: Brujo89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 12, 2014 11:55 pm
- Post datetime: 2014-11-12T22:11:38+00:00
- Post Title: Re: Asphalt 8 .pig

Hi, looking forward this tool thank you
## Post #50
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-11-13T11:34:29+00:00
- Post Title: Re: Asphalt 8 .pig

Sorry guys, I'm going through a rough patch, personal issues, and all development is on hold.
## Post #51
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-11-13T12:42:28+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> Sorry guys, I'm going through a rough patch, personal issues, and all development is on hold.don't rush man, life's first.
## Post #52
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-24T21:38:18+00:00
- Post Title: Re: Asphalt 8 .pig

Since I don't have nearly enough time to finish the app as I planned, here's a command-line tool instead that will convert pig models to FBX.
Compatible with the latest Asphalt 8 game, and all features from my MAXscript are there: normals, texture coordinates (2 channels), hierarchy and materials.

The tool will also decompress textures from newer Asphalt versions into usable pvr files. You will of course need a plugin from PVRTexTools.
All you have to do is keep the models and textures folders in the same place.

Usage:
- drag&drop a pig file on the exe
- run it in a folder to convert all pig files
- run it with a pig file or folder as parameter

Known issues:
- no support for Asphalt Overdrive; I believe AO pig files need further decompression

Download: [http://www.mediafire.com/download/3aafb ... IG2FBX.zip](http://www.mediafire.com/download/3aafbwswjqjk00c/PIG2FBX.zip)

[](http://www.imagebam.com/image/08bebc375682013) [](http://www.imagebam.com/image/0a897f375682032) [](http://www.imagebam.com/image/90afad375682068) [](http://www.imagebam.com/image/6d2dba375682052)

Merry Christmas!
## Post #53
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-12-27T18:38:43+00:00
- Post Title: Re: Asphalt 8 .pig

Small update:
- fixed an issue with regional number formatting (period as decimal point)
- added normal maps
- .NET 3.5 is now required instead of 4.0

Download link is the same.
## Post #54
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2014-12-28T03:17:29+00:00
- Post Title: Re: Asphalt 8 .pig

Mind if I give you a big hug dude? Oh, and nice tool, too!
## Post #55
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2015-05-30T21:57:12+00:00
- Post Title: Re: Asphalt 8 .pig

Chipi could you check how to convert that textures to PVR?
PIG2FBX cannot convert all of them. Or am I doing something wrong.

[http://www.mediafire.com/download/64jd6512c6jrr6q](http://www.mediafire.com/download/64jd6512c6jrr6q)
## Post #56
- Username: Dennissaurus
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Aug 12, 2014 11:16 pm
- Post datetime: 2015-07-16T21:14:04+00:00
- Post Title: Re: Asphalt 8 .pig

Can someone update it for the last update from asphalt 8? I really want the 675LT
## Post #57
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2015-07-29T02:10:01+00:00
- Post Title: Re: Asphalt 8 .pig

[http://www73.zippyshare.com/v/45YkNZip/file.html](http://www73.zippyshare.com/v/45YkNZip/file.html)

P1 GTR from latest asphalt 8
## Post #58
- Username: Matsilagi
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Aug 31, 2014 12:39 pm
- Post datetime: 2015-08-11T23:10:43+00:00
- Post Title: Re: Asphalt 8 .pig

Does anyone know if those tools are able to open the Asphalt 8 Windows files after the Hot Summer update? (2.0.0)

Im trying to convert the Dirty lens shader textures but PowerVR refuses to open the TGA for it (which is a DDS) and when it opens, the texture is all glitched.
## Post #59
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2015-10-09T14:07:56+00:00
- Post Title: Re: Asphalt 8 .pig

If someone could manage to update the script for importing the cars from the latest 2 updates, that would be great 
Here's the car list:

- McLaren 675LT
- McLaren P1 GTR
- Datsun 280Z
- Chevrolet Camaro Z28
- Shelby Cobra 427
- AC 378 GT Zagato
- Chevrolet SS NASCAR
- Lamborghini Huracan
- Bentley EXP10 Speed 6
- Cadillac 16 Concept
- Kepler Motion
- Mitsubishi Lancer Evo X
- McLaren 570S
## Post #60
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2015-12-20T02:28:29+00:00
- Post Title: Re: Asphalt 8 .pig

There are many new cool cars in but the script is outdated 

Lamborghini Egoista pig:
[http://www.filedropper.com/carlamborghi ... oncept2012](http://www.filedropper.com/carlamborghiniegoistaconcept2012)
## Post #61
- Username: MohsineF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 25, 2015 7:01 am
- Post datetime: 2016-04-29T14:39:02+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> I'm working on a maxscript, but I still have some things to figure out before it's finished.

The PIG2FBX crashes with last Asphalt8 update, anyone have solution?
## Post #62
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-04-29T15:22:43+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from MohsineF
>
> The PIG2FBX crashes with last Asphalt8 update, anyone have solution?

PIG2FBX hasn't been updated to work with the latest versions of the game.
## Post #63
- Username: MohsineF
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Dec 25, 2015 7:01 am
- Post datetime: 2016-04-29T19:55:58+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Automotive Gaming
>
> MohsineF wrote:The PIG2FBX crashes with last Asphalt8 update, anyone have solution?

PIG2FBX hasn't been updated to work with the latest versions of the game.

Hope @Chipicao update it soon!
## Post #64
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-12T17:15:48+00:00
- Post Title: Re: Asphalt 8 .pig

Any idea how to unpack PC archives with models and textures?

models_car.bin
[https://www.sendspace.com/file/cv4p7g](https://www.sendspace.com/file/cv4p7g)

car_ac_378gtzagato_df.tga
[http://www25.zippyshare.com/v/RT5Z4iSO/file.html](http://www25.zippyshare.com/v/RT5Z4iSO/file.html)

models_car.bin.hdr
[http://www25.zippyshare.com/v/HHaRTLrK/file.html](http://www25.zippyshare.com/v/HHaRTLrK/file.html)
## Post #65
- Username: lhj117383609
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 07, 2016 8:18 pm
- Post datetime: 2016-09-08T15:02:11+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Chipicao
>
> Work in progress



Where to download the GAMELOFT_PIG_exporter software, the trouble to provide download address, thank you！
## Post #66
- Username: jch824
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 24, 2017 11:08 pm
- Post datetime: 2017-01-28T03:01:23+00:00
- Post Title: Re: Asphalt 8 .pig

pig2fbx When Update？
## Post #67
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2017-01-29T14:08:23+00:00
- Post Title: Re: Asphalt 8 .pig

many new interesting models in Asphalt 8. Is possible to update .pig importer?
Maybe windows version files are different and more easy to open?
## Post #68
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-03-16T19:13:53+00:00
- Post Title: Re: Asphalt 8 .pig

i'm guessing this is dead
## Post #69
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-03-20T20:46:55+00:00
- Post Title: Re: Asphalt 8 .pig

This game can be ripped from  i will upload pictures later
## Post #70
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2017-03-22T11:44:05+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from AstroStormz
>
> This game can be ripped from  i will upload pictures later
Are you talking about the latest versions of the game? If yes, that sounds interesting.
## Post #71
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-03-23T22:35:20+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from AMG
>
> AstroStormz wrote:This game can be ripped from  i will upload pictures later
Are you talking about the latest versions of the game? If yes, that sounds interesting.

all you need is bluestacks and ninjaripper

if you guys know you can also use ninjaripper on the windows 8 version for computers but you need permission to allow ninjaripper to inject which im still working on
## Post #72
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-03-25T14:43:34+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from AstroStormz
>
> AMG wrote:AstroStormz wrote:This game can be ripped from  i will upload pictures later
Are you talking about the latest versions of the game? If yes, that sounds interesting.

all you need is bluestacks and ninjaripper

if you guys know you can also use ninjaripper on the windows 8 version for computers but you need permission to allow ninjaripper to inject which im still working on
NinjaRipper working on bluestack? wow ;o
## Post #73
- Username: AstroStormz
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Jun 27, 2015 6:01 am
- Post datetime: 2017-03-26T00:24:55+00:00
- Post Title: Re: Asphalt 8 .pig

NinjaRipper working on bluestack? wow ;o[/quote]

yea it does but the asphalt 8 for windows has more cars but the game doesnt work unless its in that specific folder...........if u move it it wont launch and if u leave it.......ninja ripper cant write in that folder
## Post #74
- Username: YouDude
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 09, 2017 5:55 am
- Post datetime: 2017-04-08T22:01:48+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from AstroStormz
>
> 
yea it does but the asphalt 8 for windows has more cars but the game doesnt work unless its in that specific folder...........if u move it it wont launch and if u leave it.......ninja ripper cant write in that folder

Hi, would you be so kind to share with us the way you ripped models and textures from Asphalt 8?
## Post #75
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2017-07-06T13:19:16+00:00
- Post Title: Re: Asphalt 8 .pig

Hello everyone,
I was able to rip the models of Fenry Supersports from the Lastest version of Asphalt 8 using Ninja Ripper and Bluestacks on my laptop.
Can anyone pls send me the texture files of fenyr Supersports? For some reason I am unable to extract the .obb files...

here is a pic...




EDIT: Got the textures...
## Post #76
- Username: Dionyseuss
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 07, 2016 6:57 am
- Post datetime: 2017-08-29T15:04:51+00:00
- Post Title: Re: Asphalt 8 .pig

I'm trying to get some models out of Gameloft's Six Gun. Neither FBX2PIG or the max import script are working for me, presumably because they use a new file version.

Does anyone have an updated importer or a good workaround?
## Post #77
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2017-09-08T02:54:00+00:00
- Post Title: Re: Asphalt 8 .pig

no updates for this?
## Post #78
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-12-21T12:42:30+00:00
- Post Title: Re: Asphalt 8 .pig

The game had changed its compression algorithm ever since the last version that PIG2FBX could still handle. Its format didn't change too much whereas
the tricky part is to find the correct algorithm it uses.
You'll see the difference if you do a compare among different version of the game:

car_renault_clio_rs.pig(v1.5.0, where Chipicao's Gameloft Pig Importer still worked)

```
00000DE0   00 00 1D 00 63 61 72 5F  72 65 6E 61 75 6C 74 5F   ....car_renault_
00000DF0   63 6C 69 6F 5F 72 73 5F  64 66 5F 6E 6D 2E 74 67   clio_rs_df_nm.tg
00000E00   61 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   a...............
00000E10   00 00 00 00 70 0D 00 00  06 00 00 00 00 00 00 00   ....p...........
00000E20   77 07 14 03 F0 F8 FF 7F  77 07 07 00 5E 07 FF 7F   w.......w...^...

```

Geometry data size recorded as a LONG interger at 0xE14, which is 0xD70. The data start right after offset 0xE18.

car_renault_clio_rs.pig(v1.8.0, where Chipicao's PIG2FBX still worked)

```
00000DE0   00 00 1D 00 63 61 72 5F  72 65 6E 61 75 6C 74 5F   ....car_renault_
00000DF0   63 6C 69 6F 5F 72 73 5F  64 66 5F 6E 6D 2E 74 67   clio_rs_df_nm.tg
00000E00   61 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   a...............
00000E10   00 00 00 00 00 00 00 00  A7 08 00 00 A8 13 00 00   ................
00000E20   2A 0E 00 01 00 E0 77 07  14 03 F0 F8 FF 7F 77 07   *.....w.......w.

```

The data had been compressed with LZ4 algorithm since then. Zip size recorded at 0xE18 is 0x8A7 while the unzip size following it is 0x13A8. 
Then the compressed data begin with a fixed header 2A 0E 00 01.

car_renault_clio_rs.pig(v3.3 above, which PIG2FBX doesn't support)

```
00000DE0   00 00 1D 00 63 61 72 5F  72 65 6E 61 75 6C 74 5F   ....car_renault_
00000DF0   63 6C 69 6F 5F 72 73 5F  64 66 5F 6E 6D 2E 74 67   clio_rs_df_nm.tg
00000E00   61 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   a...............
00000E10   00 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00   ................
00000E20   00 00 00 00 02 56 04 00  00 38 0D 00 00 26 B5 2F   .....V...8...&?.
00000E30   FD 80 38 0C 00 04 49 A2  50 77 07 14 03 F0 F8 FF   ..8...I.Pw......

```

The compression had changed to a different one. Zip size at offset 0xE25 is 0x456, while unzip size is 0xD38 followed by the compressed data starting with the fixed header 26 B5 2F FD. 
You might notice that the unzip size is actually between 0xD70 and 0x13A8, about which I don't know why.

Edit:This is because some chunks such as tangents and binormals, as well as some sequence bytes, are removed. So 
Its content is the same as the one whose size is 0xD70.
## Post #79
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-02T11:44:36+00:00
- Post Title: Re: Asphalt 8 .pig

What I have found in libmyAndroid.so in the apk file:



shot.png (9.72 KiB) Viewed 195 times
## Post #80
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-03T01:03:22+00:00
- Post Title: Re: Asphalt 8 .pig

It turns out the compression algorithm is zstd actually. I was fooled by those strings. Anyway should be easy to write a new tool to handle it now.
## Post #81
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-04T08:51:07+00:00
- Post Title: Re: Asphalt 8 .pig

Whoops... 
Optimism now seems to premature. Face indicies are encrypted:



Faceindices.png (62.75 KiB) Viewed 177 times


As far as just this small indicies buffer it seems to be some kind of offset-based encryptions, but for much larger buffer there're lots of FFFF where I can't see any regular pattern.

Again all come to a halt.
## Post #82
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-09T10:20:53+00:00
- Post Title: Re: Asphalt 8 .pig

> Reply from Bigchillghost
>
> Again all come to a halt.
Never mind. Quite simple encryption. 



bike_bmw_s_1000_rr.pig.png (102.33 KiB) Viewed 145 times


Tools should be available soon.
## Post #83
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-21T15:00:09+00:00
- Post Title: Re: Asphalt 8 .pig

Tools are released [there](http://forum.xentax.com/viewtopic.php?f=16&t=17591).
