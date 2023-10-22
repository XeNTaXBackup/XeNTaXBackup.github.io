## Post #1
- Username: s25jin
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-10T15:38:26+00:00
- Post Title: Kingdom Under Fire Online: Age of Storm

Here is a quickbms script to decrypt and extract this games files. there are a few file types i did not get the xor key for if anyone wants to add them feel free.
[http://www.youtube.com/watch?v=N49n3vvfNRY](http://www.youtube.com/watch?v=N49n3vvfNRY)
"Kingdom Under Fire Online:Age of Storm"
[http://aos.pmang.com/](http://aos.pmang.com/)
Client Download [http://pan.baidu.com/share/link?shareid ... 2569162676](http://pan.baidu.com/share/link?shareid=335852&uk=2569162676)



```
#Kingdom Under Fire Online: Avalanche
#Version 2
open FDSE "df_stroyent000.qpf" 1
get files long 1
putarray 0 0 ""
goto 0xE 1
math files - 1
for i = 0 < files
get null long 1
get var long 1
savepos nstart 1
findloc nsize string "\x0\x0\x0" 1
math nsize + 3
math nsize - nstart
getdstring UNAME nsize 1
set NAME unicode UNAME
#print "%NAME%"
putarray 0 var NAME
next i

goto 0x18
get files long
for i = 0 < files
get folder long
get hash long
savepos nstart
findloc nsize string "\x0\x0\x0"
math nsize + 3
math nsize - nstart
getdstring UNAME nsize
set NAME2 unicode UNAME
getarray NAME 0 folder
string NAME + \
string NAME + NAME2
get offset long
get size long
log MEMORY_FILE offset size
set EXT extension NAME2
get key long MEMORY_FILE
if EXT == "kf"
math key ^ 0x656D6147
elseif EXT == "asi"
math key ^ 0x00905A4D
elseif EXT == "avi"
math key ^ 0x46464952
elseif EXT == "bdr"
math key ^ 0x4C49667B
elseif EXT == "bmp"
goto 0x2C MEMORY_FILE
get key long MEMORY_FILE
elseif EXT == "cache"
math key ^ 0x5047694E
elseif EXT == "dds"
math key ^ 0x20534444
elseif EXT == "env"
math key ^ 0x00000003
elseif EXT == "flt"
math key ^ 0x00905A4D
elseif EXT == "fxo"
math key ^ 0xFEFF0901
elseif EXT == "h"
math key ^ 0x74000F0F
elseif EXT == "kfm"
math key ^ 0x6D61473B
elseif EXT == "nff"
math key ^ 0x0046464E
elseif EXT == "nif"
math key ^ 0x656D6147
elseif EXT == "nsb"
math key ^ 0x0062736E
elseif EXT == "list"
math key ^ 0x1C9F9BCF
elseif EXT == "settings"
math key ^ 0x332E3205
elseif EXT == "ogg"
math key ^ 0x5367674F
elseif EXT == "kfl"
math key ^ 0x4D581F1C
elseif EXT == "gsa"
math key ^ 0x4D581F1C
elseif EXT == "ado"
math key ^ 0x4D581F1C
elseif EXT == "npc"
math key ^ 0x4D581F1C
elseif EXT == "tga"
math key ^ 0x000A0000
elseif EXT == "ttf"
math key ^ 0x00000100
elseif EXT == "fig"
math key ^ 0x63627566
elseif EXT == "hlsl"
math key ^ 0x4E494C03
elseif EXT == "wav"
math key ^ 0x46464952
elseif EXT == "xml"
math key ^ 0x4D581F1C
elseif EXT == "db"
goto 12 MEMORY_FILE
get key long MEMORY_FILE

elseif EXT == "mpf"
set key 0
math key ^ 0x0
elseif EXT == "lua"
set key 0
math key ^ 0x0
elseif EXT == "txt"
set key 0
math key ^ 0x0
elseif EXT == "yui"
set key 0
math key ^ 0x0
elseif EXT == "ifl"
set key 0
math key ^ 0x0

else
print "%EXT% is unsupported"
endif
filexor key
log NAME 0 SIZE MEMORY_FILE
filexor ""
set key 0
next i

```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-13T14:11:17+00:00
- Post Title: Kingdom Under Fire Online: Age of Storm

I have updated the Script it reads directories now.
There will be about 5 or 6 files in the entire game that will complain in quickbms due to Korean characters just rename them and your all set.
Niftools supports this game with meshes and animations 
If anyone wants to finish the bms by getting the rest of the xor keys feel free.
## Post #3
- Username: s25jin
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2013-03-13T14:16:59+00:00
- Post Title: Kingdom Under Fire Online: Age of Storm

Very good work
