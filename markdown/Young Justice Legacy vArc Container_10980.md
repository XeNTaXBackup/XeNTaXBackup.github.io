## Post #1
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-11-22T00:08:02+00:00
- Post Title: Young Justice Legacy vArc Container

Hello all!

can you please help me in unpacking the data for the *.vArc container files?
The game uses vision engine so I gues is still new. The animation is not so good and it feel rushed the only good part ar that the models look good. I think it uses the same model format as Orcs must die 2.

link : Edit: Research complete.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-22T11:53:05+00:00
- Post Title: Young Justice Legacy vArc Container

Done.

Edited: See Below.
## Post #3
- Username: SoulReaver
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 15, 2009 11:47 pm
- Post datetime: 2013-11-22T12:43:19+00:00
- Post Title: Young Justice Legacy vArc Container

I could just double thank you it worked like a charm and yes the model is the same as the Orcs Must Die 2.

Edit: Well it seems some archives are diferent     ill upload the other archive and quite curios on why it did not work...
Edit2: Neighter the model format hope for a fix.
message:

Error: the compressed zlib/deflate input is wrong or incomplete (-3)

Error: there is an error with the decompression
         the returned output size is negative (-1)

link: edit: Research complete.
## Post #4
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2013-11-22T14:43:30+00:00
- Post Title: Young Justice Legacy vArc Container

> Reply from Ekey
>
> Done.
Code: Select all# Young Justice Legacy (VArc format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "VISIONPACKAGE\x00"
get VERSION short
get FILES long
get NAMESTABLESIZE long
goto 0x20

set NAMETABLEOFFSET = FILES
math NAMETABLEOFFSET *= 14
math NAMETABLEOFFSET += 32

for i = 0 < FILES
    get NSIZE short
    get SIZE long
    get ZSIZE long
    get OFFSET long
    savepos TEMP
    goto NAMETABLEOFFSET
    getdstring NAME NSIZE
    math NAMETABLEOFFSET += NSIZE
    math NAMETABLEOFFSET += 1
    clog NAME OFFSET ZSIZE SIZE
    goto TEMP
next i

thx ekey,but,unpack game.vArc get error
[20131122224429.jpg](https://xentaxbackup.github.io/file/6790_20131122224429.jpg)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-22T16:00:46+00:00
- Post Title: Young Justice Legacy vArc Container

Fixed.

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "VISIONPACKAGE\x00"
get VERSION short
get FILES long
get NAMESTABLESIZE long
goto 0x20

set NAMETABLEOFFSET = FILES
math NAMETABLEOFFSET *= 14
math NAMETABLEOFFSET += 32

for i = 0 < FILES
    get NSIZE short
    get SIZE long
    get ZSIZE long
    get OFFSET long
    savepos TEMP
    goto NAMETABLEOFFSET
    getdstring NAME NSIZE
    math NAMETABLEOFFSET += NSIZE
    math NAMETABLEOFFSET += 1
    if SIZE == ZSIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
    goto TEMP
next i
```
## Post #6
- Username: Dehayat
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 29, 2013 6:54 pm
- Post datetime: 2013-11-29T13:04:22+00:00
- Post Title: Young Justice Legacy vArc Container

hi im new to this how do i use the script
## Post #7
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-11-29T16:00:28+00:00
- Post Title: Young Justice Legacy vArc Container

> Reply from Dehayat
>
> hi im new to this how do i use the script
Download QuickBMS [here](http://quickbms.aluigi.org)
## Post #8
- Username: Dehayat
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 29, 2013 6:54 pm
- Post datetime: 2013-11-29T19:33:46+00:00
- Post Title: Young Justice Legacy vArc Container

how do you convert the .model files to obj i tried the orcs must die coverter but it didnt work can you please help me
## Post #9
- Username: sarzamin
- Rank: beginner
- Number of posts: 38
- Joined date: Fri Nov 19, 2010 10:19 pm
- Post datetime: 2014-08-21T11:47:18+00:00
- Post Title: Young Justice Legacy vArc Container

Hi

Is there any way to repack this files?

(quickbms -i option not works!!!)
