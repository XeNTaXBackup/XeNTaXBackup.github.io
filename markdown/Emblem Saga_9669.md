## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-24T01:38:21+00:00
- Post Title: Emblem Saga

HP: [http://wzcs.kufgame.com/](http://wzcs.kufgame.com/)

Models are just xac format.



unpacker (same as war of dragon except all files are zlib compressed

```
# Script for QuickBMS

open FDDE tbl2 1
set arcnum 0

comtype "unzip_dynamic"
goto 0x10001C 1

for i = 0
  get offset long 1
  get zsize long 1
  get null3 long 1
  get size long 1
  get arcnum long 1
  set NAME1 string "file0"
  set MYEXT string arcnum
  strlen MYEXTSZ MYEXT
  if MYEXTSZ == 1
    string NAME1 += "00"
  endif
  if MYEXTSZ == 2
    string name1 - 1
    string NAME1 += "0"
  endif
  if MYEXTSZ == 3
    string name1 - 1
    string NAME1 += ""
  endif
  string NAME1 += MYEXT
  string NAME1 += .data2
  open FDSE NAME1 0

  get null1 long 1
  get null2 long 1
  get name string 1
  Padding 4 1
  get null long 1
  clog name offset zsize zsize
next i
```

[20120702011313499.jpg](https://xentaxbackup.github.io/file/5827_20120702011313499.jpg)
