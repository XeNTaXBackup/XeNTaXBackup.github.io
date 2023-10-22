## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-21T20:54:16+00:00
- Post Title: Titan Quest 3D Files Format

I investigate abouth how to extract animation and meshes files from this game? i read something on the forum but nothing its clear, then i post here a resume of wath i found...

The packed files are .ARC files
can be unpacked with arcexplorer
unpaked files are
.msh = Meshes
.tex  = Textures
.anm = Animations
I read something in the forums of TQ but i not see nothing good, then i post here the  ARCExplorer tool and the TextureViewer tool for .tex files this tool can open the .tex files and export 

of course i post too the .msh .anm and .tex files from one unpacked folder, i hope someone can make a script or something to read this formats.

Download Link
[http://www.megaupload.com/?d=9DSZ4IH4](http://www.megaupload.com/?d=9DSZ4IH4)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-02-23T15:34:21+00:00
- Post Title: Titan Quest 3D Files Format

The contents of this post was deleted because of possible forum rules violation.
[titan.jpg](https://xentaxbackup.github.io/file/3979_titan.jpg)
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-23T17:30:47+00:00
- Post Title: Titan Quest 3D Files Format

WTF, you rock man, i agree you this game looks very good, this game use low-medium poly  models but the models are created with the exactly number of vertexs to look very nice.

Only to understand, the animations bones are right but the base model bones bad its ok?
then i can import the animations and take the base bones from any animation and skin the model.
## Post #4
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-02-24T18:31:40+00:00
- Post Title: Titan Quest 3D Files Format

Tested, i see the bones are inverted in the half model and the animation its not loaded too. Any idea to fix this?.
## Post #5
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-03-06T17:36:05+00:00
- Post Title: Titan Quest 3D Files Format

Any progress with bone position?
## Post #6
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-03-10T00:36:52+00:00
- Post Title: Titan Quest 3D Files Format

Not only the bone position of base bones are damaged the animation bones too are damaged
I adjust the  base bones position manually, but when i load the animation this its inverted in some parts.




Any idea how to fix this?
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-03-30T23:57:12+00:00
- Post Title: Titan Quest 3D Files Format

Maybe its posible fix animations?
## Post #8
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-04-14T19:39:20+00:00
- Post Title: Titan Quest 3D Files Format

Wath its the probability of make a plugin for Noesis for this game? cause animations are amazing but i think none can make a working script to read animations right.
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-28T17:15:55+00:00
- Post Title: Titan Quest 3D Files Format

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-04-28T23:45:44+00:00
- Post Title: Titan Quest 3D Files Format

Something advance in animations?
## Post #11
- Username: gameboyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 09, 2011 7:11 pm
- Post datetime: 2011-07-09T18:36:34+00:00
- Post Title: Titan Quest 3D Files Format

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-07-09T19:34:26+00:00
- Post Title: Titan Quest 3D Files Format

Most games use point as bone.
Blender use edge as bone.
For importing skeleton in Blender we must convert point to edge .
I think, in this case bone heads are correct, but maybe bone tails are not.
I don't know.
I used Tamschi'MeshView for exporting bones as .dae format, but i get wrong armature (i used Noesis for converting .dae to another format).
Blender 249 and 25 import bad .dae format from MeshView.
## Post #13
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-13T20:50:58+00:00
- Post Title: Titan Quest 3D Files Format

This tamashi can show the animations? cause maybe i can use Gameassasin tool on this and try extract the animations.
## Post #14
- Username: gameboyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 09, 2011 7:11 pm
- Post datetime: 2011-07-26T17:25:46+00:00
- Post Title: Titan Quest 3D Files Format

> Reply from Szkaradek123
>
> Most games use point as bone.
Blender use edge as bone.
For importing skeleton in Blender we must convert point to edge .
I think, in this case bone heads are correct, but maybe bone tails are not.
I don't know.
I used Tamschi'MeshView for exporting bones as .dae format, but i get wrong armature (i used Noesis for converting .dae to another format).
Blender 249 and 25 import bad .dae format from MeshView.

sorry but i was unclear: you are great just for taking the time to pull this result out. the importer works incredibly well despite the bone problem.
i meant that, since the february version correctly exported the bones in one side, if you'd figure out how to fix the other side, i'm sure the animations would follow suit.
i know a bit of blender so i can tell you that if you move bones from their original positions after you recorded an animation, the animation will play incorrectly
the latest version of the importer seems to correctly import the armature (meaning that it's evenly distributed) but since the bones orientations are incorrect, animations are very warped.

wonder if you can solve this mistery 

by the way, i don't know if this can help but i found it around:
[http://wordwood.merseine.us/TitanQuest- ... entStart=0](http://wordwood.merseine.us/TitanQuest-MeshFileFormat/?commentStart=0)

you can find specific bone information in the comments,
4 byte for number of bones.

A bone consists of:

32 byte for name
4 byte (integer) for index of child bone
4 byte (integer) for number of childs
3 * 3 floats for axis of the bone
3 floats for position of bone
## Post #15
- Username: gameboyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 09, 2011 7:11 pm
- Post datetime: 2011-07-26T18:08:29+00:00
- Post Title: Titan Quest 3D Files Format

hold on. i might have figured out something.
let me check it out with the latest importer version, and i'll be back to you this evening.
## Post #16
- Username: gameboyo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 09, 2011 7:11 pm
- Post datetime: 2011-07-26T19:11:39+00:00
- Post Title: Re: Titan Quest 3D Files Format

Ok this is what i figured out: it is quite probable that there's a "simple" head-tail issue creating the armature problem.

I believe that you can see what's happening if you look at the armature with the octahedron bone rappresentation.
In the attached image you can see that the bones SHOULD follow the red-lined path, since a child's head must be cohincident with its parent's tail.

Szkaradek123 might it be that you're not correctly aligning heads and tails?
Furthermore, i noticed that the bones on the right side of the armature (left side of the image) is "flipped" upwards (as if mirrored on the blender file x axis: could it be that there's a "global" and "local" axes reference problem when importing?
I am ignorant on the subject, but could it be that you need to use a global axis reference for -all- bones, rather than a local axis reference? I mean, right side bones UP -must- be equal to left side bones up, right?

Lol you've hooked me on this problem Szkaradek123, what can I do to help you solve it?   



source of the problem guessing.JPG (49.09 KiB) Viewed 190 times
## Post #17
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-30T17:57:32+00:00
- Post Title: Re: Titan Quest 3D Files Format

Its true!!!! the bones should follow the red-lined path, its really posible this missalign the structure   good advance Gameboyo.
## Post #18
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2011-08-09T01:32:07+00:00
- Post Title: Re: Titan Quest 3D Files Format

I see you are making great progress on Skeletal meshes, good job! Is there anyway to export a static mesh to the Titan Quest .msh format?
## Post #19
- Username: GoatSquared
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 29, 2011 10:43 am
- Post datetime: 2011-08-29T15:41:16+00:00
- Post Title: Re: Titan Quest 3D Files Format

Great work, Szkaradek123!  I also am having the same issues the others were and was wondering if you or anyone else had had a fix for this?  Again, really great work so far, but I'm hoping the problems have been addressed since then?
## Post #20
- Username: GoatSquared
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 29, 2011 10:43 am
- Post datetime: 2011-09-25T18:53:07+00:00
- Post Title: Re: Titan Quest 3D Files Format

Well I've been trying to fix this manually and for anyone else trying to find a way to get this to work for animated meshes, it appears the quickest manual solution is to turn off deformation of the skin mesh, rotate the bones to the proper orientation, then turn back on deformation of the skin mesh and finally load the animation.

Unfortunately, I'm a very novice blender user and I can't even figure out how to do that, but I'm fairly experienced in Max and I was able to do it there using FBX.  I may have been going "the long way around", but what I did was export the skin and bones separately via FBX, imported them into Max and corrected the bone orientation, then exported just the armature for a mesh which had been animated in Blender and imported that into the same scene I had with just the skeleton and mesh.  It still screws up the bones but if you fix them a second time (and flip the normals on the mesh) you wind up with something which is about 98-100% of what you'd want.  I did this using the wolf model.  Other models may present more of a challenge but hopefully not.

I'm trying to hunt down the commands in Blender 249 to 1) turn off skin mesh deformation (while I work on the bones), 2) rotate the bones individually in Blender (with a percentage snap) and really, if you know how to do those things you can almost certainly fix them in Blender, by hand.  I'm under the assumption that when you use the python script in Blender to load the anims, that it takes whatever skeletal orientation you already have and runs with it.

If someone comes up with a fix to the script itself I and I'm sure the few hundred people who are still modding Titan Quest off and on would _really_ appreciate it.  If I come up with something better, I'll post it here so everyone can benefit.
## Post #21
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-09-27T16:51:51+00:00
- Post Title: Re: Titan Quest 3D Files Format

> Reply from GoatSquared
>
> Well I've been trying to fix this manually and for anyone else trying to find a way to get this to work for animated meshes, it appears the quickest manual solution is to turn off deformation of the skin mesh, rotate the bones to the proper orientation, then turn back on deformation of the skin mesh and finally load the animation.

Unfortunately, I'm a very novice blender user and I can't even figure out how to do that, but I'm fairly experienced in Max and I was able to do it there using FBX.  I may have been going "the long way around", but what I did was export the skin and bones separately via FBX, imported them into Max and corrected the bone orientation, then exported just the armature for a mesh which had been animated in Blender and imported that into the same scene I had with just the skeleton and mesh.  It still screws up the bones but if you fix them a second time (and flip the normals on the mesh) you wind up with something which is about 98-100% of what you'd want.  I did this using the wolf model.  Other models may present more of a challenge but hopefully not.

I'm trying to hunt down the commands in Blender 249 to 1) turn off skin mesh deformation (while I work on the bones), 2) rotate the bones individually in Blender (with a percentage snap) and really, if you know how to do those things you can almost certainly fix them in Blender, by hand.  I'm under the assumption that when you use the python script in Blender to load the anims, that it takes whatever skeletal orientation you already have and runs with it.

If someone comes up with a fix to the script itself I and I'm sure the few hundred people who are still modding Titan Quest off and on would _really_ appreciate it.  If I come up with something better, I'll post it here so everyone can benefit.

Send pm to Zskaradek, he its the blender master he can do this you tell.
