## Post #1
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-13T08:02:23+00:00
- Post Title: How to use this face data

Im trying to extract models from a game that Noesis supports partially, Im a bit new regarding 3d model reverse engineering so I have no idea how the vertices/normals/faces data is organized on most formats.
On this files the vertices, normals and textures seems to be pretty straight forward, but I'm not having the same luck with the faces.
On a model I have this for example:

(After being exported from Noesis)
I know for a fact that those numbers represent the right vertices order. (I've checked manually)
Noesis saves those faces like this:
f  1/1/1 2/2/2 3/3/3
f  4/4/4 3/3/3 2/2/2
f  4/4/4 2/2/2 5/5/5
f  6/6/6 5/5/5 2/2/2
f  6/6/6 2/2/2 7/7/7
f  8/8/8 7/7/7 2/2/2
From here its easy to figure out how the faces are built,
but when I check those faces data on the file I have:
1 2 3 6 -1 6 2 5 4 -1 4 2 7 8 -1 (0000000100020005FFFF0005000100040003FFFF0003000100060007FFFF) (I've incremented the numbers by 1 so it makes more sense)
And I have no idea how to put that faces data together to export it to an .obj file (for example).

This seems to be a case of triangle strip but I have no idea how that data is organized, can you guys give me a hand?

Thank you in advance
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2012-11-13T22:49:31+00:00
- Post Title: How to use this face data

Could you please post the coordinates of the vertices?
The faces data (1 2 3 6 -1 6 2 5 4 -1 4 2 7 8 -1) only makes sense to me if I reorder the vertices like this:
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-14T12:31:06+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> Im trying to extract models from a game that Noesis supports partially,What's the name of the game? "Secret"?

> but when I check those faces data on the file I have:
>
> 1 2 3 6 -1 6 2 5 4 -1 4 2 7 8 -1 (0000000100020005FFFF0005000100040003FFFF0003000100060007FFFF) (I've incremented the numbers by 1 so it makes more sense)
>
> And I have no idea how to put that faces data together to export it to an .obj file (for example).
Hmm, interpreting FFFF as '1'?

For me it's
0000 0001 0002 0005 FFFF  -> 1 2 3 6 (FFFF)  ; ignoring the FFFFs
0005 0001 0004 0003 FFFF  -> 6 2 5 4 (FFFF)
0003 0001 0006 0007 FFFF  -> 4 2 7 8 (FFFF)

> This seems to be a case of triangle stripYep, should be quads which are split up into faces by Noesis.
But splitting up into faces would mean for the quad 6 5 2 4 -> 6 5 2 and 2 4 6 or something like that.

> Reply from herbert3000
>
> Could you please post the coordinates of the vertices?Strongly recommended; or better:
the whole Noesis output or at least all the faces and the corresponding data block from the file.
## Post #4
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-14T21:00:05+00:00
- Post Title: How to use this face data

> Reply from shakotay2
>
> fierce wrote:Im trying to extract models from a game that Noesis supports partially,What's the name of the game? "Secret"?

but when I check those faces data on the file I have:
1 2 3 6 -1 6 2 5 4 -1 4 2 7 8 -1 (0000000100020005FFFF0005000100040003FFFF0003000100060007FFFF) (I've incremented the numbers by 1 so it makes more sense)
And I have no idea how to put that faces data together to export it to an .obj file (for example).
Hmm, interpreting FFFF as '1'?
For me it's
0000 0001 0002 0005 FFFF  -> 1 2 3 6 (FFFF)  ; ignoring the FFFFs
0005 0001 0004 0003 FFFF  -> 6 2 5 4 (FFFF)
0003 0001 0006 0007 FFFF  -> 4 2 7 8 (FFFF)
This seems to be a case of triangle stripYep, should be quads which are split up into faces by Noesis.
But splitting up into faces would mean for the quad 6 5 2 4 -> 6 5 2 and 2 4 6 or something like that.
herbert3000 wrote:Could you please post the coordinates of the vertices?Strongly recommended; or better:
the whole Noesis output or at least all the faces and the corresponding data block from the file.

Naruto Shippuden: Ultimate Ninja Storm 1.

I was ignoring the FFFF aswell on the beginning, they sounded more like a "separator" to me, although it also might be treated as -1, but has I said, I'm new 

I'll send you the file with one object/mesh, it's from a file available on the online demo, downloadable on the PlayStation website so I think its ok to send it. (I've slapped a NUCC header to it just so it can be read by Noesis).

Vertex data from the file:

1628.789 1.410156 -3.90326
1515.981 -40.51709 -3.903336
1623.279 -0.9135742 88.91228
1448.056 -85.29028 136.3096
1515.981 -40.51709 144.5438
1604.066 -7.868164 124.5788
1377.035 -131.3052 68.12234
1388.034 -124.4492 -3.903328

And you were right herbert3000, I was using the data from the exported file from Noesis that's why I got that vertex order, totally forgot that Noesis swapped their order. I checked the vertex order directly from the file and it matches the one you pasted. Thanks a lot.

It is helpful to know how to handle this data so I can write an extractor/converter or a Noesis script and share it with you.

Thanks a lot for the help guys.

On a side note I already found out what data Noesis isn't reading properly on some files. Its the number of bytes that correspond to each (vertex coord.)+(normal)+(?????)+(texture coord.), not sure what the third one is.
On offset 6E and 6F, there are two int8's that tells that each vertex coord. (6E) and normals+????+texture coord (6F) corresponds to X bytes.
Example on this file:
Offset 6E = 0x06 (6) = Vertex coordinates are represented in 3 floats (6 x 2 bytes?)
Offset 6F = 0x12 (18) = Normals + ???? + Texture coordinates.
This one doesnt make much sense but it works if I change it to 0x10 (16), that would mean 16 bytes:
6 bytes for normals (3 half floats) + 6 bytes for ???? + 4 bytes for texture coordinates (2 half floats)
I'll give you the example for the first vertex:

1: 44CB 993F 3FB4 8000 C079 CF01 B592 3B7F 19B4 3C00 FFFF FFFF 342D 342D
2: 44BD 7F64 C222 1180 C079 D041 B735 3B24 0000 3C00 FFFF FFFF 3800 3800
3: 44CA E8EE BF69 E000 42B1 D316 B588 3B81 0000 3C00 C8C8 C8FF 37C8 2B9E
4: 44B5 01CB C2AA 94A0 4308 4F3F B862 3AB1 170F 3C00 C8C8 C8FF 3BE0 356E

Translated:

1:
v 1628.789 1.410156 -3.90326
vn -0.3481445 0.9370117 0.002785
(3C00 FFFF FFFF) Dont know what this corresponds to
vt 0.2609863 0.2609863
2:
v 1515.981 -40.51709 -3.903336 
vn -0.4504395 0.8925781 0.
(3C00 FFFF FFFF) Dont know what this corresponds to
vt 0.5 0.5
3:
v 1623.279 -0.9135742 88.91228 
vn -0.3457031 0.9379883 0.
(3C00 C8C8 C8FF) Dont know what this corresponds to
vt 0.4863281 0.059509
4:
v 1448.056 -85.29028 136.3096 
vn -0.5478516 0.8364258 0.001723
(3C00 C8C8 C8FF) Dont know what this corresponds to
vt 0.984375 0.3393555

Note: The third value on vertex textures is always 0.000000 after being exported by Noesis and I dont find any 0 values on the data so I'm assuming its not necessary in this case?

Can you guys help me figure out what those 6 bytes correspond to? Is it another normal coord? That would make it have 544 normals instead of 272, no?

Thank you in advance for any help
[si00bobj006_01_1.rar](https://xentaxbackup.github.io/file/5994_si00bobj006_01_1.rar)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-15T01:18:14+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> but has I said, I'm newJust kidding?  As far as I can see your knowledge is somewhat advanced.  


> Can you guys help me figure out what those 6 bytes correspond to? Is it another normal coord?

"Square sum" of components of normals vector should give 1.0
This isn't true for 1.000000 -131008.000000 -131008.000000

v 1628.789307 1.410156 -3.903260
vn -0.348145 0.937012 0.002785
#? 1.000000 -131008.000000 -131008.000000
vt 0.260986 0.260986
v 1515.981445 -40.517090 -3.903336
vn -0.450439 0.892578 0.000031
#? 1.000000 -131008.000000 -131008.000000
vt 0.500000 0.500000
v 1623.279053 -0.913574 88.912277
vn -0.345703 0.937988 0.000031
#? 1.000000 -9.562500 -9.992188
vt 0.486328 0.059509
v 1448.056030 -85.290283 136.309555
vn -0.547852 0.836426 0.001723
#vn 1.000000 -9.562500 -9.992188

There are only few different 6 bytes groups - first word is always 3C 00, last byte always FF.
So I think you can safely ignore them.
You have v, vn, vt and the faces. You don't need more, do you?
## Post #6
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T11:38:23+00:00
- Post Title: How to use this face data

> Reply from shakotay2
>
> fierce wrote:but has I said, I'm new Just kidding?  As far as I can see your knowledge is somewhat advanced.
I'm new to game dev and reverse engineering, been coding for some years though. 

How do you handle the data to get (-131008.000000 -131008.000000) out of (FFFF FFFF)? It's not very important in this case I just want to know because Noesis is saving some vertex textures like that and I would like to understand how its handling the data.

> Reply from shakotay2
>
> There are only few different 6 bytes groups - first word is always 3C 00, last byte always FF.
So I think you can safely ignore them.
You have v, vn, vt and the faces. You don't need more, do you?
You're right, thank you.

Now I only got a few issues left. I figured out almost all of the data on the header file. There seem to be vertex groups there. It's probably of common usage and it makes perfect sense. I just haven't figured out exactly how Noesis handles that data. Here are the vertex groups explained:


PS: I've edited the values of the assignments. They used to be: 06 1C - 06 1C - 06 1C - 06 1C. I've changed them to 06 14 - 06 14 - 06 14 - 06 14 as you can see on the image.

The obvious questions are:
How does the data assignment works on e)?
The 06 seems to be 6 groups of 2 bytes (3 groups of 4 bytes) representing the vertex coordinates.
Why does the second assignment 1C (28) when there are only 20 bytes (in groups of 2 bytes)
Any idea what those 2 groups that I couldn't identify mean?

And example of some vertex data from each group just to help visualize it:




Thank you in advance for any help
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-15T12:26:34+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> How do you handle the data to get (-131008.000000 -131008.000000) out of (FFFF FFFF)?I used this formula: f = ((h&0x8000)<<16) | (((h&0x7c00)+0x1C000)<<13) | ((h&0x03FF)<<13) ;
from the web for the half float (h) to float (f) -conversion. 
The result is 0xc7ffe000 for h = 0xFFFF. Maybe this case is not handled by the formula.
edit: oh, yes, my bad!

> Finally, if the exponent is 31 and the mantissa is not zero:
>
> value = ±NaN (Non a Number)

(To check whether my selfwritten I3E750_to_float() function is ok I used [http://www.h-schmidt.net/FloatConverter/IEEE754.html](http://www.h-schmidt.net/FloatConverter/IEEE754.html). For 0xc7ffe000 this also gives -131008.000000)
## Post #8
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T13:08:11+00:00
- Post Title: How to use this face data

Thank you.

Any idea on those assignments? The 06... part
I'm checking different files at the moment to see if I can find any pattern. So far I only got:
When 06 12 (06 18) is set, there are usually 16 bytes for vn/vt data. (6+6+4)
When 06 1C (06 28) is set, there are usually 20 bytes for vn/vt data. (6+6+4+4 ?)
When 06 22 (06 34) is set, there are usually 20 bytes for vn/vt data. (6+6+4+4 ?)
In all those cases I think the 06 refers to the vertex coord data (3 floats of 4 bytes each).

I think that Noesis only messes up when there are more than 1 or 2 vertex groups.
If I change the second byte to the correct amount of bytes on the vn/vt data I get everything right except the vertex textures.
I'm also trying to write a Noesis plugin to try to extract the data properly but its my first one so it might take a while, and I have no idea how to get the data out properly if I kind find the association of the vn/vt data.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-15T15:44:49+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> I'm also trying to write a Noesis plugin to try to extract the data properlyDoes Noesis use a (somehow fitting) python plugin for Ninja Storm files? (If so it would be imho easier to change this plugin for your needs.)

To my knowledge the vertex group (numbers) are needed for skinning.

Seems you want to perform a complete format analysis?
Academicly this is the correct proceeding.  

But from a practical point of view: does Noesis show up the model with its texture?
What's your final goal? To get the weighted model into Noesis?

I created an obj for blender using these faces
f 1/1/1 2/2/2 3/3/3 6/6/6 
f 6/6/6 2/2/2 5/5/5 4/4/4 
f 4/4/4 2/2/2 7/7/7 8/8/8 
f 9/9/9 10/10/10 11/11/11 14/14/14 
f 14/14/14 10/10/10 13/13/13 12/12/12 
f 12/12/12 10/10/10 15/15/15 16/16/16 
f 17/17/17 18/18/18 19/19/19 22/22/22 
f 22/22/22 18/18/18 21/21/21 20/20/20 
f 20/20/20 18/18/18 23/23/23 24/24/24 
...
and the above v,vn,vts but what was displayed then did not look like a model.
(It's my first time using quads on blender 2.49 wavefront importer so maybe I missed/misunderstood something.)
## Post #10
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T16:24:03+00:00
- Post Title: How to use this face data

> Reply from shakotay2
>
> Does Noesis use a (somehow fitting) python plugin for Ninja Storm files? (If so it would be imho easier to change this plugin for your needs.)
I have no idea where noesis stores the plugin/data to do that extraction, I did a binary search for the headers (NDP3 and XFBIN) and only found data on DLLs, not on python scripts.

> Reply from shakotay2
>
> To my knowledge the vertex group (numbers) are needed for skinning.
Skinning?

> Reply from shakotay2
>
> 
Seems you want to perform a complete format analysis?
Academicly this is the correct proceeding.
I think I already did a complete format analysis, at least I know what almost all of the values mean. If that's what you mean by "complete format analysis"

> Reply from shakotay2
>
> But from a practical point of view: does Noesis show up the model with its texture
It does, although most of the times the texture offset is wrong (Increasing it by 1 solves the problem)

> Reply from shakotay2
>
> What's your final goal? To get the weighted model into Noesis?
To do the exact same thing that Noesis already does with those game files, but working on all files. Like I said before, a lot of the files have wrong offsets. I'm writing a Noesis script to do that, read the xfbin file, display the models correctly, with all the textures correctly assigned. And share it with everyone here of course 

I think I'm already half-way on the script. I got stumped now by not knowing how I'm going to handle the quads data. Noesis doesn't support the insertion of quad data? Do I have to convert them to tris by myself on the script?

> Reply from shakotay2
>
> 
I created an obj for blender using these faces
f 1/1/1 2/2/2 3/3/3 6/6/6
f 6/6/6 2/2/2 5/5/5 4/4/4
f 4/4/4 2/2/2 7/7/7 8/8/8
f 9/9/9 10/10/10 11/11/11 14/14/14
f 14/14/14 10/10/10 13/13/13 12/12/12
f 12/12/12 10/10/10 15/15/15 16/16/16
f 17/17/17 18/18/18 19/19/19 22/22/22
f 22/22/22 18/18/18 21/21/21 20/20/20
f 20/20/20 18/18/18 23/23/23 24/24/24
...
and the above v,vn,vts but what was displayed then did not look like a model.
(It's my first time using quads on blender 2.49 wavefront importer so maybe I missed/misunderstood something.)
If I'm not mistaken those faces are from a different file than the one I pasted the sample v,vn,vts. My bad, sorry.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-15T17:08:32+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> I have no idea where noesis stores the plugin/data to do that extraction, I did a binary search for the headers (NDP3 and XFBIN) and only found data on DLLs, not on python scripts.Ok, then it's indeed up to you to write a plugin.  

> Skinning?The data that "tells" the game engine which vertices (i.e. vertex groups) to move when an NPC raises his arm for example. (As far as I understood you can create vertex groups bei weighted painting for example.)

> [...]at least I know what almost all of the values mean. If that's what you mean by "complete format analysis"More or less. Depends on your final goal. As on your following answer I guess your analysis is complete.

> To do the exact same thing that Noesis already does with those game files, but working on all files.I'm not familiar with Noesis. If it is capable of showing up the skeleton I would take a glance. Meanwhile I'm using blender and Gmax. With Gmax the vertex painting seems to be a little bit easier but I'm just at the beginning (since 1 or two years or so  ).

> And share it with everyone here of courseThat would be great.  

> Noesis doesn't support the insertion of quad data? Do I have to convert them to tris by myself on the script? As I said I'm not familiar with Noesis. There is a guy in this forum, finale00, who could answer this, I'm sure.  

> If I'm not mistaken those faces are from a different file than the one I pasted the sample v,vn,vts. My bad, sorry.Well, I took the faces from si00bobj006_01_1.xfbin, address 0x124 and the v,vn,vts from
0x524. But I chose an estimated verts count of 272; maybe I should increase it. edit: nope

but there are faces with 5 vertices -> quints???

[](http://www.pic-upload.de/view-16910342/NinjaStorm_funny.jpg.html)
## Post #12
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T18:49:13+00:00
- Post Title: How to use this face data

> Reply from shakotay2
>
> Well, I took the faces from si00bobj006_01_1.xfbin, address 0x124 and the v,vn,vts from
0x524. But I chose an estimated verts count of 272; maybe I should increase it. edit: nope

but there are faces with 5 vertices -> quints???

The mesh looks somewhat like that, but you have some messed up verts/faces. All the "separated objects" on that mesh have 8 verts and 6 tris. I dont think there are any faces with 5 vertices. On what address did you see that?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-15T19:40:36+00:00
- Post Title: How to use this face data

> Reply from fierce
>
> I dont think there are any faces with 5 vertices. On what address did you see that?
0x30E and 0x324 for example:

```

000300 00 7F FF FF 00 80 00 81  00 82 00 87 FF FF 00 85  
000310 00 86 00 81 00 84 00 83  FF FF 00 88 00 89 00 8A  
000320 00 8F FF FF 00 8D 00 8E  00 89 00 8C 00 8B FF FF  
000330 00 90 00 91 00 92 00 97  FF FF 00 95 00 96 00 91 
```
## Post #14
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-16T10:21:14+00:00
- Post Title: How to use this face data

> Reply from shakotay2
>
> fierce wrote:I dont think there are any faces with 5 vertices. On what address did you see that?
0x30E and 0x324 for example:
Code: Select allOffset  0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F

000300 00 7F FF FF 00 80 00 81  00 82 00 87 FF FF 00 85  
000310 00 86 00 81 00 84 00 83  FF FF 00 88 00 89 00 8A  
000320 00 8F FF FF 00 8D 00 8E  00 89 00 8C 00 8B FF FF  
000330 00 90 00 91 00 92 00 97  FF FF 00 95 00 96 00 91

I tried to parse the values without ignoring "FFFF", at least not treating it as a separator and the values match. But they dont seem to make sense that way.

Also there seems to be faces with only 3 values.
There seem to be:
7 quints and 7 tris

The VERT/FACE group on that file indicates a number that I'm sure its related to faces: 509
But on the header it says that the face data size is 1024 but I there only seems to be 1018 bytes of face data
(what's left is 0000 0000 on the beginning and 0000 0000 on the end that doesn't seem to fit the face data)
And 1018 makes much more sense than 1024, because 509x2 = 1018.

After exported by Noesis the .obj file has 204 faces.
If 7 quints have 3 faces (tris) each = 21
There are also 7 tris on the faces = 7
And there are 88 quads = 176
21+7+176 = 204.
So I think it kind of makes sense that it has 7 quints, 7 tris and 88 quads.
But why is it formed like that? Is it normal for mesh to be mixed with quints tris and quads?

I wish I had more experience with this.
What is a quint? A pentagon? I'm not very good with geometry either and cant seem to find any info on google.
Also how do quints transform into quads or tris? So I can check if the data matches.

Thank you.

The parsed data (considering FFFF as a separator) just to help:

1: - 1 - 2 - 3 - 6 - FFFF
2: - 6 - 2 - 5 - 4 - FFFF
3: - 4 - 2 - 7 - 8 - FFFF
4: - 9 - 10 - 11 - 14 - FFFF
5: - 14 - 10 - 13 - 12 - FFFF
6: - 12 - 10 - 15 - 16 - FFFF
7: - 17 - 18 - 19 - 22 - FFFF
8: - 22 - 18 - 21 - 20 - FFFF
9: - 20 - 18 - 23 - 24 - FFFF
10: - 25 - 26 - 27 - 30 - FFFF
11: - 30 - 26 - 29 - 28 - FFFF
12: - 28 - 26 - 31 - 32 - FFFF
13: - 33 - 34 - 35 - 38 - FFFF
14: - 38 - 34 - 37 - 36 - FFFF
15: - 36 - 34 - 39 - 40 - FFFF
16: - 41 - 42 - 43 - 46 - FFFF
17: - 46 - 42 - 45 - 44 - FFFF
18: - 44 - 42 - 47 - 48 - FFFF
19: - 49 - 50 - 51 - 54 - FFFF
20: - 54 - 50 - 53 - 52 - FFFF
21: - 52 - 50 - 55 - 56 - FFFF
22: - 57 - 58 - 59 - 62 - FFFF
23: - 62 - 58 - 61 - 60 - FFFF
24: - 60 - 58 - 63 - 64 - FFFF
25: - 65 - 66 - 67 - 70 - FFFF
26: - 70 - 66 - 69 - 68 - FFFF
27: - 68 - 66 - 71 - 72 - FFFF
28: - 73 - 74 - 75 - 78 - FFFF
29: - 78 - 74 - 77 - 76 - FFFF
30: - 76 - 74 - 79 - 80 - FFFF
31: - 81 - 82 - 83 - 86 - FFFF
32: - 86 - 82 - 85 - 84 - FFFF
33: - 84 - 82 - 87 - 88 - FFFF
34: - 89 - 90 - 91 - 94 - FFFF
35: - 94 - 90 - 93 - 92 - FFFF
36: - 92 - 90 - 95 - 96 - FFFF
37: - 97 - 98 - 99 - 102 - FFFF
38: - 102 - 98 - 101 - 100 - FFFF
39: - 100 - 98 - 103 - 104 - FFFF
40: - 105 - 106 - 107 - 110 - FFFF
41: - 110 - 106 - 109 - 108 - FFFF
42: - 108 - 106 - 111 - 112 - FFFF
43: - 113 - 114 - 115 - 118 - FFFF
44: - 118 - 114 - 117 - 116 - FFFF
45: - 116 - 114 - 119 - 120 - FFFF
46: - 121 - 122 - 123 - 126 - FFFF
47: - 126 - 122 - 125 - 124 - FFFF
48: - 124 - 122 - 127 - 128 - FFFF
49: - 129 - 130 - 131 - 136 - FFFF
50: - 134 - 135 - 130 - 133 - 132 - FFFF
51: - 137 - 138 - 139 - 144 - FFFF
52: - 142 - 143 - 138 - 141 - 140 - FFFF
53: - 145 - 146 - 147 - 152 - FFFF
54: - 150 - 151 - 146 - 149 - 148 - FFFF
55: - 153 - 154 - 155 - 160 - FFFF
56: - 158 - 159 - 154 - 157 - 156 - FFFF
57: - 161 - 162 - 163 - 168 - FFFF
58: - 166 - 167 - 162 - 165 - 164 - FFFF
59: - 169 - 170 - 171 - 176 - FFFF
60: - 174 - 175 - 170 - 173 - 172 - FFFF
61: - 177 - 178 - 179 - 184 - FFFF
62: - 182 - 183 - 178 - 181 - 180 - FFFF
63: - 185 - 186 - 187 - 190 - FFFF
64: - 190 - 186 - 189 - 188 - FFFF
65: - 188 - 186 - 191 - 192 - FFFF
66: - 193 - 194 - 195 - 198 - FFFF
67: - 198 - 194 - 197 - 196 - FFFF
68: - 196 - 194 - 199 - 200 - FFFF
69: - 201 - 202 - 203 - 206 - FFFF
70: - 206 - 202 - 205 - 204 - FFFF
71: - 204 - 202 - 207 - 208 - FFFF
72: - 209 - 210 - 211 - 214 - FFFF
73: - 214 - 210 - 213 - 212 - FFFF
74: - 212 - 210 - 215 - 216 - FFFF
75: - 217 - 218 - 219 - 222 - FFFF
76: - 222 - 218 - 221 - 220 - FFFF
77: - 220 - 218 - 223 - 224 - FFFF
78: - 225 - 226 - 227 - 230 - FFFF
79: - 230 - 226 - 229 - 228 - FFFF
80: - 228 - 226 - 231 - 232 - FFFF
81: - 233 - 234 - 235 - 238 - FFFF
82: - 238 - 234 - 237 - 236 - FFFF
83: - 236 - 234 - 239 - 240 - FFFF
84: - 241 - 242 - 243 - 246 - FFFF
85: - 246 - 242 - 245 - 244 - FFFF
86: - 244 - 242 - 247 - 248 - FFFF
87: - 249 - 250 - 251 - 254 - FFFF
88: - 254 - 250 - 253 - 252 - FFFF
89: - 252 - 250 - 255 - 256 - FFFF
90: - 257 - 258 - 259 - 262 - FFFF
91: - 262 - 258 - 261 - 260 - FFFF
92: - 260 - 258 - 263 - 264 - FFFF
93: - 265 - 266 - 267 - 270 - FFFF
94: - 270 - 266 - 269 - 268 - FFFF
95: - 268 - 266 - 271 - 272 - FFFF
96: - 130 - 132 - 136 - FFFF
97: - 138 - 140 - 144 - FFFF
98: - 146 - 148 - 152 - FFFF
99: - 154 - 156 - 160 - FFFF
100: - 162 - 164 - 168 - FFFF
101: - 170 - 172 - 176 - FFFF
102: - 178 - 180 - 184 -
## Post #15
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-16T11:31:52+00:00
- Post Title: How to use this face data

I just found on one file that I have different sizes of face entries:
3, 4, 5, 7, 9, 13, 14
Using my script that treats "FFFF" as a separator I get:
(for the first 2 groups)

Face Offset: 688
Face Size: 191
[1, 2, 0, 3]
[9, 8, 5, 6, 4, 7, 17, 16, 15, 14, 13, 10, 12, 11]
[2, 18, 3, 19]
[21, 22, 20, 23, 38]
[29, 28, 25, 26, 24, 27, 37, 36, 35, 34, 33, 30, 32, 31]
[45, 44, 41, 42, 40, 43, 53, 52, 51, 50, 49, 46, 48, 47]
[96, 97, 94, 95, 92, 93, 90, 91, 89, 86, 88, 87, 98, 99]
[101, 102, 100, 103, 118]
[109, 108, 105, 106, 104, 107, 117, 116, 115, 114, 113, 110, 112, 111]
[62, 61, 55, 56, 54, 57, 58, 64, 65]
[61, 63, 56, 57]
[54, 58, 59, 65, 60, 66, 62]
[59, 60, 54, 55]
[70, 67, 69, 68, 79, 80, 85, 84, 83, 75, 73, 74, 72]
[74, 75, 76, 77, 78, 68, 67]
[75, 84, 77, 80, 68]
[70, 69, 71, 81, 82, 85, 83]
[70, 71, 72, 73]
[69, 79, 81, 85]
[71, 82, 73, 83]
[38, 39, 20]
[57, 63, 64]
[62, 55, 60]
[118, 119, 100]
Face Offset: 1070
Face Size: 169
[1, 2, 0, 3]
[5, 6, 4, 7]
[9, 10, 8, 11]
[13, 14, 12, 15]
[17, 18, 16, 19]
[21, 22, 20, 23]
[25, 26, 24, 27]
[29, 30, 28, 31]
[33, 34, 32, 35]
[37, 38, 36, 39]
[41, 42, 40, 43]
[45, 46, 44, 47]
[49, 50, 48, 51]
[53, 54, 52, 55]
[57, 58, 56, 59]
[61, 62, 60, 63]
[65, 66, 64, 67]
[69, 70, 68, 71]
[73, 74, 72, 75]
[77, 78, 76, 79]
[81, 82, 80, 83]
[85, 86, 84, 87]
[89, 90, 88, 91]
[93, 94, 92, 95]
[97, 98, 96, 99]
[101, 102, 100, 103]
[105, 106, 104, 107]
[109, 110, 108, 111]
[113, 114, 112, 115]
[117, 118, 116, 119]
[121, 122, 120, 123]
[125, 126, 124, 127]
[129, 130, 128, 131]
[133, 134, 132, 135]

Could they be polygons with different sizes or something like that?
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-16T12:48:13+00:00
- Post Title: Re: How to use this face data

> Reply from fierce
>
> What is a quint? A pentagon?Should have set it into quotes.
I was somewhat confused and wanted to make a joke. Sry for that.  

Should look like a pentagon, yes.

To solve this riddle you could look for small simple objects (maybe rectangular, like a plank).
Maybe you are lucky and there is one with a pentagon.
Then get it displayed to see what Noesis makes of it.
And examine its obj output.

I made a test with blender and added a vertice to one of the quads of a cube:

f 1 4 8 5
f 7 8 4 3
f 2 6 7 3 1
f 1 5 6 2
f 5 8 7 6
f 4 1 2 3

After import one quad was split up into 2 tris.

I exported the cube and got this:
f 1 4 8 5
f 7 8 4 3
f 1 5 6 2
f 5 8 7 6
f 4 1 2 3
f 2 6 7
f 3 7 2
f 3 1 2

Hmm, 3 tris? After reimporting this obj 2 quads were split up into 2x2 tris.

edit: ok, forget the above. 
> If 7 quints have 3 faces (tris) each = 21
>
> There are also 7 tris on the faces = 7
>
> And there are 88 quads = 176
>
> 21+7+176 = 204.
Seems there is no riddle; just split up the pentagons like Noesis does.

edit2: forgot, that it's solved via dll.

I had a look at the export_obj.py from blender.
It contains a call quadToTriangle(0).
I don't know whether Noesis uses the same libraries but modifying 
a function like quadTotriangle() to quintToTriangle()  should not be a tremendous task
(though I never did it for myself).
## Post #17
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-16T13:44:59+00:00
- Post Title: Re: How to use this face data

I'm still very fresh to Noesis scripting but I found in a topic on  the forum someone trying to convert quads to tris (or at least use them on Noesis) and he was told to either convert it manually or use a function on Noesis that uses on of thess following parameters: (from _NPReadMe.txt)

	(RPGEO_NONE),
	(RPGEO_POINTS),
	(RPGEO_TRIANGLE),
	(RPGEO_TRIANGLE_STRIP),
	(RPGEO_QUAD), //ABC_DCB
	(RPGEO_POLYGON),
	(RPGEO_TRIANGLE_FAN),
	(RPGEO_QUAD_STRIP),
	(RPGEO_TRIANGLE_STRIP_FLIPPED),
	(NUM_RPGEO_TYPES),
	(RPGEO_QUAD_ABC_BCD),
	(RPGEO_QUAD_ABC_ACD),
	(RPGEO_QUAD_ABC_DCA),

RPGEO_QUAD should work for quads and I'm guessing that RPGEO_POLYGON would work on those faces with 3, 4, 5, 7, 9, 13, 14 verts. Otherwise It would be a bit hard for me to convert them manually.
I just finished the data parsing on my script and I'm going to start testing those functions now.
Might be a PITA as there doesnt seem to be any decent documents about Noesis scripting.
If you dont mind checking I posted on another topic one question that I have regarding that and you might be able to know:
[viewtopic.php?f=18&t=9877](http://forum.xentax.com/viewtopic.php?f=18&t=9877)

Thank you
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-16T15:48:36+00:00
- Post Title: Re: How to use this face data

> Reply from fierce
>
> I posted on another topic one question that I have regarding that

I think you should post your request in this thread:
[viewtopic.php?f=33&t=4582&start=1245](http://forum.xentax.com/viewtopic.php?f=33&t=4582&start=1245)

edit did you successfully test commitTriangles with RPGEO_POLYGON?
(I don't have a clue about Noesis.)

edit2:

> as there doesnt seem to be any decent documents about Noesis scripting.
Looks to me like an one-man-project, so don't expect to much.

I think, Rich Whitehouse does an astonishing job with Noesis.

Ngons (= polygons with more than 4 vertices I think) were introduced with blender 2.63 this year afaik.
(Ok, they used fake ngons before afaik) but there are more than one guy involved.
## Post #19
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-16T18:19:15+00:00
- Post Title: Re: How to use this face data

I've sent a message to Mr.Adults but I think I'll post on that topic aswell if I get no results by "trial and error".
Been testing a lot of stuff on the previous hours. I'm getting some results. So far I managed to get a model that looks a bit like the real model present on that file but it there are still some normals that arent showing up correctly, but that might be an issue with my scripts, I'm trying to solve that atm.

I used:
rapi.rpgCommitTriangles(ftriangles, noesis.RPGEODATA_USHORT, totalVerts, noesis.RPGEO_TRIANGLE_STRIP, 0)
(Not sure is the one that works though, cause I don't have all the normals yet so I'm not sure if the faces are correct)

> Reply from shakotay2
>
> 
as there doesnt seem to be any decent documents about Noesis scripting.
Looks to me like an one-man-project, so don't expect to much.

I think, Rich Whitehouse does an astonishing job with Noesis.
I understand. I didn't mean to say that in a pejorative way, he has done a lot and I'm thankful for that.

I'll get back to this post as soon as I get it done. Almost
## Post #20
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-16T19:07:04+00:00
- Post Title: Re: How to use this face data

Mr. Adults told me that he used RPGEO_TRIANGLE_STRIP for that game. Although I only read his message I've tried every single option xD
This is the result I get:
(My script on the left and the actual model on the right)


I'm not sure but it looks like the only problem now is with some verts. I'm going to check them manually now.
## Post #21
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-17T00:55:33+00:00
- Post Title: Re: How to use this face data

Finally got it to work!   

I was trying to "draw" all the data from all the vertex groups, and I needed to do it individually on each group cause the "numIdx" was different on each one.

I'm gonna start testing on all the other files of the game and I'll release the script as soon as its working properly.

Thank you for all the help
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-17T12:59:37+00:00
- Post Title: Re: How to use this face data

> Reply from fierce
>
> Finally got it to work!Impressive progress you make!  
Looking forward to your final solution...
## Post #23
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-17T14:30:52+00:00
- Post Title: Re: How to use this face data

Tried on a few files and everything seems to be working, now my only problem is with the textures.
That is a field that I have almost no knowledge at all. I've created a topic so someone might help me with that:
[viewtopic.php?f=18&t=9883](http://forum.xentax.com/viewtopic.php?f=18&t=9883)
## Post #24
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-18T15:11:01+00:00
- Post Title: Re: How to use this face data

I think those grey textures are just a texture map or something like that, instead of an actual texture.
I'm parsing the packed file data now to be able to extract the textures and assign them to see if everything matches.
Only got the file size, offsets and names so far, but I'll probably get it done by the end of the day.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2012-11-18T16:46:24+00:00
- Post Title: Re: How to use this face data

> Reply from fierce
>
> but I'll probably get it done by the end of the day.I'm sure you'll get it.  

I struggled for some hours with Model_Bayo_LoadTextures() (from bayonetta plugin source). I got a sample pl001a.dat from the inet, the contained model loads fine but the texture is sort of stripped.

My debug output says:
.\bayotex 000
WARNING: Unknown texture format 8389120.
.\bayotex 001
WARNING: Unknown texture format 8388736.
.\bayotex 002
WARNING: Unknown texture format 16777728.
.\bayotex 003
WARNING: Unknown texture format 33555456.

I really prefer blender where I have my material file with diffuse, normal and maybe specular map names
and the textures as 3 dds (or tga) files.

With most xbox games all textures seem to be packed into a wtb file which I succeeded to convert to xpr but
the unbundler outputs all were 0 byte sized files.

So I really would appreciate if you could give a short overview on the "how to" after you've managed to put at least a diffuse texture on your Ninja Storm model.
## Post #26
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-18T16:56:18+00:00
- Post Title: Re: How to use this face data

That problem you mention seems like an offset issue, as the script is probably getting 8389120, (...), 33555456 instead of the texture header.

There are a lot of data that I'm ignoring, the materials are most likely part of that data, but as I said previously, I have no idea how most 3d formats work, so I have no idea how the materials are saved (my guess is that its a set of bools and floats?).
I do intend to extract everything I can from this game's files but I'll probably leave that to last.
## Post #27
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-11-18T21:13:45+00:00
- Post Title: Re: How to use this face data

Yeah, it's all strips. Nothing unusual about the index data. It's mostly the same as SC4/Tekken 6/etc. there, except there are different vertex strides and/or offsets sometimes. I didn't look into that, I just halfassed support for it into the Noesis SC4 loader by making some exceptions for the header markers.

Its material data is also similar, but different enough to be a pain in the ass. SC4, Tekken 6, Time Crisis, and pretty much every other game using a variant of this core format seems to have significant differences in the material data, and the material data itself seems to be in a commandlist-like format where you need to know every "opcode" and its sometimes-variable size to successfully iterate it and get what you want out. (such as diffuse texture indices) I've made some progress there for SC4, Tekken 6 (and TTT2, which is apparently similar to T6), and TC:RS, but I didn't look at Naruto at all there either. And my other implementations aren't perfect either, that's why material assignment for Tekken is often screwy.
## Post #28
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-18T21:23:33+00:00
- Post Title: Re: How to use this face data

Thanks a lot for the help.

As I said before, I'll do my best trying to parse all the data for this game on my script with all your help.
I'll upload it as soon as it's ready and hope some of it can help you increase the support for those games you mentioned.
## Post #29
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-20T17:51:15+00:00
- Post Title: Re: How to use this face data

Been going for hours and hours trying to parse the data between the models and the textures (that is probably the materials). Made so much calculations and got no where.
I think I'm starting to figure out how the data is organized though. Its pretty weird though. It's organized in blocks, but some blocks are just "empty":

First is an int that tells me how much blocks are empty on the beginning:
0000 0006
0000000B 0000000C 0000000D 0000000E 0000000F 00000010 (11,12,13,14,15,16) 
Then the first block:
0000002A (42, size of the block or offset) 00000011 (block number, 17) 0079 1200 (this is the same on all blocks)
0000 0000 0000 0000 0000 0000 (some floats I think, their all 0 on the first block with data)
8000 0000 0000 0000 8000 0000 3F80 0000 3F80 0000 3F80 0000 3F80 0000 0000 (this is the same on all blocks)
Second block:
0000002A (42, size of the block or offset) 00000012 (block number, 18) 0079 1200 (this is the same on all blocks) 44AA 12D0 C699 0BAC 4481 9BA8 (some floats I think)
8000 0000 0000 0000 8000 0000 3F80 0000 3F80 0000 3F80 0000 3F80 0000 0000 (this is the same on all blocks)
Then it gets weird. I get an offset or size:
0000 004E (78) but it doesn't seem to make any sense cause there are only this bytes of data:
0000 0002 (block number, 2 (probably)) 0079 1200 0000 0000 (this is the same on all blocks) then the rest of the data that is usually on all blocks is missing
0006 (then I get this number that refers to 6 empty blocks) 0101 FFFF 0000 0000 0000 0000 0000 (some data that I dont know what is is)
0000 0011 0000 0012 0000 0013 0000 0014 0000 0015 0000 0016 (the 6 empty blocks)
0004 (4 empty blocks) 203A 0000 0000 (unknown data) 
0000 0001 0000 0007 0000 0009 0000 000A (the 4 empty blocks)
0000 3A20 7F7F FFFF FFFF (some data that I dunno what it is)
Then another block with data, this time the size/offset seems right:
0000 002C (44 size of the block or offset) 0000 0003 (block number, 3) 0079 1200  (this is the same on all blocks) 0001 00AB 0000 0000 0000 0001 (some floats I think) 00000000000000003F8000003F800000 (the rest of the data on that block)
0002 (2 empty blocks) 1E08 0000 0037 (unknown data) 
0000 0017 0000 0018 (the 2 empty blocks)
Another block with data:
0000 002C (44, this size/offset seems to be higher than it can be (41)) 0000 0004 (block number, 4) 0079 1200 (this is the same on all blocks) 0001 00AB 0000 0000 0000 0001 (some floats I think) 0000 0000 0000 0000 3F80 0000 3F80 0000 (the rest of the data on that block)
0002 (2 empty blocks) 1E08 0000 0037
0000 0019 000 00018 (the 2 empty blocks)
and it goes on...
There also seems to be a pattern there using the group numbers: (e = empty)
11e,12e,13e,14e,15e,16e
17,18,19,20,21,22,
2,1e?,17e,18e,19e,20e,21e,22e,1e,7e,9e,10e,
3,23e,24e,
4,25e,24e,
5,26e,24e,6,27e,24e,
That would make more sense if there was group 1 followed by some empty groups aswell.
This is just for one file though, I'm gonna check the other files and see what I can come up with
