## Post #1
- Username: HANE
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-27T23:59:00+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

俺の妹がこんなに可愛いわけがない。 ハッピーエンド
Ore no Imouto ga Konna ni Kawaii wake ga Nai
My Little Sister Can't Be This Cute HappyEnd
BLJS-10238 / NPJB-00412
[http://oreimo-game.channel.or.jp/](http://oreimo-game.channel.or.jp/)

Quickbms script to extract the dat files.

```
#My Little Sister Can't Be This Cute HappyEnd (PS3)
comtype GZIP
idstring "GPDA64BY"
get TSIZE longlong
get NULL long
get FILES long
savepos TMP
for i = 0 < files
goto TMP
get OFFSET longlong
get NULL longlong
get SIZE longlong
get NOFF longlong
savepos TMP
goto NOFF
get NSIZE long
getdstring NAME NSIZE
set EXT EXTENSION NAME
if EXT == "dat"
log NAME OFFSET SIZE
else
clog NAME OFFSET SIZE SIZE
endif
next i

```
## Post #2
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-28T01:13:24+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

Kirino ¬¬'

Ayase and Kuroneko 



Are you gonna add support for this game in noesis?? Anyways thanks for the bms script.
## Post #3
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2013-09-28T08:50:38+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

俺の妹がこんなに可愛いわけがない。 ハッピーエンド

thank you
## Post #4
- Username: Wioneul
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 15, 2012 6:00 pm
- Post datetime: 2013-10-04T20:44:42+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

Isn't work got error:



error.png (3.28 KiB) Viewed 910 times


What I need to do?
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-04T21:37:29+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

i need more info did you copy it again it has been updated since the original post.
What file are you using it on.
## Post #6
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2013-10-05T02:19:25+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

I got error too
[ore.PNG](https://xentaxbackup.github.io/file/6667_ore.PNG)
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-05T02:45:31+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

try this
[mls.zip](https://xentaxbackup.github.io/file/6668_mls.zip)
## Post #8
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2013-10-05T03:47:29+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

mls.bms same last updated script and I tried mls too but it show same error message

Sorry Im not good at English
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-05T03:59:16+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

I have had weird things with this script in quickbms for no reason if the script does not work for you change

if EXT == "dat"
into
if EXT != "dat"
## Post #10
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2013-10-05T04:38:44+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

Oh it works! !="dat" thanks chrrox
## Post #11
- Username: Wioneul
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Nov 15, 2012 6:00 pm
- Post datetime: 2013-10-05T11:45:06+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

I need help with textures, it's have format dds.phyre...how it convert to dds?

I'm add example.

Edited by CHRROX

[tweeticon_00.dds.rar](https://xentaxbackup.github.io/file/6670_tweeticon_00.dds.rar)
## Post #12
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2013-10-06T09:53:02+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

dds.phyre - dds texture file
dae.phyre - model file

dxt5
edited by chrrox
## Post #13
- Username: Wioneul
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-06T13:22:39+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

I am working on this format I am a little under the weather so it might take me a while.

This is the Header if anyone wants to join in.
kanako_base_face_b.dds.phyre
[http://pastebin.com/raw.php?i=FLJzMJaE](http://pastebin.com/raw.php?i=FLJzMJaE)

```
[1, \'m_asset\',                          (360, 8, 28, 4, 22, 0)]         00 00 00 0A
[2, \'m_assetType\',                      (368, 9, 32, 4, 18, 0)]         00 00 00 03
[3, \'m_vramBufferSize\',                 (380, 0, 72, 4, 0, 0)]          00 10 00 00
[4, \'m_vramBufferAlignment\',            (397, 0, 76, 4, 0, 0)]          00 00 00 80
[5, \'m_hostBufferSize\',                 (419, 0, 80, 4, 0, 0)]          00 00 00 00
[6, \'m_hostBufferAlignment\',            (436, 0, 84, 4, 0, 0)]          00 00 00 80
[7, \'m_phyreMarker\',                    (458, 0, 0, 4, 8, 0)]           PHYR
[8, \'m_size\',                           (472, 0, 4, 4, 8, 0)]           00 00 00 58
[9, \'m_instanceListCount\',              (479, 0, 16, 4, 8, 0)]          00 00 00 02
[10, \'m_packedNamespaceSize\',           (499, 0, 8, 4, 8, 0)]           00 00 0D D5
[11, \'m_arrayFixupSize\',                (521, 0, 20, 4, 8, 0)]          00 00 00 03
[12, \'m_arrayFixupCount\',               (538, 0, 24, 4, 8, 0)]          00 00 00 01
[13, \'m_pointerFixupSize\',              (556, 0, 28, 4, 8, 0)]          00 00 00 0A
[14, \'m_pointerFixupCount\',             (575, 0, 32, 4, 8, 0)]          00 00 00 03
[15, \'m_pointerArrayFixupSize\',         (595, 0, 36, 4, 8, 0)]          00 00 00 00
[16, \'m_pointerArrayFixupCount\',        (619, 0, 40, 4, 8, 0)]          00 00 00 00
[17, \'m_pointersInArraysCount\',         (644, 0, 44, 4, 8, 0)]          00 00 00 00
[18, \'m_userFixupCount\',                (668, 0, 48, 4, 8, 0)]          00 00 00 02
[19, \'m_userFixupDataSize\',             (685, 0, 52, 4, 8, 0)]          00 00 00 10
[20, \'m_totalDataSize\',                 (705, 0, 56, 4, 8, 0)]          00 00 01 0C
[21, \'m_headerClassInstanceCount\',      (721, 0, 60, 4, 8, 0)]          00 00 00 00
[22, \'m_headerClassChildCount\',         (748, 0, 64, 4, 8, 0)]          00 00 00 00
[23, \'m_platformID\',                    (772, 0, 12, 4, 8, 0)]          GCM.
[24, \'m_physicsEngineID\',               (785, 0, 68, 4, 8, 0)]          00 00 00 00

```
## Post #14
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-10-06T21:02:21+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

I found some tools but it didn't work with 'tweeticon_00.dds.phyre'
exhappyend.zip => [http://asmodean.reverse.net/](http://asmodean.reverse.net/)

I wonder would it be possible to make bms script for Sen no kiseki. It also use the same phyre engine.

For example, C_EQU000.pkg => split => asset_GCM.xml, dlight.dds.phyre,
ed8.cgfx#23297864EDDD7ED97E1E5B3505D188AD.phyre, equ000.dae.phyre, ply004_04.dds.phyre
[K-111.png](https://xentaxbackup.github.io/file/6680_K-111.png)
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-06T21:54:16+00:00
- Post Title: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB00412

Did you extract that file the file you posted is  a .gz file.
## Post #16
- Username: albert1905
- Rank: veteran
- Number of posts: 93
- Joined date: Wed May 09, 2012 8:13 pm
- Post datetime: 2013-10-06T22:12:20+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

> Reply from chrrox
>
> Did you extract that file the file you posted is  a .gz file.

You mean 'tweeticon_00.dds.phyre' is a .gz file? Or C_EQU000.pkg_unpacked is a .gz file?
Are these files are not .phyre..??? I can't understand what you said.
## Post #17
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-10-06T23:48:45+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

the file you posted
tweeticon_00.dds.phyre
is really
tweeticon_00.dds.phyre.gz
just extract it with 7z
## Post #18
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2013-11-13T06:25:42+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

How can I change dae.phyre  to obj ?

dae.phyre does not seem like 3ds dae
## Post #19
- Username: todzy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 25, 2014 9:47 pm
- Post datetime: 2014-11-03T11:09:02+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

Hi all, do you find where inside scripts, images files? And what program you use to open dds, i try and progs told me that it uncknown format :\
## Post #20
- Username: odrin
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Mon May 23, 2011 9:43 am
- Post datetime: 2014-11-04T04:20:13+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

so is this like crysis?
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-11T17:50:46+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

Supported by my phyre engine tools with bones.

[viewtopic.php?p=130222#p130222](http://forum.xentax.com/viewtopic.php?p=130222#p130222)
## Post #22
- Username: HANE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 16, 2023 11:07 pm
- Post datetime: 2023-08-17T04:00:54+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

> Reply from daemon1 ↑Fri May 12, 2017 1:50 am at Fri May 12, 2017 1:50 am
>
> 
Supported by my phyre engine tools with bones.

http://forum.xentax.com/viewtopic.php?p=130222#p130222
Would you repost the tool of this game?  I'm stuck with it.I can't get the mesh and bone data from the" *.dae.phyre" of this game.
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-08-17T05:27:09+00:00
- Post Title: Re: My Little Sister Can't Be This Cute HappyEnd (PS3) NPJB0

> Reply from HANE ↑Thu Aug 17, 2023 12:00 pm at Thu Aug 17, 2023 12:00 pm
>
> 
Would you repost the tool of this game?  I'm stuck with it.I can't get the mesh and bone data from the" *.dae.phyre" of this game.
[viewtopic.php?t=16930](https://forum.xentax.com/viewtopic.php?t=16930)
