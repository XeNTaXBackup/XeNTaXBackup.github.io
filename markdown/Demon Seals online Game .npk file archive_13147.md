## Post #1
- Username: diksonhe
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jul 23, 2015 10:15 pm
- Post datetime: 2015-08-04T14:13:11+00:00
- Post Title: Demon Seals online Game .npk file archive

"Demon Seals" online game for neox engine. This Game engine with NetEese Custom engine, the company from china . Game chinese name:镇魔曲 (zhen mo qu).
Games website:[http://zmq.163.com/index.html](http://zmq.163.com/index.html)
Game download:[http://zmq.gdl.netease.com/zmq-1.0.219-setup.exe](http://zmq.gdl.netease.com/zmq-1.0.219-setup.exe)

The game file is *.npk unknown format QuickBMS  all script invalid. please help me check this sample file. Thanks all.

[http://www.mediafire.com/download/8s5xy ... /model.npk](http://www.mediafire.com/download/8s5xyuf8408x09x/model.npk)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-08-04T22:02:06+00:00
- Post Title: Demon Seals online Game .npk file archive

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "NXPK"
get FILES long
get OFFSET asize
xmath OFFSET "OFFSET - (FILES * 0x1c)"
goto OFFSET
for i = 0 < FILES
    get NAME_CRC long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZCRC long
    get CRC long
    get FLAGS long
    if FLAGS == 2
        comtype lz4
    else    # 0
        comtype zlib
    endif
    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i    
```
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-08-04T22:51:44+00:00
- Post Title: Demon Seals online Game .npk file archive

this is a model's submesh:



00000014_dat.JPG (61.59 KiB) Viewed 378 times
## Post #4
- Username: diksonhe
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jul 23, 2015 10:15 pm
- Post datetime: 2015-08-05T09:18:42+00:00
- Post Title: Demon Seals online Game .npk file archive

> Reply from Ekey
>
> Code: Select all# NXPK (script 0.1.1)
# script for QuickBMS http://quickbms.aluigi.org

idstring "NXPK"
get FILES long
get OFFSET asize
xmath OFFSET "OFFSET - (FILES * 0x1c)"
goto OFFSET
for i = 0 < FILES
    get NAME_CRC long
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZCRC long
    get CRC long
    get FLAGS long
    if FLAGS == 2
        comtype lz4
    else    # 0
        comtype zlib
    endif
    if SIZE == ZSIZE
        log "" OFFSET SIZE
    else
        clog "" OFFSET ZSIZE SIZE
    endif
next i

Thanks so much ,
## Post #5
- Username: diksonhe
- Rank: beginner
- Number of posts: 22
- Joined date: Thu Jul 23, 2015 10:15 pm
- Post datetime: 2015-08-05T09:30:38+00:00
- Post Title: Demon Seals online Game .npk file archive

> Reply from shakotay2
>
> this is a model's submesh:
00000014_dat.JPG

learning tutorial, but a little difficult.
