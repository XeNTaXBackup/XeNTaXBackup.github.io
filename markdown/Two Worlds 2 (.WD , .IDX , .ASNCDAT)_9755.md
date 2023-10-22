## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T12:05:18+00:00
- Post Title: Two Worlds 2 (*.WD , *.IDX , *.ASNCDAT)

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype unzip_dynamic

idstring "WD"
goto 0x2c
get TABLESIZE long
savepos TABLEOFFSET
clog MEMORY_FILE TABLEOFFSET TABLESIZE TABLESIZE
get FILES long MEMORY_FILE

for i = 0 < FILES
     get NSIZE byte MEMORY_FILE
     getdstring NAME NSIZE MEMORY_FILE
     get FLAG byte MEMORY_FILE
     get OFFSET long MEMORY_FILE
     get NULLS long MEMORY_FILE
     get ZSIZE long MEMORY_FILE
     get SIZE long MEMORY_FILE
     get NULLS long MEMORY_FILE
   if SIZE == ZSIZE
     log NAME OFFSET SIZE
   else
     clog NAME OFFSET ZSIZE SIZE
   endif	  
next i
```


For sounds

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

open FDDE IDX 0
open FDDE IDX.ASNCDAT 1

idstring "DWXF" 0
get VERSION long 0
get PAKNAME string 0
get FILES long 0

for i = 0 < FILES
	get FLAGNAME long 0
	get NSIZE long 0
	getdstring NAME NSIZE 0
	get TERMINATOR byte 0
	get SIZE long 0
	get OFFSET long 0
	get DUMMY long 0
	get DUMMY long 0
	log NAME OFFSET SIZE 1
next i
```
## Post #2
- Username: AdrianWojnicki
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2017 9:41 pm
- Post datetime: 2017-01-18T14:57:12+00:00
- Post Title: Two Worlds 2 (*.WD , *.IDX , *.ASNCDAT)

Thank You as fuck !
