## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-11-03T13:32:38+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

ok ive been wondering for a long time now how i would successfully ripp from this game and to my surprise the main game files are stored in .ZIP archives on the disc which are readable by winRAR. HOWEVER, none of the files inside are extractable, all CRC32 values for files in the archive are 00000000. I will upload the smallest .ZIP from the disc for people to look at and study. please get back to me ASAP with your findings. 

Smallest .ZIP archiver from game disc: [http://www.mediafire.com/?22aq4nwbg6dyea4](http://www.mediafire.com/?22aq4nwbg6dyea4)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-03T14:21:17+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

here is an extractor for this zip files

> set magic 0
>
> set counter 0
>
> Do
>
> get magic long
>
> getdstring null 0x10
>
> get zsize long
>
> get size long
>
> get nsize long
>
> getdstring null 0xA
>
> get offset long
>
> getdstring name nsize
>
> putarray 0 counter offset
>
> math counter += 1
>
> while magic == 0x2014B50
>
> math counter - 1
>
> comtype inflate
>
> for i = 0 < counter
>
> getarray tmp 0 i
>
> goto tmp
>
> getdstring null 0x12
>
> get zsize long
>
> get size long
>
> get nsize long
>
> getdstring name nsize
>
> savepos offset
>
> clog name offset zsize size
>
> next i
## Post #3
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-11-03T15:37:30+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

> Reply from chrrox
>
> here is an extractor for this zip files

set magic 0
set counter 0
Do
get magic long
getdstring null 0x10
get zsize long
get size long
get nsize long
getdstring null 0xA
get offset long
getdstring name nsize
putarray 0 counter offset
math counter += 1
while magic == 0x2014B50
math counter - 1
comtype inflate
for i = 0 < counter
getarray tmp 0 i
goto tmp
getdstring null 0x12
get zsize long
get size long
get nsize long
getdstring name nsize
savepos offset
clog name offset zsize size
next i
how would i impliment this to extract the data from the .ZIP format chrrox? (im still quite noobish at this stuff)

EDIT: ignore that i just figured it out, QuickBMS always wins
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-03T15:44:48+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

its a quickbms script.
just save it as a text file then use quickbms and follow the prompts.
## Post #5
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-11-03T15:50:38+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

ok it worked for the TFA2.ZIP and the TA_Extras.ZIP but when i try it on the main TFA.ZIP i get the following error:

if needs be ill send you the main TFA.ZIP file for you to look at (its 86.6MB BTW) this error is also present when i try to extract from the SOUNDE.ZIP file aswell.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-03T15:55:17+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

yeah i would need it in a pm
to tell what is going on.
## Post #7
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-11-03T15:55:52+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

> Reply from chrrox
>
> yeah i would need it in a pm
to tell what is going on.
its on its way
## Post #8
- Username: bullettrain
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-11-03T16:24:21+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

easy fix i had  a feeling that was the problem.

```
set counter 0
Do
get magic long
getdstring null 0x10
get zsize long
get size long
get nsize long
getdstring null 0xA
get offset long
getdstring name nsize
putarray 0 counter offset
math counter += 1
while magic == 0x2014B50
math counter - 1
comtype inflate
for i = 0 < counter
getarray tmp 0 i
goto tmp
getdstring null 0x12
get zsize long
get size long
get nsize long
getdstring name nsize
savepos offset
if zsize == size
log name offset size
else
clog name offset zsize size
endif
next i

```
## Post #9
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2012-11-03T16:26:28+00:00
- Post Title: Transformers Armada: Prelude to Energon (PS2) .ZIP archives

Thx so much chroxx, I will test this out immediatly.
