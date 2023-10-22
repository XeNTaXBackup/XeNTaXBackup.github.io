## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-14T12:52:57+00:00
- Post Title: Metal Knight Zero (MKZ Online) (*.IDX)

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

get MINORVERSION short
get MAJORVERSION short
get FILES long
get MAINFOLDER string

goto 0x488

for i = 0 < FILES
    getdstring FNAME 0x80
    set NAME MAINFOLDER
    string NAME += FNAME
    get FILENUM long
    get SIZE long
    get OFFSET long
    getdstring DUMMY 0x38
    log NAME OFFSET SIZE
next i
```
