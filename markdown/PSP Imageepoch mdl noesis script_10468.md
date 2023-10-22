## Post #1
- Username: weling2010
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-29T01:20:06+00:00
- Post Title: PSP Imageepoch mdl noesis script

imports 3d mdoels from these
supported games
all psp Imageepoch games that use 3d models.
Last Ranker 
Black Rock Shooter: The Game
Final Promise Story 
7th Dragon 2020 
Sol Trigger 
7th Dragon 2020 2
not supported
weight assignment.




[Imageepoch.7z](https://xentaxbackup.github.io/file/6434_Imageepoch.7z)
## Post #2
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2013-05-29T11:54:01+00:00
- Post Title: PSP Imageepoch mdl noesis script

Nice and thanks chrrox !


[](http://www.hostingpics.net/viewer.php?id=784654639.gif)
Keeping the good work since 1901 ! :p
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-05-30T00:36:16+00:00
- Post Title: PSP Imageepoch mdl noesis script

Nice figured out the BRS format lol
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-30T12:25:45+00:00
- Post Title: PSP Imageepoch mdl noesis script

Yeah a lot of psp formats share a ton of things in common i should document some things i have found at some point.
## Post #5
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-05-31T03:59:42+00:00
- Post Title: PSP Imageepoch mdl noesis script

How do you get the mdl files for BRS and 7th dragon 2020?
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-31T10:32:53+00:00
- Post Title: PSP Imageepoch mdl noesis script

for black rock shooter i used this

```
#    xentax.com
#    .vol BMS script

idstring "RTDP"

endian little

get EOH long
get FILES long
get THISSIZE long

goto 0x20

for i = 1 to FILES

  getdstring FILENAME 32
  get FILESIZE long
  get FILEOFFSET long # relative to EOH

  filexor 0x55
  math FILEOFFSET += EOH
  log FILENAME FILEOFFSET FILESIZE
  filexor 0

next i

```

7th dragon you need to use the psp emulator to decrypt the PGD file then extract that with luigi's cpk.bms
[http://aluigi.altervista.org/papers/bms/cpk.bms](http://aluigi.altervista.org/papers/bms/cpk.bms)
## Post #7
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2013-05-31T11:35:39+00:00
- Post Title: PSP Imageepoch mdl noesis script

I extract BRS:TG and only have WRS, Villains, Weapons, ... not have BRS.
I use quickbms and extract all vol files(in CHR, SKL) and I select replace all when it ask.

Sol Trigger I use bms script here [viewtopic.php?f=10&t=9736&p=84974&hilit ... ger#p84974](http://forum.xentax.com/viewtopic.php?f=10&t=9736&p=84974&hilit=Sol+Trigger#p84974)
and I don't know what to do next to get .mdl
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-31T11:47:07+00:00
- Post Title: PSP Imageepoch mdl noesis script

sol trigger bms

> comtype ZLIB_NOERROR
>
> get tmp long
>
> if tmp == 0x305A5A5A
>
> get size long
>
> get null long
>
> get zsize asize
>
> math zsize - 12
>
> clog MEMORY_FILE 12 zsize size
>
> get unk1 long MEMORY_FILE
>
> get files long MEMORY_FILE
>
> savepos tmp MEMORY_FILE
>
> for i = 0 < files
>
> goto tmp MEMORY_FILE
>
> get offset long MEMORY_FILE
>
> getdstring name 0x1C MEMORY_FILE
>
> savepos tmp MEMORY_FILE
>
> get size long MEMORY_FILE
>
> if offset != 0
>
> if size == 0
>
> get size asize MEMORY_FILE
>
> endif
>
> math size - offset
>
> log name offset size MEMORY_FILE
>
> endif
>
> next i
>
> else
>
> get files long 
>
> savepos tmp 
>
> for i = 0 < files
>
> goto tmp 
>
> get offset long 
>
> getdstring name 0x1C 
>
> savepos tmp 
>
> get size long 
>
> if offset != 0
>
> if size == 0
>
> get size asize 
>
> endif
>
> math size - offset
>
> log name offset size 
>
> endif
>
> next i
>
> endif
to get the black rock shooter model you need to extract the bin files with offzip in the directory
PSP_GAME\USRDIR\GAMEDATA\FLD\FCHR\
## Post #9
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-05-31T18:24:01+00:00
- Post Title: PSP Imageepoch mdl noesis script

> Reply from chrrox
>
> for black rock shooter i used this
Code: Select all# -- WRS
#    xentax.com
#    .vol BMS script

idstring "RTDP"

endian little

get EOH long
get FILES long
get THISSIZE long

goto 0x20

for i = 1 to FILES

  getdstring FILENAME 32
  get FILESIZE long
  get FILEOFFSET long # relative to EOH

  filexor 0x55
  math FILEOFFSET += EOH
  log FILENAME FILEOFFSET FILESIZE
  filexor 0

next i

7th dragon you need to use the psp emulator to decrypt the PGD file then extract that with luigi's cpk.bms
http://aluigi.altervista.org/papers/bms/cpk.bms

I tried to extract the decrypted PGD file but I get this error 

I have had it happen before but ive never been able to fix it...
Nvm I tried it on a different computer and somehow it worked but I still dont know how to actually avoid this error.

I also have another question, well I guess 2, I can't find the BRS character files and i saw your reply to another question asking where it was, but how do you use offzip? It won't work for me no matter what I'm trying to do.
And also, is their supposed to be the player/classes character models in 7th dragon 2020 when you extract the decrypted PGD? Because I can't find them anywhere.
[BMSError.png](https://xentaxbackup.github.io/file/6439_BMSError.png)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-05-31T22:18:18+00:00
- Post Title: PSP Imageepoch mdl noesis script

Btw why are they "image epoch" models?
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-05-31T22:53:36+00:00
- Post Title: PSP Imageepoch mdl noesis script

[http://en.wikipedia.org/wiki/Black_Rock ... :_The_Game](http://en.wikipedia.org/wiki/Black_Rock_Shooter:_The_Game)
that is the game company.
[http://jrpg.jp/](http://jrpg.jp/)
click on about us on the page.
## Post #12
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-06-01T23:09:38+00:00
- Post Title: PSP Imageepoch mdl noesis script

I think for 7th dragon 2020 I may have found the player model files but I'm not sure. There .tpk files. I'm just wondering if possibly you can figure them out and see if they are the model files for the players. Thanks in advance and sorry to keep bothering you.
[chr_p_m01_01.rar](https://xentaxbackup.github.io/file/6442_chr_p_m01_01.rar)
## Post #13
- Username: Jobo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-02T10:04:34+00:00
- Post Title: PSP Imageepoch mdl noesis script

just delete the data before INSM
in this example its 0x30 bytes.
## Post #14
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-06-04T01:18:46+00:00
- Post Title: PSP Imageepoch mdl noesis script

And again sorry to bother you this will be the last time but, as you said about extracting the .bin files to get brs with offzip and I have manged to get it to start but, I get this error now. 

Either I'm doing the wrong command or I don't know. Can you please help me? Please answer.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-04T01:27:30+00:00
- Post Title: PSP Imageepoch mdl noesis script

use -a -z -15

c:\offzip.exe -a -z -15 c:\file.dat c:\extract 0x0
## Post #16
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2013-06-04T01:46:12+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

I got the .dat out of the bin but then I try to get that extracted or whatever and it either says Access denied or makes more .dat files but keeps replacing one and is never ending, or I'm just making it stop to soon. Is it supposed to do that?
## Post #17
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-04T01:51:32+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

i have no idea what your doing. you have something wrong in your parameters.
just keep messing with offzip you will get it eventually look at what it tells you.
## Post #18
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-04T17:09:58+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

the .dat file is the same as 7 dragon just delete all data before INSM
## Post #19
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-08T17:01:32+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

Does this script work for blender 2.49b? It's not showing up in my importers panel...

Plus the bms script for the cpk files of Last Ranker says "0 files found" when I try to export the stuff from the CHR folder... :\
## Post #20
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-08T17:46:48+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

use this
[http://hcs64.com/files/utf_tab07b5_special.zip](http://hcs64.com/files/utf_tab07b5_special.zip)
and it is not a blender script it is a noesis script.
## Post #21
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-08T20:55:57+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

> Reply from chrrox
>
> use this
http://hcs64.com/files/utf_tab07b5_special.zip
and it is not a blender script it is a noesis script.

Ah silly me! I got fooled by the .py extention! Sorry for the mistake.

Btw I just noticed something... Last Ranker is CNK, not CPK. Is it just the same stuff?
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-08T21:58:30+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

i just ran offzip on the files.
c:\offzip.exe -a -z -15 c:\file.cnk c:\extract 0
and you will get an output mdl file.
## Post #23
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-09T08:40:16+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

I seriously don't know what is wrong here... but running offzip over the .cnk files I have from LR I only get some .dat files and a message like this:

0x00006800
-zlib Z_DATA_ERROR, the data in the file is not in zip format
or uses a different windowBits value (-z). Try -z 15

- 45 valid zip blocks found

And if I use -z 15 it tells me to try -z -15 again (which isn't working).
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T10:18:44+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

48 valid files is correct. now look at those files and they will have extensions even tho in the window it does not show it.
find the biggest .ins file and rename it to .mdl then open it in noesis.
## Post #25
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-09T13:28:29+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

There is any .ins file. I get only .dat format
## Post #26
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T13:44:56+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

I saw you posted this
[http://sticklove.com/viewtopic.php?f=18&t=172](http://sticklove.com/viewtopic.php?f=18&t=172)
if you look at ZIG folder
you will see CHR_P_ZIG00.MDL
just open that in noesis
## Post #27
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-09T14:51:01+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

What did I do wrong now?   

Plus, I really don't get why I can't extract the other cnk files like you did... I think I will just give up with those...
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T14:56:57+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

your problem is you have an old noesis update noesis.
## Post #29
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-06-09T15:02:14+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

Got it! Now with an updated version this one at least works  thanks!
## Post #30
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2014-02-16T11:18:14+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

Sorry for revive a dead thread,will this support "Saigo no Yakusoku no Monogatari",the game which Sol trigger is sequence? Yes,it is an Image epoch game too!
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-02-16T17:01:45+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

did you try it?
## Post #32
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2014-02-19T03:34:54+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

> Reply from chrrox
>
> did you try it?
Sorry for noob but i don't know how to extract this
## Post #33
- Username: Deary5
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 21, 2014 4:39 pm
- Post datetime: 2015-02-01T20:48:03+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

Hai,i'm noob here. Do you have Noesis plugin for game PSP Sol Trigger and Hack.Link? Or tutorial to make plugin for noesis to open this games. Thank you.
## Post #34
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-08-25T14:29:27+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

the script not support weight bones on 7th Dragon?
## Post #35
- Username: TK4096
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 03, 2017 6:13 am
- Post datetime: 2017-12-03T03:37:33+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

Hoping to get some help here, even though its been 3 years since the last post on this thread.

In extracting the .BIN files that contain the BRS models:
1. I am unable to run Offzip.exe. When I double-click the exe it closes instantly.
2. Running Offzip.exe with THEGUI.exe either produces the "no valid full zip data find" when I use the "-a -z -15" like chrrox said on page 1, or a data file named "0000000a.dat" .

If anyone helps I'll be extremely thankful. 
I'm at my wits end here, this is needlessly complicated. 

BTW, here's a screencap of THEGUI running offzip.exe
[THEGUI.png](https://xentaxbackup.github.io/file/13634_THEGUI.png)
## Post #36
- Username: Soniko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 29, 2017 11:00 pm
- Post datetime: 2017-12-29T15:24:33+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

I don't quite understand what's needed to extract the models from BRS to be honest, anyone who can help?
## Post #37
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-29T18:40:44+00:00
- Post Title: Re: PSP Imageepoch mdl noesis script

> Reply from TK4096
>
> Hoping to get some help here, even though its been 3 years since the last post on this thread.
offzip is a commandline program, you run it from a command prompt
Start > Run > type cmd
then enter the commands chrrox posted earlier:

> Reply from chrrox
>
> c:\offzip.exe -a -z -15 c:\file.dat c:\extract 0x0
that example assumes you have the offzip.exe, the file.dat file and a folder named "extract" in the root of your C drive.
change "file.dat" to the name of the file you want to extract.
the extracted files are written to the "extract" folder.
