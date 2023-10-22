## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-25T12:46:37+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org
#
# For decrypt files with header 3nK use SCSSIITool

idstring "SCS#"
get VERSION long
idstring "CITY"
get FILES long

goto 0x1000

for i = 0 < FILES
    get HASH1 long
    get HASH2 long
    get OFFSET long
    get NULLS long
    get FLAG long
    get CRC long
    get SIZE long
    get ZSIZE long
    string NAME p= "%08X%08X" HASH1 HASH2
	
    if SIZE == ZSIZE
      log NAME OFFSET SIZE
    else
      clog NAME OFFSET ZSIZE SIZE
    endif
next i
```


Edited: Attached tool for decrypt files with header 3nK. They contained in base_cfg.scs , def.scs and locale.scs.

```
        SCSSIITool <InFILE> <OutFILE>

[Example]
        SCSSIITool 18C69F3DD9D3D2A2 18C69F3DD9D3D2A2.txt
```

[SCSSIITool.rar](https://xentaxbackup.github.io/file/5922_SCSSIITool.rar)
## Post #2
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-10-25T20:42:45+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

[Extractor](http://www.scaniadrivergame.com/en/mod_tools.php)
Распаковщик давно есть )
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-27T00:36:50+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

> Reply from Haoose
>
> Extractor
Распаковщик давно есть )

This tool for unpack default ZIP. 

> You may use the provided extractor to unpack the game archive to develop game mods. To repack the archive again use any standard ZIP utility after you've finished your mod.

> Reply from Haoose
>
> Распаковщик давно есть )
But there is no utility to decrypt 

PS: I would appreciate if someone would find a function to generate the hash.
## Post #4
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-10-27T06:36:46+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

> Reply from Ekey
>
> This tool for unpack default ZIP.
No. This tool for unpack SCS-files from game =)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-28T21:47:41+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

This extractor not work on Euro Truck Simulator 2. Anyway i found function for generate hash. They is very looooooooooooooong. Tool coded on MASM32 .
In Euro Truck Simulator 2 and in Scania Truck Driving Simulator hash algo same. So how found filenames. For Example :

Unpack def.scs. After unpack open any file and search filename path's like this:

```
	model_coll: "/model/sign/navigation/3hw_exit_far_d.pmc"
```


Correct path (remove slash / from begin)

```
	model/sign/navigation/3hw_exit_far_d.pmc
```


Example [Screen](http://img526.imageshack.us/img526/571/scshasherscreen.png)

Collect filenames and share here 
[SCSHasher_0.1.rar](https://xentaxbackup.github.io/file/5940_SCSHasher_0.1.rar)
## Post #6
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2012-10-29T06:41:56+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

> Reply from Ekey
>
> This extractor not work on Euro Truck Simulator 2.
This extractor work on Euro Truck Simulator 2.  
[](http://fastpic.ru/view/45/2012/1029/39a7ad09e90d2d28ef6e3f15758e6692.jpg.html) [](http://fastpic.ru/view/45/2012/1029/1237a4d9741a0efa17e29c43418a8cd2.jpg.html) [](http://fastpic.ru/view/45/2012/1029/68b5fc53945b3e6a89d3cc18c414109a.jpg.html)
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-29T12:38:28+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

For example.

```
*** ERROR *** : Root directory not found, can not extract this archive!
```
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-12-09T17:06:19+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Download [here](http://www.sendspace.com/file/95jcb2)
[scsunp.PNG](https://xentaxbackup.github.io/file/6072_scsunp.PNG)
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-10T10:42:02+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

just for reference, I have made a script supporting both SCS# and ZIP archives of the games developed by SCS Software:
[http://aluigi.org/papers/bms/scsgames.bms](http://aluigi.org/papers/bms/scsgames.bms)

Why supporting also the ZIP archives?
Well, because some people modify their mods to look like being password protected and with the shrink compression so this script allows to extract also these "modified" mods.
## Post #10
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2013-03-13T21:51:20+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Any chance for script or tool for repacking the damn language .sii files?

I've spent my whole life trying to figure a way to repack one file, but that's too complicated for me, as I have never programmed before and everything was with little help from one my friend that have experience (little) with programming, but not programming like this and he doesn't know how he can do things like modifying game files, because the format of the files and because he doesn't have the game.

I appreciate any given help! 

Thanks much.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-17T15:32:44+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

the script is valid for repacking so you can do it directly in quickbms.
for more info take a look at section 3 of quickbms.txt
[http://aluigi.org/papers/quickbms.txt](http://aluigi.org/papers/quickbms.txt)
## Post #12
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T18:01:54+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

> Reply from aluigi
>
> the script is valid for repacking so you can do it directly in quickbms.
for more info take a look at section 3 of quickbms.txt
http://aluigi.org/papers/quickbms.txt
He was referring - encrypt language files back in SII format
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-17T18:37:10+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

ops :)
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T19:16:57+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Well i try reimport unpacked files for test encrypted languages but get error.

```
by Luigi Auriemma
e-mail: aluigi@autistici.org
web:    aluigi.org

- REIMPORT mode enabled!
- open input file d:\Euro Truck Simulator 2\locale.scs
- open script Euro Truck Simulator 2.bms
- set output folder d:\Euro Truck Simulator 2\locale

  offset   filesize   filename
------------------------------

Error: CMD_Encryption_func with negative lastcmd

Note that if both the scripts and your files are correct then it's possible
that the script needs a newer version of QuickBMS, in which case download it:

  http://aluigi.org/quickbms
```
## Post #15
- Username: Sartr0n
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Nov 14, 2011 8:13 pm
- Post datetime: 2013-03-17T19:38:11+00:00
- Post Title: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

^ I was talking about the same.

Errors everywhere.

SCS Software  

Sometimes I think why SCS Software has done the files that way, but the answer is floating somewhere in their programmers' heads, and I can't understand what is it.
## Post #16
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-17T19:48:53+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

I never used the reimport function. W8 aluigi
## Post #17
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-17T20:31:53+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

I hate the bugs in quickbms... will fix it in the next version
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-21T21:29:46+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

bug just fixed in version 0.5.17c
new features lead ever to new problems, you know :)
## Post #19
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-21T23:55:55+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Well thanks for update. I try it later.
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-03-22T13:47:46+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Game dont work after reimport.
## Post #21
- Username: Cadde
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 07, 2015 2:13 am
- Post datetime: 2015-08-06T20:14:42+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Ekey, could you please explain the hashing function used to someone uninitiated?
## Post #22
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2016-01-31T12:10:15+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Nice, it works with American Truck Simulator's .3nk too.
## Post #23
- Username: v199629
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 21, 2017 12:50 am
- Post datetime: 2017-08-20T17:23:51+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Can someone explain to me how to decrypt the .3nk file. Do you just drag the file into the.exe and the.txt file should be in the same folder? It does seem to work for me (I have copy the .bat file to the same folder).
## Post #24
- Username: netRacer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 21, 2018 6:31 am
- Post datetime: 2018-02-24T04:44:55+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

1 - I was able to extract the file locale.scs with SCSArchivier and BSM 2- Edit file language, in TXT and Sii format ... Now I need to do the reverse way. BSM allows re packaging, but before I need to transform from TXT to 3NK, someone has some converter ... thanks
## Post #25
- Username: netRacer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 21, 2018 6:31 am
- Post datetime: 2018-02-24T22:14:39+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Hello, I am working on a special translation, I have managed to decrypt the file LOCALE.scs in two ways, with BSM and SCSArchivier, but I can not re-encrypt the files and leave the file locale.scs in a readable format. Does anyone know or have someone who can help me ???

Currently with BSM I can re-encrypt the locale.scs file but I do not know how to dump from a TXT file to a 3NK format file. Please help me thank you very much
## Post #26
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2020-04-22T12:28:16+00:00
- Post Title: Re: Euro Truck Simulator 2 (*.SCS, *.SII 3nK))

Hi guys! How result OBJ or STL from ETS2 (*.SCS)
See file *.pmg

You need:
Blender 2.81
ConverterPIXWrapper (github.com/simon50keda/ConverterPIXWrapper)
SCS Blender Tools ([https://modding.scssoft.com/wiki/Docume ... s/Download](https://modding.scssoft.com/wiki/Documentation/Tools/SCS_Blender_Tools/Download))
Conversion Tools  ([https://modding.scssoft.com/wiki/Docume ... sion_Tools](https://modding.scssoft.com/wiki/Documentation/Tools/Conversion_Tools))

1.Install plugins to blender plugins folder (copy)
2.Run Blender, Open SCS file, Check need model file (*.PMG)
3.Export exp to OBJ or STL

==============================================================================
Enjoy !!!1
