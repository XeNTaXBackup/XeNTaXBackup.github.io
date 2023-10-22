## Post #1
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-04-11T16:31:00+00:00
- Post Title: PC Killer Instinct (2013) .pak

Hello, 

I was wondering if anybody has any idea on how to unpack the .pak archives from the PC version of KI. I'm after the announcer sounds and the arbiters sounds. 

KI uses Double Helix's HEX engine and despite my best efforts, I have not been able to find any information on the engine at all. I've tried several .pak tools on it with no success.

Here is a sample. 

[https://www.mediafire.com/?f8vf5acq884dzvo](https://www.mediafire.com/?f8vf5acq884dzvo)

Thanks.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-04-11T21:30:23+00:00
- Post Title: PC Killer Instinct (2013) .pak

Yes, would very much like a way to unpack these.
## Post #3
- Username: durandal217
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-04-12T00:23:03+00:00
- Post Title: PC Killer Instinct (2013) .pak

Here is a beta script

```
get VERSION long
get NULL00 long
get TYPE long
get COUNT00 long
get COUNT01 long
get COUNT02 long
for i = 0 < COUNT02
get NULL01 long
get COUNT03 long
get COUNT04 long
math COUNT03 * 4
getdstring NULL02 COUNT03
next i
for i = 0 < COUNT01
get HASH long
get NSIZE long
getdstring NVAR NSIZE
#print "%NVAR%"
next i
for i = 0 < COUNT00
getdstring NAME 0xF0
get VAR00 short
get VAR01 short
get OFFSET long
get VAR02 long
get SIZE long
get VAR03 short
get VAR04 short
get VAR05 short
if VAR03 == 0
elif VAR03 == 1
elif VAR03 == 2
set VAR03 string "kimesh"
elif VAR03 == 3
set VAR03 string "kimat"
elif VAR03 == 4
set VAR03 string "kitex"
elif VAR03 == 13
set VAR03 string "CinematicShot.xml"
elif VAR03 == 21
set VAR03 string "EventList.xml"
elif VAR03 == 22
set VAR03 string "MeshAttachmentInfo.xml"
elif VAR03 == 28
set VAR03 string "kihkx"
elif VAR03 == 29
set VAR03 string "hkAnim"
elif VAR03 == 53
set VAR03 string "ProceduralAnimationData.xml"
endif
string NAME += .
string NAME += VAR03
print "%NAME%"
log NAME OFFSET SIZE
next i

```
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-04-12T14:24:51+00:00
- Post Title: PC Killer Instinct (2013) .pak

GODLIKE COMBO. 

the only thing is for the other .pak like the stage paks they don't extract it gives me:
STAGE_18_JUDGE.PAK

```
last script line before the error or that produced the error:
18  getdstring NVAR NSIZE 
```


I don't know if there is any audio in these .paks but I'd like to extract to be sure.
## Post #5
- Username: interloko
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Oct 27, 2009 12:53 am
- Post datetime: 2016-04-19T22:56:26+00:00
- Post Title: PC Killer Instinct (2013) .pak

> Reply from chrrox
>
> Here is a betscript
Thanks for the script. I have a question. 
I want to extract audio, with your script I got some files that contains a lot of files inside.
To extract it I just remove all before the RIFF header, save it as 
.wem and the run another tool that convert it to wav...
The thing is that the file has a lot of RIFF and only extracts the first one, so then I remove from start to next RIFF,  save and all the process again.
Is there a chance of script to extract them all? I have no idea of scripting but seems an easy task
## Post #6
- Username: abcdefgh
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Feb 27, 2016 7:41 am
- Post datetime: 2016-05-02T18:38:30+00:00
- Post Title: PC Killer Instinct (2013) .pak

--redacted--
## Post #7
- Username: thethiny
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Aug 07, 2016 8:57 am
- Post datetime: 2016-08-07T15:10:45+00:00
- Post Title: PC Killer Instinct (2013) .pak

One thing I might be sure of is the header, most .pak files have a 02 near bytes 0x8+ (first 16 bytes). Whenever you see this 02 then it's extractable, if it's 01 then it's compressed. Same thing applies to UE files. In MKX, it is a 01, and once LZO Decompressed it becomes 02.
## Post #8
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2018-11-04T20:27:13+00:00
- Post Title: PC Killer Instinct (2013) .pak

other files extracting but
KI.bms CRC32 45B50A24, script dont work with that? right?

> STAGE_00.PAK
>
> STAGE_00_BLACK.PAK
>
> STAGE_01_JAGO.PAK
>
> STAGE_02_GLACIUS.PAK
>
> STAGE_03_SABREWULF.PAK
>
> STAGE_04_THUNDER.PAK
>
> STAGE_05_SADIRA.PAK
>
> STAGE_06_ORCHID.PAK
>
> STAGE_07_SPINAL.PAK
>
> STAGE_08_FULGORE.PAK
>
> STAGE_09_SHADOW_JAGO.PAK
>
> STAGE_10_TJCOMBO.PAK
>
> STAGE_11_MAYA.PAK
>
> STAGE_12_GAUZE.PAK
>
> STAGE_13_RIPTOR.PAK
>
> STAGE_14_AGANOS.PAK
>
> STAGE_15_HISAKO.PAK
>
> STAGE_16_CINDER.PAK
>
> STAGE_17_ARIA.PAK
>
> STAGE_18_JUDGE.PAK
>
> STAGE_19_KIMWU.PAK
>
> STAGE_20_TUSK.PAK
>
> STAGE_21_ASTROFIELD.PAK
>
> TJ_STORYSTAGE_3.PAK
>
> 
>
> 
>
> QuickBMS generic files extractor and reimporter 0.7.3 (64bit test)
>
> by Luigi Auriemma
>
> e-mail: me@aluigi.org
>
> web:    aluigi.org
>
>         (Jan 31 2016 - 12:41:23)
>
> 
>
>                    quickbms.aluigi.org  Homepage
>
>                             zenhax.com  ZenHAX Forum
>
>                                @zenhax  Twitter & Scripts
>
> 
>
> - open input file G:\RS\Killer Instinct [R.G. Catalyst]@\DX11\@\STAGE_02_GLACIUS
>
> .PAK
>
> - open script KI.txt
>
> - set output folder G:\RS\Killer Instinct [R.G. Catalyst]@\DX11\@\STAGE_02_GLACI
>
> US
>
> 
>
>   offset           filesize   filename
>
> --------------------------------------
>
> 
>
> - error in src\xalloc.c line 617: xdbg_malloc()
>
> 
>
> Error: memory allocation problem
>
>        Iaainoaoi?ii iaiyoe aey ia?aaioee eiiaiau.
