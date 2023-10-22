## Post #1
- Username: neff10
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 18, 2012 2:17 pm
- Post datetime: 2014-01-03T09:14:59+00:00
- Post Title: [ps3] Ni no kuni .adat

found lot of post about ni no kuni but any cant rip .adat or .sdat fom ni no kuni european version i send a pm to howfie because he created the script but anything... i think he created the script for the japanese version or something else, anyone can help me?
## Post #2
- Username: neff10
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jul 18, 2012 2:17 pm
- Post datetime: 2014-01-20T19:58:50+00:00
- Post Title: [ps3] Ni no kuni .adat

```
endian big
idstring "PSAR"
get VER short
get MVER short
getdstring COMP 0x4
get START long
get ENTRYSIZE long
get FILES long
get CHKSIZE long
get TWO long
set BASEOFF files
math BASEOFF * ENTRYSIZE
math BASEOFF + 0x20
math files - 1
getdstring null 0x15
get TSIZE long
get NULL byte
get OFFSET long
savepos TBL
set COUNT TSIZE
math COUNT / 0x10000
math COUNT + 1
goto BASEOFF
for i = 0 < COUNT
get TMP short
putarray 0 i TMP
next i
comtype unzip_dynamic
for i = 0 < COUNT
getarray ZSIZE 0 i
append
clog MEMORY_FILE OFFSET ZSIZE ZSIZE
append
math OFFSET + ZSIZE
next i
goto 0 MEMORY_FILE
goto TBL
for i = 1 to FILES
if i == FILES
savepos tmp MEMORY_FILE
get NSIZE asize MEMORY_FILE
math NSIZE - tmp
getdstring NAME NSIZE MEMORY_FILE
else
GetCT NAME string 0x0a MEMORY_FILE
endif
getdstring null 0x15
get SIZE long
get NULL byte
get OFFSET long
log NAME OFFSET SIZE
next i

```


founded this code by chrox but dot know how to run it if anyone can help in this?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-20T21:05:13+00:00
- Post Title: [ps3] Ni no kuni .adat

it's a bms script, isn't it?
Then try quickbms.exe.

When clicking on the exe (in the windows explorer) it prompts you for selecting the BMS script, then for the input archive to extract and at last for the output folder.

btw: past tense of find is found not "founded". founded having a different meaning.
