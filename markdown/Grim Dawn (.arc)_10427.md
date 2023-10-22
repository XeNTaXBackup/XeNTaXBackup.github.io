## Post #1
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-17T19:51:14+00:00
- Post Title: Grim Dawn (*.arc)

Hi, i tired to use archivetool ( from titan quest for repack the language files, but no works anymore... ), i think is zlib, so will be cool to have unpack/repack.

ThX
[GD-TXT.rar](https://xentaxbackup.github.io/file/6404_GD-TXT.rar)
## Post #2
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-05-19T20:15:31+00:00
- Post Title: Grim Dawn (*.arc)

> Reply from hyndai
>
> Hi, i tired to use archivetool ( from titan quest for repack the language files, but no works anymore... ), i think is zlib, so will be cool to have unpack/repack.

ThX
The game is only in alpha, right? So there's no point in developing a tool for it right now, it could change a lot until it gets to release. Further more the devs told us on the official forum, that they'll release a tool for translations (I can't find the topic for that now, but believe me, they will:))
## Post #3
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-20T13:28:16+00:00
- Post Title: Grim Dawn (*.arc)

Yes still in alpha, but i want to start now translation because there are a lot to translate...
## Post #4
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2013-05-23T11:21:48+00:00
- Post Title: Grim Dawn (*.arc)

```
# QuickBMS simple script for Grim Dawn .ARC
# created by The Bacter
################################################################
idstring "ARC\0"
get VERSION long
if VERSION == 1     # Titan Quest
  comtype zlib
elif VERSION == 2   # Grim Dawn - old files
  comtype zlib
elif VERSION == 3   # Grim Dawn - new files
  comtype lz4
else                # unknown version
  # unknown game
endif

get NR_OF_FILES long
get NR_OF_FILES_AGAIN long
get DIR_TABLE_SIZE long
get NAME_TABLE_SIZE long
get DIR_START long

math NAME_TABLE_START = DIR_START
math NAME_TABLE_START += DIR_TABLE_SIZE
goto NAME_TABLE_START
log MEMORY_FILE NAME_TABLE_START NAME_TABLE_SIZE

goto DIR_START
for i = 0 < NR_OF_FILES
  get FILE_START long
  get FILE_PACKED_SIZE long
  get FILE_ORIGINAL_SIZE long
  get FILE_NAME string MEMORY_FILE
  clog FILE_NAME FILE_START FILE_PACKED_SIZE FILE_ORIGINAL_SIZE
next i

```
## Post #5
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-23T23:35:36+00:00
- Post Title: Grim Dawn (*.arc)

Hi bacter thx for your script, and i have found another way to made my modification and re-inject inside *.arc file.
## Post #6
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-05-25T21:02:06+00:00
- Post Title: Grim Dawn (*.arc)

> Reply from hyndai
>
> Hi bacter thx for your script, and i have found another way to made my modification and re-inject inside *.arc file.
Can you maybe share the method, please?
## Post #7
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-28T14:05:11+00:00
- Post Title: Grim Dawn (*.arc)

lostprophet >> No  pb  

So first you need some softs : 

- HxD 
- ZLIBC.exe 
- NOTEPAD++

open Text_EN.arc in HxD, and note all this info : 

[](http://www.zimagez.com/zimage/1bd8be62eafbf876f151efa98859ba68d.php)

DB2401 = 124DB ( total of all files "joined" and start by 789C ) tags_uimain.txt / tags_ui.txt / tags_creatures.txt / tags_tutorial.txt / tags_storyelements.txt / tags_skills.txt / tags_items.txt 

Start from 0x800 to 124DB 

Now you know this total of all files search each files : 

```
tags_ui.txt = 0x1d24 - 0x52FF = / length = 35DC = DC35
tags_creatures.txt = 0x5300 - 0x658F / length = 1290 = 9012
tags_tutorial.txt = 0x6590 - 0x78F4 / length = 1365 = 6513
tags_storyelements.txt = 0x78F5 - 0xA3D0 / length = 2ADC = DC2A
tags_skills.txt = 0xA3D1 - 0xEDCA / length = 49FA = FA49
tags_items.txt  = 0xEDCB -0x124DA / length = 3710 = 1037
```


Now we have all info for make a patch translation : 

- Re-install Titan quest , and copy Titan Quest Arc Explorer Version 1.0 or use bacter BMS script
- extract Text_EN.arc / make modification on all *.txt in your native language and save it !

Now for re-injecting tools use this batch script :
- Open notepad++ and copy/paste/save this : 

```
:: 0°) Ne pas mettre d'accent sur le fichier de traduction *.txt

ren tags_uimain.txt 1-tags_uimain.txt 
ren tags_ui.txt 2-tags_ui.txt
ren tags_creatures.txt 3-tags_creatures.txt 
ren tags_tutorial.txt 4-tags_tutorial.txt 
ren tags_storyelements.txt 5-tags_storyelements.txt
ren tags_skills.txt 6-tags_skills.txt
ren tags_items.txt 7-tags_items.txt 

pause

zlibc -k C:\GRIM\fan-translation\1-tags_uimain.txt C:\GRIM\fan-translation\1-tags_uimain.zlb 6
zlibc -k C:\GRIM\fan-translation\2-tags_ui.txt C:\GRIM\fan-translation\2-tags_ui.zlb 6
zlibc -k C:\GRIM\fan-translation\3-tags_creatures.txt C:\GRIM\fan-translation\3-tags_creatures.zlb 6
zlibc -k C:\GRIM\fan-translation\4-tags_tutorial.txt C:\GRIM\fan-translation\4-tags_tutorial.zlb 6
zlibc -k C:\GRIM\fan-translation\5-tags_storyelements.txt C:\GRIM\fan-translation\5-tags_storyelements.zlb 6
zlibc -k C:\GRIM\fan-translation\6-tags_skills.txt C:\GRIM\fan-translation\6-tags_skills.zlb 6
zlibc -k C:\GRIM\fan-translation\7-tags_items.txt C:\GRIM\fan-translation\7-tags_items.zlb 6

pause

:: ASSEMBLAGE EN 1 SEUL *.ZLB DANS l'ordre

copy /b c:\GRIM\fan-translation\*.zlb GRIM-DAWN-TXT-TRADUIS-RESULTAT.ZLB
pause
```


I took same compression level (6 for 789C) for zlib or this patch not works. 

So now all files i have translated and have new length so open each *.zlb and take some note of each length by selecting CTRL+A and looks length.

[](http://www.zimagez.com/zimage/215ef0c9edee71e5411f993ec8208fcb6.php)

```
tags_ui.zlb =  length = 393C = 3C39
tags_creatures.zlb =  length = 1290 = 9012
tags_tutorial.zlb =  length = 15CE = CE15    
tags_storyelements.zlb =  length = 2AE3 = E32A
tags_skills.zlb =  length = 49FA = FA49
tags_items.zlb  =   = length = 3710 = 1037
```


Now search in Text_EN.arc OLD length post before :

OLD 

```
tags_ui.zlb = length 35DC = DC35
tags_creatures.zlb = length = 1290 = 9012
tags_tutorial.zlb = length = 1365 = 6513
tags_storyelements.zlb = length = 2ADC = DC2A
tags_skills.zlb = length = 49FA = FA49
tags_items.zlb  = length = 3710 = 1037
```

NEW from fan-trad *.zlb 

```
tags_ui.zlb =  length = 393C = 3C39
tags_creatures.zlb =  length = 1290 = 9012
tags_tutorial.zlb =  length = 15CE = CE15    
tags_storyelements.zlb =  length = 2AE3 = E32A
tags_skills.zlb =  length = 49FA = FA49
tags_items.zlb  =   = length = 3710 = 1037
```


Now open HxD =>open Text_En.arc goto 0x800 to 124DB cut, open GRIM-DAWN-TXT-TRADUIS-RESULTAT.ZLB select all, copy, and insert in Text_EN.arc at 0x800
So i have change few files, so open HxD =>Text_EN.arc search 2415 there are two, change it for the NEW A417 / make this in all files you make change 
Now open GRIM-DAWN-TXT-TRADUIS-RESULTAT.ZLB in HxD and select all and taken again length of all files "joined" ( 1 25 DB = DB 25 01 ) and search this ( at begin if file DB2401 and change this ! )

Voila  
P.S : And i am sorry for super bad english, not my native language...
## Post #8
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2013-05-30T05:42:15+00:00
- Post Title: Grim Dawn (*.arc)

Tip: Why don't you use the Titan Quest .ARC tool?
The number in the .ARC file at position 0004 indicates the game type: 01 = Titan Quest; 02 = Grim Dawn
So, if you change the 02 to 01 in a Hex editor, the Titan Quest tool will handle it without problem.
Extract, modify and replace your files and finally change the game type indicator byte back from 01 to 02!
## Post #9
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-05-30T18:48:48+00:00
- Post Title: Grim Dawn (*.arc)

Hi bacter yes nice tip, works only for build 9. today crate make a update build 11 and *.bms script and arc tools no working anymore... 

new file Text_EN.arc (build11) : [http://www.jheberg.net/captcha/WYb0ax-texten-arc](http://www.jheberg.net/captcha/WYb0ax-texten-arc)

And offzip find nothing inside.
## Post #10
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2013-05-31T13:14:02+00:00
- Post Title: Grim Dawn (*.arc)

They changed the compression format to "lz4"!
I used the "brute force" detection method from aluigi:
[http://aluigi.altervista.org/papers/bms ... _scan2.bms](http://aluigi.altervista.org/papers/bms/comtype_scan2.bms)

Use the newest QuickBMS (v0.5.21a), because the older versions don't work perfectly!

Could anyone send some more example .ARC files?
## Post #11
- Username: hyndai
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Jun 04, 2008 4:55 am
- Post datetime: 2013-06-03T18:46:55+00:00
- Post Title: Grim Dawn (*.arc)

Hi bacter i have upload your request : 

size : 22.2 Mo
type *.rar
version : build 11 

```
http://www.jheberg.net/captcha/v7xSdV-gm-b11-rar
```
## Post #12
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2013-06-04T19:25:41+00:00
- Post Title: Grim Dawn (*.arc)

Thank you! The new archive format seems clear, so now I'm trying to make a simple extractor/rebuilder for the .ARC files!
(Hopefully the guys won't come out with some whole new idea in the next build.)
## Post #13
- Username: cienislaw
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 30, 2013 5:22 am
- Post datetime: 2013-11-06T10:27:02+00:00
- Post Title: Grim Dawn (*.arc)

thx for the script, making python (un)packer will be piece of cake.

i don't think they will change format. this game uses modified, sometimes heavy, engine from Titan Quest, but data structures seems untouched beside shift to LZ4. this could be only temporary for development time to speed up build process or they want game load faster.
## Post #14
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-11-09T20:59:59+00:00
- Post Title: Grim Dawn (*.arc)

Any news about modifying .ARC files?
## Post #15
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2014-09-27T08:39:21+00:00
- Post Title: Grim Dawn (*.arc)

Removed. (Find this info on my personal site or on Zenhax.)
## Post #16
- Username: atom0s
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Sep 27, 2014 4:19 pm
- Post datetime: 2014-09-28T01:32:53+00:00
- Post Title: Re: Grim Dawn (*.arc)

Removed. (Find this info on my personal site or on Zenhax.)
