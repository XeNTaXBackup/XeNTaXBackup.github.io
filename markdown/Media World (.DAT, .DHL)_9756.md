## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-10-17T12:08:39+00:00
- Post Title: Media World (*.DAT, *.DHL)

For unpack like [this](http://podmashinoy.ru/manual-vaz-21099-cd) multimedia guides

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

set XOR_SIZE_KEY "0x49b17ef7"
set XOR_ZSIZE_KEY "0xb153feba"

filexor XOR_SIZE_KEY
get TABLESIZE long
filexor XOR_ZSIZE_KEY
get TABLEZSIZE long
filexor ""
math FULLTABLESIZE += TABLESIZE
math FULLTABLESIZE += TABLEZSIZE
savepos TABLEOFFSET
clog MEMORY_FILE TABLEOFFSET TABLEZSIZE FULLTABLESIZE
get VERSION long MEMORY_FILE
get FILES long MEMORY_FILE
get PAKSIZE long MEMORY_FILE

getdstring TRASH 0xe0 MEMORY_FILE

for i = 0 < FILES
     get FLAG long MEMORY_FILE
     getdstring NAME 0x40 MEMORY_FILE
     get OFFSET long MEMORY_FILE
     math OFFSET += TABLEZSIZE
     math OFFSET += 8
     get ZSIZE long MEMORY_FILE
     get SIZE long MEMORY_FILE
     savepos TEMP
   if SIZE == 0
     math TEMP += 0x80
     goto TEMP
     print "Folder: %NAME%"
   elif SIZE == ZSIZE
     log NAME OFFSET SIZE
   else
     clog NAME OFFSET ZSIZE SIZE
   endif	  
next i
```


```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

get FILES short

for i = 0 < FILES
	get NSIZE long
	getdstring NAME NSIZE
	get OFFSET long
	get SIZE long
    log NAME OFFSET SIZE
next i
```
