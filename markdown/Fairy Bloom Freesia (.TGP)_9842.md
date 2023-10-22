## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-08T20:31:54+00:00
- Post Title: Fairy Bloom Freesia (*.TGP)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "TGP0"
get VERSION long
get NULLS long
get FILES long

for i = 0 < FILES
    getdstring NAME 0x60
    get OFFSET long
    get NULLS long
    get SIZE long
    get NULLS long
    log NAME OFFSET SIZE
next i
```
