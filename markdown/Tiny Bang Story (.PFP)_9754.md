## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T12:03:14+00:00
- Post Title: Tiny Bang Story (*.PFP)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PFPK"
get FILES long

for i = 0 < FILES
    get NSIZE byte
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
next i
```
