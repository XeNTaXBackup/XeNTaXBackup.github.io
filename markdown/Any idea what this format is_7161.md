## Post #1
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2011-08-11T19:37:28+00:00
- Post Title: Any idea what this format is?

Hello all,

I was going through the data files of the PC game TFX from 1993 and came across some audio files which start off looking like this:


Any idea what format this is? and if so, what can I play it with?.....
## Post #2
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-08-11T19:52:00+00:00
- Post Title: Any idea what this format is?

Looks like some kind of module. try rename it to mod, it, s3m, xm and open in modplug tracker, maybe you got luck
## Post #3
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2011-08-11T20:30:08+00:00
- Post Title: Any idea what this format is?

Thanks. Looking further into the data archive, and while I don't have the actual filename, the file extension is likely to be one of the following:

```
.dir
.dat
.way
.cfg
.sam
.000
.cmb
.col
.bin
.plt
.com
.hdd
.txt
.hud
.opt
.asc
.le2
.lev
.sta
.mis
.def
.hlp
.ody
.spr
.pos
.tmt
.dav
.bbm
.ssd
.lst
.adl
.rld
.lap
.scc
.ald
.btm
.256
.lbm
.pet
.fn
.tm
.3
.2
.h
```

Unfortunately, none of these are on the list you give....or on the list of Wikipedia's known file extensions.
## Post #4
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-08-11T20:38:15+00:00
- Post Title: Any idea what this format is?

> Reply from bored
>
> Thanks. Looking further into the data archive, and while I don't have the actual filename, the file extension is likely to be one of the following:
Code: Select all.par
.dir
.dat
.way
.cfg
.sam
.000
.cmb
.col
.bin
.plt
.com
.hdd
.txt
.hud
.opt
.asc
.le2
.lev
.sta
.mis
.def
.hlp
.ody
.spr
.pos
.tmt
.dav
.bbm
.ssd
.lst
.adl
.rld
.lap
.scc
.ald
.btm
.256
.lbm
.pet
.fn
.tm
.3
.2
.h
Unfortunately, none of these are on the list you give....or on the list of Wikipedia's known file extensions.
try eliminating process. txt, h, cfg, com, hdd, hud is weird... and tbh other extensions are weird too. upload file and i look at him
## Post #5
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2011-08-11T20:47:27+00:00
- Post Title: Any idea what this format is?

Thanks. Here's a couple of files.
I'm assuming they are audio since they have identifiable ascii, like 'lead guitar'...
[noname679.zip](https://xentaxbackup.github.io/file/4613_noname679.zip)
## Post #6
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2011-08-12T18:38:16+00:00
- Post Title: Any idea what this format is?

I tried a different line of research, and found out that the composer (or one of them) for TFX was one Barry Leitch who has a website:
[www.barryleitch.com](http://www.barryleitch.com)

From his Resume, he says this about his days at Ocean Software (who published TFX):
1992 - 1993 Ocean Software Ltd. Manchester, UK 
Senior Composer 
Responsibilities included 
* Composing music and sound effects across several platforms 
* Co-Composed several soundtracks with other composers.
* Designed proprietary music system for PC / SNES / Genesis 

So, since the first few bytes of the file are 'OSL1', I presume that this is their 'proprietary music system'.

I might try asking him about it but I'm sure he'll just refer me to Atari....

Anyway, unless anyone knows this format I guess that's it.

SirLoon. Thank you for taking an interest!
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-08-13T08:32:17+00:00
- Post Title: Any idea what this format is?

Those sound more like MIDI instrument names than anything, so this is likely some midi variant.  Possibly FM synthesis settings at the beginning (seem to short and consistent (0x122 bytes) to be PCM samples) and MIDI later?  I know pretty much nothing about what binaries for any of these look like, though, so I'm not going to be any help here.
## Post #8
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2011-08-13T10:06:13+00:00
- Post Title: Any idea what this format is?

Thanks hcs,
I suspect you're right. I'll put off digging into the binaries for a while, in the hope that someone here will recognise this.
