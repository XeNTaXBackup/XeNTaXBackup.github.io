## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-12-25T21:34:58+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

Hi folks,

Castlevania: Lords of Shadow – Mirror of Fate HD is available. 

PkgView 1.3 works to extract the files from the PS3 archive. WxPirs-1.1 works to extract the files from the XBLA archive, but the XBLA packages are smaller which I am assuming is because the xbox textures are smaller, therefor I will focus my interest on the PS3 version. Unlike the models, the character textures are not packed in any archives inside of the larger archive, but they are in .bctex format, which I believe is used in 3ds.

The skeletal and static meshes are .bcmdl files stuck in .pkg archives (these are not PS3 pkg archives, they just share the same extension). 

Per forum rules, please PM me for additional data. I would be interested in support for .pkg archives, models and textures in somethings like Quickbms or Noesis.

Cheers!

z
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-26T09:45:28+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

Share any sample archive.
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-12-26T18:10:31+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

> Reply from Ekey
>
> Share any sample archive.

I Pm'd you.
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-12-26T19:30:52+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

For PKG

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big

get TABLESIZE long
get DATASIZE long
get FILES long

for i = 0 < FILES
    getdstring NAME 1024
    get OFFSET long
    get SIZE long
    math SIZE -= OFFSET
    log NAME OFFSET SIZE
next i
```
## Post #5
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2013-12-26T21:12:58+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

Excellent, works perfectly!

Thanks Ekey!
## Post #6
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2014-03-27T20:53:07+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

works for PC edition too, just comment 'endian big'.
## Post #7
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-04-08T07:03:38+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

PC edition no work？
## Post #8
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2014-04-09T06:24:09+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

As the post above you said. 

> # Castlevania: Lords of Shadow – Mirror of Fate HD (PS3) (PKG format)
>
> #
>
> # Written by Ekey (h4x0r)
>
> # http://forum.xentax.com
>
> #
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> endian big
>
> 
>
> get TABLESIZE long
>
> get DATASIZE long
>
> get FILES long
>
> 
>
> for i = 0 < FILES
>
>     getdstring NAME 1024
>
>     get OFFSET long
>
>     get SIZE long
>
>     math SIZE -= OFFSET
>
>     log NAME OFFSET SIZE
>
> next i

to

> # Castlevania: Lords of Shadow – Mirror of Fate HD (PS3) (PKG format)
>
> #
>
> # Written by Ekey (h4x0r)
>
> # http://forum.xentax.com
>
> #
>
> # script for QuickBMS http://quickbms.aluigi.org
>
> 
>
> //endian big
>
> 
>
> get TABLESIZE long
>
> get DATASIZE long
>
> get FILES long
>
> 
>
> for i = 0 < FILES
>
>     getdstring NAME 1024
>
>     get OFFSET long
>
>     get SIZE long
>
>     math SIZE -= OFFSET
>
>     log NAME OFFSET SIZE
>
> next i

Comment out the Endian Big (Big Endian?) statement or what it's called. 
(It works, I tried it although the game has been updated once now but I think it will still work.)
## Post #9
- Username: static77
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 20, 2012 1:37 pm
- Post datetime: 2014-12-28T14:52:44+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

thx. i extracted all files succesfully.
But now i want to reimport the extracted files. which script i have to use?
## Post #10
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-15T17:50:16+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

The same one you used to export the files
## Post #11
- Username: claudiuboy83
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 02, 2014 3:38 pm
- Post datetime: 2016-01-11T10:24:13+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

How can i extract pkg from 3ds Castlevania mirror of Fate?
## Post #12
- Username: BANDIT
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 13, 2011 4:19 am
- Post datetime: 2019-03-07T14:52:54+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

Can someone help me to reimport the extracted files without size limit. I have found some tools but I don't know how it works.
[https://github.com/batteryshark/castleva](https://github.com/batteryshark/castleva)
## Post #13
- Username: Big Boss
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 31, 2020 9:10 am
- Post datetime: 2020-02-07T00:10:02+00:00
- Post Title: Castlevania: Lords of Shadow – Mirror of Fate HD

Hello guys, I'm Big Boss, new here, I work translating games from the Castlevania franchise, and I would like to know if any of you have a script to unpack and compress the Castlevania: Lords of Shadow 2 DLC Revelations, by Xbox 360, because this Script: [https://aluigi.altervista.org/bms/castlevania.bms](https://aluigi.altervista.org/bms/castlevania.bms) did not work for me, it presents an error in the half of the unpacking, and it does not recompact, I tried all that are in this Topic, and I couldn't, I need it, to fix some Localization errors of my language in the game , please help me, thank you ...
