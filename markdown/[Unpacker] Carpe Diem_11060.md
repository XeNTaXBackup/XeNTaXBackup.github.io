## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-12-20T18:56:19+00:00
- Post Title: [Unpacker] Carpe Diem

Name: 榮耀世紀
Client Download: [http://cd.funmily.com/en/08-download/08 ... d-01.shtml](http://cd.funmily.com/en/08-download/08-download-01.shtml)

BMS Script. The script looks kind of funny but for some reason && (logical AND) doesn't seem to work properly for me in that specific case.
There's probably a proper way to figure out the directories but I didn't bother.

```
# Script for QuickBMS

idstring "SFILESYSTEM\x00"
get totalSize asize

comtype unzip_dynamic
set dirName string ""
for i
  get fileType long
  getdstring NAME 256
  get zsize long
  get size long
  get unk2 long
  get unk3 long
  savepos offset
  if fileType == 0 
    if NAME != "."
      if NAME != ".."
        string dirName = NAME
      endif
    endif
  else
    set outName string dirName
    if outName != ""
      string outName += "/"
    endif
    string outName += NAME
    clog outName OFFSET ZSIZE ZSIZE
  endif
 
  goto ZSIZE 0 seek_cur
  
  savepos curr
  if curr == totalsize
    break
  endif
next i

```
