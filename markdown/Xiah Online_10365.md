## Post #1
- Username: MasterChen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 13, 2013 12:52 am
- Post datetime: 2013-04-26T08:19:38+00:00
- Post Title: Xiah Online

Hello people! 

I have been struggling with .xmp files which are supposed to be a map file for game called xiah and cant seem
to get any further on my own so i have decided to come here and ask help. 

Here is some of my research 'notes' i have written down about the format:

```
int Amount;
-loop Amount-
int unknown;
int unknown;
int address;
int length;
-loop-

after all "meshes"
loop each color or something 

AFTER COLOURS LOOP TILE TEXTURES FOR GROUND
(0xCE && 0xCF, GROUND TILE TEXTURES)

AFTER GROUND LOTS OF ZEROES
---

LATER LOAD DECALS?
0005a4b4h: 33 00 03 00 00 00 00 00 00 00 EF 00 00 00 00 00 ; 3.........ï.....
0005a4c4h: 00 00 5A 00 00 00 00 00 00 00 3E 01 00 00 01 00 ; ..Z.......>.....
0005a4d4h: 00 00 05 00 00 00 03 00 00 00 00 00             ; ............

MAP DECALS:
AMOUNT:33 00 // MAYBE TOTAL AMOUNT OF DECALS?
-LOOP
POSITION X: 03 00 00 00
POSITION Z: 00 00 00 00
POSITION Y: EF 00 00 00
ROTATE X: 00 00 00 00
ROTATE Y: 5A 00 00 00
ROTATE Z: 00 00 00 00
UNKNOWN: 3E 01 00 00 // MAYBE VISUAL ID?
UNKNOWN: 01 00 00 00 // MAYBE SIDE MODEL
UNKNOWN: 05 00 00 00 // MAYBE TOP MODEL?
-LOOP-

0x39 = 57, THE TILE HEIGHT POINT? at least for edges.. (maybe height map?)

```


I have added the .xmp file and few parsed decals on attachments if someone wants to give a try.
[XMP.rar](https://xentaxbackup.github.io/file/6354_XMP.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-26T10:15:32+00:00
- Post Title: Xiah Online

Found 256 submeshes of same size. There are two different types (see pic):
[](http://www.pic-upload.de/view-19091264/BimilRoom.jpg.html)
edit: ok, plus 8 corner elements and 3 mirrored/rotated wall elements, 13 different types
(Didn't search for more submeshes; left half a million of bytes not analysed...)

Format is as this (first submesh):
# M:\test\BimilRoom.xmp
g submesh_1

#  81 verts, 384 face Indices
#      3e: # 1.      3e:
v  0.000000 0.000000 0.000000
# FF FF FF FF  ? 0.000000 0.000000 0.000000
# 0.000000 
v  4.000000 0.000000 0.000000
# FF FF FF FF  ? 0.015625 0.000000 0.500000
# 0.000000 
v  8.000000 0.000000 0.000000
# FF FF FF FF  ? 0.031250 0.000000 1.000000
# 0.000000 
v  12.000000 0.000000 0.000000
# FF FF FF FF  ? 0.046875 0.000000 1.500000
# 0.000000 
v  16.000000 0.000000 0.000000
# FF FF FF FF  ? 0.062500 0.000000 2.000000
# 0.000000 
v  20.000000 0.000000 0.000000
# FF FF FF FF  ? 0.078125 0.000000 2.500000
# 0.000000 
...
v  20.000000 57.000000 -28.000000
# FF FF FF FF  ? 0.078125 0.109375 2.500000
# 3.500000 
v  28.000000 57.000000 -24.000000
# FF FF FF FF  ? 0.109375 0.093750 3.500000
# 3.000000 
v  24.000000 57.000000 -24.000000
# FF FF FF FF  ? 0.093750 0.093750 3.000000
# 3.000000 
v  20.000000 57.000000 -24.000000
# FF FF FF FF  ? 0.078125 0.093750 2.500000
# 3.000000 
v  20.000000 57.000000 -20.000000
# FF FF FF FF  ? 0.078125 0.078125 2.500000
# 2.500000 
v  24.000000 57.000000 -20.000000
# FF FF FF FF  ? 0.093750 0.078125 3.000000
# 2.500000 
v  28.000000 57.000000 -20.000000
# FF FF FF FF  ? 0.109375 0.078125 3.500000
# 2.500000 
v  28.000000 57.000000 -16.000000
# FF FF FF FF  ? 0.109375 0.062500 3.500000
# 2.000000 

# 2.     0x0a5e:
f 1 2 58 
f 1 58 10 
f 2 3 57 
f 5 6 54 
f 6 7 53 
f 7 8 52 
f 8 9 11 
f 8 11 52 
f 10 51 12 
f 52 11 13 
f 12 45 14 
f 46 13 15 
f 14 43 16 
f 64 15 17 
f 16 41 18 
f 18 39 20 
f 80 19 21 
...
f 73 72 31 
f 75 23 72 
f 74 73 30 
f 76 72 73 
f 77 73 74 
f 68 77 74 
f 76 75 72 
f 80 21 75 
f 77 76 73 
f 79 75 76 
f 78 76 77 
f 69 78 77 
f 78 79 76 
f 71 79 78 
f 79 80 75 
f 70 80 79 
f 81 19 80 
f 70 81 80 
f 81 17 19 
f 64 17 81 
#   0x0d5e: 
# face index min/max: 1 / 81

Tex coords might be the 2 floats after FF FF FF FF
