## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-17T17:00:11+00:00
- Post Title: [PS3] Knight Contract .hxt models

Could someone help me to figure out [PS3]Knights Contract .hxt format? I see face indices and something like a vertex buffer. Though I can't parse them, I'm missing something. Need some tips from people experienced in format reversing. 
[http://www.mediafire.com/?r3dla86uicf7gsm](http://www.mediafire.com/?r3dla86uicf7gsm)
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-18T16:11:50+00:00
- Post Title: [PS3] Knight Contract .hxt models

Figure out vertices , should work fine now. Still have issue with face indices, can't find face count to parse them right.
[test.jpg](https://xentaxbackup.github.io/file/6338_test.jpg)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-18T19:34:15+00:00
- Post Title: [PS3] Knight Contract .hxt models

> Reply from zaramot
>
> Still have issue with face indices, can't find face count to parse them right.For chr053.hxt this should be vertex cnt (511) and face indices count (1318) for a submesh (hand and forearm):

```

027330   01 00 00 00 08 <00 00 01  FF> 00 00 00 12 <00 00 05
027340   26> 00 00
```


Max face index is 511 so this seems to be ok, but1318/3= 439.33 leaves a reminder and the mesh appears full of holes.
...
f 511 504 508 
f 505 505 501 
f 501 502 510 
  2d533: 
# face index min/max: 1 / 511
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-18T19:52:30+00:00
- Post Title: [PS3] Knight Contract .hxt models

Yes, you're totally right. Mesh full of holes, it's the same problem I've had, thought indices count is bad.
[holes.jpg](https://xentaxbackup.github.io/file/6339_holes.jpg)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-18T20:41:11+00:00
- Post Title: [PS3] Knight Contract .hxt models

I thought the faces might be quads instead of triangles but that's not the solution.

So I would recommend to examine a small and simple mesh (a box for example) to get a clue what's going on here.
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-19T07:14:13+00:00
- Post Title: [PS3] Knight Contract .hxt models

Yes, I already checked small model, it's a character's blade model the one on the first pic. It appears each model has second face indices count at the end of the file? It's always -2, for example first one is 1060 - second one 1058, 2082/2080. Here's blade model.

EDIT: count 1158 fits nicely since 1158/3=386. Still sword mesh full of holes. Any ideas?
[chr176.rar](https://xentaxbackup.github.io/file/6341_chr176.rar)
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-19T10:48:45+00:00
- Post Title: [PS3] Knight Contract .hxt models

did you try triangle strips?
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-19T12:06:43+00:00
- Post Title: [PS3] Knight Contract .hxt models

No I didn't, since I'm new in formats reversing, could you please, give an example of maxscript?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-19T13:03:39+00:00
- Post Title: [PS3] Knight Contract .hxt models

@chrrox: good idea! thx. 

> Reply from zaramot
>
> No I didn't, since I'm new in formats reversing, could you please, give an example of maxscript?I'm not a maxscripter but here's the idea:
After reading the face indices 1 2 3 4 5 6 7 8 9 for example
build 7 faces such as
f 1 2 3
f 2 3 4
f 3 4 5
...
f 7 8 9

This is the result:
[](http://www.pic-upload.de/view-19008633/KnightContract_sword.jpg.html)

Still little errors (?). Maybe groups of ten face indices to be read?
Or use reverse order of face indices for every 2nd face?
Maybe chrrox will know...

These are the faces I got for chr176.hxt:
# 0x7ecf:

f 1 2 3
f 2 3 3
f 3 3 4
f 3 4 4
f 4 4 4   // hmm, confusing
f 4 4 5
f 4 5 6
## Post #10
- Username: shakotay2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-19T22:45:40+00:00
- Post Title: [PS3] Knight Contract .hxt models

something like this

```
fseek f FaceIndexOffset#seek_set
FaceDirection = 1
f1 = ReadBEword f + 1   --read face indices, games are start form 0, but Max start from 1
f2 = ReadBEword f  + 1   --so we add 1 to each index
for i = 3 to FaceBytes do (    --already readf 2 verts, so start from 3	
f3 = ReadBEword f  + 1
FaceDirection *= -1	
if (f3 != f1) AND (f3 != f2) then (   --if not idential verts, create face
if FaceDirection > 0 then append Face_array [f1,f2,f3]     --base on face direction to create face
else append Face_array [f1,f3,f2]
)
f1 = f2     --shift the verts
f2 = f3
)
fseek f FaceIndexTableStart#seek_set
)
```
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-04-20T07:25:26+00:00
- Post Title: [PS3] Knight Contract .hxt models

Perfect!   thx, chrrox.
The sword faces look now like this:

#    0x1763:
f 1 3 2
f 3 4 3
f 4 4 5
f 4 6 5
f 5 6 7
f 7 6 8
f 8 6 3
f 6 9 3
f 3 9 2
f 9 10 2
f 2 10 11
f 10 12 11
f 11 12 13
f 13 12 14
f ... ... ...

edit: chr053.hxt
[](http://www.pic-upload.de/view-19017669/birdman.jpg.html)
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-04-20T07:58:21+00:00
- Post Title: [PS3] Knight Contract .hxt models

Thank you very much chrrox  .  It helped with the sword mesh, will try with other models.

EDIT: Works fine, guess I found where are UV's.
[model_good.jpg](https://xentaxbackup.github.io/file/6346_model_good.jpg)
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-15T11:02:50+00:00
- Post Title: [PS3] Knight Contract .hxt models

about hxt format: 

1.beginning 

```
int32 - imageCount
skip 20 bytes
int32 - charCount
string = get charCount bytes
skip 108 bytes

repeat*imageCount {
	int32 - charCount
	string = get charCount bytes
	skip 44 bytes
	int32 - count
	skip count bytes
	skip 168 bytes
	}
	
#section .ddm	
string = get 4 bytes
skip 164 bytes
int32 - unk
int32 - type of data for skeletons (get from python script)
int32 - boneCount
start - get current offset
boneNameList = get boneCount bytes #numbers as  bone names
parentNameList = get boneCount bytes #numbers as bone parent names

here was problem with ending this section and i tried absolute padding (from 0 offset), but without success.
Finally i used relative padding (from start offset) and it works. In this case pad = 8 bytes.

```


I have problems with skeleton ,bone map for vertex groups, vertex items.
Here is script for importing textured meshes (not all are supported) without skinning and skeleton.
It requires Blender 249 and Python 26.
How use:
1. run Blender249.blend
2. in Blender Text Window press alt+p and select hxt file

For unpacking models from archive: [viewtopic.php?f=10&t=6949](http://forum.xentax.com/viewtopic.php?f=10&t=6949)
For unpacking textures:  [viewtopic.php?f=18&t=7026](http://forum.xentax.com/viewtopic.php?f=18&t=7026)
[Blender249[KnightsContract][PS3][hxt][2015-02-15].zip](https://xentaxbackup.github.io/file/8669_Blender249[KnightsContract][PS3][hxt][2015-02-15].zip)
## Post #14
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-02-16T10:53:25+00:00
- Post Title: [PS3] Knight Contract .hxt models

Hi Szkaradek123，Thank you very much for the great work, the script runs very well.
[model.jpg](https://xentaxbackup.github.io/file/8687_model.jpg)
