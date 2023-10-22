## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-13T18:33:55+00:00
- Post Title: CW Online

[http://cw.xoyo.com/](http://cw.xoyo.com/)
I made a quickbms script for these files.


```
get files long
get tableoff long
get unko01 long
get null long
get nameoff long
for i = 0 < files
goto tableoff
get check long
get offset long
get size long
get zsize THREEBYTE
get two byte
savepos tableoff
goto nameoff
get test string
savepos endstr
set nsize endstr
math nsize - nameoff
math nsize - 1
goto nameoff
filexor "0xa5" name
getdstring name nsize
filexor ""
math nameoff + 0x50
comtype unzip_dynamic
clog name offset zsize size
next i

```


Is there a way in quickbms when xoring a string to have it stop at a null terminated value?
i would like to do getdstring name 0x50 and just xor the value that is returned from that as only the name is xored and not the trailing 00.
this works but it would be nice to do it the correct way.
