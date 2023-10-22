## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-03-21T10:31:10+00:00
- Post Title: Mugen souls z .cl3

i think the model and texture are packed in this format,unlike previous compile heart games..

here is sample,can someone make the quickbms script/extractor for this format?



[http://www.mediafire.com/download/7ah38 ... del001.zip](http://www.mediafire.com/download/7ah38kr8yj11dza/Model001.zip)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-21T10:52:33+00:00
- Post Title: Mugen souls z .cl3

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big
idstring "CL3B"
goto 0x10
get FLCOLLECTOFFSET long
goto FLCOLLECTOFFSET
idstring "FILE_COLLECTION\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
get FILES long
get PAKSIZE long
get ENTRYOFFSET long
goto ENTRYOFFSET

for i = 0 < FILES
    getdstring NAME 0x204
    get OFFSET long
    math OFFSET += ENTRYOFFSET
    get SIZE long
    getdstring DUMMY 0x24
    log NAME OFFSET SIZE
next i
```
