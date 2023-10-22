## Post #1
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-01T01:15:25+00:00
- Post Title: Roadkill PS2 Beta Models

Hello everyone! I found this beta disk for Roadkill, a classic PS2 game. There are tools for the final game available but the beta version has a different model format and the tools break on the model files here, and there's quite a bit of unused content in this beta version that would be cool to extract. I took a crack at it myself, and been trying at it for a while now, here's how far I've gotten. 

So the collision mesh for every model, if there is one, is almost always at the top of the file, and I've managed to parse that no problem.




but unfortunately I've hit a roadblock and I'm hoping someone here with more experience than I have could give some insight. I can't seem to even get verts from anything else in the file. Using Short_Signed I've been able to kind of get a shape of the car? I think?



But there's a ton of junk data in between, i'm sure. I can't seem to pull anything else from the file though, and if I use anything other than Short_Signed then I just get a big mess of verts. 

If you look through the file, there's names for all of the meshes in the file, and I made a list of all of them to give an idea on how many submeshes there are.

```
hood_r
axlerear
fenderpass_r
object2_rd
object1_r
doordrive_rd
fenderdrive_r
body
object4_r
object3_rd
axlefront
object5_r
exhaustpass
exhaustdrive
fenderpass_rd
fenderdrive_rd
hood_rd
doorpass_r
motor
valancefront_r
doorpass_rd
wep_frontpass
wep_frontdrive
object2_r
object2_rd
valancefront_rd
wep_turretgun
body_glass1
body_glass2
body_glass3
```


The meshes starting with _r mean repaired mesh, and _rd is the damaged mesh for when the car takes too much damage on that specific part.

Any help would be appreciated, I attached the car model below, along with the separate wheel models in case those help (haven't been able to even get verts from those) 
Thanks!
[CAR01.zip](https://xentaxbackup.github.io/file/20003_CAR01.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-01T21:31:13+00:00
- Post Title: Roadkill PS2 Beta Models

Ugly format, similar to the one examined here:

> Reply from shakotay2 ↑Mon Apr 20, 2020 11:42 pm at Mon Apr 20, 2020 11:42 pm
>
> 

This point cloud is what I get (ugly, too, so dunno whether it's correct):
.



RoadkillPS2 CAR01_SMB.png (37.47 KiB) Viewed 346 times
## Post #3
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-01T23:12:18+00:00
- Post Title: Roadkill PS2 Beta Models

Yeah that kinda looks right to me, I think it might look ugly because it looks like the repaired meshes are merged with the damaged meshes. Here's some shots of this model swapped into the game, so this is how it should look.
[https://imgur.com/a/D5dGerk](https://imgur.com/a/D5dGerk)

I've been using the back as reference, mostly, since it has these two little fins.


In your cloud I can see those two fins, and the turret on top, I think the whole shape of the car might be there, unless the angle is deceiving me. It's better than anything I've been able to get anyway lol
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-02T06:58:31+00:00
- Post Title: Roadkill PS2 Beta Models

It's 130 sub meshes, so you may check them for yourself. 


 RoadkillPS2 CAR01.SMB_H2O.zip
(23.59 KiB) Downloaded 13 times


(unzip H2O files to your .SMB directory)
.
Use hex2obj (view link in my sig) with
File Open...: CAR01.SMB
then
SaveAs Mmesh (Mmesh, not mesh)

Be sure to have the "noPtC" button toggled to "PtCld" (point cloud).

You can use this py file for multiple obj import to blender (adjustment of path 'D:\\', 'tmp\\Roadkill' required, of course):

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('D:\\', 'tmp\\Roadkill')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
## Post #5
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-02T18:54:19+00:00
- Post Title: Roadkill PS2 Beta Models

Just looked at it, and yeah, it looks like everything is here.


I probably connected them improperly, but you can make out the shape of the engine popping out the top here and everything else. Considering how the meshes are split up I'm not surprised on why I wasn't able to pull much from the file myself. You got any ideas on ripping proper faces?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-02T22:03:20+00:00
- Post Title: Roadkill PS2 Beta Models

> Reply from screenracer ↑Mon May 03, 2021 2:54 am at Mon May 03, 2021 2:54 am
>
> Considering how the meshes are split upYeah, that's crazy. 

> You got any ideas on ripping proper faces?I tried faked tristrips (same as for .rws) at no avail. Assumed byte face indices and having a maximum vertex count of 40 it should not be too hard to get them (if any).
But when I checked one assumed face index block there were 10 faces only. (Too lazy to try them out.  )

You might look at 0x1270..0x128E (vertex count: 0x23) where indices 0x14, 0x15, 0x17, 0x18, (0x19), 0x1A, 0x1B, 0x1D, 0x1E, 0x20, 0x21 seem to be missing so probably that block is not a face indices' block.

Normals data assumed after signature bytes 02 80 xx xx, (3 bytes per normal?), uv data after 03 80 xx xx, assumed 2 bytes tx, 2 bytes ty.
## Post #7
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-05-02T23:22:40+00:00
- Post Title: Roadkill PS2 Beta Models

Being PS2, it uses the horrible VIF tags and packed data that are present in lots of PS2 games, which are a pain to process properly due to their complexity.  I can't see any useable face data just by looking at it, and auto-generated triangle strips don't work either.

In CAR01.SMB, this is how the VIF tags and data seem to be organised - each VIF command is highlighted in yellow.  The last one (0x00000017) is an end marker which unpacks all of the data for that section into the PS2's vector unit.  Each yellow section is a different geometry type, and usually the 3rd byte or so of each yellow entry gives the number of items for that section, so you've got 0x1a for vertices (3 Shorts), normals (3 bytes), UVs (2 Shorts), and 0xb (4 bytes) for possible triangles - although the numbers for the possible triangles seem to go beyond the vertex count for that section.  I believe (but could be wrong) that the way the data looks here is not always how it looks when unpacked.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-03T13:17:09+00:00
- Post Title: Roadkill PS2 Beta Models

After having had a look at the auto created triangle strips I came to the insight that the solution might be quads (for the tires at least):
.



tire.png (38.03 KiB) Viewed 276 times



For the car I assume you have to separate the vertices by undamaged, _r and _rd  sub meshes (but how?) before assigning quads.

Wild guess: wep_frontpass uses meshes (hex) 4A 46 4F 4C 4A 4F 4D 4C, wep_frontdrive uses 58 64 59 5A (hex)
If those numbers are below 0x82 that might be true. 

Looks like a bad idea, better collect/select them in blender's outliner window.
## Post #9
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-03T22:07:22+00:00
- Post Title: Roadkill PS2 Beta Models

Mind posting the offsets/files for the wheel? Feel like I might have better luck with a smaller file first, maybe.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-03T22:33:41+00:00
- Post Title: Roadkill PS2 Beta Models

Here you go:


 CAR01_TFL.SMB_H2O.zip
(1.4 KiB) Downloaded 18 times


.
For those who are new here: same procedure as mentioned here:

> Reply from shakotay2 ↑Sun May 02, 2021 2:58 pm at Sun May 02, 2021 2:58 pm
>
> 
but to be done with CAR01_TFL.SMB
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-04T21:40:08+00:00
- Post Title: Roadkill PS2 Beta Models

I've updated the zip file here

> Reply from shakotay2 ↑Sun May 02, 2021 2:58 pm at Sun May 02, 2021 2:58 pm
>
> 
so that the H2O files for the car are properly numbered for correct reading sequence/obj_creation process in/with hex2obj.
(_0129.obj for example is created by _0129.h2o now)

(In blender's outliner window the sorting seems spoiled again but when selecting subsequent sub meshes (by number) you'll see it works fine now, doesn't it?)

Anyways still someone needs to separate the damage/repair meshes from the normal ones.
## Post #12
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-05T00:04:35+00:00
- Post Title: Roadkill PS2 Beta Models

Well the good news is that using the ripped vertices, and enough patience, you can reconstruct the faces and recreate the meshes.



Considering what DK said, I assume we'd need a script in order to rip the proper faces right?
But I got a feel for what meshes are what now, so I can separate the damaged/repaired parts in blender though if that would help
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-05T07:59:53+00:00
- Post Title: Roadkill PS2 Beta Models

> Reply from screenracer ↑Wed May 05, 2021 8:04 am at Wed May 05, 2021 8:04 am
>
> 
Well the good news is that using the ripped vertices, and enough patience, you can reconstruct the faces and recreate the meshes.Wow! Very impressive! Did you use quads?

> But I got a feel for what meshes are what now, so I can separate the damaged/repaired parts in blender though if that would helpConsidering the faces I'm not sure any more. I applied quads to the windscreen (body_glass?) and it didn't work as it did for the tire.

So yes, we need an idea how to get the face indices from the .smb, if any.
Guess, we need a deeper understanding of the bytes after the 04040001 signature.

windscreen, 24 vertices= 0x18
# 127. 0x12da8 - 0x12de8
04 04 00 01 49 C0 0E 6E 01 04 07 0A 07 04 0D 10 0A 07 13 16 10 19 13 07
(start with 01 04..., 0x19 too big already)

```
1C 16 13 19 1F 0D 04 04 22 04 01 01 25 28 2B 2E 31 28 25 34 37 25 2E 3A 37 3D 34 25 37 3A 40 3D 28 43 2B 2B 31 46 28 28
```
## Post #14
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-05T12:01:25+00:00
- Post Title: Roadkill PS2 Beta Models

> Reply from shakotay2 ↑Wed May 05, 2021 3:59 pm at Wed May 05, 2021 3:59 pm
>
>  Wow! Very impressive! Did you use quads?

I did in some areas, just to speed things up. But I always triangulated them afterward. I didn't bother with the damaged parts though, the verts were too weirdly placed for me to understand lol. But I'm pretty sure they're correct.
## Post #15
- Username: Pileup
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 02, 2018 8:42 am
- Post datetime: 2021-05-08T10:00:58+00:00
- Post Title: Roadkill PS2 Beta Models

Trying to help screen on this one, but when I used H2, I only got one OBJ worth 32KB and a ton of errors when attempting to open the leftover OBJ in blender. If there's any chance, could I send over the SMB files and could you convert them to a point cloud? As I got the patience to put the tri's n quads in but, I've been busting my ass trying this method and it just wouldn't work for me. There's 5 cars in total including that 01 car.

-EDIT-: There's actually so much hidden stuff in this game I got no clue where to start... Tons of cars still hidden but accessible. If possible if anyone can help out get the verts etc, i'd be willing to make a contribution to them.
## Post #16
- Username: Spectresrs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 22, 2016 11:06 pm
- Post datetime: 2021-05-23T23:31:19+00:00
- Post Title: Re: Roadkill PS2 Beta Models

why are you guys doing it from scratch when this tool's full sources were available?
anyway, anyone who is still on it - [go get the new version that parses these models](https://forum.xentax.com/viewtopic.php?f=16&t=11087&p=174709#p174709)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-24T07:05:10+00:00
- Post Title: Re: Roadkill PS2 Beta Models

> Reply from Spectresrs ↑Mon May 24, 2021 7:31 am at Mon May 24, 2021 7:31 am
>
> 
why are you guys doing it from scratch when this tool's full sources were available?I don't see the point, read your own answer: 

> Reply from Spectresrs ↑Mon May 24, 2021 7:29 am at Mon May 24, 2021 7:29 am
>
> 
it has came to my attention that there exists a roadkill demo, and it has models that were removed in release, and those models are of different format that isn't immediately parsable

(Also I didn't know it's "Terminal Reality Infernal Engine" and that you (and HaDDayn) started working on it more than 3 years ago...  )

Great stuff, btw.

@screenracer:

> Reply from screenracer ↑Sat May 01, 2021 9:15 am at Sat May 01, 2021 9:15 am
>
> 
Hello everyone! I found this beta disk for Roadkill, a classic PS2 game. There are tools for the final game available but the beta version has a different model format and the tools break on the model files herewell, if you had given the link to the tools it would have spared us tons of lifetime, maybe. 

But I guess you'd missed something in your life if not having assembled car01 manually, wouldn't you?  

@me: well, try to read requester's posts more carefully
## Post #18
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-24T17:21:26+00:00
- Post Title: Re: Roadkill PS2 Beta Models

Apologies. I just wasn't sure if the creator of the tools would of been good with us using there sources and I didn't want to upset anyone. Though I guess he wouldn't of posted it publicly if that was the case, so apologies for that. Luckily he replied to my PM though, didn't think he would since it said he was inactive since 2017, lol.

But yeah, it was quite the ride assembling it from the verts. My recreation wasn't too off the mark either surprisingly. But the original's always the best, and we got the originals, yaay
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-24T17:41:55+00:00
- Post Title: Re: Roadkill PS2 Beta Models

> Reply from screenracer ↑Tue May 25, 2021 1:21 am at Tue May 25, 2021 1:21 am
>
> My recreation wasn't too off the mark either surprisingly. But the original's always the best, and we got the originals, yaayYeah, now that you can get the original could you please tell your trick, when recreating, if any? I really have not idea how someone could get such good result from a point cloud! 

> Reply from screenracer ↑Wed May 05, 2021 8:04 am at Wed May 05, 2021 8:04 am
>
> 

(Tried it with some Point Cloud Skinner in blender but the results were much far from yours.  )
## Post #20
- Username: screenracer
- Rank: beginner
- Number of posts: 26
- Joined date: Sun Sep 30, 2018 12:48 am
- Post datetime: 2021-05-24T18:16:17+00:00
- Post Title: Re: Roadkill PS2 Beta Models

> Reply from shakotay2 ↑Tue May 25, 2021 1:41 am at Tue May 25, 2021 1:41 am
>
> 
Yeah, now that you can get the original could you please tell your trick, when recreating, if any? I really have not idea how someone could get such good result from a point cloud!

Not really any tricks, just looked at the verts and connected the dots manually while looking at screenshots of the model ingame. Took a lot of time, lol. I made mistakes in some areas like under the engine or the underside of the car since it's very hard to go ingame and get references for those.
## Post #21
- Username: Spectresrs
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jul 22, 2016 11:06 pm
- Post datetime: 2021-05-24T19:28:54+00:00
- Post Title: Re: Roadkill PS2 Beta Models

> Reply from shakotay2 ↑Mon May 24, 2021 3:05 pm at Mon May 24, 2021 3:05 pm
>
> I don't see the point, read your own answer:the difference between beta and release models ended up being just a header 8 bytes shorter and a collision structure lacking a string, but all the other vertex-normals-triangles chunks are the same, so you could've saved some work applying those structures to the mesh data
...if you'd knew of that thread existing of course I mean
