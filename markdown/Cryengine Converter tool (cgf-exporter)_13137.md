## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-02T03:53:47+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Cryengine Converter

Project Location: [https://github.com/Markemp/Cryengine-Converter](https://github.com/Markemp/Cryengine-Converter) or [https://www.heffaypresents.com/GitHub](https://www.heffaypresents.com/GitHub)
Current version:  1.5.0 (2023/01/05)
Executable: [https://github.com/Markemp/Cryengine-Co ... /releases/](https://github.com/Markemp/Cryengine-Converter/releases/)

Introducing a tool designed to convert modern Cryengine games into .dae and .obj files.

This program is written in C#, and although I haven't done any performance enhancements yet it is still pretty fast.  You can script it up with Powershell to batch process a number of .cgf and .cga files at once.  There is also an [Cryengine Importer](https://github.com/Markemp/Cryengine-Importer) Blender add-on I've written that assists bringing in Cryengine files into Blender, creating the proper material Node Groups, etc.

TUTORIAL VIDEOS
[https://www.youtube.com/watch?v=6WoA2ub ... LBODtkh29b](https://www.youtube.com/watch?v=6WoA2ubTZ0k&list=PL106ZeLhxxVn551_IKGKeU_LBODtkh29b)

Usage:
Copy cgf-converter.exe to the path (for convenience, unless you want to reference the location each time you run it).  Then follow the usage details below:

```

-usage:           Prints out the usage statement

<.cgf file>:      The name of the .cgf, .cga or .skin file to process
-outputfile:      The name of the file to write the output.  Default is [root].obj
-noconflict:      Use non-conflicting naming scheme (<cgf File>_out.obj)
-allowconflict:   Allows conflicts in .mtl file name
-objectdir:       The name where the base Objects directory is located.  Used to read mtl file
                  Defaults to current directory.
-dae:             Export Collada format files (Default)
-smooth:          Smooth Faces
-group:           Group meshes into single model

-throw:           Throw Exceptions to installed debugger
```

Bug Reporting:

Please add a new Issue at the GitHub page:  [https://github.com/Markemp/Cryengine-Converter/issues](https://github.com/Markemp/Cryengine-Converter/issues)

 Future enhancements:

Games currently tested against:
Star Citizen
MechWarrior Online
Armored Warfare
Prey
ArcheAge
Evolve
Ghost Sniper 3
Sonic Boom
Hunt
Crysis
Far Cry

If you'd like to participate in the future development of this tool, please send me a message or just contribute to the Github.  Thanks!

Special thanks to shakotay2 for helping sort out some format issues.
Special thanks to Coffee for making me not stupid about transform matrices.
Special thanks to th3st0rmtr00p3r (James) for helping solve the final object rotation issue that's been plaguing me for years!
## Post #2
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-02T03:54:19+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Cryengine Importer!

This replaces the 2 powershell scripts Asset Importer and Mech Importer.  It's been consolidated into a Blender add-on, written in python, and a new Prefab Importer feature has been added.

You can find this new tool at:

[https://www.heffaypresents.com/github](https://www.heffaypresents.com/github)

The tutorial video on how to use it can be found at:

[https://www.youtube.com/watch?v=oBJzNdzFIxM](https://www.youtube.com/watch?v=oBJzNdzFIxM)

It's been tested heavily for MechWarrior Online.  It probably doesn't work for 2.3 or newer Star Citizen files, but I'll be working on updating it to handle those game files as well.  The Cryengine Converter tool does work for Star Citizen 3.0 files though!
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-29T16:24:30+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Ok, I fixed the dreaded exploded geometry issue for Cryengine files!  It turns out to be several factors:

(@revelation, if you want the code specifics for your cryengine_cgf.dll for Noesis, I'll be happy to share them with you)

1)  The transform vector is in 2 places.  A Vector3 called Transform, and then a 4x4 matrix where the bottom row was the same value.  However occasionally the Transform vector didn't have any data, so you always had to use the matrix for this info.

2)  The values needed to be divided by 100.  Why?  I have no idea.  They just do.

3)  The transform of any piece was based on where its parent was placed.  So if you had an item that was 4 deep in the hierarchy, you had to add the transforms of *each* of the parents, all the way to the root node.

Anyway, between that and bug fixes (still in progress), shit be working yo!



Well.. mostly.  There are still some pieces that aren't playing nicely, but the vast majority do.  I'll sort them out eventually.

Bonus:  These should work with Armored Warfare game files too, if you want some juicy tank models!

Caveat:  Cryengine has gone away from the .dds files containing all the mipmaps, and instead now creates a separate dds file with a numerical extension for each level (dds.1, dds.2, dds.etc), along with what is probably an index file.  No big deal, as the format is known and I can incorporate this into my program eventually.  [And tools already exist to convert them](http://www.cryengine.com/community/download/file.php?id=115943&sid=abc7b44862f3b444522e75528a1bf7e6).

As always, anyone who wants to participate in my github and help develop the program, your help is definitely appreciated!  My next goals are armatures, animation files (.caf), and exporting directly to Blender files (.blend).
## Post #4
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2015-09-03T03:00:49+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

i have been following the work you have been doing.  parts of my plugin were cross referenced against pyffi as well.  doing some major cleanup on all my plugins.  will see if i can contribute to your work when i can make some time.  will be good to get all of the features sorted out for supporting this engine and its formats.
## Post #5
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-09-16T05:52:45+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Thank you for your work!
What news about position/rotation submeshes?
I watch your sources - you use only transform matrix44 only for positions submeshes (without rotations), but class ChunkNode has Pos and Rot properties but don't use it - what is it?
## Post #6
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-10-05T14:01:20+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

> Reply from erik945
>
> Thank you for your work!
What news about position/rotation submeshes?
I watch your sources - you use only transform matrix44 only for positions submeshes (without rotations), but class ChunkNode has Pos and Rot properties but don't use it - what is it?

Crap, was on vacation when you asked this.

From my understanding:  The Node chunk is where the scale/rot/transform info is stored for each "object".  Each Node chunk has one Mesh chunk.  Each Mesh chunk can have multiple Submesh chunks, which contain the actual vertex info.

There is a parent Node chunk that all other Nodes are based off of.  And Nodes can have children as well, so think of a tree structure.  Parent Node, its children, and the children of those children, etc.  And the transform of each Node is based off of the transform of its parent, all the way to the Root.  So to calculate the actual transform of any particular Node, you have to add it to all the ones all the way to the Root.

```
        {
            float x = chunkNode.Transform.m41 / 100;
            float y = chunkNode.Transform.m42 / 100;
            float z = chunkNode.Transform.m43 / 100;
            // if we're at the parent, we just want to return.  Otherwise we want to go up to the next level.
            // Matrix math here.  final x is x*m11 + y*m12 + z*m13.  Same for y and z
            if (chunkNode.Parent != 0xFFFFFFFF)
            {
                transform.x += x * chunkNode.Transform.m11 + y * chunkNode.Transform.m12 + z * chunkNode.Transform.m13;
                transform.y += x * chunkNode.Transform.m21 + y * chunkNode.Transform.m22 + z * chunkNode.Transform.m23;
                transform.z += x * chunkNode.Transform.m31 + y * chunkNode.Transform.m32 + z * chunkNode.Transform.m33;

                transform = GetTransform((ChunkNode)ChunkDictionary[chunkNode.Parent], transform);
            }

            return transform;
        } 

```


This should actually calculate the rotation as well, but it's probably wrong which is why I'm having problems right now.  The hatch picture (round thing on front starboard side) is in the right location (at least the parent node), but some of the internal structure (children of it) aren't.  That's without applying the rotation component.  When I apply the rotation, all the subcomponents end up in the right place relative to each other, but the parent node ends up on the wrong side of the ship, near the back.

There are also some other components that have weird issues, like the hatch covers on the wing fans.  The can be located *relatively* close to where they are supposed to be, but just not quite rotated correctly.

Obviously I'm screwing up the calculations some how, but not quite sure what is going wrong yet.  I'm *so* close to having this working that it hurts.
## Post #7
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-06T19:01:56+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Thank you for answer.
If you be interested - two problematic models.
In GameSdk displayed normally.

[https://www.dropbox.com/s/o3c9lviltmjl2 ... s.cgf?dl=0](https://www.dropbox.com/s/o3c9lviltmjl2s4/mobiglas.cgf?dl=0)
[https://www.dropbox.com/s/nsx7lveimxz5o ... _.cga?dl=0](https://www.dropbox.com/s/nsx7lveimxz5owm/ax114__CGA__.cga?dl=0)
## Post #8
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-10-06T20:09:06+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

The mobiglass model did import into Blender without issue, although it did take a while to complete.  What error did you get?



I'll take a look at the other one too.

edit:  The other one "worked" too, although it's having the normal issues with the position of some child Nodes not being in the right place.
## Post #9
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-06T20:51:57+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

the problem is in the position / rotation of the elements.
In mobiglass lenses are not quite in place (see under blue glass)
## Post #10
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-10-06T20:57:05+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

> Reply from erik945
>
> the problem is in the position / rotation of the elements.
In mobiglass lenses are not quite in place (see under blue glass)

Oh yeah.  A number of models have that issue, since my transform & rotation math isn't right yet.  I'm hoping someone can point out where I'm going wrong, otherwise a lot of models are going to require a lot of manual tweaking.
## Post #11
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-10-27T02:49:29+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

It seems not work with the new build of ( 1.3)
## Post #12
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-10-27T02:58:05+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

> Reply from erik945
>
> It seems not work with the new build of ( 1.3)

Yup, I've heard there were issues.  I'll take a look and see if I can get an updated version for this weekend.
## Post #13
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-11-16T12:07:44+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Any news?
## Post #14
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-11-17T01:02:51+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

Try the dropbox download again.  I put my latest version out there (let's call it 0.84 for lack of a better term), where I'm working on cleaning up the export, adding new chunks, etc.  No major changes, but it may be a bit more reliable.  Let me know what works and what doesn't work (and specifically what didn't work).
## Post #15
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-11-19T10:13:01+00:00
- Post Title: Cryengine Converter tool (cgf-exporter)

don't work. Sorry.
Example files:
[https://www.dropbox.com/s/lekxp9hbvj3ia ... d.zip?dl=0](https://www.dropbox.com/s/lekxp9hbvj3iabu/Vanguard.zip?dl=0)
Can you add option's for skip mtl files?
Thank you!
## Post #16
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-11-24T05:45:13+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Very useful Tool, thank you!

Tested with Armored Warfare ([RU version](https://aw.mail.ru)) - works good! 
[](http://fastpic.ru/view/75/2015/1124/b8b74ad791088ef0e1c7c333342d8235.png.html)
Successfully converted .cga, .cgf and .chr models.

Btw, I have some suggestions about AW-converting:
- option for skip LODs (all of them have part name starting with $),
- option for full path to textures in .mtl file, now it's looks like this:

```

```

(note \ and / mixing bug)
I renaming it to this:

```

```

works ok, but sometimes textures loads from outside folders, like this:

```

```

or this:

```

```

or from another model folder, like this one for Leopard 2 A6:

```

```

So, it's better to detect full path to model in converting and use it for calculating base path to extracted game, i.e. for q:\!_AW\gamezero\objects\vehicles\mbt\leopard2a6\leopard2a6--leopard2a6.cga model "detected" base path is q:\!_AW\gamezero\
Then add this path to textures paths like this:

```

```


Another issue for AW .mtl's is

```
d 0.0000
```

for every material inside, so all of them have zero visibility by default - not sure it's game "feature" or convertion bug...

Tank hulls also have some shitty looking "armor proxies" attached, but with different materials:
[](http://fastpic.ru/view/76/2015/1124/e5b1f91b1a2878d501ffd22744286912.png.html)
(I set transparency to 35 for them on this image for better look)
Would be very useful if you add option to detach (by material) and skip those "proxy" meshes.

Tank turret, suspensoins, tracks and gun parts loads in the center of scene - there's no any dummies or bones to attach them in places?

Found a bug in material, not sure it's game or tool part:

```
Kd 0.1636 0.1870 0.1573
Ks  0.4151 0.4151 0.4151
d 0.0000
illum 2
map_Kd \objects/vehicles/mbt/leopard2a6/textures/leopard2a6_aps_d.dds
map_Ks \objects/vehicles/mbt/leopard2a6/textures/leopard2a6_aps_s.dds
map_bump \objects/vehicles/mbt/leopard2a6/textures/leopard2a6_aps_d.ddsobjects/vehicles/mbt/leopard2a6/textures/leopard2a6_aps_ddn.dds
```

 (Leopard2A6_Detachparts_Hull_mtl.mtl)
bump map have diffuse+bump path.

Also some materials contain double bump maps, normal and detail ones (second is for UV2 I think):

```
Kd 0.2195 0.2195 0.2195
Ks  0.2195 0.2195 0.2195
d 0.0000
illum 2
map_Kd \objects/vehicles/mh60_blackhawk/textures/mh60_interior.dds
map_Ks \objects/vehicles/mh60_blackhawk/textures/mh60_interior_spec.dds
map_bump \objects/vehicles/mh60_blackhawk/textures/mh60_interior_ddn.dds
map_bump \textures/detail_bumpmaps/metal/metal_006_detail.dds
```

(MH60_mtl.mtl)
second one trying to loads as default, so another option for skip is required.

And about options - can you made a .cfg file for changing them?
Because I use DblClick for conversion (set up cgf-converter.exe as default app for open .cga, .cgf, .chr files), so dancing with command line is not so good for me...

Samples (textures UnSplitted already):
[MH-60 BlackHawk](https://yadi.sk/d/HbYyUaD4kga7t) (15,4 Mb)
[Leopard 2 A6](https://yadi.sk/d/Lv6xKfrkkgaAg) (190,9 Mb)
## Post #17
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-11-24T12:52:43+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Thank you for checking out the program, and especially for the detailed bug reports!  I'll take a look at these after the holidays.  

The .obj file exporter is a bit limited in that the .mtl format is pretty limited into what it can do.  I'm converting the xml material files into that format, and they are much more complicated than the obj mtl format can support.  I'm currently working on the COLLADA exporter portion, which will hopefully have a lot more options as far as material support.  

Also, if you use the -objectdir argument when running the program, it should put the fully qualified path into the mtl file as well.  That will allow it to use dds files outside of the structure the model is in (like the textures\ directory).  You need to put the path to where the .pak files are located, so in my case it's:

cgf-converter.exe <file to convert> -objectdir "e:\blender projects\AW"

The / vs \ should be ok with most modern versions of windows, but I'll double check that.  I'm pretty sure Blender didn't have any problems importing based on forward vs back slashes, but will definitely test that out.

For stuff loading at the center, there is probably an XML file that contains info on where they are supposed to be placed globally.  This is how it works for MechWarrior Online, where the mechs come in dozens of separate pieces and the position info is located outside the .cga file.  I made a powershell script that moves them in Blender.

Eventually I'll make a graphical front end for the program so that the entire tank can be done in one click, based on.. probably the .cdf file info.  That usually says what pieces go where.  But first I need to get through Thanksgiving and figure out how much Fallout 4 is going to screw over my free time...
## Post #18
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-04T03:55:40+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Ok, figured out why the Opacity wasn't working properly, but not really sure of how to resolve it right now.  Some Cryengine material files don't have that value, so I commented it out.  I could add it back in, but if it doesn't exist then it'll crash when it runs into those cases.  I just need to test for the condition first; if it exists use that value.  If it doesn't, use 1.0.

That concludes today's episode of Bug Hunters!
## Post #19
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-05T01:57:44+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I think I fixed the Opacity and Shininess bug.  Anyone want to test against the Armored Warfare models to make sure it's working properly?

Going to also look at the $LOD models to see if I can skip those.  It may be more trouble than it's worth if it screws up the indexing though.

Tested against the Blackhawk.  Geometry looks good, but still needs work.  Normals messed up.

Blender seemed to be able to read the .dds files here?  I haven't converted them back to the old way, so not sure if Blender has been updated to handle the new .dds file formats or if I forgot I converted them.  Anyway...
## Post #20
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-05T15:32:58+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> I think I fixed the Opacity and Shininess bug.  Anyone want to test against the Armored Warfare models to make sure it's working properly?
Testing 0.83 from first post - didn't convert anything 

> Reply from Markemp
>
> Normals messed up.

Blender seemed to be able to read the .dds files here?  I haven't converted them back to the old way, so not sure if Blender has been updated to handle the new .dds file formats or if I forgot I converted them.
Normal maps DDS are in 3Dc format, not DXT1 or DXT5.
## Post #21
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-05T16:14:02+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

The mh60_mtl.mtl file (which is created by cgf-converter) seems to be working for me.  The Opacity setting is giving the right values.

d is set to 1.0 now instead of 0.  I still have to fix the double map_bump entries though.  Not sure how I'm going to do that though, since I don't think .obj files can support multiple map_bump.  Fortunately I'm working on the collada export now, although that will take a bit longer.

```
#
newmtl exterior
Kd 0.3112 0.3112 0.3112
Ks  0.1166 0.1166 0.1166
[b]d 1.0000[/b]
illum 2
map_Kd e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_exterior.dds
map_Ks e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_exterior_spec.dds
map_bump e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_exterior_ddn.dds
map_bump e:\blender projects\aw\textures/detail_bumpmaps/metal/metal_006_detail.dds

newmtl interior
Kd 0.2195 0.2195 0.2195
Ks  0.2195 0.2195 0.2195
[b]d 1.0000[/b]
illum 2
map_Kd e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_interior.dds
map_Ks e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_interior_spec.dds
map_bump e:\blender projects\aw\objects/vehicles/mh60_blackhawk/textures/mh60_interior_ddn.dds
map_bump e:\blender projects\aw\textures/detail_bumpmaps/metal/metal_006_detail.dds

```
## Post #22
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-06T08:27:12+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> The mh60_mtl.mtl file (which is created by cgf-converter) seems to be working for me.
New version didn't create anything for me, nor _mtl.mtl, nor .obj.
Old version does.
## Post #23
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-06T14:09:59+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Oh shit, forgot to mention it.  I changed the arguments so you can specify the output format.  

-obj:  Creates an obj (and related mtl) file
-blend:  Creates a Blender file (not yet implemented)
-collada|dae:  Creates a Collada file (not yet implemented)
-fbx:  Creates an FBX file (not yet implemented)
## Post #24
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-07T15:24:50+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> Oh shit, forgot to mention it.
Ok. Now it works 

> Reply from Markemp
>
> Anyone want to test against the Armored Warfare models to make sure it's working properly?
M1A1 Damaged model have a really wrong looking rear wheels:
[](http://fastpic.ru/view/75/2015/1207/feee9c5a2b8996248f42c12b47bcade6.png.html)
MH60 looks good, if I manually clean secondary bump map entries in _mtl.mtl:
[](http://fastpic.ru/view/67/2015/1207/8fae9ca77046307db3102002709111a6.png.html)
## Post #25
- Username: mgtmg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 23, 2011 3:43 pm
- Post datetime: 2015-12-08T08:29:30+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

TIP:

The .bat file from the DDSUnsplit Utility can be modified to work w/ this Utility, *.dds.0' becomes *.cgf' and of course DDSUnsplit.exe becomes cgf-converter.exe.

Save the .bat to the location of cgf-converter.exe and away you go.
## Post #26
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-08T12:55:14+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from mgtmg
>
> TIP:

The .bat file from the DDSUnsplit Utility can be modified to work w/ this Utility, *.dds.0' becomes *.cgf' and of course DDSUnsplit.exe becomes cgf-converter.exe.

Save the .bat to the location of cgf-converter.exe and away you go.

I'd love to be able to incorporate these features into the program.  It annoys me that Blender can't handle the new dds format natively.
## Post #27
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-10T16:55:04+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I put out an updated version of the tool this morning, available in the original post in this thread at the dropbox link.  Fixes a bug in reading some mtl files (if the shininess attribute didn't exist in the xml, it crashed) and for some chunk table reads (For some weird reason I had the chunk ID of the scene chunk set to 0xFF, when it doesn't have a chunk ID and I should have just used 0x00.)
## Post #28
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-12-11T08:19:27+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

does this tool also unpack .pak files? or do  i need other tools for that?
## Post #29
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-11T12:10:48+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from freakshow
>
> does this tool also unpack .pak files? or do  i need other tools for that?

You can use 7zip to unpack the .pak files.  Probably winzip too, but not positive about that.
## Post #30
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-12-11T13:28:04+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

most are encrypted zip, such as this from the russian moba Panzar : [https://mega.nz/#!nIIHlZLA!oa953W57WUmj ... btXhYOnzu0](https://mega.nz/#!nIIHlZLA!oa953W57WUmjbgcwkDh3veNNTkns3Ks0hbtXhYOnzu0)
## Post #31
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-11T13:30:28+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from freakshow
>
> most are encrypted zip, such as this from the russian moba Panzar : https://mega.nz/#!nIIHlZLA!oa953W57WUmj ... btXhYOnzu0

Oh, then no.  It doesn't do decryption.
## Post #32
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-12-12T16:21:31+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from freakshow
>
> does this tool also unpack .pak files? or do  i need other tools for that?
For RU-version I use tool from [this post](http://forum.xentax.com/viewtopic.php?p=107292#p107292).
## Post #33
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-15T16:45:38+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

The DDS unsplit tool provided by Cryengine isn't working on the new Star Citizen 2.0 dds files.  I'll try to work on a replacement.  It's a fairly simple format.
## Post #34
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-18T03:02:57+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Ok, officially released 0.84.  Thanks to Coffee, a lot of the transform issues have been fixed!  It's not perfect, but getting really close.

It works for all Star Citizen files up to 1.3.  Or should.  It'll also kinda sorta work for Star Citizen 2.0 files if they don't use the .cga/.cgam pair files (most of the ships for example), but I'm working on solving this as well.

I'm also working on a DDS Unsplit utility for the Star Citizen game files, so the textures will be available again.  Hopefully that will be done this weekend.
## Post #35
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2015-12-30T00:25:59+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

This tool makes easy work of some of the models I put away until a tool like this came around and fixed them, great work!
One question, do you ever plan to support CHR files? WarFace uses CHR to hold bones (not really important), and to also hold the highest poly mesh for that model. Noesis and other tools are nice, but there aren't any that properly export to usable formats and flip the UV's properly. I can upload an example file if need be.
## Post #36
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-30T01:12:31+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from HunterAP
>
> This tool makes easy work of some of the models I put away until a tool like this came around and fixed them, great work!
One question, do you ever plan to support CHR files? WarFace uses CHR to hold bones (not really important), and to also hold the highest poly mesh for that model. Noesis and other tools are nice, but there aren't any that properly export to usable formats and flip the UV's properly. I can upload an example file if need be.

Glad it's working out!  Still a lot of stuff that needs tweaking, but I'm getting there.

And yes, it can currently read .chr files and bone information, but I need to work on the Collada exporter so that it can export that geometry. It can export the geometry part of the .chr file to .obj though.

Some sample files would be nice.  I always like to test to make sure it works for other games!
## Post #37
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2015-12-30T05:16:30+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Here are two CHR files that don't currently work with the program, I think it may be because there are a lot of bones which get turned into their own meshes (40-50 meshes just from bones).

Keep up the great work, loving the tool so far.
## Post #38
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-30T12:19:33+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from HunterAP
>
> Here are two CHR files

Err... did you forget to add the link?
## Post #39
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2015-12-30T14:11:09+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hello! What news about SC 2.0 cga/cgam pair?
## Post #40
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2015-12-30T19:10:38+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> HunterAP wrote:Here are two CHR files 

Err... did you forget to add the link?

Whoops, I could've sworn I added the file.
Regardless, here they are.
[http://www.mediafire.com/download/3k0qu ... zr/CHR.rar](http://www.mediafire.com/download/3k0qup4dqq6dbzr/CHR.rar)
## Post #41
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-31T03:17:27+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from erik945
>
> Hello! What news about SC 2.0 cga/cgam pair?

Ran into a new issue. I assumed that the 3rd word in the Node chunk pointed to the parent, and as a general rule this is true. And if the word was 0xFFFFFFFF that it indicated the root node (i.e. no parent to it), but now with the Star Citizen 2.0+ files, I'm finding multiple Node Chunks with this as the parent.

This is both good and bad.  Good in that it may explain why there were still some objects that weren't in the right position, but bad in that now I have to figure out wtf is going on.  I think in the long run this is going to be good though.  Every bug like this gets me closer to the true logic of how objects are placed, so... just need some more time.
## Post #42
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2015-12-31T05:46:13+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I also wanted to ask, do you ever plan on working the animation (dba) files? Both Evolve and Warface use them, and any attempts I've had with figuring out what to do with them has done nothing.
## Post #43
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-12-31T12:13:04+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from HunterAP
>
> I also wanted to ask, do you ever plan on working the animation (dba) files? Both Evolve and Warface use them, and any attempts I've had with figuring out what to do with them has done nothing.

Yes, I plan on getting the .caf files (assuming .dba is similar in layout, but need to check) imported as well.  I need to be able to export to something other than .obj (which doesn't support animation), and am working on a Collada exporter for this purpose.
## Post #44
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-01-01T16:50:33+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Holy fook this is starting to get complicated for the .cga/.cgam pairs, although I've figured out the rest of the geometry issues.  I just don't know how to solve it right now.

There are node chunks for _dummy objects in the .cga files.  There is no equivalent to that in the .cgam file, but when you run into an object that has no parent identified, it is actually using the transform from the dummy file.  So now I'm trying to figure out how to get that transform while processing the .cgam file.  The only real link between the two is the name though.  I might have to build the structure based off the .cga file, then go to the .cgam file to grab the actual mesh information.

And I must have been skipping the dummy nodes previously, since this really should finish off the missing geometry issues.  I'll keep working at it though.
## Post #45
- Username: JackusCTB
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 21, 2016 11:25 pm
- Post datetime: 2016-01-21T15:28:24+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hello, while trying to convert an Armored Warfare tank from .cgf to .obj it gives me a rectangular shape... is it possible I am using it wrongly? I drag and drop the cryengine file into the executable since I didn't understand how to use the parameters...
## Post #46
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-01-22T02:27:14+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from JackusCTB
>
> Hello, while trying to convert an Armored Warfare tank from .cgf to .obj it gives me a rectangular shape... is it possible I am using it wrongly? I drag and drop the cryengine file into the executable since I didn't understand how to use the parameters...

You can't use it that way.  You have to start up a command prompt (Powershell for example) and put in the proper arguments. 

I'll be coming up with a tutorial soon.
## Post #47
- Username: JackusCTB
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 21, 2016 11:25 pm
- Post datetime: 2016-01-22T17:47:12+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> JackusCTB wrote:Hello, while trying to convert an Armored Warfare tank from .cgf to .obj it gives me a rectangular shape... is it possible I am using it wrongly? I drag and drop the cryengine file into the executable since I didn't understand how to use the parameters...

You can't use it that way.  You have to start up a command prompt (Powershell for example) and put in the proper arguments. 

I'll be coming up with a tutorial soon.
Very nice and gentle! Looking forward to it!
## Post #48
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-01-26T12:33:44+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Thank you for update. 
But some model don't converted with error " path1" "value cannot be null" or breaking.

here - example some models.
 Scout - converting breaking,
 Crucible - error
 Caterpillar - error

[https://www.dropbox.com/s/l6q1gy5ih24bu53/bugs.7z?dl=0](https://www.dropbox.com/s/l6q1gy5ih24bu53/bugs.7z?dl=0)
## Post #49
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-01-26T12:36:13+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I just uploaded a new copy last night.  Can you try it against those models?

If it gives you the same error, can you copy/paste the full command you used along with the full output?  Thanks.
## Post #50
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-01-26T12:47:02+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

This is last update, I have some problem with registration on robertsspaceindustries, so write here.

Error:

```
pillar\DRAK_Caterpillar_lod1.cga
Input file set to J:\17\Objects\Vehicles\ships\drak\caterpillar\DRAK_Caterpillar
_lod1.cga
CleanName is MultiMat_0

********************************************************************************

There was an error rendering J:\17\Objects\Vehicles\ships\drak\caterpillar\DRAK_
Caterpillar_lod1.cga

Value cannot be null.
Parameter name: path1

   at System.IO.Path.Combine(String path1, String path2)
   at CgfConverter.CryEngine..ctor(String fileName, String dataDir)
   at CgfConverter.Program.Main(String[] args)
********************************************************************************

```


Thank you.
## Post #51
- Username: MadestCat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 16, 2016 3:24 am
- Post datetime: 2016-02-15T19:29:36+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I also have a problem with converting cgf files

```
Input file set to leopard2a6--leopard2a6.cgf
Conflict in chunk definition
3088+8C
2EA120+8C
CleanName is Leopard2A6_Hull

********************************************************************************
There was an error rendering D:\leopard2a6--leopard2a6.cgf

Der Wert darf nicht NULL sein.
Parametername: path1

   bei System.IO.Path.Combine(String path1, String path2)
   bei CgfConverter.CryEngine..ctor(String fileName, String dataDir)
   bei CgfConverter.Program.Main(String[] args)
********************************************************************************

```


the German text means

```
Parameter name: path1
```
## Post #52
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-02-16T01:00:37+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Can you use the -objectdir argument?  If you extracted all the .pak files, it's the directory you extracted them to.  I extract mine to e:\blender projects\AW, so add a -objectdir "e:\blender projects\aw" to the command when I run it.  Just replace that with wherever you extracted them to.
## Post #53
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-02-23T12:15:39+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

what news about

```
Parameter name: path1
```

?
## Post #54
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-02-23T12:32:50+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from erik945
>
> what news about
Code: Select allValue cannot be null.
Parameter name: path1
?

This may be fixed.  I've updated the file at the Dropbox link in the original post.  Please test it out and let me know if you're still having the issue.
## Post #55
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-02-23T16:07:07+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

All work fine. Thank you!
## Post #56
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-03-27T14:42:06+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

New update, new problems...

Don't work with many models of new patch (2.3.0 live)

```
*** Chunk Header Table***
Chunk Type              Version   ID        Size      Offset    
SourceInfo              0         0         90        1D30      

...  

Mesh                    801       1FB       128       B09AA4    
Node                    824       1FC       CC        B09BCC    

********************************************************************************
There was an error rendering E:\67\StarCitizen\StarCitizen\Public\Data\Objects\Spaceships\Ships\MISC\Starfarer\MISC_Starfarer.cga

Unable to read beyond the end of the stream.

   at System.IO.BinaryReader.FillBuffer(Int32 numBytes)
   at System.IO.BinaryReader.ReadInt16()
   at CgfConverter.CryEngine_Core.ChunkDataStream_800.Read(BinaryReader b)
   at CgfConverter.CryEngine_Core.Model.Read_Chunks(BinaryReader reader)
   at CgfConverter.CryEngine_Core.Model.Load(String fileName)
   at CgfConverter.CryEngine_Core.Model.FromFile(String fileName)
   at CgfConverter.CryEngine..ctor(String fileName, String dataDir)
   at CgfConverter.Program.Main(String[] args)
********************************************************************************


```


I try on starfarer, scout and some other models.

[https://www.dropbox.com/s/919bw0tkrav2g ... er.7z?dl=0](https://www.dropbox.com/s/919bw0tkrav2gwe/Starfarer.7z?dl=0)
## Post #57
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-03-27T14:58:58+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I believe CIG is compressing the .mtl files now, which is causing problems for the exporter.  I'm not sure if it's possible to uncompress them manually prior to running the converter, but that may be a work around if so.
## Post #58
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-03-27T16:19:22+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

this directory that does not contain the mtl files
## Post #59
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-03T07:17:14+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Sorry to bump, but has there been ay progress with getting animations working?
## Post #60
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-05-04T01:04:09+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

No, sorry.  I've been sidetracked with other projects.   It's still on my to do list though.  I really want to get this done.
## Post #61
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-04T01:08:14+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

No rush, mate. I understand completely how it feels to be bogged down with work and life-related things.
## Post #62
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-08-12T10:42:54+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Latest available version doesn't convert materials from Armored Warfare, produces empty ones, with only header inside:

```
#

```

Previous version I have works ok:

```
#
newmtl Hull
... (cut)
```

Also newer version makes names without "_out" at the end - may overwrite something.
## Post #63
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-08-12T12:33:26+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Try exporting to Collada format.  -dae or -collada.  Let me know if that doesn't work.
## Post #64
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2016-08-12T15:33:59+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

It's fails:

```
Input file set to challenger1--challenger1.cga
Output format set to COLLADA (.dae)
Data directory set to R:\!_AW
Conflict in chunk definition
2F30+8C
62D348+8C
tmpmeshsubset ID is 33F

********************************************************************************
There was an error rendering r:\!_AW\objects\vehicles\mbt\challenger1\challenger1--challenger1.cga

Индекс находился вне границ массива. (translation: index out of massive range)

   в CgfConverter.COLLADA.WriteLibrary_Geometries()
   в CgfConverter.COLLADA.Render(String outputDir, Boolean preservePath)
   в CgfConverter.Program.Main(String[] args)
********************************************************************************
```


Older version is better, but fails too (log attached).

PS: challenger1_turret_challenger1.cgf successfully converted with older version, latests fails again:

```
Input file set to challenger1_turret_challenger1.cgf
Output format set to COLLADA (.dae)
Data directory set to R:\!_AW
Conflict in chunk definition
540+48
12ED80+48
Conflict in chunk definition
588+48
13FD30+48
Conflict in chunk definition
5D0+48
166E28+48
Conflict in chunk definition
618+48
22F830+48
tmpmeshsubset ID is 54

********************************************************************************
There was an error rendering r:\!_AW\objects\vehicles\mbt\challenger1\challenger1_turret_challenger1.cgf

Индекс находился вне границ массива.

   в CgfConverter.COLLADA.WriteLibrary_Geometries()
   в CgfConverter.COLLADA.Render(String outputDir, Boolean preservePath)
   в CgfConverter.Program.Main(String[] args)
********************************************************************************
```

[log.zip](https://xentaxbackup.github.io/file/11553_log.zip)
## Post #65
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2016-08-13T01:31:52+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Shit... ok.  I won't be able to look at it for a couple of weeks.   Going on vacation.  I might try to grab a model and poke around on my laptop, but can't promise anything.
## Post #66
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-05-23T01:17:22+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Does anyone have the most recent copy of this? That download link on the OP is 404'd, and I was really hoping to pull a couple .skinm props out of Prey (2017) to start some 3D printing projects.
## Post #67
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-05-23T01:21:56+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from windswept
>
> Does anyone have the most recent copy of this? That download link on the OP is 404'd, and I was really hoping to pull a couple .skinm props out of Prey (2017) to start some 3D printing projects.

Sorry, Dropbox decided to make all public links not so public.  I copied it over to a new link (in OP; also here:  [https://1drv.ms/u/s!Ahz_oM1_DqLRg599XP70BngTGbxUUw](https://1drv.ms/u/s!Ahz_oM1_DqLRg599XP70BngTGbxUUw)).  

I'll be working on an updated version once Star Citizen 3.0 comes out, complete with FBX exporter and armatures/animations.  Will take a while, but... yeah!
## Post #68
- Username: windswept
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 25, 2016 6:35 am
- Post datetime: 2017-05-23T01:36:56+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Thanks a ton, that worked like a damn charm.
## Post #69
- Username: Firedrake2k
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 12, 2017 4:16 pm
- Post datetime: 2017-07-12T08:33:41+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hey all!

So as per usual I'm late getting to the party (about 2 years late apparently).

I want to convert MWO files into 3D printable objects but am having one HELL of a time converting the .cgf files to .obj.  I tried using the Noesis method as described in the MWO forums but can't seem to get a hold of the cryengine_cgf.dll plugin file.  In my search for info I came across this post and thought it might be a viable option.

I'm new to this whole process so I don't know much about it but I guess my questions for the sake of this thread are:

1. Is this tool still relevant?
2. How do I download it?
3 How do I use it?

I'm not too familiar with powershell or scripting so if someone could give me a quick rundown on the process it'd be much appreciated!
## Post #70
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-07-12T12:46:38+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Firedrake2k
>
> I want to convert MWO files into 3D printable objects but am having one HELL of a time converting the .cgf files to .obj.  I tried using the Noesis method as described in the MWO forums but can't seem to get a hold of the cryengine_cgf.dll plugin file.  In my search for info I came across this post and thought it might be a viable option.

I'm new to this whole process so I don't know much about it but I guess my questions for the sake of this thread are:

1. Is this tool still relevant?
2. How do I download it?
3 How do I use it?

I'm not too familiar with powershell or scripting so if someone could give me a quick rundown on the process it'd be much appreciated!

Yup, the cgf-converter tool still works great for the MWO models.  I wrote that post on the MWO forums, so feel free to ask me any questions either here or there.

[https://mwomercs.com/forums/topic/85411 ... gis-mechs/](https://mwomercs.com/forums/topic/85411-how-to-create-your-own-art-using-pgis-mechs/)

The Youtube tutorial videos have a lot of info on how to import the mech.  To convert the files in the cgf-converter program, it's probably easiest to just click and drag the cgf/cga files you want to convert onto cgf-converter.exe in the file explorer, but a more controlled way from the powershell prompt is to do:

foreach ($file in (get-childitem -recurse *.cg*)) { cgf-converter.exe $file }

This assumes you're in the directory with all the cga/cgf files you want to convert (like Objects\Mechs\Catapult\body) and that you added the directory that cgf-converter is in to the path.  Highly recommend you add it to the path, along with the mech-importer.ps1 powershell script.  Just makes everything easier.

Feel free to ask me any questions.  I haven't done any printing so can't help on that side, but can help get the models into Blender for you.
## Post #71
- Username: Firedrake2k
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 12, 2017 4:16 pm
- Post datetime: 2017-07-14T06:58:43+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

hmm... ok I tried adding the cgf-converter.exe to the Path in Environment Variables and I keep getting this-

cgf-converter.exe : The term 'cgf-converter.exe' is not recognized as the name of a cmdlet, function, script file, or
operable program. Check the spelling of the name, or if a path was included, verify that the path is correct and try
again.
At line:1 char:53
+ ... ($file in (get-childitem -recurse *.cg*)) { cgf-converter.exe $file }
+                                                 ~~~~~~~~~~~~~~~~~
    + CategoryInfo          : ObjectNotFound: (cgf-converter.exe:String) [], CommandNotFoundException
    + FullyQualifiedErrorId : CommandNotFoundException

What am I doing wrong?

Also what is the mech-importer.ps1 script?
## Post #72
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-07-14T13:34:04+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

You need to start up a new Powershell session to get it to update the path.  The existing shells won't have the updated path, as it's not dynamically refreshed.

Mech-importer is a powershell script that takes a cdf file (like catapult.cdf) in the root of the particular mech's directory, and creates a python import script so all the parts can be put into Blender with the right orientation/location.  A mech is made up of dozens of separate components, and those components need to be told where they are relative to each other.  That's what the .cdf file has, and mech-importer just automates that process.
## Post #73
- Username: Firedrake2k
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 12, 2017 4:16 pm
- Post datetime: 2017-07-16T07:14:07+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Wow this is all a bit over my head...  Sorry for being a pain but as I said this is all new to me...

On a positive note, I did have some success with the drag and drop method you mentioned.  I am at least able to view the .obj files in 123D.  Unfortunately they import as meshes which don't allow me to modify them.  But at least its a start.  I will continue to watch your videos on blender and research on my own to see if i can figure out how to turn the meshes into solids and edit them into something I can print.  In the mean time if you have any suggestions I appreciate all your help and if I have any more questions I'll be sure to check back on here or the MWO forums to ask.

Thanks again!
## Post #74
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-07-16T22:10:34+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

You'll need a program that can modify meshes, such as Blender (free) or Max 3D.  Both these programs can handle .obj files and lets you modify them as much as you want.  I'm not sure what the process is for solidifying a mesh, but... all game models will be meshes and need a bit of work to make them printable.
## Post #75
- Username: foxhoundvenom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 15, 2017 2:24 am
- Post datetime: 2017-09-14T18:27:23+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I am trying to convert the cgf files that are from Star Citizen. When I use the program everything looks like it works fine but when I import into Blender, everything is crazy.

I will submit what I can, please let me know what I can do to help.
## Post #76
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-09-14T18:31:36+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

The converter doesn't work with the 2.6.3 Star Citizen files yet, but I have a fix that will be released in the next 2 weeks that will solve that.
## Post #77
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-10-09T01:13:56+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Here is the latest release:

[https://github.com/Markemp/Cryengine-Converter](https://github.com/Markemp/Cryengine-Converter)

Now has full support for Collada documents, armature and vertex weights, better material handling, etc.  Check out the Readme at the github for more details.

I'll be making a tutorial video and updating the original post here soon.  Thanks!
## Post #78
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-10-10T04:52:27+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> Here is the latest release:
Armored Warfare meshes (not from latest version of game) have zero dimensions after import with the latest [OpenCollada plugin](https://github.com/KhronosGroup/OpenCOLLADA/releases):
[](http://fastpic.ru/view/94/2017/1010/a2d6e4c8b1941dab8339281556fce466.png.html)

Sample is uploaded [here](https://www.mediafire.com/file/gwjb132coad775r/akatsiya2s3.zip).
## Post #79
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-10T10:06:20+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> Here is the latest release:

https://github.com/Markemp/Cryengine-Converter

Now has full support for Collada documents, armature and vertex weights, better material handling, etc.  Check out the Readme at the github for more details.

I'll be making a tutorial video and updating the original post here soon.  Thanks!

Thanks so much for this update! 
I'm not sure if the error is on my part, but Prey (2017) files result in this error: [https://cdn.pbrd.co/images/GOguhQ9.png](https://cdn.pbrd.co/images/GOguhQ9.png)

I set the programs path and used these commands "cgf-converter.exe MorganKarl_GenMaleHead01.cgf -objectdir "x:\Games\Steam\steamapps\common\Prey\GameSDK\Objects\characters\humans\MorganKarl" -dae"
The files usually have the extension .skinm instead of .cgf, however renaming them to .cgf made them work with the previous version of the tool.

If you have the time, would you be able to look into it?
Here are a few files from the game: [https://yadi.sk/d/PsyIyATX3NdATz](https://yadi.sk/d/PsyIyATX3NdATz)
## Post #80
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-11-25T02:03:36+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from o0Crofty0o
>
> 
Thanks so much for this update! 
I'm not sure if the error is on my part, but Prey (2017) files result in this error: https://cdn.pbrd.co/images/GOguhQ9.png

I set the programs path and used these commands "cgf-converter.exe MorganKarl_GenMaleHead01.cgf -objectdir "x:\Games\Steam\steamapps\common\Prey\GameSDK\Objects\characters\humans\MorganKarl" -dae"
The files usually have the extension .skinm instead of .cgf, however renaming them to .cgf made them work with the previous version of the tool.

If you have the time, would you be able to look into it?
Here are a few files from the game: https://yadi.sk/d/PsyIyATX3NdATz

Sorry I missed this; for some reason I didn't get a notification about this thread being updated.  I'll take a look at this soon.  I'm not sure what the exact error says there... can you give me the english equivalent to it?

I'm guessing it can't find the .mtl file associated with the model, but not really sure.

edit:  I think I have it, but can't do the materials since I don't have access to the .dds files.  Link to a testing version of cgf-exporter for prey files:  [https://www.dropbox.com/s/x8wlfrd16wax2 ... r.exe?dl=0](https://www.dropbox.com/s/x8wlfrd16wax2ai/cgf-converter.exe?dl=0)
## Post #81
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2017-11-25T03:53:17+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Andrakann
>
> Markemp wrote:Here is the latest release:
Armored Warfare meshes (not from latest version of game) have zero dimensions after import with the latest OpenCollada plugin:


Sample is uploaded here.

Weird... the geometry data is all zeroes.  Let me see if I can figure out what happened.
## Post #82
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-01-09T09:23:30+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I set the programs path and used these commands "J:\age> .\cgf-converter.exe .\bird_a.chr -objectdir "j:\age" -dae"
It's not working？？ didn't support this game？（archeage ol）



Ashampoo_Snap_2018.01.09_16h53m16s_001.jpg (73.46 KiB) Viewed 148 times


here is some samples~~
[https://pan.baidu.com/s/1mjYaIik](https://pan.baidu.com/s/1mjYaIik)
[https://mega.nz/#!vt4m3bYR](https://mega.nz/#!vt4m3bYR)
## Post #83
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-01-09T14:21:54+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

I haven't tested it against archeage, but it looks like a newer game.

The program is pretty dependent on having the full game structure available, so it helps to copy all the pak files into a depot and extract them into a separate (complete) depot.  I'll grab the code for this game and see if I can figure out why this model isn't working properly.
## Post #84
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-01-09T15:45:36+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> I haven't tested it against archeage, but it looks like a newer game.

The program is pretty dependent on having the full game structure available, so it helps to copy all the pak files into a depot and extract them into a separate (complete) depot.  I'll grab the code for this game and see if I can figure out why this model isn't working properly.

Thank you for your answer.I will upload more samples if you grab the code for support this game.
## Post #85
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-01-09T16:02:27+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

How did you extract the pak file?  It's 36GB, and 7zip doesn't recognize it by default.
## Post #86
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-01-10T00:23:49+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> How did you extract the pak file?  It's 36GB, and 7zip doesn't recognize it by default.

ues quickbms~~here is the bms~
[http://aluigi.altervista.org/bms/archeage.bms](http://aluigi.altervista.org/bms/archeage.bms)
It takes a long time to unzip the pak file~it's too big！
your tool support cry series ，Crysis series&other crytek engine game？？？
## Post #87
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-01-10T00:31:48+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Yup, it should support most modern Cryengine formats, including Star Citizen.  But there are lots of one-off file structures out there, and this looks like one of them.  I'll see what I can find out and update the tool to support this game as well.  Thank you!
## Post #88
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-01-10T00:38:01+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Ok, got the extractor and am getting the game files out.  May be a little while before I get the new format figured out, but shouldn't be too long.  Thank you for the info!
## Post #89
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-01-10T03:32:27+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> Ok, got the extractor and am getting the game files out.  May be a little while before I get the new format figured out, but shouldn't be too long.  Thank you for the info!
 you are welcome! It took me 1 hour to extract the file ~~~~maybe my pc is too old~~I'M looking forward to your tool 。   
sorry about my bad English~
## Post #90
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-01-10T04:49:57+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Ok, got all the files extracted, and the .cgf files seem to export nicely, aside from the materials.  Will look at the chr files, which have armatures and probably need some work.
## Post #91
- Username: phay008
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 11, 2016 11:59 am
- Post datetime: 2018-01-10T05:10:49+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> Ok, got all the files extracted, and the .cgf files seem to export nicely, aside from the materials.  Will look at the chr files, which have armatures and probably need some work.
## Post #92
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2018-02-17T19:58:17+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

In this file I try change extension to cgf and convert with cgf-converter but there was no luck. Someone has tried?
[https://mega.nz/#!Ps01AZCa!gtBQmB1E0rTO ... W1t0Iizuwc](https://mega.nz/#!Ps01AZCa!gtBQmB1E0rTOCDebZre8xpykGiCfg7K9BW1t0Iizuwc)
## Post #93
- Username: satanekk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 30, 2018 10:06 am
- Post datetime: 2018-09-02T11:53:18+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hi friends hmm i have small problem with this cgf exporter beqouse this give me file from chr mesh suspension but cga cgf give me empty file like m1a2_hull.cga i use -obj or -dae or objectdir and this give me obj or dae format but when i import file into blender 3ds or noesis file is empty but have 5mb anyone can help?:) also i try iporter from ryse but not work on armored files
## Post #94
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-09-02T13:44:41+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

The converter hasn't been tested much against some games like Ryse, so there may be some issues.  The empty import may be due to Blender (I'm assuming Blender) not being happy with the Collada file it generated, but I'd have to have access to the source model to verify.
## Post #95
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-09-06T10:05:53+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from Markemp
>
> The empty import may be due to Blender (I'm assuming Blender) not being happy with the Collada file it generated, but I'd have to have access to the source model to verify.
For latest version of AW, looks like vertex coordinates is missing in output .dae file, and all vertices in output .obj file have zeroed coordinates.
Sample models uploaded [here](http://www.mediafire.com/file/nybz6xdjxsspnq6/AW_2018-09.zip) (textures already unsplitted).
## Post #96
- Username: GentlePayload
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 28, 2018 3:27 am
- Post datetime: 2018-09-27T19:31:54+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

First off, Thank you for your work on keeping this tool up to date. Any chance there are plans to convert the .lmg animation files as well? I have been looking for a tool to do so as the Cryengine SDK no longer supports them. Hoping you at lease know of a way to do so.
## Post #97
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-09-28T02:29:55+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

> Reply from GentlePayload
>
> First off, Thank you for your work on keeping this tool up to date. Any chance there are plans to convert the .lmg animation files as well? I have been looking for a tool to do so as the Cryengine SDK no longer supports them. Hoping you at lease know of a way to do so.

It's on my list.  I think most of the animations are in .anim files, but I'll have to see what the .lmg files are as well.  Is there a particular game where you are seeing those files?
## Post #98
- Username: GentlePayload
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 28, 2018 3:27 am
- Post datetime: 2018-10-09T18:31:52+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

MWO is the game with the .lmg files. They are a cryengine format from what I have been able to tell. I have been porting mew mech models into Battletech by overwriting the meshes on existing mechs but want to build an assetbundle from scratch and want to use the animation files from MWO as a base. I will still have to build some of them from scratch but I am looking to reduce the workload as much as possible.
## Post #99
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-10-10T01:23:25+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

MWO is the game of choice I use for developing features for this app.  The animation files have been on my list for... too long.  But it will happen!
## Post #100
- Username: Maybe Magpie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 10, 2018 1:54 am
- Post datetime: 2018-10-16T08:35:42+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hi! I've managed to convert a few Prey things with this tool, but unfortunately I am having some trouble. I posted a youtube comment a little while ago and I solved the issue there, but now that I'm trying to move onto something like a player model rather than just the pistol model, I'm having some trouble. There's plenty of .skins and .skinms in the Morgan Yu model folder, but very few .cgfs (literally only the hair model worked) and renaming the skins to cgf like I saw suggested didn't work with the converter. I've been using the Prey specific release linked earlier in the the thread. 

Here's my specific error:



I feel like I'm doing something wrong, but I re-watched your youtube video a bajillion times and cannot seem to get this to work, I want to rip pretty much everything I can so I can use Blender to port it to SFM, and to also make 3D prints. Should I be using the most recent release? Am I doing something screwy?

Thanks in advance.
## Post #101
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2018-10-17T00:52:09+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

It doesn't look like you're doing anything wrong.  The powershell command looks good.  The most likely issue is that there are some new chunks in the prey models that aren't recognized by the converter yet.

Prey is on my list to look at when I have some free time.  The program really should handle that error more gracefully.
## Post #102
- Username: Maybe Magpie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 10, 2018 1:54 am
- Post datetime: 2018-10-17T04:34:57+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

If there's anything I can do to help, let me know. I can upload the Morgan files/geometry/textures and a few random props/weapons as a sampler for testing maybe?
## Post #103
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2018-10-22T01:05:05+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Any news for Archeage ? Thx
## Post #104
- Username: Maybe Magpie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 10, 2018 1:54 am
- Post datetime: 2018-10-29T23:46:51+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Any Prey news? It converted some files that were already cgf but it just doesn't seem to like handling skin/skinm files that are renamed like it worked for some people. I'm going crazy here because NinjaRipper isn't working either; it won't rip the models I need most and I can't tell why, and having full .dae stuff is better than just mesh rips.
## Post #105
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2018-11-22T17:16:07+00:00
- Post Title: Re: Cryengine Export tool (cgf-exporter)

Hello!
Thanks for your project.


Unfortunately, I encountered a number of problems when importing sc 3.3 files.
1. Converter version 1.03 creates files from which you can import only the skeleton. The geometry is present in the file, but not processed. It looks like an error in the structure of xml. Tested on a blender, autodesk collada and opencollada
2. most models of ships have problems with the transform matrix - their parts are not in their places, turned, etc.
Examples here:
[https://www.dropbox.com/s/nj4da3i10l1x8 ... ST.7z?dl=0](https://www.dropbox.com/s/nj4da3i10l1x8xg/SC_TEST.7z?dl=0)

Can you help?
Thank you.
## Post #106
- Username: TheTwilightDancer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 01, 2018 7:00 am
- Post datetime: 2018-12-22T06:41:58+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Is this currently able to extract the Prey (2017) models with the armature included or just the mesh? Considering it can't read the texture files from the game yet, I wonder if it at least reads armature. I haven't been able to get it to convert anything from Prey to DAE format, dunno if I was doing something wrong or if the tool can still only handle OBJ conversions for Prey.
## Post #107
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2019-12-31T01:40:20+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I've made some updates (v1.0.4), and this is working a lot better now.  Tested against MWO (of course), Evolve, Ghost Sniper 3, and Prey, and all good so far.  Including armatures.
## Post #108
- Username: TheTwilightDancer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 01, 2018 7:00 am
- Post datetime: 2020-01-01T22:32:38+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Sounds awesome! I'll be sure to try it out on some Prey models! This also can get the textures too?
## Post #109
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-01-01T23:51:36+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Depends on what you mean by textures.  Some Cryengine games now use a .dds format that isn't supported by much, where the .dds file has the basic info, and all the mip maps are in separate files (dds.0, dds.1, dds.2, etc).  If the converter can find the proper material file for the model, it will create materials that refer to the right texture file with just the dds extension.  But converting those to something that Blender or Maya can use ... that's a bit outside the scope of this program.

It will at least assign the right materials to the right vertices.
## Post #110
- Username: TheTwilightDancer
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Aug 01, 2018 7:00 am
- Post datetime: 2020-01-02T03:26:50+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Ahh I use Blender so that's not something that Blender will be able to use anyway, the textures of the models I want to extract are dds files. I wanna convert rigged models from Prey (2017) Like Morgan Yu, Operators, and Typhon. I have all the files, but I seem to be having trouble getting the CGF Converter to download. Someone might be using the program to extract the models anyway so I'll be keeping an eye out regardless. There are many people that wanna get a hold of Prey's models and they may likely have a program that can extract and utilize those dds files, programs of which I do not have.
## Post #111
- Username: WoodyChuck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 30, 2019 7:29 pm
- Post datetime: 2020-03-04T11:52:23+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hey I was trying the converter out and it kinda works for me in that it gets clean geometry, but it seems to miss all vertex color data. 
e.g. when converting a vegetation asset.
There also seems no way to get the physics proxy mesh atm? 
Any chance that vertex color and physics proxy mesh could be added into the output? this would help me a lot in reviving an old project!
## Post #112
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-03-04T12:18:42+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I think so?  Which game?  Vertex colors aren't used in all the CryEngine games, so I think I intentionally dumped it when I ran across the data structures.  I think Collada also supports it, so it should be something that could be added.  Same with physics proxy meshes.  I actually think those are captured, but only exist in certain files.  Can you please open an Issue on the github so this can be tracked?  Thank you!
## Post #113
- Username: WoodyChuck
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 30, 2019 7:29 pm
- Post datetime: 2020-03-04T12:56:15+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hey, as asked for, I added a GitHub issue ticket. 
[https://github.com/Markemp/Cryengine-Co ... /issues/31](https://github.com/Markemp/Cryengine-Converter/issues/31)

As already mentioned, that would be very, very helpful for me to get Vertex Color exported with the mesh and Physics proxy meshes would be cherry on top if included into the export!
The assets in question are mostly the old GameSDK, vegetation assets. Also found in original Crysis, then converted to CE3, also bundled with early versions of Amazon Lumberyard.
If you need, I can also provide one as an example.
## Post #114
- Username: zNiiC
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 01, 2020 6:56 am
- Post datetime: 2020-03-31T22:57:41+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Any chance to support Hunt: Showdown? I'd love to extract their models to 3d print
## Post #115
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-04-19T16:55:14+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Somebody was looking for a way to convert this Spriggan model, but I'm not sure which game it was for.  I've updated the converter to work with these now too.  Will release the updated version in the very near future.
## Post #116
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-04-22T02:11:51+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Version 1.0.5 is out!  Fixes a super annoying rotation issue that has been plaguing me for years.  Also verified it works great on Star Citizen 3.8 files.

Enjoy!
## Post #117
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-03T06:32:56+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

very nice work, it support Cabal 2?
## Post #118
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-05-03T12:49:52+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I'm not sure, but probably.  I don't have the game files to test this, but feel free to give it a try and let me know how it goes.  Thanks!
## Post #119
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-04T05:39:08+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Sun May 03, 2020 8:49 pm at Sun May 03, 2020 8:49 pm
>
> 
I'm not sure, but probably.  I don't have the game files to test this, but feel free to give it a try and let me know how it goes.  Thanks!
> Reply from Markemp ↑Sun May 03, 2020 8:49 pm at Sun May 03, 2020 8:49 pm
>
> 
I'm not sure, but probably.  I don't have the game files to test this, but feel free to give it a try and let me know how it goes.  Thanks!well I download again fully client and try if this work, really you do a great job here, gratz for your tool, is working with models I test, freaking awesome, thanks for your hard work, keep working hard bro.

PS: about caf files any way to convert to collada o something like that?
## Post #120
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-05-04T13:42:30+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Yup, animation files are on the to do list.  Not sure when I'll get to them though.  Working on getting vertex colors sorted out.
## Post #121
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-04T13:59:03+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Mon May 04, 2020 9:42 pm at Mon May 04, 2020 9:42 pm
>
> 
Yup, animation files are on the to do list.  Not sure when I'll get to them though.  Working on getting vertex colors sorted out.good I hope you can resolve soon, thanks for your work.
## Post #122
- Username: slinkydink
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 20, 2020 9:26 pm
- Post datetime: 2020-05-20T13:28:29+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Thanks for this tool!

Any idea why trees from Kingdom Come doesn't export correctly? Everything else from the game seems to work.
Here is a cgf to test to see the result:
[https://www31.zippyshare.com/v/FVZygJrl/file.html](https://www31.zippyshare.com/v/FVZygJrl/file.html)
## Post #123
- Username: aVSL
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 17, 2020 1:13 am
- Post datetime: 2020-08-02T15:30:43+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello! great tool! haven't you started with animation yet?
## Post #124
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2020-10-17T13:34:21+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

There seems to be a problem with the (soon to be dead) Crucible cgf files. (Maybe just different offsets?)
I'm including one example mesh in the next post.
[CrucibleModel.png](https://xentaxbackup.github.io/file/18843_CrucibleModel.png)
## Post #125
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2020-10-17T13:34:38+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

the cgf
[technomancerpillar.zip](https://xentaxbackup.github.io/file/18844_technomancerpillar.zip)
## Post #126
- Username: LotionPlayer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 20, 2020 4:10 am
- Post datetime: 2020-10-20T01:14:48+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hey hey,

So I successfully extracted and converted Hunt: Showdown's assets. However upon importing I just get a bunch of empties, except for a few select cases.

Is this indicative that the game just isn't supported? Or is something wrong?
## Post #127
- Username: Leo73
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Feb 18, 2019 5:06 am
- Post datetime: 2020-10-24T06:30:29+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hopefully a stupid question, but i seem to being unable to download from heffaypresents.com

when i click nothing happens...  

Can someone tell me what to do?
## Post #128
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2020-10-24T17:38:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Try here.  I need to fix my website, but... broken arm...

[https://github.com/Markemp/Cryengine-Co ... tag/v1.0.6](https://github.com/Markemp/Cryengine-Converter/releases/tag/v1.0.6)
## Post #129
- Username: Leo73
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Feb 18, 2019 5:06 am
- Post datetime: 2020-10-24T20:10:26+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Thank you! Your work is very helpful and much appreciated! Get well soon
## Post #130
- Username: LotionPlayer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 20, 2020 4:10 am
- Post datetime: 2020-10-26T01:06:58+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

So it seems to only be working with files that have relevant .chr and .skin files. Anything else doesn't contain any triangle data
## Post #131
- Username: HiryuX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jan 14, 2017 5:12 am
- Post datetime: 2020-10-30T15:27:54+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from LotionPlayer ↑Mon Oct 26, 2020 9:06 am at Mon Oct 26, 2020 9:06 am
>
> 
So it seems to only be working with files that have relevant .chr and .skin files. Anything else doesn't contain any triangle data

Does that mean weapons can't be extracted currently? Thanks for testing it on Hunt and reporting back your results! Appreciate any more info you can give.
## Post #132
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-01-24T17:59:19+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Released v1.0.8.  See initial post for more details.

I still need to look at the Hunt files when I have a chance.  Will probably have to wait until March though.
## Post #133
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-01-26T18:30:05+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Mon Jan 25, 2021 1:59 am at Mon Jan 25, 2021 1:59 am
>
> 
Released v1.0.8.  See initial post for more details.

I still need to look at the Hunt files when I have a chance.  Will probably have to wait until March though.

Here are a load of character and weapon models from my archive to help with that <Link removed due to site policy>
I ran the tool over all the models there, alot did convert successfully.
## Post #134
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-01-27T01:36:26+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Thank you for the models!  Are those from Hunt, and the converter worked on some of them?

If you have specific ones where it failed, let me know and I can try to see what happened with those.  Thanks!
## Post #135
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-01-27T07:43:43+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Wed Jan 27, 2021 9:36 am at Wed Jan 27, 2021 9:36 am
>
> 
Thank you for the models!  Are those from Hunt, and the converter worked on some of them?

If you have specific ones where it failed, let me know and I can try to see what happened with those.  Thanks!

They are all from Hunt showdown.
I remember the immolator grunt being a sigficant one, I will re check a number of them later.
## Post #136
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-01-27T21:19:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

These models fail to convert or have deformed meshes:
devices\attachments\hedgehog\hedgehog_frame\hedgehog_frame.skin
grunt Immolator
grunt\attachments\themed\female_01\female_01_skirt_sim_01.skin
grunt_armored
grunt_armored\brushes\grunt_armored02.cgf
hand_crossbow\attachments\receiver\receiver_01\hand_crossbow_receiver_01.skin
hfus_hair_009\hfus_hair_009.skin
hfus_lgnd_chinese_001\hfus_lgnd_chinese_001_hair.skin
molotov\attachments\fire_bomb.skin
mosin_nagant_m1891\barrel_02_avtomat\mosin_nagant_m1891_barrel_02_avtomat.skin"
## Post #137
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-02-10T19:50:58+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Also the below models from Prey 2017 have the same issue:
Cystoid
CystoidNest
LunarNightmare
Mimic
Nightmare (Specifically the Nightmare01_Outter.dae)
Weaver

Files <Link removed due to site policy>
## Post #138
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-06T15:23:46+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello, thanks for the great program. I have a question though. I'm converting mechs from MWO. However, I cannot completely change a leg, for example, but only the individual components. What could be the reason? It seems to me that some links are missing.
After converting, Powershell tells me: "conflict in chunk definition". Could it have something to do with the fact that I can't change the pose of the mech the way you can in your youtube video?
Thank you for your help
## Post #139
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-03-07T01:38:33+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

What do you mean by completely change a leg?

The conflict in chunk definition is just a warning, and shouldn't impact any conversions.  It's just a reminder to me that the MWO game files aren't exactly standard.
## Post #140
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-08T12:17:22+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Thank you for your prompt reply. In your videos you can select the foot of the mech and pull it forward and the entire leg moves with it. So you can easily change your posture. When I do this, I pull my foot forward, but the rest of the leg stays where it was originally. So I would have to change everything individually. Then the posture doesn't look realistic, but rather deformed. And it takes a lot longer. When I select the cube and move, only the cube moves, not the leg. Either I'm too stupid to use Blender or something is wrong. As I understood that, it is controlled by the IK. These are darkened in my list and not white like all other components.
## Post #141
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-08T12:25:23+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Perhaps these are missing, which is why there is no connection between the individual bones?
## Post #142
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-08T13:06:17+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

After importing the mech ich get this info
[Blender.png](https://xentaxbackup.github.io/file/19675_Blender.png)
## Post #143
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-03-08T15:09:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Got it.  Looks like there might be a bug in the importer.  I'll take a look!
## Post #144
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-03-11T03:24:01+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Since I don't see a mention of it here, how would you feel about taking a look at MechWarrior: Living Legends?

If you haven't heard of it, it's pretty much a multiplayer-based conversion mod for Crysis Wars based around MechWarrior.


I ask because while you can convert the torso files of the mechs, the converter doesn't seem to work with the leg files.
I haven't tested the files for stuff like the vehicles and weapons though, so I can't say much about those.

If you are interested, I can send some samples of the files for the Mad Cat MK II.
## Post #145
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-15T19:05:37+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I tested with the tanks, planes, towers and battle armours and it works.
I have the same problem with the legs.
## Post #146
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-03-15T19:13:55+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I'll take a look at them.  Do you know where I can find some sample leg models?
## Post #147
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-03-15T21:03:51+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

You got a pn.
## Post #148
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-04-04T16:13:50+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

is there anything new about the mech importer?
## Post #149
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-04-05T01:53:43+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Soon.  Just finishing up a project.  Sorry... lots going on still.
## Post #150
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-04-06T13:11:01+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

No hurry. I'm thankfull for your tool. if i could i would help you.
## Post #151
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-04-19T17:23:08+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello ,
i don´t know what is happen now, but i can´t import the mechs. That is what blender show me after importing the mech. Can anybody help me with this problem. 
Thanks for your help!!!
[Blender.png](https://xentaxbackup.github.io/file/19927_Blender.png)
## Post #152
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-04-23T02:21:57+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Which mech was this for?
## Post #153
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-04-25T10:04:37+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Black Lanner
## Post #154
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-04-25T10:10:00+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I also tried it with the adder but only the bones were imported. Some weeks ago i had no problems to import the mechs.
## Post #155
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-05-30T23:55:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from 09williamsad ↑Thu Jan 28, 2021 5:19 am at Thu Jan 28, 2021 5:19 am
>
> 
These models fail to convert or have deformed meshes:
devices\attachments\hedgehog\hedgehog_frame\hedgehog_frame.skin
grunt Immolator
grunt\attachments\themed\female_01\female_01_skirt_sim_01.skin
grunt_armored
grunt_armored\brushes\grunt_armored02.cgf
hand_crossbow\attachments\receiver\receiver_01\hand_crossbow_receiver_01.skin
hfus_hair_009\hfus_hair_009.skin
hfus_lgnd_chinese_001\hfus_lgnd_chinese_001_hair.skin
molotov\attachments\fire_bomb.skin
mosin_nagant_m1891\barrel_02_avtomat\mosin_nagant_m1891_barrel_02_avtomat.skin"


hello, excellent tool, any news or progress on this post about the hunt showdows models?
## Post #156
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-06-09T02:57:13+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Wed Jan 27, 2021 9:36 am at Wed Jan 27, 2021 9:36 am
>
> 
Thank you for the models!  Are those from Hunt, and the converter worked on some of them?

If you have specific ones where it failed, let me know and I can try to see what happened with those.  Thanks!


Hello, here are some of the models that present problems when decompiled, there are some others but it is the same problem
[Hunt_models_problems.rar](https://xentaxbackup.github.io/file/20265_Hunt_models_problems.rar)
## Post #157
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-06-12T13:24:08+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Think I have this figured out.  Will do a bit more testing but should have a release this weekend.
## Post #158
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-06-12T22:11:37+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

v1.1.1 release, now supporting (more) Hunt models.  Check out the initial post in this thread for the location.
## Post #159
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-06-18T08:35:56+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello. two months have passed since my last post. I would like to politely ask whether the importer's problems are being worked on or whether I can give up hope. i hope of course that i will soon be able to use the importer to assemble the mechs that i use in the game. i need your help. best regards.
## Post #160
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-06-18T21:13:04+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

The latest release added support for Hunt models.  As far as I know, they should all work now.  Is there a specific model that is giving you problems?

Also, the latest Importer version allows mechs to be imported even if the full game directory hasn't been extracted.  This was released last weekend (v2.0.7).
## Post #161
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-06-20T10:49:14+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Oh, thank you. I will try it now.
## Post #162
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-06-20T18:07:58+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I tried again today. At first I had problems installing the importer. I did that. I still can't import mechs. I then uninstalled and reinstalled blender. but i have the same problem. what am I doing wrong? in the picture you can see what blender shows me after importing.
Thank you for your help.
[blender.png](https://xentaxbackup.github.io/file/20340_blender.png)
## Post #163
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-06-20T19:30:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

The only thing I can think of at this time is you either aren't using the latest release of the importer, or you haven't extracted/converted all the game files.  The latest version specifically fixed the recursion error for missing textures, and I'm not sure what else could be causing that.

From the error you posted, I'm guessing you haven't extracted the pak files properly, or just extracted parts of them and then messed around with the directory structures.  All .pak files extract into object/ or textures/ or one of a limited number of subfolders under the game folder.  If you get rid of the relative structure, the program can't find necessary files.  

If you can take a video of what you are doing and upload it to youtube as an unlisted video, I can take a look and try to figure out what is wrong.
## Post #164
- Username: BenAD
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Mar 06, 2021 11:21 pm
- Post datetime: 2021-06-21T15:48:46+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

You are absolutely right. I accidentally changed the folder structure. I can import the mechs again. I still get an error message. The IKs don't work again. Is it me or the importer. I am really very grateful for the good help.
[blender.png](https://xentaxbackup.github.io/file/20345_blender.png)
## Post #165
- Username: jeeperdy
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Aug 29, 2021 2:11 am
- Post datetime: 2021-08-28T18:42:52+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from 09williamsad ↑Wed Jan 27, 2021 2:30 am at Wed Jan 27, 2021 2:30 am
>
> 
Markemp wrote: ↑Mon Jan 25, 2021 1:59 am
Released v1.0.8.  See initial post for more details.

I still need to look at the Hunt files when I have a chance.  Will probably have to wait until March though. 


Here are a load of character and weapon models from my archive to help with that https://mega.nz/folder/3LgWARaJ#at6I-sUttezC1b3K_CPGKg.
I ran the tool over all the models there, alot did convert successfully.

Hey I tried opening this link but it takes an insanely long time to load. Is this archive still active?

I'm only trying to grab a handful of gun models, I dont need access to the whole thing.
## Post #166
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-08-28T18:52:16+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from jeeperdy ↑Sun Aug 29, 2021 2:42 am at Sun Aug 29, 2021 2:42 am
>
> 
Hey I tried opening this link but it takes an insanely long time to load. Is this archive still active?
I'm only trying to grab a handful of gun models, I dont need access to the whole thing.

Mega currently appears to be having some issues, nothing I can do about it.
## Post #167
- Username: jeeperdy
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Aug 29, 2021 2:11 am
- Post datetime: 2021-08-28T22:00:42+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from 09williamsad ↑Sun Aug 29, 2021 2:52 am at Sun Aug 29, 2021 2:52 am
>
> 
jeeperdy wrote: ↑Sun Aug 29, 2021 2:42 am
Hey I tried opening this link but it takes an insanely long time to load. Is this archive still active?
I'm only trying to grab a handful of gun models, I dont need access to the whole thing.


Mega currently appears to be having some issues, nothing I can do about it.

Thanks, I was able to get what I needed. Thought I should let you know, though, that the bergman reciever seems to be messed up. Came out as a giant cube with messed up edges when I imported it into blender.
## Post #168
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-08-29T07:16:25+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from jeeperdy ↑Sun Aug 29, 2021 6:00 am at Sun Aug 29, 2021 6:00 am
>
> 
Thanks, I was able to get what I needed. Thought I should let you know, though, that the bergman reciever seems to be messed up. Came out as a giant cube with messed up edges when I imported it into blender.
Some are broken, cgf-exporter is not 100% compatible.
## Post #169
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-09-16T02:02:25+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

I'm hoping the animation support for the engine is still considered? Would be a nice addition  if not thank you for still updating the tool, so far is great from what i have tried.
## Post #170
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-09-20T12:28:38+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Quick bug report for Sniper Ghost Warrior Contracts.

There is a small issue with the meshes converted from this game.

The skeletons/armatures of the meshes are converted correctly, but the meshes have no weights on them when converted, so the skeleton cannot be used to move the meshes.

Cheers
## Post #171
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-09-26T23:03:05+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Released v1.3.1  The latest .exe can be found at [https://github.com/Markemp/Cryengine-Co ... tag/v1.3.1](https://github.com/Markemp/Cryengine-Converter/releases/tag/v1.3.1).

This should fix the issue with some Star Citizen files getting stuck in an endless loop, along with some additional #ivo file enhancements.
## Post #172
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-10-27T08:42:23+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Can the tool work with the animation file?hope it will be updated!
## Post #173
- Username: SoldierTODD
- Rank: beginner
- Number of posts: 35
- Joined date: Sat Oct 25, 2014 5:15 am
- Post datetime: 2021-11-21T14:12:45+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hi.
Does your Cryengine Converter work with animation files?
I need an animation from "War of Rights". Is it possible to convert animation using "Cryengine Converter"?

P.S. Sorry for my English, I use a translator.
## Post #174
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-11-28T19:15:36+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Sun Aug 30, 2015 12:24 am at Sun Aug 30, 2015 12:24 am
>
> 
Ok, I fixed the dreaded exploded geometry issue for Cryengine files!  It turns out to be several factors:

(@revelation, if you want the code specifics for your cryengine_cgf.dll for Noesis, I'll be happy to share them with you)

hello Markemp some time ago I am working on a script for noesis to import cryengine models. You tool is great but mainly I do it for study and practice in terms of analyzing the model binary files if you have if had the code specifics for cryengine_cgf.dll  I want to do an update for noesis for the new models and a version in python. to tell the truth at the moment I'm a bit tangled with bones import in python I would like to see some different approach for read of bones
## Post #175
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2021-11-28T19:37:47+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

You can check out the github where I have all the source code for the converter:  [https://github.com/Markemp/Cryengine-Converter](https://github.com/Markemp/Cryengine-Converter)

I also use 010 to analyze the binary files, and can share the templates I've made for that.  It's a lot simpler to look at, but probably not much use if you don't have the 010 editor.  Let me know if you want those though.
## Post #176
- Username: dkl77
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Oct 26, 2020 4:06 am
- Post datetime: 2021-11-28T20:43:54+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Mon Nov 29, 2021 3:37 am at Mon Nov 29, 2021 3:37 am
>
> 
You can check out the github where I have all the source code for the converter:  https://github.com/Markemp/Cryengine-Converter

I also use 010 to analyze the binary files, and can share the templates I've made for that.  It's a lot simpler to look at, but probably not much use if you don't have the 010 editor.  Let me know if you want those though.


i have already the source code for the Cryengine-Converter, thanks. and yes i use 010 editor also i really appreciate the templates if you can provide to my.
I have tried to contact (MrAdults) to see if he count whith the source code of noesis plugin for cryengine since is outdated.
and I would like to try to make an updated one for new versions of cryengine and I say try because I am new and I am learning to program and code.
## Post #177
- Username: not a russian spy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 15, 2022 11:43 am
- Post datetime: 2022-01-23T05:57:22+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello! I have been searching for a method to extract rigged models from Prey 2017. I have been trying to rename characters .skinm into .cgf files and then using the tool, but everytime I do that, I keep getting only non rigged mesh. 

If someone knows how to get models with armature, it would be really helpful if someone commented how to do that.
## Post #178
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2022-01-23T13:35:22+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

You shouldn't need to rename the extensions.  The .skin file should be the one you convert, and the converter will find the associated .skinm file and attach the geometry.  Can you take a screenshot of the command you are running?
## Post #179
- Username: not a russian spy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 15, 2022 11:43 am
- Post datetime: 2022-01-24T07:09:04+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

> Reply from Markemp ↑Sun Jan 23, 2022 9:35 pm at Sun Jan 23, 2022 9:35 pm
>
> 
You shouldn't need to rename the extensions.  The .skin file should be the one you convert, and the converter will find the associated .skinm file and attach the geometry.  Can you take a screenshot of the command you are running?

Many thanks!   I thought the .skin file was just a low poly version of the .skinm. So it works almost perfectly.
The only thing I didn't understand is, do the bones have to be so small?
I will attach a screenshot below.

(it's converted from .skin into .dae)

edit: just ran with your blender plugin and now the bones are normal sizes!
[Screenshot 2022-01-24 17-06-30.png](https://xentaxbackup.github.io/file/21669_Screenshot 2022-01-24 17-06-30.png)
## Post #180
- Username: Fenris
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 13, 2013 3:35 am
- Post datetime: 2022-02-23T13:20:53+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Hello, thanks for the tool !

I'm bumping into issue trying to convert .skin files from Kingdom Come Deliverance, with that error using the cgf-converter.exe :

```

There was an error rendering S:\KCD\Data\IPL_Heads\Objects\characters\humans\hea
d\henry.skin

Version 802 of ChunkCompiledMorphTargets is not supported

   at CgfConverter.CryEngineCore.Chunk.New[T](UInt32 version)
   at CgfConverter.CryEngineCore.Chunk.New(ChunkType chunkType, UInt32 version)
   at CgfConverter.CryEngineCore.Model.ReadChunks(BinaryReader reader)
   at CgfConverter.CryEngineCore.Model.Load(String fileName)
   at CgfConverter.CryEngine.ProcessCryengineFiles()
   at CgfConverterConsole.Program.Main(String[] args)
********************************************************************************
```


I extracted the whole .pak archives with 7zip, and I only get .skin and .mtl files (almost no .cgf ones, wich convert well into .cae using this tool).

I tried to install blender plugin for cryengine import, but .skin files (or any other for that matters) dont appear in the blender browser...

Is there anything missing here, what am I doing wrong (maybe) ?

Thanks for any help !
## Post #181
- Username: Halomaster481
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 20, 2022 1:20 pm
- Post datetime: 2022-04-20T05:27:28+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

Yea I'm also having the same problem that Fenris is having that some of the .skin files in Kingdom Come won't export giving the error of  
There was an error rendering C:\Users\senad\Kcdriped\Kingdomcome\patch\Objects\characters\humans\cloth\s2_p2_l1_v0.skin

Version 802 of ChunkCompiledMorphTargets is not supported

   at CgfConverter.CryEngineCore.Chunk.New[T](UInt32 version)
   at CgfConverter.CryEngineCore.Chunk.New(ChunkType chunkType, UInt32 version)
   at CgfConverter.CryEngineCore.Model.ReadChunks(BinaryReader reader)
   at CgfConverter.CryEngineCore.Model.Load(String fileName)
   at CgfConverter.CryEngine.ProcessCryengineFiles()
   at CgfConverterConsole.Program.Main(String[] args) 
So any help with this would be much appreciated!
## Post #182
- Username: Kenvida
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 25, 2021 6:39 pm
- Post datetime: 2022-04-20T10:27:15+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

There is any chance to pull out models in cabal 2 with animation.
Chr(+)caf using. I havn aion with caf but for aion only
## Post #183
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2022-10-09T16:24:05+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

1.4.0 is released!

Lots of goodies happening here!
Updated the solution to .Net 6 and converted many files to take advantage of file scoped namespaces (as well as general code cleanup).
Fixed material handling! It is more important than ever to ensure the game's object directory path is set up, since the converter really needs to find the material files for the model to work properly. Without it, it will create generic material names.
Implement Half type in .Net and remove references to the math toolkit.
Added an XML deserializer for Sonic Boom material files.
Added support for older Cryengine games (version 0x744 which I believe is Cryengine 1 and 2).
Fixed a bug in reading armatures for older versions (size has to be computed to get proper number of bones).

Known issues:
Older models with armatures have an issue where the armature is flipped 180 degrees from the model. This can be fixed in Blender by going into edit mode for the armature, selecting all the bones, rotating 180 degrees on the z axis, and slightly moving it on the y axis to match up with the model. Weight mapping does appear to be correct if you do it this way.
Upcoming:

Add support for USD (Pixar's model format). This seems to be the most accepted standard for generic model formats, and the direction that Blender seems to be moving.
Create new videos on how to use the converter.

Link to the download:  [https://github.com/Markemp/Cryengine-Converter/releases](https://github.com/Markemp/Cryengine-Converter/releases)
## Post #184
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2023-01-06T01:24:20+00:00
- Post Title: Re: Cryengine Converter tool (cgf-exporter)

1.5.0 is released!

Biggest fix is for Star Citizen Ivo file structures.  I finally figured out the armature rotations, so now any Ivo file with a skeleton will be properly generated.

Also a few bug fixes and cleanup.  I don't think I'll ever add FBX or direct Blender (.blend file) support, as the future for Blender seems to be with USD files.  That format is still being implemented in Blender, so once it becomes more feature complete, I'll add USD support.

Enjoy!

Link to the download: [https://github.com/Markemp/Cryengine-Converter/releases](https://github.com/Markemp/Cryengine-Converter/releases)
