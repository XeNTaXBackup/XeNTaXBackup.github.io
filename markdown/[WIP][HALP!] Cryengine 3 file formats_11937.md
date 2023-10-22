## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2014-09-11T21:31:48+00:00
- Post Title: [WIP][HALP!] Cryengine 3 file formats

Hi everyone,

I want to create an updated version of revelation's fantastic Cryengine plug-in for Noesis.  His works great for v2 and many v3 models, but there are some weird anomalies with some of the newer files used in Cryengine games (such as MechWarrior Online or Star Citizen).  In addition, there isn't any support currently for .cga files, which contain animation data, and the materials info changed significantly in versions (Cryengine .mtl files are now an xml formatted text file).

So... step 1:  Figuring out the face data.
Here's the hex code from a Cryengine file:


This is what the current Noesis output to .obj creates:


This is where I'm trying to walk through the tutorial on getting the face data from the hex code and running into problems.  Is this bigE or litE?  I don't think the faces are welded since each tri has its own set of vertices, even though the positions are exactly the same.  Why would vertices that are in the same position listed separately?

And how exactly does this face stuff work?  It looks like the first face is defined by 01 02 02 03?  The second is 04 05 06 06?  That doesn't match up with the .obj face data.

Ok, on to step 2 (or maybe I should call it problem 2):  Parts lost in space.

When using the cryengine plug-in, some objects end up way out there.  They are the proper size and all in the right spot, but they are miles away from the origin. 


The X position is off by about 1000, and the z off by about 6000.  I'd show the relative location of the hex code for this, but I'm not even really sure where to find it (the tutorial was a bit beyond me by then).  I can kinda sorta get the object in the right spot in Blender by taking each vertex location and dividing the position by 1000, but can't be sure that it really is in the right position.

This is probably a good start.  Eventually I want to use python or Powershell (don't laugh) to make a new plug-in for Noesis, but first things first.
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-09-11T22:12:13+00:00
- Post Title: [WIP][HALP!] Cryengine 3 file formats

I believe the MAX importer/exporter code was leaked for Crysis 2 (CryEngine3).. Perhaps it might be useful for you to adapt/adjust and understand the file structure a little more.
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2014-09-11T22:23:28+00:00
- Post Title: [WIP][HALP!] Cryengine 3 file formats

> Reply from Gh0stBlade
>
> I believe the MAX importer/exporter code was leaked for Crysis 2 (CryEngine3).. Perhaps it might be useful for you to adapt/adjust and understand the file structure a little more.

Ok, some rough googling (and binging... because you never know) around isn't finding any source code for this.  Do you perchance have a link or maybe a hint on where to narrow down my search?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-12T20:11:40+00:00
- Post Title: [WIP][HALP!] Cryengine 3 file formats

> Reply from Markemp
>
> This is where I'm trying to walk through the tutorial on getting the face data from the hex code and running into problems.  Is this bigE or litE?it's little endian. You might use hex2obj:



aws_centre_torso_8q_lod3-cfg.JPG (37.51 KiB) Viewed 124 times

 (first submesh only)

> And how exactly does this face stuff work?  It looks like the first face is defined by 01 02 02 03?  The second is 04 05 06 06?  That doesn't match up with the .obj face data.you don't need to worry about this as long as the model and it's uvs are displayed properly using:
f 1/1 2/2 3/3 
f 3/3 4/4 1/1 
f 5/5 6/6 7/7 
f 7/7 8/8 9/9 
...

> When using the cryengine plug-in, some objects end up way out there.  They are the proper size and all in the right spot, but they are miles away from the origin. 
>
> 
>
> 
>
> The X position is off by about 1000, and the z off by about 6000.in some rare cases the simpler program seems to provide better results:  
# 0xaac: verts= 42
v 3.882273 -1.691395 1.057338 
v 3.712605 1.237598 1.505350 
v 5.271502 0.904054 1.057337 
v 5.779134 -1.402209 1.505349 
...

(Maybe revelation's plugin gets some offsets from the model file and adds them?)
## Post #5
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2014-09-12T21:16:34+00:00
- Post Title: [WIP][HALP!] Cryengine 3 file formats

> Reply from Markemp
>
> Ok, some rough googling (and binging... because you never know) around isn't finding any source code for this.  Do you perchance have a link or maybe a hint on where to narrow down my search?
The MaxTools are part of the free CryEngine SDK. But I don't think there are code-snippets for import/export, cuz the relevant source is in compiled plugin-DLL-files.
