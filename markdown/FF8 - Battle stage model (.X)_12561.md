## Post #1
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-01-31T19:37:45+00:00
- Post Title: FF8 - Battle stage model (.X)

I recently began researching this .X file from FF8, but I met some problems I can't figure out. I read all TIM, TMD specifications, searched for headers, everything...

First, I am attaching sample file. Here's what I found:

This is Textured model, with hardcoded texture.
Texture is uncompressed .TIM, that can be found at header 
```
10 00 00 00 09
```
, in a0stg105 case it's 0x8070.
File contains camera animation, that starts probably at 0x5d4, with: 
```
02 00 08 00 20
```
. 
Next is probably vertices, that looks like TMD, has similiar ASCII pattern, but there's no header, and I can't find any software that can read RAW bytes in TMD way. By HEX'ing I found, that there're three objects there. Every new object starts with specific:

```
01 00 00 00 08 00 00...
```
, also I found pattern, that has increasing ID, has 24bytes and ends with 0x2c.
Sample:

```
20 00 35 00 21 00 36 00 54 9c 80 3c 54 68 b2 00 7e 9c 7e 68 80 80 80 2c
```

that is probably:
0x0 (1B) - Stands for ID, with every verticle it raises up by 1.
0x2 (1B) - Same as above (?)
0x3 (17B) - Not yet researched
0x21 (3B) - It does repeat in every single object
0x24 (1B) - End of object.

Also, there's second pattern, that doesn't match above, but also deletes triangles. Sample 16 bytes:

```
4e 0c 4e 0c   00 00 4e 0c   68 10 00 00   4e 0c 99 ef
```

See? It looks like a place, where it does connects everything into faces, but this also makes no sense, because:
null'ying every 4 byte deletes one face, it's okay, but changing this to some other variables like aa aa 0c 0c makes the triangle go high up the world. This could be TMD, but even with documentation, I just can't find anything that make it work.
Please help!
Thread on Qhimm:
[http://forums.qhimm.com/index.php?topic ... 223521#new](http://forums.qhimm.com/index.php?topic=15906.msg223521#new)
[a0stg105.7z](https://xentaxbackup.github.io/file/8577_a0stg105.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-01T08:11:40+00:00
- Post Title: FF8 - Battle stage model (.X)

the places where you assume objects to start reveal some patterns:



a0stg105.JPG (65.08 KiB) Viewed 350 times



First I thought of vertex blocks with a size of 24 bytes and face indices contained, but they are to regular:
(0x51EE: cnt= 20)
51f4: 1 21 2 22 
520c: 2 22 3 23 
5224: 3 23 4 24 
523c: 4 24 5 25 
5254: 5 25 6 26 
526c: 6 26 7 27 
5284: 7 27 8 28 
529c: 8 28 9 29 
52b4: 9 29 10 30 
52cc: 10 30 11 31 
52e4: 11 31 12 32 
52fc: 12 32 13 33 
5314: 13 33 14 34 
532c: 14 34 15 35 
5344: 15 35 16 36 
535c: 16 36 17 37 
5374: 17 37 18 38 
538c: 18 38 19 39 
53a4: 19 39 20 40 
53bc: 20 40 1 21 
53d4: 2 2 121 6832 
----------------------
(0x56B2: cnt=100)
56b8: 1 21 2 22 
56d0: 2 22 3 23 
56e8: 3 23 4 24 
5700: 4 24 5 25 
5718: 5 25 6 26 
5730: 6 26 7 27 
5748: 7 27 8 28 
5760: 8 28 9 29 
5778: 9 29 10 30 
5790: 10 30 11 31 
57a8: 11 31 12 32 
57c0: 12 32 13 33 
57d8: 13 33 14 34 
57f0: 14 34 15 35 
5808: 15 35 16 36 
5820: 16 36 17 37 
5838: 17 37 18 38 
5850: 18 38 19 39 
5868: 19 39 20 40 
5880: 20 40 1 21 
5898: 21 41 22 42 
58b0: 22 42 23 43 
...
5fa0: 96 116 97 117 
5fb8: 97 117 98 118 
5fd0: 98 118 99 119 
5fe8: 99 119 100 120 
6000: 100 120 81 101 
-------------------------
## Post #3
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-01T15:19:25+00:00
- Post Title: FF8 - Battle stage model (.X)

That's probably it. Basically, this stage model has three objects:

1.Ground (simple plane)
2.Spherical mesh with some details (Either sky or BG)
3.As above

So, use of Hex2OBJ was an excellent one. I of course modified the parameters, so I got no flying vertices beneath the first object which is a plane, so I got . I read your tutorial, but I couldn't find so called "alphabet" thing. In tutorial there were clear "byte 00 byte 00 byte 00", here I'm having . This is totally other "alphabet" thing. Could you help me some more with this?




Also, there's a stage, that contains only plane for ground, and spherical sky. This one contains UV layout in texture, maybe this could be useful. 
. There are numbers on the right from 00 to FF. 
First object, the ground:

Thank you very much shakotay2.
[a0stg160.zip](https://xentaxbackup.github.io/file/8580_a0stg160.zip)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-01T20:01:07+00:00
- Post Title: FF8 - Battle stage model (.X)

> Reply from MaKiPL
>
> This is totally other "alphabet" thing. Could you help me some more with this?
face indices as a continous scrambled alphabet is the simple version.
They also maybe appear like this:

```
Offset 00 01 02 03 04 05 06 07  08 09 0A 0B 0C 0D 0E 0F
```
..007500 00 00 00 00 00 00 40 00  00 00 00 00 00 00 01 00
..007510 03 00 02 00 01 CF 00 3D  01 BC B3 00 20 CF 20 BC
..007520 80 80 80 2C 03 00 02 00  05 00 04 00 20 CF 00 3D
..007530 20 BC B3 00 40 CF 40 BC  80 80 80 2C 05 00 04 00
..007540 07 00 06 00 40 CF 00 3D  40 BC B3 00 5F CF 5F BC

But the max face index (80) is greater than the count of this block (64) so they may be just continous indices, not faces indices.
7ac4: 62 78 63 79 
7adc: 63 79 64 80 
7af4: 64 80 49 65

(Sadly the vertices of this block seem to concentrate on 4 little spots only.)


> There are numbers on the right from 00 to FF.which tool did you use?
In Texturefinder it looks like this:



a0stg160.JPG (93.74 KiB) Viewed 320 times
## Post #5
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-01T21:05:07+00:00
- Post Title: FF8 - Battle stage model (.X)

It's a TIM texture, so TextureFinder will make the texture look with wrong colors. Either way is to use TIMviewer, or cut bytes to end from header 
```
10 00 00 00 08
```
, and save as .TIM, then open in graphic software that is capable in opening this. 

Here: [http://www.zophar.net/utilities/psxutil/tim-viewer.html](http://www.zophar.net/utilities/psxutil/tim-viewer.html)

I pointed that file, because it has that ground, that is just a plane, but has this simple UV for it, so the UV for this plane is just... a plane.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-01T21:23:23+00:00
- Post Title: FF8 - Battle stage model (.X)

thx, I have that viewer on my harddrive, even a newer version (v.104b) but seems I've forgotten it
(rare to no use because I don't have a console  ).
## Post #7
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-02T11:07:09+00:00
- Post Title: FF8 - Battle stage model (.X)

I cut the objects from the header 
```
01 00 00 00 08
```
 to three files. Then tried to work on those objects individually. How long is one vertex? I took , 
divided length by 6, and I got 152, which looks exactly like a stage vertices. . The additional vertices by the main square are as I can see in-game some extension to ground. The model unfortunately contains UV, this harders face searching. In tutorial, you're dividing it by 2, maybe this face has more size than WORD.



EDIT:

Looks like I found it, but this giant numbers inside are making the max vertex index go great also.
I can do manually "Cut" those things, but does this do the thing?



Notes:
* I'm at school ATM, so I leave here some notes:
0xC - 152
01 - 01 ~3D-5? ...
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-02T19:40:16+00:00
- Post Title: FF8 - Battle stage model (.X)

> Reply from MaKiPL
>
> In tutorial, you're dividing it by 2, maybe this face has more size than WORD.yes, "face indices" (not "faces") can be DWORDs (or even bytes in some rare cases).

> Looks like I found it, but this giant numbers inside are making the max vertex index go great also.
>
> I can do manually "Cut" those things, but does this do the thing?well, it's not too easy with face indices in this format.
What you mention starts from 0x8F4 and I don't think they are face indices (too regular and the max face index is 137, which should equal the vertex count)
8f4: 1 2 10 11 
90c: 2 3 11 12 
924: 3 4 12 13 
93c: 4 5 13 14 
954: 5 6 14 15 
96c: 6 7 15 16 
984: 7 8 16 17 
99c: 8 9 17 18 
...
126c: 132 123 131 126 
1284: 124 125 127 128 
129c: 131 126 130 129 
# max fInd= 137

Also it's 4 indices (quads, which hex2obj doesn't handle) instead of 3 for triangles. (the column after the address column could contain just a simple counter but after 107 it steps to 137)


What looks more like face indices (but I'm not sure) is this:

3a4: 1 138 2 
3b8: 2 138 139 
3cc: 2 139 3 
3e0: 3 139 4 
3f4: 4 139 140 
408: 4 140 5 
41c: 5 140 6 
430: 6 140 141 
444: 6 141 7 
458: 7 141 8 
46c: 8 141 142 
480: 8 142 9 
494: 18 9 143 
4a8: 18 143 135 
4bc: 27 18 135 
4d0: 27 135 36 
4e4: 36 135 133 
4f8: 45 36 133 
50c: 45 133 54 
520: 54 133 132 
534: 63 54 132 
548: 72 63 132 
55c: 72 132 131 
570: 81 72 131 
584: 90 81 131 
598: 90 131 130 
5ac: 99 90 130 
5c0: 108 99 130 
5d4: 108 130 144 
5e8: 117 108 144 
5fc: 116 117 145 
610: 116 145 146 
624: 115 116 146 
638: 114 115 146 
64c: 114 146 147 
660: 113 114 147 
674: 112 113 147 
688: 112 147 148 
69c: 111 112 148 
6b0: 110 111 148 
6c4: 110 148 149 
6d8: 109 110 149 
6ec: 109 150 100 
700: 100 150 128 
714: 100 128 91 
728: 91 128 82 
73c: 82 128 125 
750: 82 125 73 
764: 73 125 64 
778: 64 125 122 
78c: 64 122 55 
7a0: 55 122 46 
7b4: 46 122 119 
7c8: 46 119 37 
7dc: 37 119 28 
7f0: 28 119 136 
804: 28 136 19 
818: 19 136 10 
82c: 10 136 151 
840: 10 151 1 
854: 137 151 136 
868: 151 138 1 
87c: 9 142 143 
890: 135 143 134 
8a4: 130 129 144 
8b8: 117 144 145 
8cc: 150 109 149 
8e0: 127 128 150 

max face index is 151

Together with your vertices from 0x0C it looks like this:



TestMesh.JPG (74.02 KiB) Viewed 274 times



but it's just the result of combining regular vertices with regular indices.
Many vertices are not connected. So I don't think it's the solution.
## Post #9
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-03T22:11:36+00:00
- Post Title: FF8 - Battle stage model (.X)

Found a vertices length byte location. Tested in on many levels.

This is another stage, where I was testing this way:



Structure:
After 
```
01 00 00 00 08
```
 header, there's from 20 to even 160 on some maps of data, to get to vertices length byte. See here:


Yellow selected bytes, are starting from that header, to get to length byte, we have to find the nearest 01 00 01 00 ** 00 STRT.
Where ** is DEC(uint) containing vertices amount. Vertices start two bytes after that (5c on screen, in red square). Then either:

a) ByteLength*6=Bytes of vertices data. (They're ending with set of 00, and probably another length appears, this time two bytes, as this section is way higher than 255. 
b) Just put offset of ByteLengthOffset+2, and in count in HEX2OBJ - DEC of ByteOffset.



Also, the starting section of the file is having probably scene animation data. In every static stage, it's header is always the same, up to 500+ bytes and more. I took a look at levels, where there is animation like flowing lava, then the header is totally different. 

Oh, I just want to write thanks to you, because without you we wouldn't get so far with this. Thank you shakotay2!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-04T11:34:30+00:00
- Post Title: FF8 - Battle stage model (.X)

> Reply from MaKiPL
>
> Oh, I just want to write thanks to you, because without you we wouldn't get so far with this. Thank you shakotay2!you're welcome.
Always nice to see people making senseful use of hex2obj (seems there are not too many  ).

For the face indices you might have a look at a smaller object like a chest or a book
(though I don't know whether the indices in there follow the same rules as with level meshes).
## Post #11
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-07T19:40:34+00:00
- Post Title: FF8 - Battle stage model (.X)

Okay. Made it. 

All levels use quads. The only thing I could rip with HEX2OBJ is:

Do you know any software working with quads, that can help me get over this? 
Also UV in this format is hardcoded in 20 bytes quad info. Where one quad has:

8 bytes of data, for 2 uint's each point. 
12 bytes for texture ID's and etc, even with brightness.

I could use a plugin source for Noesis's FF8 .DAT open.
It has pre-made texture coord's reader, the same stage models are using, and also some .DAT files contained quads, that Noesis is just doing fine with them.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-07T21:22:30+00:00
- Post Title: FF8 - Battle stage model (.X)

PMed you.
(try a face index offset of ( quadinfo_size - 8 ) in the editbox left to the checkbox)

for me it looks like this:



a0stg105_.JPG (75.2 KiB) Viewed 211 times



The holes might be a problem of face culling which Noesis and other 3D programs can handle.
(maybe the mesh_viewer hex2obj uses has an option for it)

edit: well, smaller holes but mesh overlap with 'face cull' in Noesis when loading the
hex2obj-created test.obj. Seems there's still too less face indices.
## Post #13
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-07T23:05:32+00:00
- Post Title: FF8 - Battle stage model (.X)

same here

That format uses also mixed way - has a info for triangles, and quads. But for stages the triangles length byte is set to 00 00, so only quads are present. Hmph. After vertices data, there's 00's padding, and just after that is XX YY, where:
xx- 20 bytes (triangle)
yy- 24 bytes (quad)

I'll search on old topics about FF8 animated objects, they also contained quads and I think I remember similiar problem we do have here.
## Post #14
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-08T10:46:18+00:00
- Post Title: FF8 - Battle stage model (.X)

User on Qhimm posted link to a old topic regarding other file reverse. They also had the same problem, here's the link for synopsis on this "half triangle invisible " thing: [http://everything2.com/user/TheMoog/wri ... ngle+strip](http://everything2.com/user/TheMoog/writeups/triangle+strip)
This model is complete, just needs some post-processing for tweaking this half triangle.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-08T11:01:28+00:00
- Post Title: FF8 - Battle stage model (.X)

Not sure whether this is a "triangle strip" problem, since we've quads here.

Maybe there's a simple solution:
have a look at the upper left part of the attached picture:



quadMe.JPG (48.52 KiB) Viewed 190 times



The "bad" quad is f 4 3 6 5

# 0x732a: verts= 80
v 108.265625 23.437500 44.847656 
v 108.265625 0.000000 44.847656 
v 82.863281 23.437500 82.863281 
v 82.863281 0.000000 82.863281 
v 44.847656 23.437500 108.265625 
v 44.847656 0.000000 108.265625 

f 1 2 4 3 
f 4 3 6 5 

This is the position of vertices in space.

5   3   1
6   4   2

connecting 4,3,6,5,4 reveals a "crossing" of vertices

so the 2nd quad should be
f 4 3 5 6

So for all even quads the face indice 3 and 4 to be swapped?
Maybe it's as simple as that.

Well, "even" simpler: all quads to be handled as such.
But other problems arise, too complex for me (view lower part of pic)

How to decide which quads to be swapped and which not, that's the question.
## Post #16
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-08T20:10:44+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

I worked some in 3DS Max on this, and found out, that converting from quads to triangles has to be in 

ABD
ACD

So quad:

```
f 394 395 416 417
```

will be:

```
f 394 416 417
```


After this, the "crossing" looks finally as a square. Didn't test changing quad order though, does this make a difference?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-08T20:52:25+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

> Reply from MaKiPL
>
> I worked some in 3DS Max on this, and found out, that converting from quads to triangles has to be in 

ABD
ACDsadly (concerning the holes) it doesn't work for my example, with
quads
f 1 2 4 3 
f 4 3 6 5 
f 6 5 8 7 
...

changed to
f 1 2 3
f 1 4 3

f 4 3 5
f 4 6 5

f 6 5 7
f 6 8 7

...

> After this, the "crossing" looks finally as a square.yep, but doesn't prevent holes, does it?



blender_quads2tris_still holes.JPG (34.99 KiB) Viewed 106 times


but the solution maybe simple: just change the winding order of every second triangle face.
ABD
DCA

edit: ah, great. Seems we've made it! (though there's some ugly part with my example)

but not sure whether my first solution: quad ABCD -> ABDC (for all quads) isn't the better one.
Will have to check a more complex sample to decide it.


> Didn't test changing quad order though, does this make a difference?
quad order? It's tris now, so you mean "tris order"?

order of triangle faces is irrelevant (as long as you leave vertices' order unchanged)

edit: where "order" is meant such as this:
f 1 2 3
f 4 5 6

different order:

f 4 5 6
f 1 2 3

(If you change the order of the faceindices such as f 3 2 1 it will change the winding, of course.)
## Post #18
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-09T16:04:34+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

> Reply from shakotay2
>
> 
quad order? It's tris now, so you mean "tris order"?

I meant this ABCD > ABDC you already pointed.  And I'm happy to say it works with other meshes, here example:

I only changed one sub-mesh, and the quad now looks like a quad. 

EDIT: Copied all sub-mesh'es info to Excel, and replaced columns, then reimported. After that I've seen a clear, 100% ready quad model.  


Thank You shakotay2, job here is done.
## Post #19
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-02-17T14:17:03+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

How do I calculate vt from byte?
I do have bytes:
U1, V1
U2, V2
U3, V3
U4, V4

Solution I came with is:
float u = U1/256
float v = V1/256
string str = String.format("vt {0}, {1}", u, f);
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-17T19:57:30+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

choosing a divider that causes the results to be in the range of {0.0..1.0} should work for most cases
(sure vtx, vty are bytes?)
## Post #21
- Username: MaKiPL
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Sep 13, 2014 9:05 pm
- Post datetime: 2015-03-21T18:43:57+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

Just to update.

.X battle stage is documented here:
[http://wiki.qhimm.com/view/FF8/FileFormat_X](http://wiki.qhimm.com/view/FF8/FileFormat_X)

100% of geometry. I wrote the thanks to you shakotay2 at the beginning of the wiki page. 

I'm currently coding the FF8 .X to OBJ converter. Keep updated at:
[http://forums.qhimm.com/index.php?topic=15906.100](http://forums.qhimm.com/index.php?topic=15906.100)

@up - yup, UV coords were bytes, with TPage + texture height/width. My code example:

```
Float U = (float)U_Byte / (float)(TIM_Texture_Width * 2) + ((float)Texture_Page/(TIM_Texture_Width * 2));
```


Thanks again shakotay2.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-21T19:22:47+00:00
- Post Title: Re: FF8 - Battle stage model (.X)

> Reply from MaKiPL
>
> Just to update.

.X battle stage is documented here:
http://wiki.qhimm.com/view/FF8/FileFormat_X

100% of geometry.Great work!  

> I wrote the thanks to you shakotay2 at the beginning of the wiki page.Thx. (First time that I'm mentioned on a wiki's page, if I'm not mistaken  )
