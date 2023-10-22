## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-07T23:52:11+00:00
- Post Title: Cryengine vertex information weirdness

Hi everyone,

I'm working on a program to be able to export modern Cryengine files ([https://github.com/Markemp/Cryengine-Converter](https://github.com/Markemp/Cryengine-Converter)) with the eventual goal of being able to import them directly into Blender.  However, I'm running into some weirdness on the vertex data for some types of files.

Normally the vertex data consists of 3 floats for the x, y and z positions, called Vector3.  And for many of the files, Cryengine does say that these objects are indeed 12 bytes which goes nicely into a 3 float data structure.

```
    {
        public float x;
        public float y;
        public float z;
    }  // Vector in 3D space {x,y,z}
```


When I output the values from the .cga files, it all makes sense in the good ones:

```
ChunkType: DataStream
Version: 800
DataStream chunk starting point: 1260
DataStreamType: VERTICES
Number of Elements: 419
Bytes per Element: 12

```


However I'm running into some files where the Chunk says the size of the structure is just 8 bytes, but the object type is still Vector3.  And I can't for the life of me figure out how you get 3 float vectors into just 8 bytes.  Going on the vertex data it does line up with 8 byte per vertex, but... I feel like I'm missing some sort of conversion.

Here's the output for one where the BytesPerElement is just 8:

```
ChunkType: DataStream
Version: 800
DataStream chunk starting point: 4CC
DataStreamType: VERTICES
Number of Elements: 1076
Bytes per Element: 8
*** END DATASTREAM ***
```


8 Bytes per element?  How?   How do I get 1076 points with just 8 bytes?  And even weirder, using the old cryengine plugin for Noesis, the object has 2628 vertices.  That actually matches the number of indices, but not vertices.

Been driving me nuts for a couple of weeks here.  Anyone have any idea why?  Is each float in that structure a position (x, y or z) in that file, and the indices indicate which ones to use?  Why would they use bytes per element in that case, and why would some use 8 and some 12?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-08T06:23:14+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from Markemp
>
> And I can't for the life of me figure out how you get 3 float vectors into just 8 bytes.
iirc there was a packed format, 11bits,11bits,10bits where the latter being used for the height coordinate. Maybe it's something similar here? (there are various possibilities to devide 64bits up in a similar way: 22,22,20 for ex.)
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-09T00:08:29+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from shakotay2
>
> Markemp wrote:And I can't for the life of me figure out how you get 3 float vectors into just 8 bytes.
iirc there was a packed format, 11bits,11bits,10bits where the latter being used for the height coordinate. Maybe it's something similar here? (there are various possibilities to devide 64bits up in a similar way: 22,22,20 for ex.)

I think I was looking at it the wrong way.  The 1076 8-byte elements are I think referring to 2152 separate float values, that when combined with the indices form all the vertices.  At least I hope that's it.  Won't know until I pop it into a viewer.

I think there's a scale value I also need to find.  Good project for the night I guess.
## Post #4
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-20T06:37:50+00:00
- Post Title: Cryengine vertex information weirdness

I haven't got very far in figuring this out.  Let me throw some specific examples out though.

Here are the first 3 8-byte elements in one of the data files:
29 36 53 b7 f6 3b 20 3c  
b8 35 53 b7 08 3c 20 3c  
09 36 a5 b7 f6 3b 20 3c  

Here is what Noesis prints out using the cryengine dll file:
v  0.385010 -0.457764 0.995117
v  0.357422 -0.457764 1.007813
v  0.377197 -0.477783 0.995117

Any idea how to go from that hex to the decimal vertex info?  For the files that are simple 12 byte elements, it's an easy 3 float conversion, but I can't seem to get there from here.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-20T09:04:50+00:00
- Post Title: Cryengine vertex information weirdness

it's just half floats (20 3C ignored)
## Post #6
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-21T04:44:35+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from shakotay2
>
> it's just half floats (20 3C ignored)

I wish there were some native C# or .Net functions that could convert shorts to half floats.  I'm beating my head against the wall trying to get good values out of these 2 byte structures.

How do you do it in your hex2obj file, shakotay2?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-21T11:30:19+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from Markemp
>
> I wish there were some native C# or .Net functions that could convert shorts to half floats.  I'm beating my head against the wall trying to get good values out of these 2 byte structures.
why not use a library?
[http://stackoverflow.com/questions/2166 ... into-array](http://stackoverflow.com/questions/21660365/reading-half-floats-into-array)

> How do you do it in your hex2obj file, shakotay2?
C-code, float HalfFloat(char* &pFBuf, DWORD &j, bool bBigE) 

As you can see it's using pointers so I'd suggest using the solution in the link above.
## Post #8
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-21T12:00:23+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from shakotay2
>
> Markemp wrote:I wish there were some native C# or .Net functions that could convert shorts to half floats.  I'm beating my head against the wall trying to get good values out of these 2 byte structures.
why not use a library?
http://stackoverflow.com/questions/2166 ... into-array

I've been looking for one.   Unfortunately everything at sourceforge.net seems to be down.  They've been having problems...
## Post #9
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-26T16:37:27+00:00
- Post Title: Cryengine vertex information weirdness

Getting really close to having my Cryengine converter up and running!  



The mesh is nice and clean, the materials and UV all line up right, and everything is fine *except* I can't figure out where to put each of the objects.

Each submesh as a Center object, which is just a position (x,y,z).  I'm trying to figure out how to apply this to the mesh.  Subtracting it from each vertex moves each object to the exact center.  Adding it though doesn't really put it in the right position, as can be seen from the image above (things really aren't where they are supposed to be).

Is there any other sort of offset that gets applied to the vertex information to get them in the right place relative to the other groups in the data file globally?  I almost think there has to be something at the Mesh Chunk level, since applying the Center for each submesh to that submesh causes them to look like... above.

edit:  Yup, there is a position element in the Node chunk!  And it seems to put everything in the relative right position, but the scale is off.  Fortunately there is a scale object as well, so now I can play with that to see how it affects everything.
## Post #10
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-26T22:42:39+00:00
- Post Title: Cryengine vertex information weirdness

OK, running out of ideas.  Each node chunk imports great.  The center is placed at 0,0,0.  If I try to apply the Node's position Vector, all the nodes shoot out all over the place.  When it says one node is located at 0,0,0 and another (that should be attached) is at 0,0,6 when the Position is applied to the center... bad things happen.



If I try to apply those position values to the vertices, the 2 parts end up 6 units apart (i.e. very far).

I'm just not sure how to apply the position, scalar, rotation and transform attributes of the node chunk to the Vertices.  Stuff is in the wrong position relative to each other, but... yeah. 

Noesis with the cryengine plug-in does the exact same thing.  Exploded geometry.  Means I'm not doing something right.

Here's the .cgf file:  [https://dl.dropboxusercontent.com/u/816 ... girl_a.cga](https://dl.dropboxusercontent.com/u/81602544/hulagirl_a.cga)
## Post #11
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-26T22:53:23+00:00
- Post Title: Cryengine vertex information weirdness

Oh, and I forgot to print up the transformation matrix as well.



I'm sure that has some factor in where to put all the objects.
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-07-26T23:19:17+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from Markemp
>
> Oh, and I forgot to print up the transformation matrix as well.

I'm sure that has some factor in where to put all the objects.

is that transformation matrix correct? i'm not familiar with blender but shouldn't the translation be in the forth col?
## Post #13
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-26T23:27:19+00:00
- Post Title: Cryengine vertex information weirdness

> Reply from WRS
>
> Markemp wrote:Oh, and I forgot to print up the transformation matrix as well.

I'm sure that has some factor in where to put all the objects.

is that transformation matrix correct? i'm not familiar with blender but shouldn't the translation be in the forth col?

It's very likely transposed.  I guessed on the i vs j side.

And it's not blender; it's a C# program I'm working on to update the Noesis + Cryengine dll to work with modern Cryengine games.  That's just the output.

                // Read the 4x4 transform matrix.  Should do a couple of for loops, but data structures...
                Transform.m11 = b.ReadSingle();
                Transform.m12 = b.ReadSingle();
                Transform.m13 = b.ReadSingle();
                Transform.m14 = b.ReadSingle();
                Transform.m21 = b.ReadSingle();
                Transform.m22 = b.ReadSingle();
                Transform.m23 = b.ReadSingle();
                Transform.m24 = b.ReadSingle();
                Transform.m31 = b.ReadSingle();
                Transform.m32 = b.ReadSingle();
                Transform.m33 = b.ReadSingle();
                Transform.m34 = b.ReadSingle();
                Transform.m41 = b.ReadSingle();
                Transform.m42 = b.ReadSingle();
                Transform.m43 = b.ReadSingle();
                Transform.m44 = b.ReadSingle();  

Code snippet from my program (or you can see it directly at [https://github.com/Markemp/Cryengine-Converter](https://github.com/Markemp/Cryengine-Converter))  It's possible taht I should have read transform.m11, transform.m21, transform.m31 instead...  The raw data is:



I guess the problem I'm having is:  how do you use that, or is it even necessary?
