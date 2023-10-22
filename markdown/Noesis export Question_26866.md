## Post #1
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-15T18:49:36+00:00
- Post Title: Noesis export Question

Is there a way to Export each frame of an animation to the Wavefront obj format?
I've tried Export from Preview but I only get the base pose of the model.

This is to allow export of each frame as an obj file in a numbered sequence.
Those files can then be Imported using S3D which is a Tool for Silent Hunter 3.
SH3 uses MeshAnimations.

And I like to Thank Whom Ever moved this post.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-15T22:22:06+00:00
- Post Title: Noesis export Question

> Reply from 05SpeedMaster ↑Fri Jun 16, 2023 2:49 am at Fri Jun 16, 2023 2:49 am
>
> Is there a way to Export each frame of an animation to the Wavefront obj format?To my knowledge (standard) wavefront obj doesn't support animations (?). You're better of to use smd or fbx export, for example. (But that would be all frames together.)

Answer from Brian Campbell on stackoverflow, 2009: "You could potentially export one .obj per frame, but that would be cumbersome. Depending on the tools, it may be possible to export one .obj per keyframe."

On the same site: "Blender 2.63 can export animations in .obj, with each keyframe (as hypothesized above) being a complete .obj of it's own. Blender can handle this export func relatively quickly and efficiently. "

Source: [https://stackoverflow.com/questions/757 ... -animation](https://stackoverflow.com/questions/757145/do-wavefront-obj-files-support-animation)
## Post #3
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-15T22:36:40+00:00
- Post Title: Noesis export Question

Thanks for the reply.

Yeah. I guess I'll have to figure out a Work flow for what I want.
I know in 3D Max I can export meshes from a Keyframe animation to numbered obj files with a script.

I'm not a Blender user but do have 2.79b portable so I'll look into that.
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-15T22:56:52+00:00
- Post Title: Noesis export Question

> Reply from 05SpeedMaster ↑Fri Jun 16, 2023 2:49 am at Fri Jun 16, 2023 2:49 am
>
> 
Is there a way to Export each frame of an animation to the Wavefront obj format?...
Sadly, from Noesis alone you can not, that i am aware of as i have tried in the past, unless someone whips up a python script for it, by default Noesis cant do that.

Yet if your models that have animations are tied to Noesis import, you could try exporting to FBX with your desired options from Noesis, then import that FBX to Blender, i recommend current last version 3.5.x for faster imports/exports and optimized OBJ plugin too, after checking its all what you look for after imported in Blender export to Wavefront OBJ.
At the top in the option pane that just opened tick to enable Export Animations and pick your frame count start/finish, and your OBJ will be exported in a sequence manner easily to import in your other 3D editors or modding, etc.

have fun

edit: i had the page opened in my browser while i was doing some tests to see how fast is in new versions of Blender for animations import/export and didnt see shakotay already answered, oops
## Post #5
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-15T23:00:10+00:00
- Post Title: Noesis export Question

Thank You. 
I'll check into that.
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-15T23:04:20+00:00
- Post Title: Noesis export Question

> Reply from 05SpeedMaster ↑Fri Jun 16, 2023 7:00 am at Fri Jun 16, 2023 7:00 am
>
> 
Thank You. 
I'll check into that.
I would strongly recommend to avoid 3dsMax for this all together it is very buggy with FBXs exported from either Noesis/Blender or pretty much any other software NOT from their Autodesk family.
## Post #7
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-15T23:42:59+00:00
- Post Title: Noesis export Question

The whole object of the project is to enable others to easily get the animations exported as obj files.
I already have the script for Noesis to extract the meshes and animations.

It's a modified version of Jayn23's GR2 script that he helped me develop.
It's was intended to export information in a way that I could convert to the SH4 animation format.
Finding a way to convert to obj for each frame is just an extra.
## Post #8
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-16T19:16:41+00:00
- Post Title: Noesis export Question

> Reply from 05SpeedMaster ↑Fri Jun 16, 2023 7:42 am at Fri Jun 16, 2023 7:42 am
>
> ...Finding a way to convert to obj for each frame is just an extra.
In that case alone then, i strongly recommend Blender route for your workflow, the later version the better.
## Post #9
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-06-16T19:39:46+00:00
- Post Title: Noesis export Question

I tested with Blender 2.79b and it did fine.
Thanks again to both of you.
