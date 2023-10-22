## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-09-01T14:53:37+00:00
- Post Title: Finished games with animations?

I did a search on ANIMATION and didn't really find any useful info. Do we have some games where you actually extracted both meshes + animation? Would be really fun to play around with
## Post #2
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-10-01T23:25:28+00:00
- Post Title: Finished games with animations?

Doom 3 + Quake 4 give you the MD5mesh, complete with bones, and the MD5anim files for the in-game animations.  There are several 3dsmax plugins that let you import the mesh and an animation, the only downside is you cannot save the scene with that animation without losing the link from the bones to the mesh (the bones save the animation you import but it no longer controls the mesh).
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-10-05T22:39:55+00:00
- Post Title: Finished games with animations?

hm, that is quite cool. Because the engine i use actually only needs the model as a .fbx format and then the bones+animation in another .fbx file that you merge with script. Will try that. Thanks
## Post #4
- Username: RavynousHunter
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 07, 2008 6:00 pm
- Post datetime: 2008-10-05T23:00:27+00:00
- Post Title: Finished games with animations?

If I remember correctly, Thief I & II both store their meshes, textures, and animations in renamed *.zip files.  The TTLG community over [here](http://www.ttlg.com/forums/forumdisplay.php?f=83) has developed some nice tools for messing around with Thief; one of them being, to my best recollection, a tool that converts the meshes and whatnot into 3D Studio files, might prove useful.
## Post #5
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-10-06T00:47:31+00:00
- Post Title: Finished games with animations?

Curious, which "engine" are you speaking of that utilizes 2 FBX files for mesh and animation and bone data?  Usually FBX is a universal format for most autodesk stuff and especially for Motionbuilder, which gives you access to the mesh, and it's bone data and animation.  I use Naturalmotion Endorphin.
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-10-20T18:51:48+00:00
- Post Title: Finished games with animations?

First i want to thank you for the tip. I have extracted some characters from Quake4 to max and was able to get the animations too.

But, whenever I export the animations to fbx the exporter treats the bones as meshes. Even though the bones really are bones. It is very weird

I use the 3d engine GAMECORE [http://www.gamecore.ca](http://www.gamecore.ca)

Here is a cool pic from it with a q4 model:
## Post #7
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-10-21T18:08:31+00:00
- Post Title: Finished games with animations?

Nice work!  the animation importer imports the animation sequence as it's own mesh and will only work properly if you first import the MD5mesh file and then import an MD5anim directly after.  If you save the scene in Max, Max will lose the link to the mesh and the bones will just move on their own.
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-10-21T19:06:22+00:00
- Post Title: Finished games with animations?

I have made it animate inside max without problem. It's only at export. Is there a workaround? I think i read somewhere you can use any mesh as a bone. Should be possible to convert these "meshes" back to bones or something
