## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-06T19:40:38+00:00
- Post Title: Aquitania / Cradle Of Persia (*.PAK)

For [this](http://www.awem.com/cradle-of-persia.html) and [this](http://www.awem.com/aquitania.html) games.

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get VERSION short
get FILES long

for i = 0 < FILES
    get NSIZE short
    filexor "\xcd"
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    filexor ""
    log NAME OFFSET SIZE
next i
```
