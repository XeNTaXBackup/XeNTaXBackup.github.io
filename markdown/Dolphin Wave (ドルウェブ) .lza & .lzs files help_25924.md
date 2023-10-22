## Post #1
- Username: Demon9705
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 15, 2021 8:53 am
- Post datetime: 2022-10-21T06:44:18+00:00
- Post Title: Dolphin Wave (ドルウェブ) .lza & .lzs files help

Hi! I want to extract the character models for the newest game of the creators of Senran Kagura New Link; dolphin wave. I managed to acces the game files and I see a bunch of .lza and .lzs files that I think is a method of compressing the files but I dont find anyway of opening them.

Is there anyway to extract them or a .bms file for it?

Thanks!

PD: here are some file examples if needed: [https://www119.zippyshare.com/v/bWmxe6LB/file.html](https://www119.zippyshare.com/v/bWmxe6LB/file.html)
## Post #2
- Username: vefalst
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 30, 2015 10:10 pm
- Post datetime: 2022-10-21T09:09:14+00:00
- Post Title: Dolphin Wave (ドルウェブ) .lza & .lzs files help

chrrox bms script seems to work for lzs files. No idea what are those lza files. 

```
#by chrrox
#http://aluigi.altervista.org/quickbms.htm
comtype LZSS0
get zsize asize
get size long
math zsize -= 4
if SIZE & 0x80000000
log MEMORY_FILE 4 zsize
else
clog MEMORY_FILE 4 zsize size
endif
get files short MEMORY_FILE
goto 0 MEMORY_FILE
for i = 0 < files
get null short MEMORY_FILE
get type short MEMORY_FILE
get offset long MEMORY_FILE
get size long MEMORY_FILE
get id long MEMORY_FILE
get name basename
getdstring name2 0x30 MEMORY_FILE
string name + \
string name + name2
log name offset size MEMORY_FILE
next i
```


Maybe chrrox can give us a help here
## Post #3
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-10-21T20:16:58+00:00
- Post Title: Dolphin Wave (ドルウェブ) .lza & .lzs files help

> Reply from vefalst ↑Fri Oct 21, 2022 5:09 pm at Fri Oct 21, 2022 5:09 pm
>
> 
chrrox bms script seems to work for lzs files. No idea what are those lza files. 
Code: Select all#Quickbms Script
#by chrrox
#http://aluigi.altervista.org/quickbms.htm
comtype LZSS0
get zsize asize
get size long
math zsize -= 4
if SIZE & 0x80000000
log MEMORY_FILE 4 zsize
else
clog MEMORY_FILE 4 zsize size
endif
get files short MEMORY_FILE
goto 0 MEMORY_FILE
for i = 0 < files
get null short MEMORY_FILE
get type short MEMORY_FILE
get offset long MEMORY_FILE
get size long MEMORY_FILE
get id long MEMORY_FILE
get name basename
getdstring name2 0x30 MEMORY_FILE
string name + \
string name + name2
log name offset size MEMORY_FILE
next i

Maybe chrrox can give us a help here

The resulting  .bum files don't seem to work with the 2 scripts for noesis that I know:

ToLoveRu
[viewtopic.php?f=16&t=16034#p128875](https://forum.xentax.com/viewtopic.php?f=16&t=16034#p128875)

Senran Kagura
[viewtopic.php?f=16&t=17608&p=162265&hil ... nk#p140046](https://forum.xentax.com/viewtopic.php?f=16&t=17608&p=162265&hilit=senran+kagura+new+link#p140046)
## Post #4
- Username: kasim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 23, 2022 9:45 am
- Post datetime: 2022-10-23T05:39:01+00:00
- Post Title: Dolphin Wave (ドルウェブ) .lza & .lzs files help

I use chrrox bms script
it work on pl01001

```
--------------------------------------
  00000400 264760     pl01001\pl01001_mdl.bum
  00040e80 151304     pl01001\pl01001_mdl_face.bum
  00065e00 175920     pl01001\pl01001_mdl_mtn.bum
  00090d80 109184     pl01001\pl01001_mdl_weapon01.bum
  000ab800 5389       pl01001\pl01001_brow_dif.png
  000acd80 3068       pl01001\pl01001_brow_line.png
  000ad980 6004       pl01001\pl01001_brow_mask.png
  000af100 3623       pl01001\pl01001_eye_highlight00.png
  000aff80 11980      pl01001\pl01001_eye_matcap00.png
  000b2e80 176659     pl01001\pl01001_face00_dif.png
  000de100 20547      pl01001\pl01001_face00_line.png
  000e3180 151098     pl01001\pl01001_face00_mask.png
  00108000 4468       pl01001\pl01001_face00_toon.png
  00109180 219101     pl01001\pl01001_weapon01_dif.png
  0013e980 5998       pl01001\pl01001_weapon01_mask.png
  00140100 4249       pl01001\pl01001_weapon01_toon.png

- 16 files found in 0 seconds
  coverage file 0   100%   1086805    1086805    . offset 00000004
  coverage file -1   99%   1314378    1315328    . offset 00000400

```


In pl01002.lzs texture become bc7 not PNG
I thinks this format is DDS, and it did show on HxD

```
--------------------------------------
  00000380 264760     pl01002\pl01002_mdl.bum
  00040e00 151304     pl01002\pl01002_mdl_face.bum
  00065d80 184152     pl01002\pl01002_mdl_mtn.bum
  00092d00 16532      pl01002\pl01002_brow_dif.bc7
  00096e00 1172       pl01002\pl01002_brow_line.bc7
  00097300 16532      pl01002\pl01002_brow_mask.bc7
  0009b400 4244       pl01002\pl01002_eye_highlight00.bc7
  0009c500 65684      pl01002\pl01002_eye_matcap00.bc7
  000ac600 1048724    pl01002\pl01002_face00_dif.bc7
  001ac700 65684      pl01002\pl01002_face00_line.bc7
  001bc800 1048724    pl01002\pl01002_face00_mask.bc7
  002bc900 16532      pl01002\pl01002_face00_toon.bc7
  002c0a00 16532      pl01002\pl01002_hr99999_00_toon.bc7

- 13 files found in 0 seconds
  coverage file 0   100%   993240     993240     . offset 00000004
  coverage file -1   99%   2901410    2902784    . offset 00000340

```


Here is pl01002 file [https://www.mediafire.com/file/xn804tvm ... 2.zip/file](https://www.mediafire.com/file/xn804tvm6h1cng3/pl01002.zip/file)

But still no clue with .lza format
## Post #5
- Username: 12121212j
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 30, 2023 9:12 pm
- Post datetime: 2023-09-19T22:28:15+00:00
- Post Title: Dolphin Wave (ドルウェブ) .lza & .lzs files help

Is there any progress, how can I import the Bum model file, and how to unpack the Lza file? I am at a loss right now  The model of this game is really great
