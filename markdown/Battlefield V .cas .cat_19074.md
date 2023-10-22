## Post #1
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-14T21:34:15+00:00
- Post Title: Battlefield V .cas .cat

Hello,

I would love some help extracting the sounds/audio. The game apparently uses Frostbite 3. And everything is packed in these .cas files as you can see in the image below:



I tried a couple of Python scripts that were written for Battlefield 1 but none of them worked or I couldn't make them work.

Here's that last cas_07.cas 20mb file for testing. Oh and the cas.cat catalog just in case.

Thank you very much!
## Post #2
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2018-11-15T16:20:27+00:00
- Post Title: Battlefield V .cas .cat

I tried Luigi's Frostbite TOC/SB script on this cas.cat file, and it extracted roughly 3.9GB out of those 4.6GB. The extracted files always start with "00 01 00 00 00 71 00 00", so I guess that's the header. I recognized some PNG headers inside some of them, so I guess they are not compressed. However, I don't know what to do with those files, since fb3decoder and ealayer3 decoders don't work.
## Post #3
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-22T11:49:29+00:00
- Post Title: Battlefield V .cas .cat

Well, here's another problem. Encryption has changed. Patch folder and .sb files are missing.I already tried to do something, but nothing but two sounds. And one sound is from Bf1, and the other I do not know from where.
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-23T02:11:47+00:00
- Post Title: Battlefield V .cas .cat

To those of you who do not know yet, a new python script that supports the new format for SWBF2 and BFV has been created by the dev of FrostyToolSuite and someone already posted it [here](https://zenhax.com/viewtopic.php?p=40429#p40429).
Now you can dump the whole game again to your own pleasure.
## Post #5
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-23T04:10:25+00:00
- Post Title: Battlefield V .cas .cat

Thank you, but already broke my head, thank you )
## Post #6
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T09:55:45+00:00
- Post Title: Battlefield V .cas .cat

Yes, it's working! Thank you very much to all who helped, and especially to mono24 for getting back to me :>
## Post #7
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-24T12:53:04+00:00
- Post Title: Battlefield V .cas .cat

And by the way for those who want to unpack sounds. There is a problem with EASpeex. The script can not find : EASpeex dll not detected. Although I have it and it is in the folder. This happened when I reinstalled Python for version 2.7.6. And I wanted to load Battlefield V into FrostyToolSuite editor  and I was not lucky
## Post #8
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T14:35:59+00:00
- Post Title: Battlefield V .cas .cat

Yeah after like 3 hours of unpacking I also cannot seem to extract the sounds :< It's just a 60 gigs of .chunks
## Post #9
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-24T14:53:07+00:00
- Post Title: Battlefield V .cas .cat

You are have 60Gb chunks? This is BFV or SWBF2 ? Just in BFV, there are generally very few chunks formed (250 chunks) <500Mb. All the same for BFV need to refine the script.
## Post #10
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T15:40:37+00:00
- Post Title: Battlefield V .cas .cat

Yep, almost 70GBs actually:



And a couple of gigs of of 'res'
## Post #11
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-24T15:44:03+00:00
- Post Title: Battlefield V .cas .cat

And in the res folder, what were the other folders?
## Post #12
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T15:56:21+00:00
- Post Title: Battlefield V .cas .cat

Just this



The sound folder is literally 8Kb :<
## Post #13
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-24T16:00:10+00:00
- Post Title: Battlefield V .cas .cat

We have to wait. I saw a video on YouTube where one person get voices from the BFV.
## Post #14
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T16:23:12+00:00
- Post Title: Battlefield V .cas .cat

Thanks for trying to help at least, I'll keep you updated if I find anything :>
## Post #15
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-24T19:42:08+00:00
- Post Title: Battlefield V .cas .cat

Alright I think I did it. You need Python 2.7.6, that's very important.

First use the x64 version of Python to extract the chunks and everything else. Then install the x32 version of the same Python 2.7.6 and use the script called fb3decoder.py. To basically extract/convert the sounds using all the .chunks and .ebx files that you already extracted before.

This is very important, make sure the paths are correct



And if then run the script by pressing F5.

During the extracting and converting you might get some errors like this one



I couldn't fix it so I just moved the file causing the error out of that folder. So if the converting stopped at Wood003, just remove Wood004 and it should continue. But you'll have to restart the script, and it's wise to also remove all of the .ebx files that it already processed out of there too, so it doesn't convert them again. If it doesn't, just keep removing files until it does.

And that's pretty much it. [Here's a little thing I put together really quick](https://puu.sh/C73P3/260a2c452b.wav) :>
## Post #16
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2018-11-25T02:26:30+00:00
- Post Title: Re: Battlefield V .cas .cat

I can't dump the files with Python 2.7.6 x32. This is the error log:

> Traceback (most recent call last):
>
>   File "C:\Users\Marcus\Desktop\Dump Scripts\Dump Scripts\swbf2_bfv_dumper.py", line 77, in <module>
>
>     ZSTD = cdll.LoadLibrary("ZSTD")
>
>   File "C:\Python27_x86\lib\ctypes\__init__.py", line 443, in LoadLibrary
>
>     return self._dlltype(name)
>
>   File "C:\Python27_x86\lib\ctypes\__init__.py", line 365, in __init__
>
>     self._handle = _dlopen(self._name, mode)
>
> WindowsError: [Error 193] %1 ist keine zulässige Win32-Anwendung

Any ideas what I should do? The old dumper for BF1 works with my tools.
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-25T05:52:52+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from FunnyML
>
> Any ideas what I should do?
The newly updated script by GalaxyMan2015 requires 64bit of python, latest version of python works as well.

> Reply from Luriam
>
> You need Python 2.7.6, that's very important.
Your wrong, the audio decoding process is NOT tied up to that specific python version (those instructions you read in the archive are outdated and inaccurate from a different python script), yes it has to be 2.7 and not 3.x.x, BUT it will work with anything between 2.7.3 32-bit up to latest 2.7.15 32-bit versions of python.
The only thing changed on the newly dumping python script is that it requires python 2.7.3 64-bit up to latest 2.7.15 64-bit

> Reply from Luriam
>
> During the extracting and converting you might get some errors like this one
The main reason your getting those errors is because well, outdated files on, pretty much everything, ealayer3.exe needs latest update by ID-Daemon including it's xas_decoder with its entry inside the python script to be updated, then everything will decode properly.

> Reply from Luriam
>
> I couldn't fix it so I just moved the file causing the error out of that folder. So if the converting stopped at Wood003, just remove Wood004 and it should continue. But you'll have to restart the script, and it's wise to also remove all of the .ebx files that it already processed out of there too, so it doesn't convert them again. If it doesn't, just keep removing files until it does.
Do NOT remove anything, you need full dump intact of the game with every EBX where it belongs and its chunk files.
So basically use this decoder script, I updated the proper entry of the decoder, and all should run smoothly, make sure you have correct paths and for the ealayer3.exe too, make sure you use sound folder NOT the whole EBX folder and you're good to go.


 BFVdecoder.zip
(216.34 KiB) Downloaded 233 times


And if you happen to see few errors like this:

```
Error executing Xas_decode.
```

when xas_decode cant decode the old xas.dll will decode it instead that specific audio ebx/chunk.

Also if you think that some sounds might not get decoded/missing, well that could mean they might have added a new format and needs further reversing, who knows what can be the reason, I didn't fully tested every audio, were talking 10s of thousands of files.

have fun
## Post #18
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-25T06:57:26+00:00
- Post Title: Re: Battlefield V .cas .cat

After some time, the script has work, but there are some errors. 

chunkerrorChunnk does not exist: 900ec5e80fb0d5dcb639b2be11d0a2bc Sound/Core/Soldier/Footsteps/Sand/Soldier_Footsteps_Sand_Scufflestep
chunkerrorChunnk does not exist: 0b904f201a94a4fcc8bedcfc0a25c4a8 Sound/Core/Soldier/Footsteps/Sand/Soldier_Footsteps_Sand_Scufflestep
chunkerrorChunnk does not exist: 91a87b195c18ed682106970de148515c Sound/Core/Soldier/Footsteps/Sand/Soldier_Footsteps_Sand_Scufflestep

And this with all the files.
## Post #19
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-11-25T10:14:15+00:00
- Post Title: Re: Battlefield V .cas .cat

Thanks mono! I did what I could but this was my first time using Python so I had no idea what I was doing half the time  

Thank you for the link :>
## Post #20
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-11-25T10:49:02+00:00
- Post Title: Re: Battlefield V .cas .cat

Yea guys i have music. Thanks Guys ! I will leave almost all the music here, well almost all the music there [https://drive.google.com/open?id=120Fde ... 6IFIpP35i3](https://drive.google.com/open?id=120Fde2kJavhbuJA_-mTlNI6IFIpP35i3)
## Post #21
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-11-29T07:23:10+00:00
- Post Title: Re: Battlefield V .cas .cat

Are you going to post the voices and SFX from the game onto this site?: [www.sounds-resource.com](http://www.sounds-resource.com) ?
## Post #22
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-07T08:41:57+00:00
- Post Title: Re: Battlefield V .cas .cat

Interestingly, there was no error until the update, but now after the first patch, there’s such a surprise    

EBX
Bundle: a390d240

Traceback (most recent call last):
  File "F:\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 752, in <module>
    processManifest(bf1Directory)
  File "F:\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 688, in processManifest
    binBundle=BinaryBundle(bundleFile.fileRef.getCas(catalogs), bundleFile.offset)
  File "F:\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 486, in getCas
    def getCas(self,catalogs): return self.getCatalogPath(catalogs) + "cas_" + str(self.casIndex()).zfill(2) + ".cas"
  File "F:\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 480, in getCatalogPath
    root=catalogs[self.getCatalogIndex()]
IndexError: list index out of range
>>>
## Post #23
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-07T14:19:46+00:00
- Post Title: Re: Battlefield V .cas .cat

The problem is in the file F:\Battlefield V\Data\Win32\installation\initialexperience\cas_07.cas And if you delete it, there will be an error, If you delete the initialexperience folder completely, the system ddos will start-the python will use all the RAM
## Post #24
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2018-12-07T19:08:44+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BGmoder
>
> The problem is in the file F:\Battlefield V\Data\Win32\installation\initialexperience\cas_07.cas And if you delete it, there will be an error, If you delete the initialexperience folder completely, the system ddos will start-the python will use all the RAM

So what should we do ? Does it work well when the folder "initialexperience" is deleted even if it tooks full ram ?
## Post #25
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-08T06:04:52+00:00
- Post Title: Re: Battlefield V .cas .cat

As if the system itself reserves from my 16 GB to 2-3 GB, but I'm afraid the plate may boil, because nothing happens, but the memory modules are still under 15.7 GB clogged. I think maybe this is the version of python, but I try everything I can
## Post #26
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-08T08:17:04+00:00
- Post Title: Re: Battlefield V .cas .cat

This error is a python bug or the script.But I noticed that 20 bundles were quickly processed before the error.And here I have tried almost all versions, except for 32-bit. Help
## Post #27
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2018-12-08T11:38:41+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BGmoder
>
> This error is a python bug or the script.But I noticed that 20 bundles were quickly processed before the error.And here I have tried almost all versions, except for 32-bit. Help

I think this error is caused by the new update of bfv.
## Post #28
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-12-08T18:24:37+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Damoclès
>
> BGmoder wrote:This error is a python bug or the script.But I noticed that 20 bundles were quickly processed before the error.And here I have tried almost all versions, except for 32-bit. Help 

I think this error is caused by the new update of bfv.
But you'll still put up the VO and SFX right?
## Post #29
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-08T18:39:33+00:00
- Post Title: Re: Battlefield V .cas .cat

I have a reserve left
## Post #30
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-12-09T00:48:48+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BGmoder
>
> I have a reserve left
And once you have gotten rid of any duplicates, you'll put them up on the Sounds Resource and/or Google Drive?
## Post #31
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-09T05:50:16+00:00
- Post Title: Re: Battlefield V .cas .cat

Yea, but, i packed two archives: V1/JB2 Rocket Sounds, and soundtrack [https://drive.google.com/open?id=14O4mf ... 8ruValodvl](https://drive.google.com/open?id=14O4mfNKLBIojs2B2owVYLi8ruValodvl)
[https://drive.google.com/open?id=120Fde ... 6IFIpP35i3](https://drive.google.com/open?id=120Fde2kJavhbuJA_-mTlNI6IFIpP35i3)
## Post #32
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2018-12-09T12:26:13+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BGmoder
>
> Yea, but, i packed two archives: V1/JB2 Rocket Sounds, and soundtrack https://drive.google.com/open?id=14O4mf ... 8ruValodvl
https://drive.google.com/open?id=120Fde ... 6IFIpP35i3

Did you solve the problem from python ?
## Post #33
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-09T12:29:22+00:00
- Post Title: Re: Battlefield V .cas .cat

One man unelegal, from Frosty ToolSuite channel give me fix. And i edit script, and this working   [https://cdn.discordapp.com/attachments/ ... perFix.rar](https://cdn.discordapp.com/attachments/485815052025462796/521301222733381632/BFVDumperFix.rar)
## Post #34
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2018-12-09T18:41:54+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BGmoder
>
> One man unelegal, from Frosty ToolSuite channel give me fix. And i edit script, and this working   https://cdn.discordapp.com/attachments/ ... perFix.rar

Thanks man, i will test it tomorrow.  
The only difference is that those lines were added.



adad.JPG (167.79 KiB) Viewed 417 times
## Post #35
- Username: BGmoder
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Nov 22, 2018 7:43 pm
- Post datetime: 2018-12-10T06:15:11+00:00
- Post Title: Re: Battlefield V .cas .cat

761 line, after try going binBundle=BinaryBundle(bundleFile.fileRef.getCas(catalogs), bundleFile.offset)
[21..JPG](https://xentaxbackup.github.io/file/15301_21..JPG)
## Post #36
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-25T19:08:23+00:00
- Post Title: Re: Battlefield V .cas .cat

Could i have all the raw/lossless music files, i cant figure out how to rip this lol
## Post #37
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-26T05:40:06+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> Could i have all the raw/lossless music files, i cant figure out how to rip this lol
As far as I know the raw files not only are highly illegal/DMCA stuff, but there is no such lossless sound/music in the game, they where already encoded by the devs during game development thus no longer lossless, at best you can just grab the scripts make sure you have correct settings/paths and dump game, then decode music yourself, you really have every bit of information already available.
## Post #38
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-26T13:33:12+00:00
- Post Title: Re: Battlefield V .cas .cat

This is as far as i can get, im stuck here:


Traceback (most recent call last):
  File "C:\Users\Chuck\Desktop\BFVDumperFix\Audio\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 829, in <module>
    processManifest(bf1Directory)
  File "C:\Users\Chuck\Desktop\BFVDumperFix\Audio\BfVPreset\Dump Scripts\swbf2_bfv_dumper.py", line 725, in processManifest
    layout = cas.readToc(root + "\\Data\\layout.toc")
  File "C:\Users\Chuck\Desktop\BFVDumperFix\Audio\BfVPreset\Dump Scripts\cas.py", line 102, in readToc
    return Entry(unXor(tocPath))
  File "C:\Users\Chuck\Desktop\BFVDumperFix\Audio\BfVPreset\Dump Scripts\cas.py", line 84, in unXor
    f=open(path,"rb")
IOError: [Errno 2] No such file or directory: 'C:\\Users\\Chuck\\Desktop\\BATTLEFIELD V FILES\\mp_installpkg\\Data\\layout.toc'
## Post #39
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-27T01:25:37+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> IOError: [Errno 2] No such file or directory: 'C:\\Users\\Chuck\\Desktop\\BATTLEFIELD V FILES\\mp_installpkg\\Data\\layout.toc'
Huh, how did you end up having such an error based on the script baffles me, but, lets take one step at a time.
You used old script, new one was slightly modified by GalaxyMan2015 to support latest updates, did you used correct paths, did you enable necessary parameters, there for, lets begin.

First you need to install python, versions between 2.7.3-64bit up to 2.7.15-64bit will work, default settings and path installation is fine, after that you need to grab last updated script, I named the .zip 2nd to know which one people are using to avoid confusion in future.


 BFV_2nd_dumper.zip
Updated script about the mentioned error down below. (181 KiB) Downloaded 154 times


After that done right click on: swbf2_bfv_dumper.py
And click: Edit with IDLE
The IDLE window will open and you'll see a bunch of text in green/red/black/blue/orange
Scroll down a bit and on the following strings:
Change bf1Directory = r"[GameDirectory]" to where your game is installed.
Change targetDirectory = r"[OutDirectory]" to where you want to dump the game (make sure its different HDD to speed things up)
Example:

```
targetDirectory   = r"D:\BFV_dump"
```


And then right under those strings above the following should look like this, all set to True,

```
# EVERYTHING ELSE ←↓
dumpResEnabled = True
dumpChunksEnabled = True
dumpChunksTocEnabled = True
```


After making sure you set correct paths and settings, hit F5 on your keyboard, click OK when prompted.
Now another IDLE window will open showing all game assets being dumped in blue strings, just let it run.
Once you will see this >>> as last line means its done, it can take between tens of minutes to even more than an hour, or if you have an old computer half a day, so be prepared regardless.

Now that you have whole game dumped, audio decoding is next.
Now make sure you uninstall that python 64-bit and now grab the 32-bit this time, because the required components do not support 64-bit, and install it same way you did the other one.
Get the BFVdecoder script posted here on previous page: [viewtopic.php?p=146185#p146185](http://forum.xentax.com/viewtopic.php?p=146185#p146185)
And make sure the following are changed accordingly, don't touch anything else, unless you know what your doing of course.

```
targetDirectory     = r"X:\YOUR PATH GOES HERE"

ealayer3Path        = r"X:\YOUR PATH GOES HERE\ealayer3.exe"
```

As you can see the steps are similar just different scripts, you get the idea.

PS: these steps work assuming you have a legit copy of the game with files intact and not corrupted, with their required file/folder structure, this is 100% procedure for 100% success rate, period, no other errors occur if everything done right.
Just be patient and follow through every step.

have fun
## Post #40
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-12-27T05:19:57+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from mono24
>
> BRAGme wrote:IOError: [Errno 2] No such file or directory: 'C:\\Users\\Chuck\\Desktop\\BATTLEFIELD V FILES\\mp_installpkg\\Data\\layout.toc'
Huh, how did you end up having such an error based on the script baffles me, but, lets take one step at a time.
You used old script, new one was slightly modified by GalaxyMan2015 to support latest updates, did you used correct paths, did you enable necessary parameters, there for, lets begin.

First you need to install python, versions between 2.7.3-64bit up to 2.7.15-64bit will work, default settings and path installation is fine, after that you need to grab last updated script, I named the .zip 2nd to know which one people are using to avoid confusion in future.
BFV_2nd_dumper.zip
After that done right click on: swbf2_bfv_dumper.py
And click: Edit with IDLE
The IDLE window will open and you'll see a bunch of text in green/red/black/blue/orange
Scroll down a bit and on the following strings:
Change bf1Directory = r"[GameDirectory]" to where your game is installed.
Change targetDirectory = r"[OutDirectory]" to where you want to dump the game (make sure its different HDD to speed things up)
Example:
Code: Select allbf1Directory   = r"C:\Origin\Battlefield V"
targetDirectory   = r"D:\BFV_dump"

And then right under those strings above the following should look like this, all set to True,
Code: Select alldumpEbxEnabled = True  # DATA
# EVERYTHING ELSE ←↓
dumpResEnabled = True
dumpChunksEnabled = True
dumpChunksTocEnabled = True

After making sure you set correct paths and settings, hit F5 on your keyboard, click OK when prompted.
Now another IDLE window will open showing all game assets being dumped in blue strings, just let it run.
Once you will see this >>> as last line means its done, it can take between tens of minutes to even more than an hour, or if you have an old computer half a day, so be prepared regardless.

Now that you have whole game dumped, audio decoding is next.
Now make sure you uninstall that python 64-bit and now grab the 32-bit this time, because the required components do not support 64-bit, and install it same way you did the other one.
Get the BFVdecoder script posted here on previous page: viewtopic.php?p=146185#p146185
And make sure the following are changed accordingly, don't touch anything else, unless you know what your doing of course.
Code: Select alldumpDirectory       = r"X:\YOUR PATH GOES HERE"
targetDirectory     = r"X:\YOUR PATH GOES HERE"

ealayer3Path        = r"X:\YOUR PATH GOES HERE\ealayer3.exe"
As you can see the steps are similar just different scripts, you get the idea.

PS: these steps work assuming you have a legit copy of the game with files intact and not corrupted, with their required file/folder structure, this is 100% procedure for 100% success rate, period, no other errors occur if everything done right.
Just be patient and follow through every step.

have fun

Does this mean you can now give us the entire sound directory?
## Post #41
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-27T05:40:34+00:00
- Post Title: Re: Battlefield V .cas .cat

Ok now the problem i ran across is this: 

for installChunk in layout.installManifest.installChunks:
        catFile=root + "\\Data\\Win32\\" + installChunk.name + "\\cas.cat"
                 if not(installChunk.name.startswith("installation/default")):
            catalogs.append(root + "\\[PATH]\\Win32\\" + installChunk.name + "\\")

It said theres an error in your program: unexpected indent. That indent is right before it says "if not(installChunk.name.startswith("installation/default")):
## Post #42
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-28T03:48:33+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Puterboy1
>
> Does this mean you can now give us the entire sound directory?
You have every necessary needed tools to do that yourself, don't beg for actual game files, those are illegal, own the game and play with to your own hearts content in your own privacy.
And do NOT quote the whole freaking comment, your making a mess.

> Reply from BRAGme
>
> It said theres an error in your program: unexpected indent. That indent is right before it says "if not(installChunk.name.startswith("installation/default")):
Make sure you at least include an error as such in a code not as text as it gets scrambled, like this:

```
        catFile=root + "\\Data\\Win32\\" + installChunk.name + "\\cas.cat"
		if not(installChunk.name.startswith("installation/default")):
            catalogs.append(root + "\\[PATH]\\Win32\\" + installChunk.name + "\\")

```

An also a screenshot explains better what is going on, even code mode for text messes up the lines, but since I know what is that error about all you have to do is remove those two tab spaces and your good to go, like this, see the difference?

```
        catFile=root + "\\Data\\Win32\\" + installChunk.name + "\\cas.cat"
        if not(installChunk.name.startswith("installation/default")):
            catalogs.append(root + "\\[PATH]\\Win32\\" + installChunk.name + "\\")

```




Example of wrong vs correct. sample.JPG (44.61 KiB) Viewed 364 times



I've also corrected it myself and updated the link above.
## Post #43
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-28T14:20:11+00:00
- Post Title: Re: Battlefield V .cas .cat

Problem after problem lol, so i redownloaded your updated script, now i have this error:
[Error.PNG](https://xentaxbackup.github.io/file/15394_Error.PNG)
## Post #44
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-28T16:18:57+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> Problem after problem lol, so i redownloaded your updated script, now i have this error:
Attach that .TOC, I want to check it.
But it clearly seems your doing something wrong with your selected game path, so that is NOT a script error, its a error caused by your path selection, like it cant access it to move forward.

But if you cant find it means you have a pirated version, or borrowed files from a friend or something, because with out it the process will never be able to continue.
## Post #45
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-29T14:13:08+00:00
- Post Title: Re: Battlefield V .cas .cat

Ok so the .toc was in another location. Its now where its supposed to be, But now i have this error: (EDIT- I dont have any sound files, thats what im looking for)
[Erroe.PNG](https://xentaxbackup.github.io/file/15395_Erroe.PNG)
## Post #46
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-30T00:16:31+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> I dont have any sound files, thats what im looking for)
There's clearly something wrong with your files, no error occurs on a retail copy of the game form Origin, with files/folder structure intact, period, everything works smooth.
I'm afraid you'll be on your own from now on to discover what is your doing wrong, your game files are incomplete, and obviously not having latest version.
## Post #47
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2018-12-30T14:20:07+00:00
- Post Title: Re: Battlefield V .cas .cat

Ok i appreciate you trying to help me, could you upload the frostbite 2 engine script so i can rip those fb2 engine games?
## Post #48
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-01-03T13:25:43+00:00
- Post Title: Re: Battlefield V .cas .cat

This script works perfectly.

[https://mega.nz/#!y8Ng3Q6I!f9CjWE2fcFY_ ... jxtWD9j_9Q](https://mega.nz/#!y8Ng3Q6I!f9CjWE2fcFY_UMgnJoeWsCrfSJqgHzDotjxtWD9j_9Q)

Don't forget ! You must use a python 32-bit software to extract audio files when you have ebx, chunk files.
The texture tool also works (res files are indispensable).
## Post #49
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-04T01:01:50+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Damoclès
>
> This script works perfectly.
Once again another example of no one reading anything or doing a bit of research, literally nothing, anyway.
He does NOT have a problem with the script, in the end was all about incomplete files and wrong file/folder structure, if you would have paid attention on previous posts I used already the last script updated by GMan.
And what needs to be done to achieve accurate results, so on and so forth.
## Post #50
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2019-01-04T08:31:23+00:00
- Post Title: Re: Battlefield V .cas .cat

Actually he's right, I downloaded that script and now I got all the files. Now can I convert those scoundrels to WAV and not mp3?
## Post #51
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-04T09:17:52+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> Actually he's right
It is odd none the less giving the fact its simply the same updated script by GMan, and it works smooth on my end with original game files, yet looking at them both side by side it seems that bfv_dumper_fix_2.1.py has some spaces/tabs/indentations adjusted, yet makes no sense why you where unable to dump since its still original untouched script.

> Reply from BRAGme
>
> WAV and not mp3



wav.JPG (10.74 KiB) Viewed 293 times
## Post #52
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2019-01-04T14:01:48+00:00
- Post Title: Re: Battlefield V .cas .cat

EALayer 3 is giving me wav files but the sound data is still cut off, in order for no data cut off, also it says XAS and EASpeex dll not detected, where do i put those?
Edit- i forgot to reinstall 32bit lol now its working
## Post #53
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2019-01-05T15:24:59+00:00
- Post Title: Re: Battlefield V .cas .cat

I know this isnt BFV but im trying to dump Hardline and i come across this issue
[Capture.PNG](https://xentaxbackup.github.io/file/15420_Capture.PNG)
## Post #54
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-06T00:22:59+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme
>
> I know this isnt BFV but im trying to dump Hardline and i come across this issue
It works if you have the rest of the DLCs/Extra content the game has otherwise it will not continue with extraction.
Usually these games extract smoothly as long as people have complete files, otherwise you'll have to remove files from folder structure in order to progress.
Basically your missing Expansion Packs that the game has, plus their required updates.
The game has 4 XPacks and you've reached first one that is missing.
## Post #55
- Username: squanders
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 22, 2018 9:44 pm
- Post datetime: 2019-01-18T18:48:02+00:00
- Post Title: Re: Battlefield V .cas .cat

Hey, how many hours shall it take normally for dumping the BFV files?
## Post #56
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-19T00:49:28+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from squanders
>
> Hey, how many hours shall it take normally for dumping the BFV files?
It can take between 40min up to 9h+, that varies based on multiple factors, such as location of both game and dump, HDD or SSD so on and so forth.
## Post #57
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2019-01-24T03:08:43+00:00
- Post Title: Re: Battlefield V .cas .cat

Would anyone like to send me the sound files for the Stuka, I might want to use the Jericho Trumpet sound effects for a project or two.
## Post #58
- Username: stalja
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Sep 12, 2009 6:33 pm
- Post datetime: 2019-01-28T15:06:30+00:00
- Post Title: Re: Battlefield V .cas .cat

For demo of a new frostbite game they seem to have changed the structure again. The manifest seems to be missing from layout.toc. I get the following error in python:

> Traceback (most recent call last):
>
>   File "E:\dontmatter\swbf2_bfv_dumper.py", line 830, in <module>
>
>     processManifest(bf1Directory)
>
>   File "E:\dontmatter\swbf2_bfv_dumper.py", line 732, in processManifest
>
>     fileRef = ManifestFileRef(manifest.file)
>
> AttributeError: 'NoneType' object has no attribute 'file'

When I do the following:

```
    l = dir(layout)
    print l
```


I get :

```
['__doc__', '__init__', '__module__', 'fs', 'get', 'head', 'installManifest', 'superBundles']
```


So ... no manifest to read from.
## Post #59
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-28T21:49:10+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from stalja
>
> For Anthem demo they seem to have changed the structure again.
Yes its already known, the script is useless because its a completely new format that it does NOT involve cas.cat files anymore, I am sure sooner or later someone will come up with something, until then I'd suggest to not post any game files because the game is not officially out yet.
The devs can change their mind and screw things up more for us, if you know what I mean.
## Post #60
- Username: idchoppers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 29, 2019 6:12 am
- Post datetime: 2019-05-29T00:09:33+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from mono24 ↑Thu Dec 27, 2018 9:25 am at Thu Dec 27, 2018 9:25 am
>
> 
BRAGme wrote:IOError: [Errno 2] No such file or directory: 'C:\\Users\\Chuck\\Desktop\\BATTLEFIELD V FILES\\mp_installpkg\\Data\\layout.toc'
Huh, how did you end up having such an error based on the script baffles me, but, lets take one step at a time.
You used old script, new one was slightly modified by GalaxyMan2015 to support latest updates, did you used correct paths, did you enable necessary parameters, there for, lets begin.

First you need to install python, versions between 2.7.3-64bit up to 2.7.15-64bit will work, default settings and path installation is fine, after that you need to grab last updated script, I named the .zip 2nd to know which one people are using to avoid confusion in future.
........
PS: these steps work assuming you have a legit copy of the game with files intact and not corrupted, with their required file/folder structure, this is 100% procedure for 100% success rate, period, no other errors occur if everything done right.
Just be patient and follow through every step.

have fun

Dear mono, first off thanks for your excellent work. I've followed every step and triple checked everything, but still I'm getting an error while extracting Battlefront 2 (original copy), I even repaired my installation to make sure any files were not corrupt.

Here's where it stops:

```
EBX
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/mpvur_d_heavy_orig_mos_01_bpb.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/d_heavy_orig_mos_01.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/texture/t_d_heavy_orig_mos_01_parts_cs.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/texture/t_d_heavy_orig_mos_01_nm.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/texture/t_d_heavy_orig_mos_01_cs.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/texture/t_d_heavy_orig_mos_01_backpack_cs.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/texture/t_d_heavy_orig_mos_01_aosl.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/mpvur_d_heavy_orig_mos_01_bpb/meshvariationdb_win32.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/d_heavy_orig_mos_01_parts.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/d_heavy_orig_mos_01_mesh.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_heavy_orig/d_heavy_orig_mos_01/d_heavy_orig_01_backpack_mos.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_assault_orig/d_assault_orig_mos_01/texture/t_d_assault_orig_mos_01_helmet_cs.ebx
 K:\BF2_dump/bundles/ebx/characters/dark/d_assault_orig/d_assault_orig_mos_01/d_assault_orig_mos_01_helmet.ebx
RES
excepted error: 3639990959L
```


I'm only interested in the audio but followed the instructions to dump everything to avoid issues. I've tried dumping to different disks and still it stops in the exact same spot. Mono or anyone else has any idea why this is happening?  Thanks in advance!
## Post #61
- Username: idchoppers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 29, 2019 6:12 am
- Post datetime: 2019-05-29T12:00:12+00:00
- Post Title: Re: Battlefield V .cas .cat

I was able to extract all chunks and ebx files, but no res due to the error in my previous post. I looked at the BFVdecoder.py and there is no mention to any res... is it really necessary? 

Anyway, I tried to decode and nothing happens:

```
Type "copyright", "credits" or "license()" for more information.
>>> ================================ RESTART ================================
>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.
>>> 
```


Any ideas?
## Post #62
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-31T04:41:49+00:00
- Post Title: Re: Battlefield V .cas .cat

What game are you working on though, I am confused, STAR WARS Battlefront II?
The BFV audio script is not working with SWBFII game to decode audio. Assuming that's the game your working on.
## Post #63
- Username: idchoppers
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 29, 2019 6:12 am
- Post datetime: 2019-05-31T06:03:04+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from mono24 ↑Fri May 31, 2019 12:41 pm at Fri May 31, 2019 12:41 pm
>
> 
What game are you working on though, I am confused, STAR WARS Battlefront II?
The BFV audio script is not working with SWBFII game to decode audio. Assuming that's the game your working on.

Yes, Star Wars Battlefront II. Is there any other script that is working? I had partial luck with this one [https://cdn.discordapp.com/attachments/ ... perFix.rar](https://cdn.discordapp.com/attachments/485815052025462796/521301222733381632/BFVDumperFix.rar) the script inside the Audio folder decodes 33 WAV files (Titan mode music) out of 18,000 files. Here's how it looks like:



Files inside green rectangles were decoded. Red ones (the vast majority) nothing happened. Any ideas?
## Post #64
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-05-31T15:46:45+00:00
- Post Title: Re: Battlefield V .cas .cat

Don't remember where it is exactly, daemon1 posted it here in his main thread, the audio decoder script, just take one page at a time and see his posts, its in there somewhere:
[https://forum.xentax.com/viewtopic.php?f=16&t=17114](https://forum.xentax.com/viewtopic.php?f=16&t=17114)

good luck
## Post #65
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2019-06-22T19:24:37+00:00
- Post Title: Re: Battlefield V .cas .cat

You can now easily extract sounds, models with the FrostyEditor.

[https://frostytoolsuitedev.gitlab.io/downloads.html](https://frostytoolsuitedev.gitlab.io/downloads.html)
## Post #66
- Username: Fnftab
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 31, 2019 1:06 pm
- Post datetime: 2019-08-31T05:10:54+00:00
- Post Title: Re: Battlefield V .cas .cat

I read all comments but i need experts help. Will this scrpt works on  crkd vr. of bf5. I tried but while extracting chunks it gave some failed process. And i only got chunks folder of around 38 gb.
## Post #67
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-08-31T12:51:57+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Fnftab ↑Sat Aug 31, 2019 1:10 pm at Sat Aug 31, 2019 1:10 pm
>
> while extracting chunks it gave some failed process.
Post a screenshot of the error.
## Post #68
- Username: hbelouf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 8:43 am
- Post datetime: 2019-10-22T16:53:46+00:00
- Post Title: Re: Battlefield V .cas .cat

I wanted to find out if there are any videos(FMVs) embedded inside?
## Post #69
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-22T19:03:41+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from hbelouf ↑Wed Oct 23, 2019 12:53 am at Wed Oct 23, 2019 12:53 am
>
> 
I wanted to find out if there are any videos(FMVs) embedded inside?
Not sure what you mean by embedded, their just inside the cas/cat archives.
If I remember correctly they should all be VP8/WEBM videos.
This is a random sample:

```
Format version              : Version 2
File size                   : 527 MiB
Duration                    : 4 min 16 s
Overall bit rate mode       : Variable
Overall bit rate            : 17.2 Mb/s
Writing application         : Lavf56.40.101
Writing library             : Lavf56.40.101

Video
ID                          : 1
Format                      : VP8
Codec ID                    : V_VP8
Duration                    : 4 min 16 s
Bit rate                    : 16.1 Mb/s
Width                       : 1 920 pixels
Height                      : 1 080 pixels
Display aspect ratio        : 16:9
Frame rate mode             : Constant
Frame rate                  : 30.000 FPS
Compression mode            : Lossy
Bits/(Pixel*Frame)          : 0.259
Stream size                 : 492 MiB (93%)
Language                    : English
Default                     : Yes
Forced                      : No

Audio
ID                          : 2
Format                      : Vorbis
Format settings, Floor      : 1 / 8710
Codec ID                    : A_VORBIS
Duration                    : 4 min 16 s
Bit rate mode               : Variable
Bit rate                    : 450 kb/s
Channel(s)                  : 6 channels
Sampling rate               : 48.0 kHz
Compression mode            : Lossy
Delay relative to video     : -3 ms
Stream size                 : 13.8 MiB (3%)
Writing application         : Lavc56.58.100
Writing library             : libVorbis (⛄⛄⛄⛄) (20150105 (⛄⛄⛄⛄))
Language                    : English
Default                     : No
Forced                      : No
```
## Post #70
- Username: hbelouf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 06, 2011 8:43 am
- Post datetime: 2019-10-24T23:36:21+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from mono24 ↑Wed Oct 23, 2019 3:03 am at Wed Oct 23, 2019 3:03 am
>
> 
hbelouf wrote: ↑Wed Oct 23, 2019 12:53 am
I wanted to find out if there are any videos(FMVs) embedded inside?
Not sure what you mean by embedded, their just inside the cas/cat archives.
If I remember correctly they should all be VP8/WEBM videos.
This is a random sample:
Code: Select allFormat                      : WebM
Format version              : Version 2
File size                   : 527 MiB
Duration                    : 4 min 16 s
Overall bit rate mode       : Variable
Overall bit rate            : 17.2 Mb/s
Writing application         : Lavf56.40.101
Writing library             : Lavf56.40.101

Video
ID                          : 1
Format                      : VP8
Codec ID                    : V_VP8
Duration                    : 4 min 16 s
Bit rate                    : 16.1 Mb/s
Width                       : 1 920 pixels
Height                      : 1 080 pixels
Display aspect ratio        : 16:9
Frame rate mode             : Constant
Frame rate                  : 30.000 FPS
Compression mode            : Lossy
Bits/(Pixel*Frame)          : 0.259
Stream size                 : 492 MiB (93%)
Language                    : English
Default                     : Yes
Forced                      : No

Audio
ID                          : 2
Format                      : Vorbis
Format settings, Floor      : 1 / 8710
Codec ID                    : A_VORBIS
Duration                    : 4 min 16 s
Bit rate mode               : Variable
Bit rate                    : 450 kb/s
Channel(s)                  : 6 channels
Sampling rate               : 48.0 kHz
Compression mode            : Lossy
Delay relative to video     : -3 ms
Stream size                 : 13.8 MiB (3%)
Writing application         : Lavc56.58.100
Writing library             : libVorbis (⛄⛄⛄⛄) (20150105 (⛄⛄⛄⛄))
Language                    : English
Default                     : No
Forced                      : No

Thank you, that is what I am looking for.
## Post #71
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2019-10-26T15:34:18+00:00
- Post Title: Re: Battlefield V .cas .cat

Not sure what you mean by embedded, their just inside the cas/cat archives.
If I remember correctly they should all be VP8/WEBM videos.
This is a random sample:

```
Format version              : Version 2
File size                   : 527 MiB
Duration                    : 4 min 16 s
Overall bit rate mode       : Variable
Overall bit rate            : 17.2 Mb/s
Writing application         : Lavf56.40.101
Writing library             : Lavf56.40.101

Video
ID                          : 1
Format                      : VP8
Codec ID                    : V_VP8
Duration                    : 4 min 16 s
Bit rate                    : 16.1 Mb/s
Width                       : 1 920 pixels
Height                      : 1 080 pixels
Display aspect ratio        : 16:9
Frame rate mode             : Constant
Frame rate                  : 30.000 FPS
Compression mode            : Lossy
Bits/(Pixel*Frame)          : 0.259
Stream size                 : 492 MiB (93%)
Language                    : English
Default                     : Yes
Forced                      : No

Audio
ID                          : 2
Format                      : Vorbis
Format settings, Floor      : 1 / 8710
Codec ID                    : A_VORBIS
Duration                    : 4 min 16 s
Bit rate mode               : Variable
Bit rate                    : 450 kb/s
Channel(s)                  : 6 channels
Sampling rate               : 48.0 kHz
Compression mode            : Lossy
Delay relative to video     : -3 ms
Stream size                 : 13.8 MiB (3%)
Writing application         : Lavc56.58.100
Writing library             : libVorbis (⛄⛄⛄⛄) (20150105 (⛄⛄⛄⛄))
Language                    : English
Default                     : No
Forced                      : No
```


Im wondering where do you extract these files? Can i use FrostyEditor to get them?
## Post #72
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-26T23:22:38+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme ↑Sat Oct 26, 2019 11:34 pm at Sat Oct 26, 2019 11:34 pm
>
> Im wondering where do you extract these files? Can i use FrostyEditor to get them?
BTW, you didn't properly embedded my message in to CODE and I got sooo confused lol.

As Frosty dev said numerous times, Frosty will never be used for mass extraction of any kind, you need to use the python script to dump them, or any other asset for that matter.
And to be honest I don't think Frosty supports the extraction of cinematic videos.
## Post #73
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2019-10-27T13:19:45+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from mono24 ↑Sun Oct 27, 2019 7:22 am at Sun Oct 27, 2019 7:22 am
>
> 
BRAGme wrote: ↑Sat Oct 26, 2019 11:34 pmIm wondering where do you extract these files? Can i use FrostyEditor to get them?
BTW, you didn't properly embedded my message in to CODE and I got sooo confused lol.

As Frosty dev said numerous times, Frosty will never be used for mass extraction of any kind, you need to use the python script to dump them, or any other asset for that matter.
And to be honest I don't think Frosty supports the extraction of cinematic videos.
Oh sorry the auto quote was messed up lol. So im trying to use the fb3 decoder and im getting this error, what is wrong?
[Capture.PNG](https://xentaxbackup.github.io/file/16951_Capture.PNG)
## Post #74
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-27T23:14:14+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from BRAGme ↑Sun Oct 27, 2019 9:19 pm at Sun Oct 27, 2019 9:19 pm
>
> So im trying to use the fb3 decoder and im getting this error, what is wrong?
Ummm, looks like your using wrong one, you need this: [viewtopic.php?p=146185#p146185](https://forum.xentax.com/viewtopic.php?p=146185#p146185)
## Post #75
- Username: zestoflemon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 22, 2019 8:02 pm
- Post datetime: 2020-02-08T17:36:45+00:00
- Post Title: Re: Battlefield V .cas .cat

Hello All. I have been a long time lurker and have benefited from the excellent tools and advice on this forum. For a while, I have been able to extract BFV sound data into wav/mp3 but since the recent 6.0 patch (as of 9th, Feb. 2020), I no longer can. 

I wonder is it the patch that is at fault or just me forgetting a crucial step. It might also be the BFV Dumper that is faulty in the first place and not a problem with the BFVdecoder. All tools used are up to date (to the best of my knowledge) and running on the correct python versions.

It seems that I can dump the BFV data just fine but when running BFVdecoder, I consistently get this error:

```
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.

Traceback (most recent call last):
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 540, in <module>
    main()
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 537, in main
    dbx.decode()
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 398, in decode
    for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 169, in get
    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
Exception: Could not find complex with name: $::SoundDataAsset
Full path: $::SoundDataAsset/Chunks::array
Filename: Sound/PlaceholderDummy_Casablanca
>>> 
```


Could it be a faulty dump (I have dumped the files twice to check) or has something changed with the update? Thank you in advance.
## Post #76
- Username: Sebastiel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 24, 2016 10:10 am
- Post datetime: 2020-02-21T02:33:35+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from zestoflemon ↑Sun Feb 09, 2020 1:36 am at Sun Feb 09, 2020 1:36 am
>
> 
Code: Select all>>> 
XAS1 dll detected.
EASpeex dll detected.
EALayer3 tool detected.

Traceback (most recent call last):
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 540, in <module>
    main()
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 537, in main
    dbx.decode()
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 398, in decode
    for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
  File "D:\BFV Dump Tools\BFVdecoder\BFVdecoder.py", line 169, in get
    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
Exception: Could not find complex with name: $::SoundDataAsset
Full path: $::SoundDataAsset/Chunks::array
Filename: Sound/PlaceholderDummy_Casablanca
>>>

I'm having the EXACT same error, unfortunately just like you I can't tell what's the problem here: the dumper or the decoder. 

Hopefully someone will update them to work with the latest version of the game.

It's either that or both of us are making the very same mistake lol
## Post #77
- Username: BRAGme
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Dec 10, 2017 10:28 am
- Post datetime: 2020-02-26T17:50:53+00:00
- Post Title: Re: Battlefield V .cas .cat

I get the exact same error, its most likely on the games update side
## Post #78
- Username: Akkurat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 16, 2020 5:12 am
- Post datetime: 2020-06-16T17:26:21+00:00
- Post Title: Re: Battlefield V .cas .cat

I'm getting the same error as zestoflemon, Sebastiel, and BRAGme. Does anyone have access or knowledge to create an updated decoder script for the latest version of BFV?
## Post #79
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2020-10-09T13:30:02+00:00
- Post Title: Re: Battlefield V .cas .cat

I finally solved the problem in which the script could not "find complex with name: $::SoundDataAsset"
I'm a noob in programming/coding so this took me hours.

Anyway i converted some bf4 and bfV .ebx sound files to .txt files in order to compare them, after all the audio decoder works fine with bf4 .ebx files. 



tttr.jpg (105.49 KiB) Viewed 362 times



The python script tries to reach the Chunk datas with the given path but since the recent bfv updates the path has changed as you can see. 

"$::SoundDataAsset/Chunks::array" has to be replaced by "$::SoundWaveAssetBase/$::SoundDataAsset/Chunks::array"

Line 419, fb3decoder.py file
## Post #80
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-09T17:33:19+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Damoclès ↑Fri Oct 09, 2020 9:30 pm at Fri Oct 09, 2020 9:30 pm
>
> ...The python script tries to reach the Chunk datas with the given path but since the recent bfv updates the path has changed as you can see. 

"$::SoundDataAsset/Chunks::array" has to be replaced by "$::SoundWaveAssetBase/$::SoundDataAsset/Chunks::array"

Line 419, fb3decoder.py file
That is a nice find, i haven't messed with these Frostbite games in so long, will give it a try myself, had no clue there was an issue before, hm.

PS:
Although i'd normally do NOT recommend those decoders any more since at the time they where the only solution available, and results where not always accurate, and ever since these: https://github.com/NicknineTheEagle/Frostbite-Scripts have become available, the rest of old stuff has rendered obsolete.
## Post #81
- Username: Eradicon
- Rank: beginner
- Number of posts: 28
- Joined date: Fri Feb 11, 2011 1:20 am
- Post datetime: 2020-10-12T02:52:54+00:00
- Post Title: Re: Battlefield V .cas .cat

Will this work on Star Wars Squadrons? I want to get some certain files for personal reasons. And is there even a tutorial that I can learn from this step by step?
## Post #82
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-10-12T14:06:48+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from Eradicon ↑Mon Oct 12, 2020 10:52 am at Mon Oct 12, 2020 10:52 am
>
> 
Will this work on Star Wars Squadrons?
The above link ONLY works for audio extracted AFTER the game has been dumped first with the old SWBFII script, as both games share same structure as BFV.

> Reply from Eradicon ↑Mon Oct 12, 2020 10:52 am at Mon Oct 12, 2020 10:52 am
>
> And is there even a tutorial that I can learn from this step by step?
Yes, this forum is FULL of them, and your in the right thread too, read a long and you'll see what you need to do.

have fun
## Post #83
- Username: ironsniper1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 16, 2020 12:18 pm
- Post datetime: 2020-10-16T04:20:41+00:00
- Post Title: Re: Battlefield V .cas .cat

anyone else manage to get models and textures from star wars squadrons? so far i have only been able to extract everything and get the ebx files
## Post #84
- Username: CobeFelon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 23, 2021 5:52 am
- Post datetime: 2021-03-22T21:53:12+00:00
- Post Title: Re: Battlefield V .cas .cat

A common problem with the latest BF5 updates downloaded via the origin platform. Honestly, many players are just tired of developer errors that prevent you from performing any actions with the game, I have it started to hang and lag very much that even my skill does not help to play. So I took and downloaded the cheats from [wallhax.com/hacks/battlefield-5/](https://wallhax.com/hacks/battlefield-5/) to play and after a couple of updates do not go into this game anymore. BUT I enjoyed playing with cheats so much that now it's a great pleasure for me, I do 13 kills per game. I think this is a very good result for such a level of play as I have. I advise developers to fix their errors.
## Post #85
- Username: tretretrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 12, 2021 4:49 pm
- Post datetime: 2021-08-12T08:53:26+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from stalja ↑Mon Jan 28, 2019 11:06 pm at Mon Jan 28, 2019 11:06 pm
>
> 
For demo of a new frostbite game they seem to have changed the structure again. The manifest seems to be missing from layout.toc. I get the following error in python:
Traceback (most recent call last):
  File "E:\dontmatter\swbf2_bfv_dumper.py", line 830, in <module>
    processManifest(bf1Directory)
  File "E:\dontmatter\swbf2_bfv_dumper.py", line 732, in processManifest
    fileRef = ManifestFileRef(manifest.file)
AttributeError: 'NoneType' object has no attribute 'file'

When I do the following:
Code: Select alllayout = cas.readToc(root + "\\Data\\layout.toc")
    l = dir(layout)
    print l

I get :
Code: Select all['__doc__', '__init__', '__module__', 'fs', 'get', 'head', 'installManifest', 'superBundles']

So ... no manifest to read from.

Hello i've been trying to look at BF2042 files (im in the tech alpha)
and i get the same result as you.
and like mono24 mentioned : "Yes its already known, the script is useless because its a completely new format that it does NOT involve cas.cat files anymore"
the format must have changed.
Anyone else is working on that? 
i'll look around if some tool for Anthem works in the meantime
Edit: yeah tried a tool for anthem and the file structure seems different too
## Post #86
- Username: Damoclès
- Rank: beginner
- Number of posts: 35
- Joined date: Wed Oct 21, 2015 6:10 pm
- Post datetime: 2021-08-12T19:09:36+00:00
- Post Title: Re: Battlefield V .cas .cat

Some of you have access to the tech demo, lucky boys   
Can you please share some of the bf2042 data files ?
## Post #87
- Username: tretretrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 12, 2021 4:49 pm
- Post datetime: 2021-08-13T05:48:50+00:00
- Post Title: Re: Battlefield V .cas .cat

Too risky, you know there are watermark everywhere in game, and i wont doubt they put some inside the files too.
I'm open to advice on how to proceed to extract stuff (i've never done it , but is reasonable tech savy)
for now i tried swbf2_bfv_dumper and anthem tool, didnt work (missing .sb files)
gonna try frosty-toolsuite but i dont have my hopes up
## Post #88
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-08-14T02:54:12+00:00
- Post Title: Re: Battlefield V .cas .cat

This thing is already out there, spread out all over, it just require some search, that's all.
And no, currently no known script will dump the assets nor frosty, as its a new format structure, it has to be reversed and a new python script created for it.
In time.
## Post #89
- Username: tretretrer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 12, 2021 4:49 pm
- Post datetime: 2021-08-14T06:29:03+00:00
- Post Title: Re: Battlefield V .cas .cat

Thx for the confirmation.
"This thing is already out there" you mean the actual files ?
## Post #90
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-08-14T18:47:24+00:00
- Post Title: Re: Battlefield V .cas .cat

> Reply from tretretrer ↑Sat Aug 14, 2021 2:29 pm at Sat Aug 14, 2021 2:29 pm
>
> 
"This thing is already out there" you mean the actual files ?
The entire folder structure, yes.
