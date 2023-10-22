## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-25T22:23:19+00:00
- Post Title: End of Nations (Beta) (*.MEG)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get ID long
  if ID == 0xffffff8f
    print "Archive encrypted and unsupported!"
    cleanexit
  else if ID == 0xffffffff
endif

get DUMMY1 long
get DUMMY2 long
get FILES long
get FILES2 long
get NAMESSIZE long
savepos NAMESOFFSET

set TABLEOFFSET = NAMESSIZE
math TABLEOFFSET += NAMESOFFSET
math TABLEOFFSET += 2
goto TABLEOFFSET

for i = 0 < FILES
    get CRC long
    get FILENUM long
    get SIZE long
    get OFFSET long
    get FLAG long
    savepos TEMP
    goto NAMESOFFSET
    get NSIZE short
    getdstring NAME NSIZE
    log NAME OFFSET SIZE
    math NAMESOFFSET += NSIZE
    math NAMESOFFSET += 2
    goto TEMP
next i
```


CONFIG.MEG - Not supported because encrypted with AES-128-CBC
