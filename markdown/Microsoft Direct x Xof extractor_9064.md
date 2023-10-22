## Post #1
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-10T16:28:19+00:00
- Post Title: Microsoft Direct x Xof extractor

this will create a cab file you can extract from any compressed . x file.
then just add the proper 0x10 byte header for a uncompressed .x file and it will load no problem.

```
most likely
xof 0303txt 0032
or 
xof 0303bin 0032
or in hex
78 6F 66 20 30 33 30 33 74 78 74 20 30 30 33 32
or
78 6F 66 20 30 33 30 33 62 69 6E 20 30 30 33 32

http://paulbourke.net/dataformats/directx/ 

```


```
set MEMORY_FILE binary "\x4D\x53\x43\x46\x00\x00\x00\x00\x41\x48\x00\x00\x00\x00\x00\x00\x2C\x00\x00\x00\x00\x00\x00\x00\x03\x01\x01\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x74\x3D\x6C\x4B\x20\x00"
get NAME FILENAME
goto 0x3C MEMORY_FILE
append
put NAME string MEMORY_FILE
append
get SIZE asize MEMORY_FILE
string NAME + .cab
putVarChr MEMORY_FILE 0x24 SIZE long
set CHECKSUM 0
set CHUNKCOUNT 0
set USIZE 0
goto 0x14
get tmp2 asize
append
for
goto SIZE MEMORY_FILE
get CSIZE short
get ZSIZE short
putVarChr MEMORY_FILE SIZE CHECKSUM long
math SIZE + 4
putVarChr MEMORY_FILE SIZE ZSIZE short
math SIZE + 2
putVarChr MEMORY_FILE SIZE CSIZE short
math SIZE + 2
savepos OFFSET
goto SIZE MEMORY_FILE
log MEMORY_FILE OFFSET ZSIZE
math OFFSET + ZSIZE
goto OFFSET
math SIZE + ZSIZE
math CHUNKCOUNT + 1
math USIZE + CSIZE
savepos tmp
if tmp == tmp2
append
putVarChr MEMORY_FILE 0x28 CHUNKCOUNT byte
get SIZE asize MEMORY_FILE
putVarChr MEMORY_FILE 0x8 SIZE long
putVarChr MEMORY_FILE 0x2C USIZE long
log NAME 0 SIZE MEMORY_FILE
cleanexit
endif
next

```
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-22T18:08:31+00:00
- Post Title: Microsoft Direct x Xof extractor

made a bms script to decompress the tzip/bzip back to txt or bin .x file  

```
string NAME + "_decomp.x"

set MEMORY_FILE binary "\x78\x6f\x66\x20\xAA\xAA\xBB\xBB\xCC\xCC\xCC\xCC\xDD\xDD\xDD\xDD"

comtype mszip
get ZSIZE asize
idstring "xof "
get MAJORVERSION short
get MINORVERSION short
getdstring FORMATTYPE 0x4
get FLOATSIZE long
get SIZE long
math OFFSET = 0x18
math ZSIZE - OFFSET

if FORMATTYPE == "tzip"
	FORMATTYPE = 0x20747874 #"txt " 
elif FORMATTYPE == "bzip"
	FORMATTYPE = 0x206e6962 #"bin " 
endif

putVarChr MEMORY_FILE 0x4 MAJORVERSION short #AAAA
putVarChr MEMORY_FILE 0x6 MINORVERSION short #BBBB
putVarChr MEMORY_FILE 0x8 FORMATTYPE long #CCCCCCCC
putVarChr MEMORY_FILE 0xc FLOATSIZE long #DDDDDDDD

append
log NAME 0 0x10 MEMORY_FILE 
clog NAME OFFSET ZSIZE SIZE
append

```

the decompressed file is ready for import by most directX .x plugins
