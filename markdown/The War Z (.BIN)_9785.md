## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-24T21:16:56+00:00
- Post Title: The War Z (*.BIN)

Official Site: [Here](http://thewarz.com)
Screenshots: [Here](http://thewarz.com/media.html)
Download: [Web Installer (17.3Mb)](http://arktos-icdn.pandonetworks.com/WarZ_WebSetup.exe) or [Full Game (1.51Gb)](http://www.shacknews.com/file/33261/the-war-z-alpha-client-20121016)

Script for Unpack

```
#
# Written by Ekey (h4x0r)
# http://www.progamercity.net
#
# script for QuickBMS http://quickbms.aluigi.org
#
# For unpack open WZ_00.bin

comtype unzip_dynamic

open FDSE "WZ_00.bin" 0 #Table
open FDSE "WZ_01.bin" 1 #Main archive (part 1)
open FDSE "WZ_02.bin" 2 #Main archive (part 2)

idstring "arfl"
get VERSION long
get DUMMY long
get FILES long
get TABLESIZE long
get DUMMY long
savepos TABLEOFFSET

clog MEMORY_FILE TABLEOFFSET TABLESIZE TABLESIZE

for i = 0 < FILES
    getdstring NAME 0x104 MEMORY_FILE
    get PAKNUM short MEMORY_FILE
    get OFFSET long MEMORY_FILE
    math OFFSET += 4
    get SIZE long MEMORY_FILE
    get ZSIZE long MEMORY_FILE
    get CRC long MEMORY_FILE
    getdstring TRASH 0x12 MEMORY_FILE
   
    if PAKNUM == 2
      clog NAME OFFSET ZSIZE SIZE 1
    else if PAKNUM == 258
      clog NAME OFFSET ZSIZE SIZE 2
    endif
next i
```


Edited: Eh found some one script by aluigi [here](http://forum.xentax.com/viewtopic.php?p=79624#p79624)
