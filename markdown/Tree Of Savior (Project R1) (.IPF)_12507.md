## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-14T23:42:41+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

Official Site: [here](http://tos.nexon.com/main/index.aspx)
Download: [here](http://tosvod-nexon30.ktics.co.kr/launcher/filelist.txt)

Script for unpack

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
goto -0x18
get FILES short
get TABLEOFFSET long
get FLAG short
goto TABLEOFFSET

for i = 0 < FILES
    get NSIZE short
    get CRC long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get CSIZE short
    getdstring COMMENT CSIZE
    getdstring NAME NSIZE

    if ZSIZE == SIZE 
        log NAME OFFSET SIZE 
    else 
        clog NAME OFFSET ZSIZE SIZE 
    endif
next i
```


Note: Thanks to chrrox for client and iaw
## Post #2
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2015-01-15T05:50:25+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

fix bug

```
if  ZSIZE = SIZE 
log NAME OFFSET ZSIZE 
else
clog NAME OFFSET ZSIZE SIZE
endif

```
## Post #3
- Username: mumphster
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 17, 2015 7:46 am
- Post datetime: 2015-01-17T00:32:29+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

> Reply from Ekey
>
> Official Site: here
Download: here

Script for unpack
Code: Select all# Tree Of Savior (Project R1) (CBT1) (IPF format)
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate
goto -0x18
get FILES short
get TABLEOFFSET long
get FLAG short
goto TABLEOFFSET

for i = 0 < FILES
    get NSIZE short
    get CRC long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    get CSIZE short
    getdstring COMMENT CSIZE
    getdstring NAME NSIZE

    if ZSIZE == SIZE 
        log NAME OFFSET SIZE 
    else 
        clog NAME OFFSET ZSIZE SIZE 
    endif
next i

Note: Thanks to chrrox for client and iaw

Thanks for this. I wrote an implementation in golang if anyone is interested. Check the releases for a precompiled exe.

[https://github.com/Ell/tostools](https://github.com/Ell/tostools)

Now I just need to figure out how to read the 3d files...
## Post #4
- Username: Salivaxiu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 18, 2012 5:43 pm
- Post datetime: 2015-01-17T12:54:26+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

Thank you ekey! greeeeeat job
## Post #5
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2016-01-05T19:09:34+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

Hi Guys,


I installed all 4 parts of the client in the link and keep getting the same type of error,

Can someone help me with this error I keep getting?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2016-01-05T22:42:58+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

In new client used encryption. Script unsupported it.
## Post #7
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2016-01-05T23:10:49+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

Oh I see, but does anyone have the old client?
## Post #8
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2016-10-20T12:19:12+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

SumAni.7z
(1.32 KiB) Downloaded 28 times


this is new ver ipf,please check it
## Post #9
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2017-02-27T14:34:49+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

any update??
## Post #10
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2017-02-27T14:38:50+00:00
- Post Title: Tree Of Savior (Project R1) (*.IPF)

any one trying extract this game now?
