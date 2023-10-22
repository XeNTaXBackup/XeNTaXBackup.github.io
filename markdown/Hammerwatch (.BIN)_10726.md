## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-28T13:03:54+00:00
- Post Title: Hammerwatch (*.BIN)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "HWRA"
get FILES long

for i = 0 < FILES
    get NSIZE byte
    getdstring NAME NSIZE
    get SIZE long
    savepos OFFSET
    set TEMP = OFFSET
    math TEMP += SIZE
    log NAME OFFSET SIZE
    goto TEMP
next i
```
