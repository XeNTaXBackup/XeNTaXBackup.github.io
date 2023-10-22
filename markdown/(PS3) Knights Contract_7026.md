## Post #1
- Username: raykingnihong
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T17:20:33+00:00
- Post Title: (PS3) Knights Contract

Here is a texture extractor that works on all models.
you must put the model and texture file in the same directory and name them the same name only a different extension for example
the model file is chr063.hxt
and the texture file is chr063.txb
all i did was rename chr063_5A5591DA.txb to chr063.txb

```
#updated 7/22/2011
open FDDE hxt 1
open FDDE txb 0
endian big
comtype inflate
goto 0x8C 1
get files long 1
getdstring null 0x14 1
get fldrsize long 1
getdstring folder fldrsize 1
getdstring null 0x6C 1
for i = 0 < files
get nsize long 1
getdstring TexName nsize 1
getdstring null 0x2A 1
get type byte 1
get unk05 byte 1
get ddsSize long 1
getdstring null ddsSize 1
get unk01 long 1
get unk02 long 1
get unk03 long 1
savepos tbl1 1
getdstring null 0x48 1
getdstring tex4 0x18 1
savepos tbl2 1
for j = 0 < 3
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\x80\x00\x00\x00\x80\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
set name TexName
string name + j
string name + .dds
goto tbl1 1
get width long 1
get height long 1
get one long 1
get mips long 1
get unk04 long 1
get picsize long 1
savepos tbl1 1
goto tbl2 1
get offset long 1
get totalsize long 1
get size long 1
get zsize long 1
savepos tbl2 1
if size != 0
append
clog MEMORY_FILE offset zsize size
append
else
append
clog MEMORY_FILE offset zsize totalsize
append
endif
if type == 0x47
putVarChr MEMORY_FILE 0x57 0x31 byte
endif
if type == 0x4E
putVarChr MEMORY_FILE 0x57 0x35 byte
endif
endian little
putVarChr MEMORY_FILE 0x0C height long
putVarChr MEMORY_FILE 0x10 width long
endian big
math offset + zsize
math totalsize + 0x80
if size != 0
Do
goto offset
get size long
get zsize long
savepos offset
print "%offset%"
append
clog MEMORY_FILE offset zsize size
math offset + zsize
append
get tsize asize MEMORY_FILE
while tsize !=  totalsize
endif
get tsize asize MEMORY_FILE
log NAME 0 tsize MEMORY_FILE
next j
getdstring unk05 0xC 1
next i

```



[http://imageshack.us/g/834/chr06302b0.png/](http://imageshack.us/g/834/chr06302b0.png/)


```
chr053 some green costume
chr061 Gretchen in orange outfit
chr063 Gretchen in Normal outfit
chr064 heinrich beast mode
chr068 Rapunzel
chr072 Gretchen in red outfit
chr079 heinrich in costume
chr081 Gretchen in blue outfit
chr083 Gretchen in orange outfit
chr084 heinrich in costume
chr085 Gretchen in orange outfit
chr094 heinrich in costume
chr151 some armor
chr201 damage maps
chr217 some monster?
chr236 fire maps
chr238 some monster?
chr246 stone maps
chr251 Trude
chr252 Trude Snakes
chr255 Streagelle
chr256 Streagelle 2nd form
chr257 fire monster? holda?
chr258 some witch
chr259 some witch 2nd form? rendula?
chr260 Verderinde
chr261 De Faust
chr264 harpie?
chr271 De Faust some monster form
chr272 fire monster? holda?
chr273 De Faust some monster form
chr274 De Faust some monster form
chr 282 some skeleton monster
chr542 some green guy in human form
chr519 some witch 2nd forum?


```
## Post #2
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-16T10:50:04+00:00
- Post Title: (PS3) Knights Contract

Hi chrrox,Thank you very much for the great work, the script runs very well
