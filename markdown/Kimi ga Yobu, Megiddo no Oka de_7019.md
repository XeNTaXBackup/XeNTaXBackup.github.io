## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T00:46:55+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

[http://www.youtube.com/watch?v=yzknvTocakI](http://www.youtube.com/watch?v=yzknvTocakI)

lol kind of cute, and since I had this game ever since it came out (C74..which is like 6-7 years ago) and just found an extractor (although I wanted to write a bms script myself).

Models aren't particularly high-quality, but whatever  
[Leaf.7z](https://xentaxbackup.github.io/file/4518_Leaf.7z)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T01:59:30+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

quickbms script.

```
#script by chrrox
get temp long
get files long
savepos tbl
comtype PUYO_LZ01
for i = 0 < files
goto tbl
savepos nstart
findloc NameEnd string "\x0"
math NameEnd - nstart
filexor "0xff"
getdstring name NameEnd
filexor ""
set skip 31
math skip - NameEnd
getdstring null skip
get comp byte
get zsize long
math zsize - 4
get offset long
savepos tbl
goto offset
get size long
savepos offset
clog name offset zsize size
next i

```
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-20T02:16:47+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

Hmm how did you figure out the compression type?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-20T02:26:46+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

well i had the extractor source code of asmodean but that was not even really needed.
all i did was find the zipped size and the size then use the compscan2.bat to try all the compressions then look at the files that it spit out to find the correct one.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-28T17:44:28+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

Here is a rough outline of the format. I've identified the vertices, but the faces are still unknown and especially models with multiple meshes are weird.

Here's an outline of a tree



```

char_3 idstring
byte meshType
word unk
word numMesh
word sectionSize

numMesh unk { #lots of unknowns. Total 193 bytes
   float_8 unk
   dword_10 unk
   float unk
   byte unk
   char_40 name
   char_??? texture (maybe)
   #just read bytes till you have 193 for this struct
}

#(seek to sectionSize + 53)

word numCoords
numCoords {
   float_3, vx, vy, vz
}

word numNormals
numNormals {
   float_3, nx, ny, nz
}

word numUV
numUV {
   float_2, tu, tv
}

word unkCount
unkCount {
   float unk
}

#a bunch of floats, followed by faces section
#face indexes coords, normals, and UV, but I haven't figured out the structure for a single face. Maybe material as well, since all mesh names and textures are defined at once.

```
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T01:22:41+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

There are only two types of meshes: skinned and unskinned. They are identified by 0x81 and 0x01 respectively.
The outline above correctly loads vertices for all tested unskinned meshes (even large ones like stages)

Four samples with increasing number of vertices, all less than 10 vertices.

Have not found a way to determine how many faces there are.
[leaf2.7z](https://xentaxbackup.github.io/file/4548_leaf2.7z)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T14:48:20+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

Ok so right now I'm going with the assumption that all faces will have the same structure and the same size.

Here is the leftover section that I didn't fill out from before.

```

byte unk
dword_11 unk (nulls?)
float_4 unk
dword_4 unk (nulls?)
word unk
dword sectionLength (or num shorts)

#then we run into a bunch of shorts.

```


After messing around with the hex looking for a way to re-arrange them nicely,

Here are two of them I attached before

From the tree_02_bli, 4 coords, 4 normals, 4 UV, 1 unk

```
02 00 00 00 03 00 03 00 00 00 00 00 00 00 01 00 02 00 02 00 00 00 02 00 03 00 03 00 00 00

```


monument: 0C coords, 1E normals, 1A UV's, 0D unks

```
00 00 01 00 10 00 03 00 08 00 00 00 00 00 00 00 02 00 01 00 01 00 01 00 07 00 02 00
02 00 02 00 03 00 07 00 02 00 02 00 02 00 02 00 01 00 01 00 01 00 01 00 03 00 03 00
03 00 03 00 0B 00 04 00 04 00 04 00 0A 00 05 00 05 00 05 00 04 00 06 00 06 00 06 00
03 00 0A 00 05 00 05 00 05 00 05 00 07 00 07 00 07 00 04 00 06 00 06 00 06 00 03 00
02 00 08 00 08 00 01 00 04 00 09 00 09 00 06 00 05 00 0A 00 0A 00 07 00 03 00 02 00
08 00 08 00 01 00 05 00 0A 00 0A 00 07 00 01 00 0B 00 0B 00 03 00 03 00 00 00 0C 00
0C 00 08 00 03 00 0D 00 0D 00 09 00 02 00 08 00 08 00 01 00 03 00 03 00 0D 00 0D 00
09 00 04 00 09 00 09 00 06 00 02 00 08 00 08 00 01 00 03 00 09 00 0E 00 0E 00 0A 00 
0B 00 0F 00 0F 00 04 00 03 00 10 00 10 00 09 00 03 00 0B 00 0F 00 0F 00 04 00 04 00
11 00 11 00 06 00 03 00 10 00 10 00 09 00 03 00 06 00 12 00 12 00 0B 00 00 00 13 00
13 00 08 00 08 00 14 00 14 00 00 00 03 00 08 00 14 00 14 00 00 00 00 00 13 00 13 00
08 00 02 00 15 00 15 00 01 00 03 00 06 00 12 00 16 00 0B 00 09 00 0E 00 17 00 0A 00
03 00 10 00 18 00 09 00 03 00 06 00 12 00 16 00 0B 00 03 00 10 00 18 00 09 00 00 00
13 00 19 00 08 00 03 00 0A 00 16 00 1A 00 05 00 07 00 17 00 1B 00 02 00 05 00 18 00
1C 00 07 00 03 00 07 00 17 00 1B 00 02 00 01 00 19 00 1D 00 03 00 05 00 18 00 1C 00 00 00

```


This is assuming that the sectionLength I wrote down is an integer rather than a short (if I considered it a short, it'd have a limit of 65536 shorts, and considering how a single face probably references a bunch of stuff, it may or may not be enough for very large models.

And if it were a short, none of the stuff lines up nicely, so I would stick with this for now.

The extra two 00's at the end I'd probably just chop off, so let's say the integer represents numShorts - 1.

Using the values provided, we can probably look at the maximum index and then use some elimination to guess at what they could be. Presumably they're all triangles so there'd be 9 shorts for coords, normals, and UV, and then another short possibly for that unknown.

But then checking for the location of all the 0B's (max coord index, it shows up in the column that has values greater than it, so perhaps this isn't right.

So then I treat the numShorts as a short, and get

```
02 00 02 00 02 00 03 00 07 00 02 00 02 00 02 00 02 00 01 00 01 00 01 00 01 00 03 00
03 00 03 00 03 00 0B 00 04 00 04 00 04 00 0A 00 05 00 05 00 05 00 04 00 06 00 06 00
06 00 03 00 0A 00 05 00 05 00 05 00 05 00 07 00 07 00 07 00 04 00 06 00 06 00 06 00
03 00 02 00 08 00 08 00 01 00 04 00 09 00 09 00 06 00 05 00 0A 00 0A 00 07 00 03 00
02 00 08 00 08 00 01 00 05 00 0A 00 0A 00 07 00 01 00 0B 00 0B 00 03 00 03 00 00 00
0C 00 0C 00 08 00 03 00 0D 00 0D 00 09 00 02 00 08 00 08 00 01 00 03 00 03 00 0D 00
0D 00 09 00 04 00 09 00 09 00 06 00 02 00 08 00 08 00 01 00 03 00 09 00 0E 00 0E 00
0A 00 0B 00 0F 00 0F 00 04 00 03 00 10 00 10 00 09 00 03 00 0B 00 0F 00 0F 00 04 00
04 00 11 00 11 00 06 00 03 00 10 00 10 00 09 00 03 00 06 00 12 00 12 00 0B 00 00 00
13 00 13 00 08 00 08 00 14 00 14 00 00 00 03 00 08 00 14 00 14 00 00 00 00 00 13 00
13 00 08 00 02 00 15 00 15 00 01 00 03 00 06 00 12 00 16 00 0B 00 09 00 0E 00 17 00
0A 00 03 00 10 00 18 00 09 00 03 00 06 00 12 00 16 00 0B 00 03 00 10 00 18 00 09 00
00 00 13 00 19 00 08 00 03 00 0A 00 16 00 1A 00 05 00 07 00 17 00 1B 00 02 00 05 00
18 00 1C 00 07 00 03 00 07 00 17 00 1B 00 02 00 01 00 19 00 1D 00 03 00 05 00 18 00 1C 00 

```


Which still doesn't work out. Could be possible they reference all of the coords, then the normals, then UV's, though unlikely since you can see the same index showing up multiple times (12, 12, 0B)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T12:54:47+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

position, normal, uv buffer
n position, normal, uv index buffers all indexing into the above.

Would've been really slow if I used rpg interface for this.
## Post #9
- Username: tomatopasta
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Aug 17, 2012 2:49 am
- Post datetime: 2012-10-10T21:00:59+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

I had this game too, could I modify the models in the game and then insert the mods back into the games with this tools? There are a numbers of games I would like to mods them but couldnt find appropriate tools. This threads is the closet solutions to my goals.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-11T01:39:35+00:00
- Post Title: Kimi ga Yobu, Megiddo no Oka de

No this is just a viewer and I barely have the format figured out.
