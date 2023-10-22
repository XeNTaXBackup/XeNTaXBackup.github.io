## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-28T17:44:42+00:00
- Post Title: SS OMEGA Online

Anyone can help with this file to extract the content its from SS Omega Online.

[http://www.mediafire.com/?gg1a4bddd5lu9vn](http://www.mediafire.com/?gg1a4bddd5lu9vn)

Thanks.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T18:02:01+00:00
- Post Title: SS OMEGA Online

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

comtype tdcb_lzw15v

get PSIZE asize
math PSIZE -= 8

goto -0x4
filexor "0xff"
get TABLEOFFSET long
goto TABLEOFFSET

for
   filexor "0xff"
   get NULLS long
   getdstring NAME 0x100
   get OFFSET long
   get ZSIZE long
   get SIZE long
   filexor ""
 if ZSIZE == SIZE
    log NAME OFFSET ZSIZE
 else
   clog NAME OFFSET ZSIZE SIZE
 endif
    savepos TMP
    if TMP == PSIZE
  cleanexit
 endif
next
```
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-08-28T21:17:21+00:00
- Post Title: SS OMEGA Online

Wtf u are greath.   , Thanks ekey
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-08-28T21:21:48+00:00
- Post Title: SS OMEGA Online

@Edited: Updated script.
