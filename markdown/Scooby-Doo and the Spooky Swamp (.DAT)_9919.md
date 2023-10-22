## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-28T17:05:34+00:00
- Post Title: Scooby-Doo and the Spooky Swamp (*.DAT)

```
#
# Written by Ekey (h4x0r) 0.1
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org

idstring "PAK\x00"
get FILES long

for i = 0 < FILES
    get HASH long
    get TOFFSET long
    get ZSIZE long
    savepos TEMP
    goto TOFFSET
    idstring "!ZLS"
    get SIZE long
    savepos OFFSET
    string NAME p= "%08X" HASH
    clog NAME OFFSET ZSIZE SIZE
    goto TEMP
next i
```
