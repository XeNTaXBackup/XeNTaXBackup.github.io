## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-01-09T20:24:17+00:00
- Post Title: DO Online (*.VFS)

Official Site: [here](http://www.doonline.co.kr)
Media: [here](http://www.doonline.co.kr/psd/psd_wallpaper.html)
Download: [here](http://cdn.doonline.co.kr/do_install/doonline_20141230.exe)

For unpack open data.inf

```
# http://www.doonline.co.kr
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

get INF_PATH FILE_FOLDER
set ARCHIVE_PATH string INF_PATH
string ARCHIVE_PATH += "/data/data.vfs"
open FDSE "data.inf" 0 EXISTS
open FDSE ARCHIVE_PATH 1 EXISTS

idstring "VFS001" 0
goto 0xC 0
get FILES long 0
goto 0x18 0

for i = 0 < FILES
    getdstring NAME 104 0
    get OFFSET long 0
    get DUMMY long 0 # 0
    get SIZE long 0
    get DUMMY long 0 # 0
    getdstring TRASH 24 0
    log NAME OFFSET SIZE 1
next i
```
