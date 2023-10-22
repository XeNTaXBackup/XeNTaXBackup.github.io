## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-06T00:06:20+00:00
- Post Title: king of Fighters online

Here is a bms for this game.
It is the same format as Kingdom under fire Age of Storm. (Nif models)
Some of these xor keys might be wrong but the ones that matter work and i dint feel like figuring out the others.
[http://kof.gg.in.th/home/default.aspx](http://kof.gg.in.th/home/default.aspx)

```
open FDDE kpf 1
get files long 1
math files - 1
putarray 0 0 "\"
goto 0xE 1
for i = 0 < files
get type long 1
get index long 1
savepos nstart 1
findloc nsize string \x00\x00 1
math nsize - nstart
math nsize + 3
getdstring uname nsize 1
set name unicode uname
string name + \
putarray 0 i name
#print "%name%"
next i
get ver long
get start long
get unk1 long
get unk2 long
get asize longlong
get files long
for i = 0 < files
get fldr long
get hash long
savepos nstart
findloc nsize string \x00\x00
math nsize - nstart
math nsize + 3
getdstring uname nsize
set name unicode uname
get offset long
get size long
if size != 0
log MEMORY_FILE offset size
set EXT extension name
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
elseif EXT == "ecs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
elseif EXT == "env"
math key ^ 0x00000003
elseif EXT == "flt"
math key ^ 0x00905A4D
elseif EXT == "fxo"
math key ^ 0xFEFF0901
elseif EXT == "h"
math key ^ 0x74000F0F
elseif EXT == "kcs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
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
goto 0xC MEMORY_FILE
get key long MEMORY_FILE
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
elseif EXT == "scs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
elseif EXT == "tga"
get tmp asize MEMORY_FILE
math tmp - 16
goto tmp MEMORY_FILE
get key long MEMORY_FILE
math key ^ 0x49564555
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
math fldr - 1
getarray name2 0 fldr
string name2 + name
log NAME2 0 SIZE MEMORY_FILE
filexor ""
set key 0
endif
next i

```
## Post #2
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-09-06T16:19:41+00:00
- Post Title: king of Fighters online

Nice. Too bad the nif version isn't supported by any tools.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-09-06T23:21:33+00:00
- Post Title: king of Fighters online

i believe the blender script can import them no problem
## Post #4
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-09-07T00:57:05+00:00
- Post Title: king of Fighters online

> Reply from chrrox
>
> i believe the blender script can import them no problem
Well MariusZ script gives a memory error and the one from niftools only import bones.
[ashe_toon.rar](https://xentaxbackup.github.io/file/6598_ashe_toon.rar)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-07T10:34:40+00:00
- Post Title: king of Fighters online

This is contained in the nif:
[](http://www.pic-upload.de/view-20647817/ashe_toon.jpg.html)
The mesh at the left is a mess but the one at the right side is o.k.
edit: no, the mess is not a mess. I just displayed the uv map as 3D. Didn't realize it because it's not flat due to a strange coincidence.

If you uploaded the original (unconverted) model I could have a look if Szkaradek's script can be adapted easily.
## Post #6
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2013-09-07T16:52:06+00:00
- Post Title: king of Fighters online

> Reply from shakotay2
>
> This is contained in the nif:

The mesh at the left is a mess but the one at the right side is o.k.
If you uploaded the original (unconverted) model I could have a look if Szkaradek's script can be adapted easily.
I did not convert it, that file is the output of chrrox bms.
## Post #7
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2013-09-08T08:54:19+00:00
- Post Title: king of Fighters online

the mesh did not appear even NifSkope
[http://i.imgur.com/7bFxq1r.jpg](http://i.imgur.com/7bFxq1r.jpg)
where can I get the Szkaradek's script?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-08T09:44:46+00:00
- Post Title: king of Fighters online

I don't know which blender script chrrox was speaking of.

From Szkaradek there's a kingdom-under-fire-heroes-dat-unpacker.
Since I don't have the dat files I guess this unpacker just would unpack nifs from them as chrrox' script does.

(There's also an importer: import-kingdom-under-fire-2011-03-12, but it's for BM and BA files.)

Search for "Kingdom under" in this forums and then for Szkaradek's posts.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-08T10:06:13+00:00
- Post Title: king of Fighters online

mariusz did a blender script for Catherine as well, which i believe was gamebryo. not sure if it was wiped out during the purge or not though. mariusz is a nice guy so if it has been wiped out just pm him and ask him to reup it.
## Post #10
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-09-08T14:31:09+00:00
- Post Title: king of Fighters online

> Reply from howfie
>
> mariusz did a blender script for Catherine as well, which i believe was gamebryo. not sure if it was wiped out during the purge or not though. mariusz is a nice guy so if it has been wiped out just pm him and ask him to reup it.

Are talking about this??

[viewtopic.php?f=16&t=6879&p=57777&hilit ... ine#p57777](http://forum.xentax.com/viewtopic.php?f=16&t=6879&p=57777&hilit=catherine#p57777)
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-08T16:32:47+00:00
- Post Title: king of Fighters online

yeah, thats the only nif script that i remember mariusz writing. he has kind of really slowed down his releases over the last two years.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-09T07:16:56+00:00
- Post Title: king of Fighters online

> Reply from porimac
>
> the mesh did not appear even NifSkopeI think that's because NifSkope doesn't support 'NiMesh' so far.

Wasn't as easy to adapt the script as I thought.
I set nChildren to 0 when it got oversized (what caused the memory error).

Then the mesh addresses below could be logged for ashe_toon.nif.
(You might try to create the mesh I marked as 'o.k.'
#    0xd4df: 
v  0.020748 -0.043436 0.000000
#vn  0.441769 -0.822861 0.357407
...
#    0xd272:
f 1 2 3 
f 4 5 6 
f 7 8 9 
...
Some others seem to be a little bit flat, don't know.)

uv_bool == 1 wasn't met; didn't check, why. 
So the tex data addresses are missing here.
(NiDs means NiDataStream)

facesStart 0x2d6aL
(NiDS018) faceindices  0 132
vert_size is 24, 3 floats position, 3 floats normals
(NiDS118) vertexNos  0 92
vertexStart  0x2e93L
-----------
facesStart 0x20c0L
(NiDS018) faceindices  0 162
(NiDS118) vertexNos  0 112
vertexStart  0x2225L
-----------
facesStart 0x1416L
(NiDS018) faceindices  0 162
(NiDS118) vertexNos  0 112
vertexStart  0x157bL
-----------
facesStart 0x6100L
(NiDS018) faceindices  0 234
(NiDS118) vertexNos  0 190
vertexStart  0x62f5L
-----------
facesStart 0x3eb2L
(NiDS018) faceindices  0 258
(NiDS118) vertexNos  0 202
vertexStart  0x40d7L
-----------
facesStart 0x55ceL
(NiDS018) faceindices  0 132
(NiDS118) vertexNos  0 92
vertexStart  0x56f7L
-----------
facesStart 0x9e4eL
(NiDS018) faceindices  0 234
(NiDS118) vertexNos  0 190
vertexStart  0xa043L
-----------
facesStart 0x7c44L
(NiDS018) faceindices  0 258
(NiDS118) vertexNos  0 202
vertexStart  0x7e69L
-----------
facesStart 0x936eL
(NiDS018) faceindices  0 132
(NiDS118) vertexNos  0 92
vertexStart  0x9497L
-----------
facesStart 0xb434L
(NiDS018) faceindices  0 294
(NiDS118) vertexNos  0 267
vertexStart  0xb6a1L
-----------

(this one seems to be o.k.)
facesStart 0xd272L
(NiDS018) faceindices  0 294
(NiDS118) vertexNos  0 267
vertexStart  0xd4dfL
-----------
facesStart 0xf139L
(NiDS018) faceindices  0 36
(NiDS118) vertexNos  0 24
vertexStart  0xf1a2L
-----------
facesStart 0xf54aL
(NiDS018) faceindices  0 36
(NiDS118) vertexNos  0 24
vertexStart  0xf5b3L
-----------

Another mesh (not logged by the script) is this:
[](http://www.pic-upload.de/view-20669029/ashe_toon__.jpg.html)

vertsStart at 0x2933C, VertsCnt= 1816, vert_size is 48
FaceIndexCnt = 2092*3, which start at 0x254A7
(max faceindexnumber is 1398, so not all verts being "addressed")

edit: ha, just puzzled mesh and uv data.[](http://www.pic-upload.de/view-20669346/ashe_toon_with_uv.jpg.html)
## Post #13
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-09T08:39:31+00:00
- Post Title: king of Fighters online

most vertex semantics can have multiple channels, including position. two or even three uv channels are very common in games. thats probably some kind of effect uv channel. ive seen a game that had that type of uv map recently too (some cell shaded games, one of the sonic ones). 

so there is another uv map probably hiding in there somewhere, and the different channels dont have to be the same data type either (see tomb raider 2013, as an example, diffuse channel is floats and alpha and lightmap channels are signed shorts).
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-09T08:57:30+00:00
- Post Title: king of Fighters online

Didn't not refresh my browser so I couldn't read your hint. Me dumbo just puzzled uv and mesh data: 5 floats, separated as 3 for position and 2 for uv, "as always" but this time is was 2 uvs, 3 for position. But thx for your hint anyway.
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-09T09:04:35+00:00
- Post Title: king of Fighters online

looks like ur doing a good job thus far.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-09T09:50:24+00:00
- Post Title: Re: king of Fighters online

Yep.   But it's the mesh/uv only:
[](http://www.pic-upload.de/view-20669682/ashe_toon_mesh_uv.jpg.html)

wavefront obj
[ashe_toon,obj.zip](http://www.uploadmb.com/dw.php?id=1378719726) (upps, typo: replace ',' by '.')
To activate the normals you'll have to change f 1/1 2/2 3/3  to f 1/1/1 2/2/2 3/3/3. I don't care for normals. (You could also autocreate them in blender for example. )
## Post #17
- Username: Darko
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-02T04:10:05+00:00
- Post Title: Re: king of Fighters online

Noesis NIF support works on this game, with skinning and animations.
## Post #18
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-11-02T08:52:13+00:00
- Post Title: Re: king of Fighters online

> Reply from MrAdults
>
> Noesis NIF support works on this game, with skinning and animations.

Fuck yeah!!! Thanks!!!
## Post #19
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2014-01-07T01:29:50+00:00
- Post Title: Re: king of Fighters online

> Reply from chrrox
>
> Here is a bms for this game.
It is the same format as Kingdom under fire Age of Storm. (Nif models)
Some of these xor keys might be wrong but the ones that matter work and i dint feel like figuring out the others.
http://kof.gg.in.th/home/default.aspx
Code: Select allopen FDDE kof 0
open FDDE kpf 1
get files long 1
math files - 1
putarray 0 0 "\"
goto 0xE 1
for i = 0 < files
get type long 1
get index long 1
savepos nstart 1
findloc nsize string \x00\x00 1
math nsize - nstart
math nsize + 3
getdstring uname nsize 1
set name unicode uname
string name + \
putarray 0 i name
#print "%name%"
next i
get ver long
get start long
get unk1 long
get unk2 long
get asize longlong
get files long
for i = 0 < files
get fldr long
get hash long
savepos nstart
findloc nsize string \x00\x00
math nsize - nstart
math nsize + 3
getdstring uname nsize
set name unicode uname
get offset long
get size long
if size != 0
log MEMORY_FILE offset size
set EXT extension name
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
elseif EXT == "ecs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
elseif EXT == "env"
math key ^ 0x00000003
elseif EXT == "flt"
math key ^ 0x00905A4D
elseif EXT == "fxo"
math key ^ 0xFEFF0901
elseif EXT == "h"
math key ^ 0x74000F0F
elseif EXT == "kcs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
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
goto 0xC MEMORY_FILE
get key long MEMORY_FILE
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
elseif EXT == "scs"
goto 0x10 MEMORY_FILE
get key long MEMORY_FILE
elseif EXT == "tga"
get tmp asize MEMORY_FILE
math tmp - 16
goto tmp MEMORY_FILE
get key long MEMORY_FILE
math key ^ 0x49564555
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
math fldr - 1
getarray name2 0 fldr
string name2 + name
log NAME2 0 SIZE MEMORY_FILE
filexor ""
set key 0
endif
next i
This game is a changed key  after closed beta 
Can Not work bms
[KOFOnline_Setup_20131203a.exe.zip](https://xentaxbackup.github.io/file/6904_KOFOnline_Setup_20131203a.exe.zip)
## Post #20
- Username: deant
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Jul 15, 2013 6:11 pm
- Post datetime: 2014-03-21T05:55:51+00:00
- Post Title: Re: king of Fighters online

the bms works for me, also the noesis NIF plugin. Thanx the guys  that worked on this.
## Post #21
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-25T06:31:26+00:00
- Post Title: Re: king of Fighters online

very nice model, like dress
## Post #22
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2014-03-25T06:59:09+00:00
- Post Title: Re: king of Fighters online

> Reply from oamio
>
> 
This game is a changed key  after closed beta 
Can Not work bms
me too


> Reply from deant
>
> the bms works for me, also the noesis NIF plugin. Thanx the guys  that worked on this.
> Reply from CriticalError
>
> very nice model, like dress
did you use  which version of the game and bms script?
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-25T07:36:31+00:00
- Post Title: Re: king of Fighters online

> Reply from porimac
>
> oamio wrote:
This game is a changed key  after closed beta 
Can Not work bms
me too

deant wrote:the bms works for me, also the noesis NIF plugin. Thanx the guys  that worked on this.CriticalError wrote:very nice model, like dress   
did you use  which version of the game and bms script?key changed, just use model attached into thread to load, so maybe chrox can update it.
## Post #24
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-03-25T09:22:06+00:00
- Post Title: Re: king of Fighters online

Well you can try upload main executable with all modules.
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-03-25T09:49:18+00:00
- Post Title: Re: king of Fighters online

> Reply from Ekey
>
> Well you can try upload main executable with all modules.ok here you have binaries, thanks a lot for try.


[https://www.dropbox.com/s/cvu9bk0f386g9 ... ries%29.7z](https://www.dropbox.com/s/cvu9bk0f386g9l9/KOF%20%28Binaries%29.7z)
