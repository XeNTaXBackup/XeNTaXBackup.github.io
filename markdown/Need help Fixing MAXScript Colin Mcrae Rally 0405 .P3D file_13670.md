## Post #1
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-13T14:41:03+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

Hello everyone!

After a long search I found tools for converting models from CMR04/05 and they work,but I got errors with every model.
Basically,they all have damaged normal data and some of the faces are facing wrong direction.

Maybe there's a way to automatically fix them or fix the script?

Here are the examples and a script  

[http://www.mediafire.com/download/h9k8q ... AMPLES.rar](http://www.mediafire.com/download/h9k8qvzgdhq4vhz/CMR5_EXAMPLES.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-13T19:02:21+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from Ferrari formula 1
>
> Hello everyone!

After a long search I found tools for converting models from CMR04/05 and they work,but I got errors with every model.
Basically,they all have damaged normal data and some of the faces are facing wrong direction.First of all: whose script is it?
Can't tell about normals since you didn't provide the textures for Lansd.p3d.
What do you mean by "damaged" normal data and wrong directed faces?
(Guess you mean those black holes visible in max?)

Would be helpful to have textures.

(Only oddness I can see so far are those additional submeshes/rectangles which can be erased to make the model look better.
 Well, and the position of the steering wheel is a little bit funny.  )



Lansd.JPG (134.06 KiB) Viewed 192 times


(I would suggest to separate the lod models. But I don't have the time to modify the script.)
## Post #3
- Username: shakotay2
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-14T02:56:32+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

I fear there is no quick fix for this script.

Parenting is read, but never applied.  That would possibly fix the rotation issues with the steering wheel and wiper blades and make it easier to separate the lod meshes.  Something strange going on with the way the faces are read and the normals are applied and then manipulated.  There also may be some vertex issues, but what I'm seeing there may be caused by the face issue, or vice-versa.

--MDA
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-14T08:44:59+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

Thx - now I can see wrong/strange faces at least:



Lansd_.JPG (30.69 KiB) Viewed 181 times
## Post #5
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-14T09:31:13+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

I don't know who made this script,It's old and it was very hard to find,I searched for hour visiting dead websites which are not updated since 2006  

Here are the textures for tests  
[http://www.mediafire.com/download/awp52 ... xtures.rar](http://www.mediafire.com/download/awp52kbww97chqx/Lancia_delta_textures.rar)

Kinda like how It's supposed to look like (Simulated with DoubleSided Shader,you can still easily see broken places)


And what it looks like when It's imported  





A look at the normals in 3DSMax,they seem to be just reversed


> Reply from shakotay2
>
> Thx - now I can see wrong/strange faces at least:
Lansd_.JPG

I bet It's just a broken tire model,not a corrupted face...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-14T10:19:35+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from Ferrari formula 1
>
> Here are the textures for teststhanx.  

> A look at the normals in 3DSMax,they seem to be just reversedIn blender there's a "flip normals" button.
There should be something similar in max. But you should apply it to the concerning submeshes only - not the whole model.
Hmm, that's strange: it's only some of the faces of a submesh which have wrong orientated normals.



strangeNormals.JPG (12.71 KiB) Viewed 173 times


Guess the face winding of those 6 faces is incorrect. Means you have to dig into the script how the faces are constructed.

Sadly I'm too busy with my own projects but I'll check the Lansd submeshes sooner or later.

> I bet It's just a broken tire model,not a corrupted face...I see - but one face is corrupt, obviously.
## Post #7
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-14T11:09:37+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from shakotay2
>
> Ferrari formula 1 wrote:Here are the textures for tests  thanx.  
A look at the normals in 3DSMax,they seem to be just reversedIn blender there's a "flip normals" button.
There should be something similar in max. But you should apply it to the concerning submeshes only - not the whole model.
Hmm, that's strange: it's only some of the faces of a submesh which have wrong orientated normals.
strangeNormals.JPG
Guess the face winding of those 6 faces is incorrect. Means you have to dig into the script how the faces are constructed.

Sadly I'm too busy with my own projects but I'll check the Lansd submeshes sooner or later.
I bet It's just a broken tire model,not a corrupted face...I see - but one face is corrupt, obviously.

There are flip normals options both in Cinema4D and 3DSMax but there's a bit of a problem with it

1)Flipping normals on some faces from a whole part is very hard in 3DSMax
2)Some of the parts(Like mudflaps) are correct and supposed to use double-sided shaders
3)When I'm doing it in Cinema4D I get this,even strangier problem (for example,wing and spoiler)






And I can't really dig into this script because I'm not familliar with Max scripting and data extraction
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-14T12:17:58+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from Ferrari formula 1
>
> And I can't really dig into this script because I'm not familliar with Max scripting and data extractionmaybe you don't need to.  
I'm not sure but maybe it's just a matter of handling materials/textures in 3ds max?
I simply put SDBod.dds onto the whole selected mesh and the door texture seems to be ok despite those few wrong orientated normals.



Lansd_looks_fine_doesn't_it.JPG (49.94 KiB) Viewed 167 times


(I didn't unselect the window glass so the texture appears there, too. Sry for that.  )

btw: what a genius script. Really would like to know who the creator was or from which site you got it.
## Post #9
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-14T14:03:27+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from shakotay2
>
> Ferrari formula 1 wrote:And I can't really dig into this script because I'm not familliar with Max scripting and data extraction maybe you don't need to.  
I'm not sure but maybe it's just a matter of handling materials/textures in 3ds max?
I simply put SDBod.dds onto the whole selected mesh and the door texture seems to be ok despite those few wrong orientated normals.
Lansd_looks_fine_doesn't_it.JPG
(I didn't unselect the window glass so the textures appears there, too. Sry for that.  )

btw: what a genius script. Really would like to know who the creator was or from which site you got it.

Well,first of all,even if 3ds max shows textured car correctly(doesn't works for me  But it's still pretty useless...),it doesn't fixes the normals and it can't be used anywhere outside the 3DSMax


I also have a script for CMR04 Models but it works absolutely the same way with the same errors(can post with examples if needed)

There's no alive website with this archive(they are all dead) and I just was lucky enough to find an archive on Russian social network with utilites for CMR04/05 by some annonymous
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-14T14:20:43+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from Ferrari formula 1
>
> Well,first of all,even if 3ds max shows textured car correctly(doesn't works for me  But it's still pretty useless...),it doesn't fixes the normals and it can't be used anywhere outside the 3DSMaxI see - same problem with blender.



Lansd_blender.JPG (64.76 KiB) Viewed 164 times


Maybe I'll find out why 3dsmax displays that textured door correctly in my previous post. Guess it uses LOD2's normals or something like that.
(As I've told I've selected the complete mesh before applying the texture.)
## Post #11
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-14T14:29:48+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from shakotay2
>
> Ferrari formula 1 wrote:Well,first of all,even if 3ds max shows textured car correctly(doesn't works for me  But it's still pretty useless...),it doesn't fixes the normals and it can't be used anywhere outside the 3DSMaxI see - same problem with blender.
Lansd_blender.JPG
Maybe I'll find out why 3dsmax displays that textured door correctly in my previous post. Guess it uses LOD2's normals or something like that.
(As I've told I've selected the complete mesh before applying the texture.)

Well,how could it do that? When I'm importing the car there are no any lod parts...
Car is just LOD0 everywhere 

Maybe it just ignores the rules and shows it by using double-sided shader?
(As I showed before)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-14T22:03:02+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from Ferrari formula 1
>
> When I'm importing the car there are no any lod parts...
Car is just LOD0 everywhereyeah, it's simply an inner and an outer door. I confused that. 
I also have probs to get the correct sum of 315 verts for both parts of the door:



Lansd_door.JPG (102.53 KiB) Viewed 154 times


Just another project for life time wasters... 

There's something strange with the creation of tristripped faces in this script.
There's only aface = [fa,fb,fc].
Normally you've an alternative assignment such as aface = [fa,fc,fb] depending on a face orientation variable which toggles with each face.
I'll check that...

(But not sure whether adding aface = [fa,fc,fb] will do any good because too many faces are correct.)

yay, seems I got it - at least for that damned door.
try

```
					faceDir = 1
```
and

```
						(
							faceDir *= -1 ;
							if faceDir > 0 then aface = [fa,fb,fc]
							else aface = [fa,fc,fb]
							append face_array aface							
						)
```

Checked for the right door only. So don't blame me if there's still other weird meshes...
## Post #13
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2015-12-16T08:15:29+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

how to extract Colin Mcrae Rally 05 textures from BIG?
cmr04big.exe not working?
## Post #14
- Username: Ferrari formula 1
- Rank: advanced
- Number of posts: 72
- Joined date: Mon Aug 11, 2014 6:42 pm
- Post datetime: 2015-12-16T10:55:12+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

> Reply from shakotay2
>
> Ferrari formula 1 wrote:When I'm importing the car there are no any lod parts...
Car is just LOD0 everywhere yeah, it's simply an inner and an outer door. I confused that. 
I also have probs to get the correct sum of 315 verts for both parts of the door:
Lansd_door.JPG
Just another project for life time wasters... 

There's something strange with the creation of tristripped faces in this script.
There's only aface = [fa,fb,fc].
Normally you've an alternative assignment such as aface = [fa,fc,fb] depending on a face orientation variable which toggles with each face.
I'll check that...

(But not sure whether adding aface = [fa,fc,fb] will do any good because too many faces are correct.)

yay, seems I got it - at least for that damned door.
try
Code: Select all					face_array = #()
					faceDir = 1and
Code: Select all						if ((fa!=fb)and(fa!=fc)and(fc!=fb)) then
						(
							faceDir *= -1 ;
							if faceDir > 0 then aface = [fa,fb,fc]
							else aface = [fa,fc,fb]
							append face_array aface							
						)
Checked for the right door only. So don't blame me if there's still other weird meshes...

Wow,man,you rock!Amazing stuff!  

Oh and could you please send me your .ms script? Seems like I'm modifying it not correctly and I can't change it:D

> how to extract Colin Mcrae Rally 05 textures from BIG?
>
> cmr04big.exe not working?

Here are all the tools for cmr 04/05. theese can extract car textures and sounds.
[http://www.mediafire.com/download/m14y3 ... ntools.rar](http://www.mediafire.com/download/m14y3kqzohuqqbt/extractiontools.rar)
To extract textures/sounds from 05 version of the game you should first convert bin file with CMR5_BIG_decomp.exe and only then convert them with cmr04big.exe
## Post #15
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2015-12-16T12:18:36+00:00
- Post Title: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D file

Thank you the decompress tools!
After decompressed the CMR5 big file use cmr04big tools can get texture easily!

[https://www.mediafire.com/?l2pg1fhogpooqyj](https://www.mediafire.com/?l2pg1fhogpooqyj)
## Post #16
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2015-12-17T07:22:44+00:00
- Post Title: Re: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D 

Tagging this great Thread !
## Post #17
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-12-19T17:37:11+00:00
- Post Title: Re: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D 

In an attempt to create a more complete script I've mapped the format.

```

(1)   FILE HEADER
      -----------
      00000000    CHAR[4]      "CP3D"
      00000004    BYTE[4]      Unknown
      00000008    LONG         Offset to (2) Data Header
	
(2)   DATA HEADER (56 bytes)
      -----------
      00000000    BYTE[4]      Unknown
      00000004    LONG         Offset to (3) Node
      00000008    BYTE[8]      Unknown
      00000016    LONG         End of File Data
      00000020    LONG         Offset to (4) Texture Table
      00000024    LONG         Texture Count
      00000028    BYTE[4]      Unknown
      00000032    LONG         Object Count
      00000036    LONG         Offset to (5) Object Table
      00000040    LONG         Count for Unknown Table below
      00000044    LONG         Offset to (6) Unknown Table
      00000048    BYTE[8]      Unknown

(3)   NODE (336 bytes)
      ----
      00000000    BYTE[64]     Unknown
      00000064    FLOAT[16]    Matrix
      00000128    LONG         Offset to (7) Mesh Object Data
      00000132    LONG         Offset to (3) Node (Parent ???)
      00000136    LONG         Offset to (3) Node (Child Node ???)
      00000140    LONG         Offset to (3) Node (Sub-Child Node ???)
      00000144    BYTE[128]    Unknown
      00000272    FLOAT[4]     Bounding Box Min ???
      00000288    FLOAT[4]     Bounding Box Max ???
      00000304    LONG         Unknown
      00000308    BYTE[12]     Unknown
      00000320    LONG         Unknown
      00000324    LONG         Unknown
      00000328    BYTE[8]      Unknown

(4)   TEXTURE TABLE (4 bytes) (Repeat equal to Texture Count)
      -------------
      00000000    LONG         Offset to Texture Name

(5)   OBJECT TABLE (8 bytes) (Repeat equal to Object Count)
      ------------
      00000000    LONG         Offset to Object Header (see below)
      00000004    LONG         Object Type (0 --  (8) Object Header
                                            1 --  (9) Object Header
                                            3 -- (10) Object Header)

(6)   UNKNOWN TABLE (4 bytes) (Repeat equal to Unknown Count)
      -------------
      00000000    LONG         Unknown

(7)   MESH OBJECT DATA (16 bytes ???)
      ----------------
      00000000    BYTE[4]      Unknown
      00000004    LONG         Offset to (10) Object Header
      00000008    LONG         Unknown
      00000012    LONG         Unknown

(8)   OBJECT HEADER (432 bytes) (Object Type 0)
      -------------
      00000000    BYTE[4]      Unknown
      00000004    LONG         Unknown
      00000008    LONG         Object and Texture Count
      00000012    BYTE[8]      Unknown
      00000020    BYTE[4]      Color Information (r, g, b, a) ???
      00000024    BYTE[280]    Unknown

            OBJECT OFFSETS (64 bytes) (Read as Long equal to Child Count, skip remainder)
            --------------            (These are consequetive)
            00000304    LONG         Offset to (9) Object Header
	
            TEXTURE OFFSETS (64 bytes) (Not sure about this one as the material offsets are not in a straight line.)
            ---------------            (These are not consequetive, leads me to believe their position possibly determines the type of texture map)
            00000368    LONG         Offset to (11) Texture Name
	
(9)   OBJECT HEADER (112 bytes) (Object Type 1)
      -------------
      00000000    BYTE[48]     Unknown
      00000048    FLOAT[16]    Matrix

(10)  OBJECT HEADER (208 bytes) (Object Type 3)
      -------------
      00000000    BYTE[8]      Unknown
      00000008    LONG         Mesh Count
      00000012    LONG         Offset to (12) Mesh Table
      00000016    LONG         Offset to (13) Unknown Table
      00000020    BYTE[12]     Unknown
      00000032    LONG         Offset to (14) Vertex Index Table
      00000036    LONG         Offset to (15) Face Index Table
      00000040    LONG         Face Index Count
      00000044    LONG         Unknown
      00000048    BYTE[144]    Unknown
      00000192    LONG         Unknown
      00000196    LONG         Vertex Index Count
      00000200    BYTE[8]      Unknown

(11)  TEXTURE NAME (variable)
      ------------
      00000000    STRING       Null-terminated Texture Name

(12)  MESH TABLE (20 bytes) (Repeat equal to Mesh Count)
      ----------
      00000000    LONG         Offset to (8) Object Header
      00000004    LONG         Unknown
      00000008    LONG         Offset to (16) Mesh Data Table
      00000012    BYTE[8]      Unknown

(13)  UNKNOWN TABLE (12 bytes)
      -------------
      00000000    BYTE[4]      Unknown
      00000004    LONG         Unknown
      00000008    BYTE[4]      Unknown

(14)  VERTEX INDEX TABLE (12 bytes)
      ------------------
      00000000    LONG         Offset to (17) Vertex Data
      00000004    LONG         Unknown
      00000008    BYTE[4]      Unknown

(15)  FACE INDEX TABLE (12 bytes)
      ----------------
      00000000    LONG         Offset to (18) Face Data
      00000004    LONG         Unknown
      00000008    BYTE[4]      Unknown

(16)  MESH DATA TABLE (16 bytes)
      ---------------
      00000000    LONG         Face Index Start at
      00000004    LONG         Face Index Count
      00000008    LONG         Vertex Index Start at
      00000012    LONG         Vertex Index End at

(17)  VERTEX DATA (36 bytes) (Repeat equal to Object Header:Vertex Index Count)
      -----------
      00000000    FLOAT[3]     Vertex Position (x, y, z)
      00000012    FLOAT[3]     Vertex Normal (x, y, z) ???
      00000024    BYTE[4]      Vertex Color (r, g, b, a)
      00000028    FLOAT[2]     Texture Map Co-ordinates (u, v)

(18)  FACE DATA (2 bytes) (Repeat equal to Object Header:Face Index Count)
      ---------
      00000000    USHORT       Face Index

```


Still working on the script.

--MDA
## Post #18
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2018-09-09T08:54:18+00:00
- Post Title: Re: Need help Fixing MAXScript Colin Mcrae Rally 04/05 .P3D 

Was it just me or is the .*tag model format (.STAG, .CTAG, etc.) any similar to the ones found in Colin McRae 3? I took a quick peek at an .STAG model through HxD and the header seems to line up with Mike's documentation.
