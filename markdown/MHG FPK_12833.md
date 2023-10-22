## Post #1
- Username: yiwang
- Rank: beginner
- Number of posts: 21
- Joined date: Sat Apr 28, 2012 9:30 am
- Post datetime: 2015-05-11T19:40:06+00:00
- Post Title: MHG FPK

[http://www.uploadmb.com/dw.php?id=1431373003](http://www.uploadmb.com/dw.php?id=1431373003)
[fpk.png](https://xentaxbackup.github.io/file/9189_fpk.png)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-05-12T13:54:00+00:00
- Post Title: MHG FPK

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

endian big
comtype COMP_PRS_8ING

get UNKNOWN long
get FILES long
get HEADERSIZE long
get ARCHIVESIZE long

for i = 0 < FILES
    getdstring NAME 36
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
