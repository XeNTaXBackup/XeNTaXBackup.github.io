## Post #1
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-03-13T05:47:53+00:00
- Post Title: A-MEN (ps3) .pak extracted

Help create a script pack BMS unpacking archive.
Compression applied to the archive zlib.

[http://i33.fastpic.ru/big/2014/0313/a6/ ... b159a6.jpg](http://i33.fastpic.ru/big/2014/0313/a6/32fa894782aa0bf50b5c5e6293b159a6.jpg)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-13T11:06:10+00:00
- Post Title: A-MEN (ps3) .pak extracted

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big
comtype unzip_dynamic
idstring "PAK"
goto 0xC
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get FLAG byte
    get OFFSET long
    get ZSIZE long
    get SIZE long
	
    if ZSIZE == SIZE
      log NAME OFFSET SIZE
    else
      clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: Kaltan
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 04, 2011 12:14 am
- Post datetime: 2014-03-13T12:51:52+00:00
- Post Title: A-MEN (ps3) .pak extracted

> Reply from Ekey
>
> Code: Select all# A-MEN (PS3) (PAK format)
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big
comtype unzip_dynamic
idstring "PAK"
goto 0xC
get FILES long

for i = 0 < FILES
    get NSIZE long
    getdstring NAME NSIZE
    get FLAG byte
    get OFFSET long
    get ZSIZE long
    get SIZE long
	
    if SIZE == ZSIZE
      log NAME OFFSET SIZE
    else
      clog NAME OFFSET SIZE ZSIZE
    endif
next i

Thank you. Everything works. 
Good job.
