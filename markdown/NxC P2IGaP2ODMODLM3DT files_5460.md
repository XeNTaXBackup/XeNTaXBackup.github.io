## Post #1
- Username: nneonneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 24, 2010 7:29 am
- Post datetime: 2010-11-25T08:10:02+00:00
- Post Title: NxC P2IGa/P2OD/MODL/M3DT files?

I'm currently working on a game called [Namco x Capcom](http://en.wikipedia.org/wiki/Namco_%C3%97_Capcom), trying to parse out as much stuff as I can. I've mainly been working on the game logic (conveniently supplied as bytecode for a game logic interpreter), but I also stumbled upon the game's 3D models (for terrain, scenery, etc. since the game is a 3D engine with 2D sprites overlaid).

I'm mainly experienced with code-like formats, and haven't had a great deal of experience dealing with 3D formats. Has anyone ever seen these formats before? I suspect that they are once-off formats specifically for this game (as is the case with a lot of game formats), but I thought I might ask around first 

There's also about 4 different archive systems used here (FARC, TARC, WDPK, UPAK), and several of the formats contain subfiles as part of their structure (e.g. MODL files contain M3DT subfiles, which in turn contain P2OD sub-subfiles). Luckily, nothing's compressed or encrypted, and most of the formats were pretty straightforward to extract from.

Anyway, attached is a sample P2OD file, which seems to describe vertices. The format is as follows:

```

byte[4] signature = 'P2OD'
byte[4] version = '\x80\0\0\0'
int32 numobjs
byte[20] null = '\0'*20

Object Header (immediately follows regular header):
byte[8] unk (ffff0100ffff0000, 0000ffff02000000, 0000ffffffff0000 have been seen here)
int32 fileoffset [First object header refers to the P2OD itself, so it has an offset of 0; the rest refer to actual objects]
float32[17] unk = {0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0}

Object (starts at fileoffset):
int32 blockcount
int32 unk[3] = {8, 0, 0}
float32 minx, miny, minz, unk, maxx, maxy, maxz, unk
Block blocks[blockcount]

Block:
int32 groupcount
int32 type
int32 unk [A small integer; might be related to an external resource like a texture?]
float32[2] unk = {0.0, 1.0}
byte[76] unk = '\0'*76
Group groups[groupcount]

Group if type == 0x18006:
int32 count
int32 unk[3] = {124, 0, 0}
(float32 row1[4])[count]
(float32 row2[4])[count]
(float32 row3[4])[count]

Group if type == 0x18007:
int32 count
int32 unk[3] = {124, 0, 0}
(float32 row1[4])[count]
(float32 row2[4])[count]
(float32 row3[4])[count]
(float32 row4[4])[count]

```


Here's some parsed values:

```
  values (-1300.0, -300.0, -2300.0, 1.0, 1300.0, 156.06452941894531, 1700.0, 1.0)
 block 0
  unk 0
  array 0 count 15 type 124
   entry 0
      1300.0000, -100.0000, -208.1415,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.4770,    1.0000,    0.0000
   entry 1
      1300.0000,   50.0000, -208.1400,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.4770,    1.0000,    0.0000
   entry 2
      1300.0000, -100.0000, -400.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.5250,    1.0000,    0.0000
   entry 3
      1300.0000,    0.0000, -400.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.5250,    1.0000,    0.0000
   entry 4
      1300.0000, -100.0000, -600.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.5750,    1.0000,    0.0000
   entry 5
      1300.0000,    0.0000, -600.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.5750,    1.0000,    0.0000
   entry 6
      1300.0000, -100.0000, -800.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.6250,    1.0000,    0.0000
   entry 7
      1300.0000,    0.0000, -800.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.6250,    1.0000,    0.0000
   entry 8
      1300.0000, -100.0000,-1000.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.6750,    1.0000,    0.0000
   entry 9
      1300.0000,    0.0000,-1000.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.6750,    1.0000,    0.0000
   entry 10
      1300.0000, -100.0000,-1200.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.7250,    1.0000,    0.0000
   entry 11
      1300.0000,    0.0000,-1200.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.7250,    1.0000,    0.0000
   entry 12
      1300.0000,    0.0000,-1400.1083,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.7750,    1.0000,    0.0000
   entry 13
      1300.0000,  300.0000,-1200.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.7250,    1.0000,    0.0000
   entry 14
      1300.0000,  300.0000,-1400.0000,    0.0000
        47.0000,   47.0000,   47.0000,  128.0000
         1.0000,    0.7750,    1.0000,    0.0000
```


I think it defines some portion of terrain, but I haven't been able to reliably reconstruct the terrain based on the data in the file. Maybe I'm just missing something obvious.

Thoughts?
[0020.zip](https://xentaxbackup.github.io/file/3640_0020.zip)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-11-25T21:42:22+00:00
- Post Title: NxC P2IGa/P2OD/MODL/M3DT files?

those entry things look like an array for materials.. diffuse colour, or other shader settings... cause model data won't be that consistent, the numbers will all be different from each other
## Post #3
- Username: nneonneo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 24, 2010 7:29 am
- Post datetime: 2010-11-29T21:37:40+00:00
- Post Title: NxC P2IGa/P2OD/MODL/M3DT files?

I've mostly figured it out. The first set of numbers in each entry are vertices, and the third set are UV coordinates; the textures are specified by a small container format (the M3DT files). Vertices are specified as if they were drawn with GL_TRIANGLES_STRIP; each array (group) defines a separate strip, and each block defines a separate object. Each block has a material assigned to it, and every array (group) in that block refers to the block's material.

There's still a few things I don't know: what the second set of numbers represents, and what several of the other files do. I found that the vertex coordinates specified in the P2OD need to be displaced by a second set of coordinates specified in another file before they can be imported onto the base map (object 0).

I wrote up a dirty hack script that parses map files and generates Wavefront .OBJ and .MTL files which can be imported into Blender or any similar tool. I now have the full 3D maps for every stage of NxC 

At this point, I've gotten most of the game files decoded. There's still a few outliers, but they are far less common, and are probably for dealing with special cases (and I haven't gotten to those levels in the game yet!).
