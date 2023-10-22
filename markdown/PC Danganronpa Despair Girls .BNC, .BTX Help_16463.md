## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-06-28T03:14:59+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

I was wondering if anyone could create a script for these files if possible.
Heres some samples of "pc00":
[https://mega.nz/#!i4NXwKDI!6-TYJWoJeOxG ... oUwUuYAKJY](https://mega.nz/#!i4NXwKDI!6-TYJWoJeOxGPi6juFRinsKQSMYGOcqj5oUwUuYAKJY)
Ones with _anm are animation I believe, and .BTX are the textures.
The .bnc each have a header with "PSCa" and the BTX files seem to have something close to a DDS header.
## Post #2
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2017-06-29T01:44:06+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

Luckily I was able to rip some textures with a profiler, because BTX files are DDS with repeating bytes trimmed.
[https://mega.nz/#!7MtjFIiD!DtLV0KJQaSy_ ... yVsQIDyppc](https://mega.nz/#!7MtjFIiD!DtLV0KJQaSy_R_smzP8ClD3N8jgDmGeGbyVsQIDyppc) This has a btx and a complete DDS that I ripped. 
There is something going on with these that I don't fully understand, hopefully these will help someone smarter than me.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-29T02:56:42+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from anime663
>
> I was wondering if anyone could create a script for these filesnoone can create a script before the format is known. So the first request would be for getting the format.
Anyways, the first submesh only (as always):



pl00_ac_face-bnc.jpg (189.92 KiB) Viewed 815 times
## Post #4
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-15T06:15:31+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

Has any progress been made on figuring these files out? I`d like to rip the models myself sometime
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-28T20:02:01+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

the format appears to be rather simple so I don't know why you don't care for yourself since I showed how to get the first submesh?

There's some ugly extra faces, though, but I don't have the time to care for.



pl00_ac_face_2SMs.jpg (134.87 KiB) Viewed 709 times


search for 0000 0100 0200 gives 5 finds where the first one is not valid, I guess.

So these are starting points of face indices blocks (fi count):
0x83C50  (2307) 1st submesh
0x84e56  (1941) 2nd SM
0x85d80   (294)
0x85fcc -0x862FC (408)

assumed start address of vertices for 2nd SM:
0x333e8 +2143x72 (dec.) = 0x58EA0

H2O file for 2nd SM:

0x84E56 1941
Vb1
72 24
0x58EA0 1778
020000
0x0 255
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-19T16:00:45+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

Has anyone made some progress with this?

I tried giving it a go, using shakotay's example, and got the meshes like this :


First one is okay, but the second one seems to have some vertices in wrong coordinates. I believe the data is read correctly, so I don't know why it ends up like that. I mean every vertex has a block size of 72 bytes with no exception, so it isn't like the program is skipping to wrong offset or anything.

The third and the fourth meshes seem really wrong too but I want to focus on the second one first. Any help or opinion would be appreciated.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-19T18:29:13+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from akderebur
>
> First one is okay, but the second one seems to have some vertices in wrong coordinates.I don't care for those models, just for sake of the superfluous faces. For one model I found it simple to just erase them manually:



pl00_ac_face.jpg (112.84 KiB) Viewed 611 times


but there's a good chance to solve it via code, simply replace all vertices like v 0.000000 -0.090487 0.003321
(x coord==0.0) by v 0.0 0.0 0.0
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-19T19:48:47+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from shakotay2
>
> 
but there's a good chance to solve it via code, simply replace all vertices like v 0.000000 -0.090487 0.003321
(x coord==0.0) by v 0.0 0.0 0.0

I tried that, but it ended up like this :


Also I have tried getting the first mesh from "pl00_bodyD1.bnc" and got something completely broken. It might be that I have the offsets wrong but I think I got them right. UV seems fine.


Can you take a look when you have the time? Do you think the problem is just related to the faces? It looks too broken to me to just be faces, but I am not sure.

Thank you very much for your help.
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-20T00:53:39+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

Hmm I have found out something interesting. In the "pl00_ac_face.bnc" there is this byte set right after the uvs in every vertex block : FE FE FE FF. For the first mesh vertices I have noticed that it is always followed by lots 0s. For other meshes it is occasionally followed by "00 00 80 3F", "00 00 00 40",  "00 00 40 40". So 1, 2, 3 in float but I don't know what it should represent. Basically it is a value other than 0. 

So for those vertices that don't have "00 00 00 00" right after "FE FE FE FF", I set the vertex coordinates to 0 0 0. It turned out much better. It seems to have just affected those vertices that were positioned away from the face.


I am starting to think that those values after the "FE FE FE FF" are related to reading the vertices correctly. I mean it couldn't be a coincidence that the wrong/out of place vertices are being affected.

Edit: 
It actually looks like bone indices and weights. After "FE FE FE FF" there are 4 floats (why floats?) for bone indices, and 4 floats for weights.

So there isn't like any extra offset or something to fix the vertex positions. I can just conclude that the vertices that have influences other than bone0 appear in wrong position. I have no idea how to fix that though. Do you think we need the skeleton?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-20T18:52:06+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from akderebur
>
> So for those vertices that don't have "00 00 00 00" right after "FE FE FE FF", I set the vertex coordinates to 0 0 0. It turned out much better.So is it fixed or not?  

> I can just conclude that the vertices that have influences other than bone0 appear in wrong position. I have no idea how to fix that though.Is there something special with bone ids or weights for those extra vertices which need to be set to  v 0.0 0.0 0.0

> Do you think we need the skeleton?So you mean face bones? Dunno.
I think it could help if you made a list with vertices, bone ids and weights with the extra vertices marked.

such as
v 0.004502 -0.058517 0.011331 0 1 2 3 0.2 03 0.25 0.25
v 0.000000 -0.045317 0.013346 1 2 3 4 0.2 03 0.2 0.3  -> set to v 0.0 0.0 0.0
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-20T19:43:21+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from shakotay2
>
> So is it fixed or not?
No, I couldn't fix it completely. Setting the vertices to v0 0 0 just kinda hides them, it isn't the right coordinate.

> Reply from shakotay2
>
> Is there something special with bone ids or weights for those extra vertices which need to be set to  v 0.0 0.0 0.0
Are you sure those are extra vertices?. It seems to me like they are normal vertices but they just have different bones influencing them, and for some reason they have weird coordinates. Only vertices that have correct coordinates are the ones that are just influenced by bone0 (all of the first mesh and some vertices of the other meshes).

With models that have more bones you can see that it gets worse. For example these are the meshes from the body model "pl00_bodyD1.bnc" : 


The vertices are all over the places. I haven't seen a proper mesh there. Most of the vertices have 3-4 bones influencing them in this model.

From what I see if the vertices are influenced by bone0  only (which I think has the coordinate 0 0 0, so it isn't really doing anything), the mesh loads fine, meaning all of the vertices are in correct coordinates. If there are other bones, the coordinates become wrong. I don't want to say wrong but maybe they are relative to the bones that influence them? I don't know if something like that is reasonable/possible in a model format.

I will try making a list like you suggested. Btw if you have the time can you try getting a mesh from one of the body models? I want to make sure that I am not reading the wrong data. Like maybe the first mesh from "pl00_bodyD1.bnc".

Also thank you again for looking into this.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-20T21:47:18+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from akderebur
>
> Like maybe the first mesh from "pl00_bodyD1.bnc".yep, looks weird. Chosing 500 face indices only makes it look better but I don't know where to proceed with the next vertices to get a proper (sub) mesh.

It's strange that pl00_weapon00 doesn't have such problems, maybe because it has no bones:



bodyD1.jpg (116.24 KiB) Viewed 529 times
## Post #13
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-20T22:14:43+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from shakotay2
>
> 
It's strange that pl00_weapon00 doesn't have such problems, maybe because it has no bones:
Exactly. There is no problem with no bones/no skinning. As soon as there are some bones and weights it gets messy.

I may be completely wrong here but I think it might be similar to md5mesh. Like how vertex positions are stored based on the joint/bone space. So you would need to calculate the actual vertex position using the bone transformations and weight influences. I think the models like that weapon load fine because all vertices are connected to a single root bone placed at the origin(0, 0, 0). That would mean the joint space is same as the world space, so the vertex positions are fine.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-03-25T19:49:27+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

I think I found some good information here:
[https://stackoverflow.com/questions/108 ... -smd-model](https://stackoverflow.com/questions/10864453/importing-3d-skeletal-animations-from-smd-model)
Especially the part Vertex transformation.

(Not sure whether this will solve the problem here but there's a good chance, I guess.)
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-25T21:03:17+00:00
- Post Title: PC Danganronpa Despair Girls .BNC, .BTX Help

That is somewhat what I had in mind, but maybe in reverse. Notice that in that link you posted it says all the vertex positions are in model space and need to be converted to bone space? I think in danganronpa files all of the vertices are already in bone space, and need to be converted to model space. I mean if they were in model space the meshes should have showed up fine just with vertex positions.

Anyway I think it is worth a try, but we need the skeleton. I have found these offsets, that might give some info.

Body - pl00_bodyD1
Offset (hex): 20     - 4 bytes - 125 (value) - I think it is the bone count
Offset (hex): 0CD0 - bone count * 16 bytes - So 16 bytes for each bone, I am thinking 4 floats. Last float is always 1. I suspect first 3 floats to be local bone position (relative to parent). I am not sure though.

For the face model offsets are 20 and 140.

There should also be something like a parent table that shows which bone is the parent of a specific bone. For the body model I am suspecting the data is either at A4 or 8A0, but it doesn't seem to match up with the bone count exactly.

I am not sure about these at all. It might be that there are matrices for bone transformations somewhere, or maybe blocks with both a position vector and quaternion for rotation. It is just that I haven't seen anything like that, so I though those floats might be the bone positions. Also they were near the bone names  I will look further into it when I have the time.
## Post #16
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2018-06-12T03:19:09+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

Dead thread but:

The actual bone count is after 50 53 43 61 (PSCa). This can be compared to the parenting if this appears incorrect (further discussed below).

Parenting table starts at offset A0 where the rule is:

Parent 00 FF FF Child 00 FF FF (armature of 2 bones) (from now I will use P to refer to parent, and C for child)
When there is more then one child they are listed as: P 00 FF FF C 00 C 00 FF FF
FF FF signifies a child and the end of the armature. 
When there is more then 1 bone listed between 2 sets of FF FF, the first bone chain is finished first. As far as I can tell, the chain only stops when the next number is not the previous with one added.

With pl00_ac_face the rig is:
00 00 05 00 FF FF 01 00 FF FF 02 00 03 00 04 00 FF FF
With the names at offset 1F0: AC_FACE_NULL.HEAD.FACE_EYE_R.FACE_EYE_L.FACE_JAW.(No Group)
Bones are given IDs to be used in parenting based off the order, thus giving us

AC_FACE_NULL 00
HEAD               01
FACE_EYE_R     02
FACE_EYE_L     03
FACE_JAW        04
(No Group)       05

Fitting well with the bone count, 06. If the bone count is too big to count, find the 2nd bone in parenting (No group) and add one for Null.
Thus we have
AC_FACE_NULL 00 (No Group) 00 FF FF HEAD 00 FF FF FACE_EYE_R 00 FACE_EYE_L 00 FACE_JAW 00 FF FF



The parenting of the face FaceRig.png (33.6 KiB) Viewed 329 times


(please note that I made a mistake, (No group) should have no parents)

I am less sure about the positions because of the set of floats followed by 00 00 80 3F, that may have some relation to the distorted meshes, but the bone positions can be found at offset CC for the face (as floats).
This gives us the positions 0,0,0 for both AC_FACE_NULL and HEAD, and others for the eyes and jaw. (No group) appears not to have a position though, and if you compare the positions to the ones found at offset 140, you'll see only the head to jaw positions are listed, so its possible that *only* the previously mentioned vertex groups have bones.

In any case, we now have the bone names, parenting and positions. Unfortunately, the faces mesh has bones quite close together (the eyes in rest position are inside the head), however with the body the rig is a lot more clear.
(I can't seem to add another image, refer to my next post)
## Post #17
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2018-06-12T03:54:14+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

Here is the bodies rig (partial)



The bodies rig until the 3rd Thumb bone BodyRigPart.png (143.38 KiB) Viewed 329 times


(Only a section has been remade as I don't know how to code)
In relation to the possible bone co-ords (floats followed by 00 00 80 3F) 00 00 80 3F may be a scale, as within the animation files there are (if treated as a float) there are slightly different values at times. 
If we consider the bone position to be the floats before 00 00 80 3F then we get some pretty interesting rigs, and they might have a connection to the distortion. (Image in next post)
## Post #18
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2018-06-12T03:58:59+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

First set of floats vs 2nd set with mesh. File name: pl00_hair.bnc AhogeRigs.png (123.31 KiB) Viewed 329 times


This is all that I have been able to determine. Sorry for the spam, and I hope that this will provide useful to someone more capable then me!
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-02T14:58:40+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

Decided to return to this format after some time. I was able to get proper vertex positions. There is something like a bone palette near the beginning with bone ids and vertex positions. These positions are essentially same as the positions inside the vertex blocks, but they are fewer. Since the vertex count doesn't match the vertex blocks, I was also unable to use the indices. Those indices match the vertex blocks. So only point clouds for starters :



Thanks to Argg for his findings on the skeleton. Saved me some time.

I can probably make a tool for this format after a bit more research. Need to handle the indices first. I have a feeling that bone weights will be problematic too, but we'll see. I should say this is a weird format in this day and age. Spike Chunsoft is either doing something right, or something awfully wrong
## Post #20
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2018-11-08T12:56:29+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

Indices should be fine. If float 0 is considered to be the bone HEAD (0x3340C) (pl00_ac_face.bnc) and we consider there to be maximum 4 floats influencing a vertex at a time, the first bone weight is float 1. That leaves padding (length 4) between vertices.

Only the different positions for the vertices are listed at 0x3E0, and the count for the amount of different positions is at 0x240, followed by the face count at 0x242. Both are length 2.

Nice to see other people posting here! Good luck on the tool.
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-08T15:50:56+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from Argg
>
> and we consider there to be maximum 4 floats influencing a vertex at a time, the first bone weight is float 1.
I have tried loading those as weights, but they didn't come out great. Weird bone indices for some of the vertices. I have instead found out another weight table, starting at 0x3D90.

> Reply from Argg
>
> Only the different positions for the vertices are listed at 0x3E0
They are not different positions. Same positions as the ones inside the vertex blocks. They just have a bone index at the start, which you need to transform the vertices by to get the proper world/model space vertex positions.

I am more or less done with the tool. Still I recently decided to collect my works in a single tool. I will probably release this as a module for that tool I am planning to release soon.

UPDATE

Model tool : [viewtopic.php?f=16&t=19078](http://forum.xentax.com/viewtopic.php?f=16&t=19078)
## Post #22
- Username: Argg
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 21, 2018 4:14 pm
- Post datetime: 2018-11-09T02:50:34+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

When I wrote the different positions I was referring to vertices with different co-ords, so there aren't any doubles, sorry. Nice work!
## Post #23
- Username: Ziella
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 04, 2018 12:45 pm
- Post datetime: 2018-12-02T05:46:57+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

Kinda stuck trying to figure out this since the information is all over the place. With the padding between the bone parenting and the bone positions, is there a way to calculate the size of that or something? The size of it appears to be different between files.

Edit: Nevermind, Found that the pointer to the bone position table is actually further down in the file.
## Post #24
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2018-12-04T15:17:43+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

how to get textures?
## Post #25
- Username: Ziella
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 04, 2018 12:45 pm
- Post datetime: 2018-12-05T13:12:52+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

I was wondering if anyone knew if this format has any kind of pointers that point towards the Faces table and Vertices? As well as maybe some kind of vertices count?
## Post #26
- Username: herrfraulein
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 28, 2019 8:17 am
- Post datetime: 2019-08-28T00:20:21+00:00
- Post Title: Re: PC Danganronpa Despair Girls .BNC, .BTX Help

> Reply from Simguy ↑Thu Jun 29, 2017 9:44 am at Thu Jun 29, 2017 9:44 am
>
> 
Luckily I was able to rip some textures with a profiler, because BTX files are DDS with repeating bytes trimmed.
https://mega.nz/#!7MtjFIiD!DtLV0KJQaSy_ ... yVsQIDyppc This has a btx and a complete DDS that I ripped. 
There is something going on with these that I don't fully understand, hopefully these will help someone smarter than me.

Mind telling me what you used to rip the textures?
