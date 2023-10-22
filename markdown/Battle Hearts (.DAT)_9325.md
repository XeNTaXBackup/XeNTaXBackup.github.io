## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-07-21T14:15:54+00:00
- Post Title: Battle Hearts (*.DAT)

Finally done 

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# Thanks Aluigi
# script for QuickBMS http://quickbms.aluigi.org

set KEY "0x69 0x6F 0x6E 0x30 0x76 0x61 0x73 0x64 0x6E 0x76 0x56 0x6E 0x47 0x72 0x39 0x38 0x35 0x36 0x59 0x69 0x75 0x64 0x68 0x66 0x67 0x66 0x2D 0x38 0x34 0x35 0x2E 0x53"

goto -0x10
get NULLS long
get TABLEOFFSET long
get TABLESIZE long
get VERSION long

goto TABLEOFFSET

for
    filexor KEY NULLS
    get NSIZE byte
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
    savepos TMP
    if TMP == TABLESIZE
  cleanexit
 endif
next
```


Thx aluigi.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-21T14:23:40+00:00
- Post Title: Battle Hearts (*.DAT)

you can make the last part smaller removing filexor "" because doesn't get used and using do while:

```
do
    filexor KEY NULLS
    get NSIZE byte
    getdstring NAME NSIZE
    get OFFSET long
    get SIZE long
    log NAME OFFSET SIZE
    savepos TMP
while TMP < TABLESIZE
```
I know that a "while {} do" would have been better (only in case there are no files at all in the archive) but doesn't exist that command in the bms language
