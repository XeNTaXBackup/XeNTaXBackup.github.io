## Post #1
- Username: omfgpota
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-19T18:48:50+00:00
- Post Title: Divina Online

Here is a bms to extract the files from Divina Online.
I only had dds and nif files to look at if there are other different files feel free to send them and ill add them to the script.
[http://dn.gamania.co.jp/beginners_guide ... nload.aspx](http://dn.gamania.co.jp/beginners_guide/start_guide/download.aspx)

```
#by chrrox
comtype LZO1X
get NAME BASENAME
get EXT EXTENSION
print "%NAME%"
print "%EXT%"
if EXT == ni_
goto 0x14
get nsize long
getdstring null nsize
get zsize long
get size long
getdstring null 0xC
savepos offset
string NAME + .nif
clog NAME offset zsize size
elseif EXT == dd_
string NAME + .dds
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
goto 0xC
get width long
get height long
goto 0x14
get nsize long
getdstring null nsize
get zsize long
get size long
getdstring null 0x8
get type long
savepos offset
putVarChr MEMORY_FILE 0XC height long
putVarChr MEMORY_FILE 0x10 width long
putVarChr MEMORY_FILE 0x54 type long
append
clog MEMORY_FILE offset zsize size
append
get size asize MEMORY_FILE
log NAME 0 size MEMORY_FILE
endif

```

The nif files work fine in nifskope
## Post #2
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2013-04-18T16:02:31+00:00
- Post Title: Divina Online

I have modified your script sir and successfuly extracted the kf data from the files that i sent you earlier, all i did was copy some lines and edit them along with your script.

```
#by chrrox
comtype LZO1X
get NAME BASENAME
get EXT EXTENSION
print "%NAME%"
print "%EXT%"
if EXT == ni_a
goto 0x14
get nsize long
getdstring null nsize
get zsize long
get size long
getdstring null 0xC
savepos offset
string NAME + .nif
clog NAME offset zsize size
elseif EXT == k_
goto 0x14
get nsize long
getdstring null nsize
get zsize long
get size long
getdstring null 0xC
savepos offset
string NAME + .kf
append
clog MEMORY_FILE offset zsize size
append
get size asize MEMORY_FILE
log NAME 0 size MEMORY_FILE
endif
elseif EXT == dd_
string NAME + .dds
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
goto 0xC
get width long
get height long
goto 0x14
get nsize long
getdstring null nsize
get zsize long
get size long
getdstring null 0x8
get type long
savepos offset
putVarChr MEMORY_FILE 0XC height long
putVarChr MEMORY_FILE 0x10 width long
putVarChr MEMORY_FILE 0x54 type long
append
clog MEMORY_FILE offset zsize size
append
get size asize MEMORY_FILE
log NAME 0 size MEMORY_FILE
endif
```


it successfuly extracts tha kf file to its native format. but unfortunately when i attach the kf to the model via nifskope, it says the following error:

couldn't find the animation's root node ().

did i get something wrong? please help sir! thank you so much
