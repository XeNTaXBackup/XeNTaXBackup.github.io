## Post #1
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2022-03-25T08:01:31+00:00
- Post Title: Epic Mickey 2 The Power of Two

HI,

How do I open the a HKX character file and the NIF texture files. The files are in the dropbox link here.

[https://www.dropbox.com/s/ta0vf7p5fffa1 ... s.rar?dl=0](https://www.dropbox.com/s/ta0vf7p5fffa1dq/characters.rar?dl=0)

Thanks.
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-25T15:13:24+00:00
- Post Title: Epic Mickey 2 The Power of Two

> Reply from Pigeon ↑Fri Mar 25, 2022 4:01 pm at Fri Mar 25, 2022 4:01 pm
>
> 
NIF

> Reply from shakotay2 ↑Tue Oct 20, 2015 4:15 am at Tue Oct 20, 2015 4:15 am
>
> 
did you try Noesis? (plugin fmt_gamebryo_nif.py)
## Post #3
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2022-03-25T20:59:43+00:00
- Post Title: Epic Mickey 2 The Power of Two

HI

I tried the noesis plugins. it does not work 

Thanks
## Post #4
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2022-05-05T11:41:30+00:00
- Post Title: Epic Mickey 2 The Power of Two

HI

link to skin from the game and the noesis plugins. it does not work 

The texture format is NIF and the character HKX

[https://www.dropbox.com/s/o4t7cw2fmgdp7 ... 2.rar?dl=0](https://www.dropbox.com/s/o4t7cw2fmgdp7ah/skin%20Epic%20mickey%202.rar?dl=0)

Thanks
## Post #5
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2022-05-05T14:03:46+00:00
- Post Title: Epic Mickey 2 The Power of Two

Hm, textures opened just fine, but I when try to open any model with .nif extension it gives me a error
## Post #6
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-05-05T17:14:16+00:00
- Post Title: Epic Mickey 2 The Power of Two

> Reply from Carpethop ↑Thu May 05, 2022 10:03 pm at Thu May 05, 2022 10:03 pm
>
> 
any model .nif
using MeshFinder(Android) or Hex2obj



oswald.nif.png (31.59 KiB) Viewed 297 times
## Post #7
- Username: Pigeon
- Rank: n00b
- Number of posts: 19
- Joined date: Mon Mar 29, 2021 2:04 pm
- Post datetime: 2022-05-07T21:48:39+00:00
- Post Title: Epic Mickey 2 The Power of Two

HI

Here is some more characters   

[https://www.dropbox.com/s/v1h56ji7uo2uw ... s.rar?dl=0](https://www.dropbox.com/s/v1h56ji7uo2uwh8/Disney%20Epic%20Mickey%202%20all%20characters.rar?dl=0)

Thanks
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-12T13:45:01+00:00
- Post Title: Epic Mickey 2 The Power of Two

> Reply from Pigeon ↑Sun May 08, 2022 5:48 am at Sun May 08, 2022 5:48 am
>
> 
Here is some more characters

in fact all files have 4 identical bytes before the faces. you can make a plugin without delving into the format

[fmt_MICKEY_NIF.zip](https://xentaxbackup.github.io/file/22479_fmt_MICKEY_NIF.zip)
## Post #9
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-07-13T17:20:41+00:00
- Post Title: Epic Mickey 2 The Power of Two

any chance to support environments ?  

[](https://ibb.co/wgp0dSq)
[DBC_courtyard_01a_hallwayBalconyDoor_inert_01a.zip](https://xentaxbackup.github.io/file/22481_DBC_courtyard_01a_hallwayBalconyDoor_inert_01a.zip)
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-13T21:19:33+00:00
- Post Title: Epic Mickey 2 The Power of Two

> Reply from Sharppy ↑Thu Jul 14, 2022 1:20 am at Thu Jul 14, 2022 1:20 am
>
> 
any chance to support environments ?

i edit plugin. try it  

[fmt_gamebryo_nif.zip](https://xentaxbackup.github.io/file/22483_fmt_gamebryo_nif.zip)
## Post #11
- Username: Techttv
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 23, 2022 8:48 pm
- Post datetime: 2022-07-14T12:23:23+00:00
- Post Title: Epic Mickey 2 The Power of Two

Hi man thanks for editing the plugin but it doesn't work for everything. In fact sometimes i get this error. 

```
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\fmt_g
amebryo_nif.py", line 69, in noepyLoad Model
UVBUF=bs.readBytes(size)
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\inc_n
oesis.py", line 141, in readBytes
return noesis.bsReadBytes(self.h, numBytes)
MemoryError
```

or

```
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\fmt_g
amebryo_nif.py", line 58, in noepyLoadModel
bs.seek(size, 1)
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\inc_n
oesis.py", line 188, in seek
self.toUnpacker(); r = noeSuper(self).seek(addr, is Relative);
self.fromUnpacker(); return r
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\inc_n
oesis.py", line 181, in fromUnpacker
self.setOffset(self.byteOfs)
File
"C:\Users\tomma\Desktop\noesisv4464\plugins\python\inc_n
oesis.py", line 80, in setOffset
noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size.
(33571902 > 28303)
```

or Could not preview file
## Post #12
- Username: AbsoluteZero
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Aug 04, 2021 6:05 am
- Post datetime: 2022-08-01T05:11:01+00:00
- Post Title: Epic Mickey 2 The Power of Two

> Reply from Durik256 ↑Thu Jul 14, 2022 5:19 am at Thu Jul 14, 2022 5:19 am
>
> 
Sharppy wrote: ↑Thu Jul 14, 2022 1:20 am
any chance to support environments ? 


i edit plugin. try it

This works perfectly for Epic Mickey 2. Thank you. Do you think you could edit the script to work with the original game? It is in big endian but the file format seems to be about the same, and the extension is nif_wii instead of nif. I would greatly appreciate it.

Here is an example (Mickey):
[https://cdn.discordapp.com/attachments/ ... ey.nif_wii](https://cdn.discordapp.com/attachments/996984376640425995/1003530101142605884/Mickey.nif_wii)
## Post #13
- Username: DiMickfoxed65
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Feb 13, 2020 12:41 pm
- Post datetime: 2023-04-03T23:27:20+00:00
- Post Title: Epic Mickey 2 The Power of Two

Um.. i tried export the sorcerer mickey texture, but it has the colors bad :I
