## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-23T19:30:53+00:00
- Post Title: PS3 How to train your dragon 2 hunkfile

Sup, Im not an archive guy and if I ever try it will take a long time.
Sample hir.
Would be happy if anyone make bms script for it.
[tryin-find-adorable-beauty.rar](https://xentaxbackup.github.io/file/8362_tryin-find-adorable-beauty.rar)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-12-23T22:02:47+00:00
- Post Title: PS3 How to train your dragon 2 hunkfile

My guess for this file:

Little endian
offset 0x2DD
4 bytes (long) => width  // maybe height
4 bytes (long) => height // maybe width
2 bytes (short) = > null
4 bytes (long) => texture length
4 bytes (long) => unknown
0x20000 bytes texture data

This sample file contains DXT1 512x512px texture without mipmaps.

[](http://www.fastimages.eu/?v=512x512.jpg)
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2015-12-18T19:03:45+00:00
- Post Title: PS3 How to train your dragon 2 hunkfile

Okay, so it will be year soon since I posted it, and still nothing, I have decided to use my noob skillz and create bms script, actually I just finished it.
I will add code for texture conversion soon, and maybye ms too.

```
# Author Lukáš Kužel in 2015
# script for QuickBMS http://quickbms.aluigi.org

set curoff long 0
set size long 0
set curname string ""
get fsiz ASIZE
math fsiz -= 8
for i = 0 < fsiz
  savepos Slump
  get LumpLen long
  get LumpID long 
  if LumpID == 0x40071   
    get unk11 short
    get unk12 short
    get unk13 short 
    get typelength short
    get namelength short 
    getdstring TYPE typelength
    getdstring curname namelength 
    string curname + "."
    string curname + TYPE
  elif LumpID == 0x40070     
    get blcount short
    get unk22 short
    get unk23 short 
    get unk24 short   
    get unk25 long  
    get usedblocks long 
    for i2 = 0 < blcount
      getdstring name 64 
      get unk26 long  // offset or size?
      get unk27 long  // identifier, last short from lumpid
    next i2
  elif LumpID == 0x40072    
    math size = Slump
    math size -= curoff
    log curname curoff size
    //Print "Log %curname% %curoff% %size%"
    math curoff = 0
  elif curoff == 0 
    math curoff = Slump
    goto LumpLen 0 SEEK_CUR  
  else
    goto LumpLen 0 SEEK_CUR                                                                                                    
  endif
  if fsiz == Slump
    cleanexit
  endif 
next i
```
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2015-12-18T21:24:16+00:00
- Post Title: PS3 How to train your dragon 2 hunkfile

And we have texture conversion to dds.

```
# Author Lukáš Kužel in 2015
# script for QuickBMS http://quickbms.aluigi.org

get ddsname BASENAME 
string ddsname + ".dds"

log MEMORY_FILE 0 0

Put 0x20534444 Long MEMORY_FILE  
Put 0x7c long MEMORY_FILE 
     
set flags long 7
math flags | 0x1000
math flags | 0x8
math flags | 0x800000
Put flags Long MEMORY_FILE

goto 8
get type byte
goto 19
get size1 short
get size2 short
goto 100
get size3 long
get lumpid long

Put size2 Long MEMORY_FILE
Put size1 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 1 Long MEMORY_FILE
Put 11 Long MEMORY_FILE   // mipmaps
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0x20 Long MEMORY_FILE
Put 5 Long MEMORY_FILE

if type == 0xa1
  Put 0x31545844 Long MEMORY_FILE 
else
  Put 0x35545844 Long MEMORY_FILE 
endif
   
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE

set pflags long 0x400000
math pflags | 0x1000
math pflags | 5

Put pflags Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE
Put 0 Long MEMORY_FILE


set fsize 125
math fsize += size3

for i = 0 < size3
  get tmp byte
  Put tmp byte MEMORY_FILE
next i 

goto 0 MEMORY_FILE
log ddsname 0 fsize MEMORY_FILE
```
## Post #5
- Username: keybladegames
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 16, 2022 2:59 pm
- Post datetime: 2022-03-11T08:06:22+00:00
- Post Title: PS3 How to train your dragon 2 hunkfile

it doesn't work at all.
