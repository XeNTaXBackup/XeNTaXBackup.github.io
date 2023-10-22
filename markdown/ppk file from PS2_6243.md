## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-03-19T08:46:03+00:00
- Post Title: ppk file from PS2

Hi there~
I have some .ppk files from PS2 MSG Seed Destiny Generation of C.E.
Some body knows how to unpack .ppk files.

Here is a sample archive.
[delete](delete)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-19T11:40:40+00:00
- Post Title: ppk file from PS2

script for QuickBMS:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "ppk\0"
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
for i = 0 < FILES
    goto OFFSET
    getdstring SIGN 4
    get HEADDATA_SIZE long
    get DUMMY long
    get HEAD_SIZE long
    get ZSIZE long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get NAME string
    math OFFSET += HEAD_SIZE
    if SIGN == "ppkc"
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET SIZE
    endif
    math OFFSET -= HEAD_SIZE
    math OFFSET += HEADDATA_SIZE
next i
```
## Post #3
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2011-03-19T12:04:23+00:00
- Post Title: ppk file from PS2

Awesome!
Thanks aluigi
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-03-19T12:45:40+00:00
- Post Title: ppk file from PS2

> Reply from aluigi
>
> script for QuickBMS:
Code: Select all# MSG Seed Destiny Generation of C.E
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "ppk\0"
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
for i = 0 < FILES
    goto OFFSET
    getdstring SIGN 4
    get HEADDATA_SIZE long
    get DUMMY long
    get HEAD_SIZE long
    get ZSIZE long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get NAME string
    math OFFSET += HEAD_SIZE
    if SIGN == "ppkc"
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET SIZE
    endif
    math OFFSET -= HEAD_SIZE
    math OFFSET += HEADDATA_SIZE
next i
Thank you very much for your script.
## Post #5
- Username: girivh93
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 21, 2018 1:32 am
- Post datetime: 2019-11-20T05:07:29+00:00
- Post Title: ppk file from PS2

> Reply from aluigi ↑Sat Mar 19, 2011 7:40 pm at Sat Mar 19, 2011 7:40 pm
>
> 
script for QuickBMS:
Code: Select all# MSG Seed Destiny Generation of C.E
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "ppk\0"
get DUMMY long
get DUMMY long
get FILES long
get OFFSET long
for i = 0 < FILES
    goto OFFSET
    getdstring SIGN 4
    get HEADDATA_SIZE long
    get DUMMY long
    get HEAD_SIZE long
    get ZSIZE long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get NAME string
    math OFFSET += HEAD_SIZE
    if SIGN == "ppkc"
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET SIZE
    endif
    math OFFSET -= HEAD_SIZE
    math OFFSET += HEADDATA_SIZE
next i

hello mr.aluigi. pls.. can you make bms script to open .ppk and ppk_y from sengoku basara 2 heroes ps2? 
i have bunch of file from this iso game ps2 and i don't know which formats contains 3d model and texture

:this is sample file format from this iso game:
[https://drive.google.com/open?id=19661V ... kQdPikOKNC](https://drive.google.com/open?id=19661VMJGrPaWo3JYq-iemQkQdPikOKNC)

thanks
