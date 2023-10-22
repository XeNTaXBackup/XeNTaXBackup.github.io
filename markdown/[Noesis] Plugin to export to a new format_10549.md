## Post #1
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-28T20:09:59+00:00
- Post Title: [Noesis] Plugin to export to a new format

Just need to figure out how to import SFX data, if that's even possible in Noesis? And is it possible to import collision data into Noesis?

Also, lets say I export my game model as .obj and then made some changes to the obj model, how/what would I have to do to export that obj model back to my game's format (via Noesis)? I have the entire structure of the file already, but I have no idea how to convert it back to normal. I was wondering, since Noesis is able to load all the supported model types, is it possible to read the model data drawn by Noesis and use that to write into the file, rather than parse the obj file directly? This way it would maximize compatibility? Also, would the bone names still be stored, since they are needed to be associated with the original skeleton file.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-06-28T22:06:36+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from Alsair
>
> The problem is, I am unable to identify the structure of the skeleton file.Why starting with bone06 which appears to be the head bone? Why not starting with the body parenting? (bone01..05)
Which kind of monster is this?

Anyway this is a dump of gr_bone.bon
from address  0x1304a6:

```
-0.023781  0.881102 -0.181916 0.000000   // rotation
 0.899672  0.024285  0.000013 0.000000
 0.004922 -0.181849 -0.881423 0.000000
-0.724543  78.850624 8.867167 1.000000  // position

-0.025428  0.879284 -0.190297 0.000000
 0.899641  0.024870 -0.005299 0.000000
 0.000082 -0.190370 -0.879636 0.000000
-0.770086 78.314934  8.512207 1.000000

-0.030081   0.873726 -0.213772 0.000000
 0.899397   0.026028 -0.020178 0.000000
-0.013406   -0.214303 -0.874011 0.000000
-0.899963   77.700729 7.514522 1.000000

-0.037345   0.863854 -0.249722 0.000000
0.898584   0.026413 -0.043013 0.000000
-0.033956   -0.251114 -0.863591 0.000000
-1.105014   76.986885 5.977794 1.000000

-0.046852   0.848857 -0.295376 0.000000
0.896779   0.024426 -0.072049 0.000000
-0.059939   -0.298069 -0.847091 0.000000
-1.376558   76.144737 4.009815 1.000000

-0.058227   0.828017 -0.347847 0.000000
0.893625   0.018603 -0.105304 0.000000
-0.089692   -0.352196 -0.823355 0.000000
-1.705532   75.148705 1.722245 1.000000

-0.071077   0.800981 -0.404199 0.000000
0.888918   0.007940 -0.140578 0.000000
-0.121545   -0.410324 -0.791745 0.000000
-2.081883   73.985062 -0.771028 1.000000

-0.084963   0.767947 -0.461561 0.000000
0.882672   -0.007873 -0.175581 0.000000
-0.153857   -0.469249 -0.752418 0.000000
-2.494184   72.657814 -3.356892 1.000000

-0.099398   0.729762 -0.517269 0.000000
0.875143   -0.028332 -0.208138 0.000000
-0.185052   -0.525971 -0.706478 0.000000
-2.929508   71.191910 -5.927074 1.000000

-0.113828   0.687936 -0.569024 0.000000
0.866827   -0.052125 -0.236418 0.000000
-0.213667   -0.577952 -0.655987 0.000000
-3.373468   69.633598 -8.382324 1.000000

-0.127633   0.644573 -0.615008 0.000000
0.858420   -0.077261 -0.259124 0.000000
-0.238378   -0.623343 -0.603837 0.000000
-3.810497   68.048309 -10.635828 1.000000

-0.140131   0.602246 -0.653959 0.000000
0.850761   -0.101291 -0.275583 0.000000
-0.258010   -0.661089 -0.553526 0.000000
-4.224190   66.516663 -12.614957 1.000000

-0.150577   0.563831 -0.685142 0.000000
0.844751   -0.121558 -0.285691 0.000000
-0.271517   -0.690881 -0.508882 0.000000
-4.597660   65.128906 -14.260590 1.000000
```


But this looks like keyframes I assume.

For the structure (i.e. the parenting) you should look at the beginning of the bon file:

Bone 11, 19
Bone 10, 19
Bone 12, 19
Bone 14, 19 etc.

What I find strange are some cut strings like "one03" (disabled bone?)
## Post #3
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-28T22:17:36+00:00
- Post Title: [Noesis] Plugin to export to a new format

Yeah I found that odd too, also I did some more research on the unknown data (after the anim frames)

It turns out

unknowndata (unused data? - 0x2423) some of the data in here controls the actual hitbox of when a monster is attacked.

I was looking at the head since that object only used one bone so I thought it would be easier to find the association/offsets for this bone.


Also, is there a way to calculate how many matrixes there are? I still can't seem to find how the game knows how many to read.

Edit:

It turns out each group of matrix is apart of one frame in the animation (just as you said), I tested this by editing some values and seeing the head disappear in a specific frame. 


Still have no clue on how to map them Noesis though x.x
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-06-29T07:34:32+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from Alsair
>
> Still have no clue on how to map them Noesis though x.xThe matrices?

Want to get the bones structure or want to display the animations?

Maybe try one step after the other.  

Don't know how comfortable Noesis is in handling animations.

For unknown animation files I tend to transfer their keyframes to .x format to get them viewed using DirectX Viewer.

Here's a snippet from my try with LastChaos Healer:

```

 FrameTransformMatrix {  1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,-0.000000,1.087123,-0.005999,1.000000;;
  }
  Frame Bip01_Pelvis {

   FrameTransformMatrix {   1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.003336,1.000000;;
   }
   Frame Bip01_Spine {

    FrameTransformMatrix {    1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,-0.000000,0.078779,0.016375,1.000000;;
    }
    Frame Bip01_Spine1 {

     FrameTransformMatrix {  1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.000000,0.000000,1.000000,0.000000,0.000000,0.119362,0.002851,1.000000;;
     }
     Frame Bip01_Spine2 {
...

```
## Post #5
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-29T09:40:33+00:00
- Post Title: [Noesis] Plugin to export to a new format

For now I was thinking of using one frame from all the bones and map them to the mesh, and if possible try to integrate frame by frame animation in Noesis. I am just hoping to get my models standing nicely rather than in one clunk of junk in the middle.

I just want to map the relevant data Noesis requires for a model to have a bone structure behind it, and if it requires matrices from one frame than that would be good.
## Post #6
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-30T02:30:39+00:00
- Post Title: [Noesis] Plugin to export to a new format

Anyways, I've updated the main topic to add in more structure data for the skeleton. I still have no clue on how to map it though, think you can post a snippet of the code for Noesis that does this?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-06-30T08:27:31+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from Alsair
>
> Anyways, I've updated the main topic to add in more structure data for the skeleton. I still have no clue on how to map it though, think you can post a snippet of the code for Noesis that does this?Well, then first of all:
What's the name of the game?
2nd: your thread title seems to lack "using Noesis"
3rd: your request seems to concern MrAdults himself. 

> Reply from MrAdults
>
> [...]hierarchical bone transforms for the skeleton. You can let Noesis do that for you too. Just set up your NoeBones with standard parent-relative matrices and then call rapi.multiplyBones. (syntax is "boneList = rapi.multiplyBones(boneList)")

In noesis\plugins\phyton I found this:
__NPReadMe.txt
	//writeanim handler should be defined as def fmtWriteAnim(anims, bsOut), where anims is a list of NoeAnim and bsOut is a NoeBitStream that should have the resulting anim binary written into it

__NPExample.txt
"Stand-alone animations cannot be written to the .noepy format."

Just wondering what's the opposite of "stand-alone" animations.

It also might be worth to look at: fmt_bulletwitch_cpr.py
#this is an example of how to use procedural animations to test your weighting (this assumes bone 11=right shoulder and bone 16=left shoulder)
#panims = [NoeProceduralAnim("bone011", 30.0, 1, 0.1), NoeProceduralAnim("bone016", 60.0, 1, 0.1)]
#anims = rapi.createProceduralAnim(cpr.boneList, panims, 100)
#mdl.setAnims(anims

or in pluginsource, bayonetta.cpp
#if 0 //create a procedural anim where bayonetta turns her upper torso and hips
	if (bones)


You might search for noeAnim in xentax forum.

There's a thread by Demonsangel (Titan Quest)
[viewtopic.php?f=16&t=8405](http://forum.xentax.com/viewtopic.php?f=16&t=8405)

Last not least: [viewtopic.php?f=33&t=4582](http://forum.xentax.com/viewtopic.php?f=33&t=4582)
## Post #8
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-30T09:19:09+00:00
- Post Title: [Noesis] Plugin to export to a new format

This looks good I will take a further look at this tomorrow. Do you have Skype or something in case I need help with something? That would be great thanks.  Also my first step is to sucessfully have the bones mapped behind the skeleton followed by the anims afterwards, I will try to find some examples relevant to my issue.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-06-30T10:35:31+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from Alsair
>
> This looks good I will take a further look at this tomorrow. Do you have Skype or something in case I need help with something?I'm not very good/productive in live communication I guess.  
But feel free to PM me.

Also I'm no expert with animations. Don't have a deeper insight in using Noesis rapi functions.
Just answered you because I'm  interested in understanding for myself how to display animations.
## Post #10
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-30T23:23:42+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from shakotay2
>
> Alsair wrote:This looks good I will take a further look at this tomorrow. Do you have Skype or something in case I need help with something?I'm not very good/productive in live communication I guess.  
But feel free to PM me.

Also I'm no expert with animations. Don't have a deeper insight in using Noesis rapi functions.
Just answered you because I'm  interested in understanding for myself how to display animations.


What else would I have to do?
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-06-30T23:50:17+00:00
- Post Title: [Noesis] Plugin to export to a new format

not always, every game is different.
there are hundreds of scripts on this site... you should check out some of chrrox's noesis scripts to learn how to do bone mapping. also, the tomb raider 2013 script also contains bone mapping and it works great. you should look at that code.
## Post #12
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-30T23:56:46+00:00
- Post Title: [Noesis] Plugin to export to a new format

Okay, I'm unable to find the Child/Parent index for each bone. Would this be located within the skeleton file or the object file itself?

Also I'm doing this but it results in an error.
## Post #13
- Username: shakotay2
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-01T03:54:05+00:00
- Post Title: [Noesis] Plugin to export to a new format

You'd have to post your full script for someone to diagnose your error, I couldn't tell you what's wrong just from that descrption.

Some things that should be clarified here:

1) In Noesis terminology, bone mapping generally refers to the process of remapping per-weight bone indices, a common practice for games that use bone palettes. This is probably not what you want.

2) When your models are "one clunk of junk in the middle", that generally means your vertices are in bone-local space. To fix this, you go through and transform your vertices using your bone matrices and weights. You need to make sure your bone matrices are all in model space too, not relative to their parents. If you have parent-local bone matrices, this can be corrected with rapi.rpgMultiplyBones. If you don't want to run through and transform your vertex positions/normals/etc. yourself, you can use the recently-added rapi.rpgSkinPreconstructedVertsToBones function:

```

```
For Noesis to do these transforms for you, you will have to feed it valid vertex weights. If your format doesn't use explicit weights and only provides a per mesh or per vertex bone index, just feed that index to Noesis for each vertex, while using a weight value of 1.0.

3) Your format, like many others, might lack any kind of "base pose" skeleton, and it provides only animation matrices. There's no real reason in terms of vertex skinning to provide a base pose when your vertices are in bone space. So yeah, you can take your matrices from a frame of animation data, and use them to skin the verts. It is quite likely, though, that those matrices will be local to each other, so you will need to use rapi.rpgMultiplyBones after you've set your bones up with matrices from a frame of animation.

4) Unlike model bone matrices, Noesis animation matrices are local to each other. Most games have animation data in local space, so you can pass it straight to Noesis. However, if animation matrices are all in absolute model space (meaning you don't have to use rapi.rpgMultiplyBones to use them as your main skeleton), you will need to put them back in parent-local space. This can be accomplished by transforming each animation matrix by the inverse of its parent bone's matrix for that particular animation frame.
## Post #14
- Username: shakotay2
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-01T04:04:48+00:00
- Post Title: [Noesis] Plugin to export to a new format

Oh, and:

> Reply from shakotay2
>
> Just wondering what's the opposite of "stand-alone" animations.
Stand-alone animations there refers to animation data without model data. For example, the BioVision Hierarchy format that Noesis supports is an animation-only format. If you wanted to support animation-only .noepy files, you'd modify that chunk of code to write out an animation-only .noepy file. The way that example script is written, it'll accept being the animation export target, but only if it's also the model export target, because it wants to combine animations into the model format.
## Post #15
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T04:58:49+00:00
- Post Title: [Noesis] Plugin to export to a new format

> Reply from MrAdults
>
> You'd have to post your full script for someone to diagnose your error, I couldn't tell you what's wrong just from that descrption.

Some things that should be clarified here:

1) In Noesis terminology, bone mapping generally refers to the process of remapping per-weight bone indices, a common practice for games that use bone palettes. This is probably not what you want.

2) When your models are "one clunk of junk in the middle", that generally means your vertices are in bone-local space. To fix this, you go through and transform your vertices using your bone matrices and weights. You need to make sure your bone matrices are all in model space too, not relative to their parents. If you have parent-local bone matrices, this can be corrected with rapi.rpgMultiplyBones. If you don't want to run through and transform your vertex positions/normals/etc. yourself, you can use the recently-added rapi.rpgSkinPreconstructedVertsToBones function:
Code: Select all	{"rpgSkinPreconstructedVertsToBones", RPGSkinPreconstructedVertsToBones, METH_VARARGS, "skins all relevant committed (via immEnd/rpgCommitTriangles) vertex components using the provided bone list. must be performed prior to rpgConstructModel. (O)"}, //args=bone list
For Noesis to do these transforms for you, you will have to feed it valid vertex weights. If your format doesn't use explicit weights and only provides a per mesh or per vertex bone index, just feed that index to Noesis for each vertex, while using a weight value of 1.0.

3) Your format, like many others, might lack any kind of "base pose" skeleton, and it provides only animation matrices. There's no real reason in terms of vertex skinning to provide a base pose when your vertices are in bone space. So yeah, you can take your matrices from a frame of animation data, and use them to skin the verts. It is quite likely, though, that those matrices will be local to each other, so you will need to use rapi.rpgMultiplyBones after you've set your bones up with matrices from a frame of animation.

4) Unlike model bone matrices, Noesis animation matrices are local to each other. Most games have animation data in local space, so you can pass it straight to Noesis. However, if animation matrices are all in absolute model space (meaning you don't have to use rapi.rpgMultiplyBones to use them as your main skeleton), you will need to put them back in parent-local space. This can be accomplished by transforming each animation matrix by the inverse of its parent bone's matrix for that particular animation frame.

1.) I just want the model standing in a way that is displayed in the game.


2.) What would you say would be the ideal method to use in my situation? The animation + bone data is all stored in a skeleton file. (Meaning it's not in local-space - not in the model) Also, I am unable to locate the child index/parent index id in the skeleton file, is this absolutely necessary? How would I go about transforming the vertices in Noesis, are there any examples that does this? Also I noticed you don't have documentation for your methods (well I couldn't find any), like msdn, or javadocs.

3.) You're right based on what I've analyzed so far. I was thinking of using one keyframe from the animation's matrices to construct the stance.

4.) Based on my analysis, I was only able to find animation data (e.g. matrices for each frame) in the skeleton.
## Post #16
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-01T12:16:40+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

NoeBone takes a string and/or an index to specify parent, for convenience. This way you can have it match bone hierarchies by names or by index. You're trying to pass in an int for the string argument, you rather want: 
```
b = NoeBone(bc, boneNames[bc], NoeMat43(list(k)), None, bc)
```
 However, that means you're passing in the the bone's index as its parent index, which translates to "no parent", so rpgMultiplyBones will hand you back the same matrices you passed it. You'll need to use the correct hierarchy, unless there really are no parents, which means your bones are all in correct space already, not needing to be multiplied and not needing to be put in parent-local space. (since they have no parents)

When I refer to model space, bone-local space, etc., I'm talking about coordinate systems, not binary locations.  So the animation data being in a different file doesn't have anything to do with what space things are in.

All the documentation there is on the Python API is in the __NPReadMe.txt file. I've been too lazy to make real documentation with example usages and all that, as the API is large enough that it would be its own undertaking, and when I have that kind of time I usually prefer to spend it actually programming. Which makes the API larger. It's a vicious cycle.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-01T13:41:40+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from Alsair
>
> This code should work with the skeletons + .bsc files I've included in my main post.It surely would if one corrected the indentation errors at line 32 and 166.  

Then I had a look at gr_010_body.bsc in Noesis and I wondered which would be the moving parts?
Although this could be solved by viewing the bot ingame
the strange bone indexing from 1 to 5, 9, 34, 36, 38, 39, 40 for the body doesn't make things clearer.

So from a practical point of view I would suggest you to start your investigation on a simpler model if any.

> Reply from MrAdults
>
> It's a vicious cycle.Hehehe, I really hope Alsair becoming your fellow Noesis follower who will create a Noesis documentation thread where he will present a collection of links to all your valuable comments you've given so far on rapi functions.

Alsair, will you?
## Post #18
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-07-01T15:22:41+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from shakotay2
>
> Hehehe, I really hope Alsair becoming your fellow Noesis follower who will create a Noesis documentation thread where he will present a collection of links to all your valuable comments you've given so far on rapi functions.

Alsair, will you?

I started something like this a year ago, the only comments I got were "don't bother".
## Post #19
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-01T17:04:02+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Who said don't bother? That would be very useful. Although my random comments wouldn't be that useful totally out of context. Real docs with my remarks in-context would be very helpful though.
## Post #20
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-07-01T17:38:31+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Can't remember really, I removed the pm's. But I basically asked for some Noesis regulars to help me since I still consider myself a rookie.
I think I removed the project from my drive so I only have this robust example attached below.


 Noesis Manual.rar
(15.78 KiB) Downloaded 53 times



The reason I wanted others to help is to filter out my errors or provide examples.
## Post #21
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T20:08:18+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> NoeBone takes a string and/or an index to specify parent, for convenience. This way you can have it match bone hierarchies by names or by index. You're trying to pass in an int for the string argument, you rather want: Code: Select allb = NoeBone(bc, boneNames[bc], NoeMat43(list(k)), None, bc) However, that means you're passing in the the bone's index as its parent index, which translates to "no parent", so rpgMultiplyBones will hand you back the same matrices you passed it. You'll need to use the correct hierarchy, unless there really are no parents, which means your bones are all in correct space already, not needing to be multiplied and not needing to be put in parent-local space. (since they have no parents)

When I refer to model space, bone-local space, etc., I'm talking about coordinate systems, not binary locations.  So the animation data being in a different file doesn't have anything to do with what space things are in.

All the documentation there is on the Python API is in the __NPReadMe.txt file. I've been too lazy to make real documentation with example usages and all that, as the API is large enough that it would be its own undertaking, and when I have that kind of time I usually prefer to spend it actually programming. Which makes the API larger. It's a vicious cycle.

The only matrices I was able to locate was the ones found in the skeleton for each frame in the animation. (Per bone)
I'm not sure if there are more, but as far as I could tell I couldn't find any additional ones.
Anyways, after setting the bones how would I go about to transforming the current model to use the bone structure? (Unless thats what setBones is supposed to do, since apparently in my case it did nothing)

@ Shakotay2
The indentation is fine when I used it, not sure why it threw you an error.


Edit:

After some more research, it looks like I may need to use rapi.rpgBindBoneIndexBufferOfs and rapi.rpgBindBoneWeightBufferOfs.
Where/What would be the BoneIndexBuffer and the BoneWeightBuffer? (Do I even need this at all?)
## Post #22
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-01T21:56:44+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

usually there's a matrix set for the bind pose, which is separate from the animation data. you have to find it. sometimes it's not a matrix set either. Tekken 6, for example, use Euler angles for bone orientations. Dynasty Warriors uses quaternions.

btw, i would remove that download link to all of the models, it might piss Rich (the author of Noesis) off lol.
## Post #23
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T22:12:30+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Oh, I didn't know it violated the rules.

The game is free to play, and the client itself is available for for anyone to download. This is merely an archive of some of the model files from the game.

I'll see what MrAdults says whether it's permitted or not, and I'll remove it based on his request.
## Post #24
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-01T22:15:51+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

oh ok, cool, then i might download it then too he he he. what game was this again?
## Post #25
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-01T22:17:51+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> oh ok, cool, then i might download it then too he he he. what game was this again?

It's an MMO game, with pretty cool models.
## Post #26
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-01T22:57:18+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

so i looked at gr_bone briefly.

did you look at the data from offsets

0x50D5 to 0x1E7E0 using a stride of 0xEF? there are 0x1B4 entries, one of the columns is a zero-based index and another 6 columns are standard little-endian floats. last two columns are short and kind of reference something... you can ignore the CDCDCDCD crap and the Bone01 one01 ne01 stuff. this appears to be the list of joints. since there are 6 float values i would try xyz and euler first... depending on if the floats are oftentimes like 1.57 (pi/2).
## Post #27
- Username: Satoh
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-02T00:30:34+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> usually there's a matrix set for the bind pose, which is separate from the animation data. you have to find it. sometimes it's not a matrix set either.
Like I said, plenty of games don't use a bind pose, especially when vertices are in bone-local space. Also like I said, given that his verts are in bone-local space, he doesn't actually need the bind pose even if it exists separately.

Regarding transforming your verts ("fitting them to the skeleton"): Again like I mentioned some posts ago, you can skin model verts to a bone list with rapi.rpgSkinPreconstructedVertsToBones. It takes a list of NoeBones as input and operates on all committed vertices in the active RPG context. As indicated by my other post.

These valuable remarks of mine would be much more valuable if people would read them.

If you can't find per-vertex weight or index values, you'll find a per-vertex-chunk bone index or it'll be dictated by the chunk ordering or whatever else the format wants to do to provide it. If you don't have per-vertex values, you can generate a bytearray from a single value to bind using something like:
```
data = noePack("i"*numVerts, *[boneIndex]*numVerts)
```
## Post #28
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T01:38:22+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> howfie wrote:usually there's a matrix set for the bind pose, which is separate from the animation data. you have to find it. sometimes it's not a matrix set either.
Like I said, plenty of games don't use a bind pose, especially when vertices are in bone-local space. Also like I said, given that his verts are in bone-local space, he doesn't actually need the bind pose even if it exists separately.

Regarding transforming your verts ("fitting them to the skeleton"): Again like I mentioned some posts ago, you can skin model verts to a bone list with rapi.rpgSkinPreconstructedVertsToBones. It takes a list of NoeBones as input and operates on all committed vertices in the active RPG context. As indicated by my other post.

These valuable remarks of mine would be much more valuable if people would read them.

If you can't find per-vertex weight or index values, you'll find a per-vertex-chunk bone index or it'll be dictated by the chunk ordering or whatever else the format wants to do to provide it. If you don't have per-vertex values, you can generate a bytearray from a single value to bind using something like:Code: Select alldata = noePack("i"*numVerts, *[boneIndex]*numVerts)

I've tried using rpgSkinPreconstructedVertsToBones on my existing Bone List, but no changes occured. I've used it after I committed the vertices.
## Post #29
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T02:09:12+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

rich, you really love making things more complex than they really are . did you look at the bon file this guy posted? he's got more problems than just figuring out which noesis function to call lol.
## Post #30
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T02:18:03+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> rich, you really love making things more complex than they really are . did you look at the bon file this guy posted? he's got more problems than just figuring out which noesis function to call lol.

Sorry if I'm bothering you guys too much, this is my first time working with 3d models, and my first time with Noesis 

I thought it would be something interesting to do.

I am a programmer, so I picked up a lot of it quite quickly.


Edit:

@howfie
I just filled that entire region with 00's and launched the game. The model loads perfectly with no issues. One thing I noticed, when I do an action (e.g. block, jump, run) and then stop (meaning it switches back to the idle standing animation) I get some frame lag.
Other than that the model appears to be normal.
## Post #31
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T02:35:17+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

it's no problem lol, you're not bothering me.
so, did you check out the data in gr_bone i asked you to check out? don't even worry about noesis yet, figure out the data and then worry about noesis.
## Post #32
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T02:36:44+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

lol? really? you filled it with zeroes and it ran hahahahahaha? ok, tell u what... lemme check out the data right now...
## Post #33
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T02:37:27+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> lol? really? you filled it with zeroes and it ran hahahahahaha?

Yep, I was pretty amazed too.

Edit:
If you haven't already, you should take a look at the structure of the Skeleton I've analyzed so far in the main post.

edit2:

In that, the four bytes (before the matrices begins) is unknown, not sure what they are for...?
## Post #34
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T02:51:38+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

oh ok, i'll take a look at it... but first i'm going to analyze the first part, before all the animation data.
## Post #35
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T02:58:26+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> oh ok, i'll take a look at it... but first i'm going to analyze the first part, before all the animation data.

I will start filling other regions with 00's to see what changes I would get. (Most of the time I would crash though.)

I'll post my findings so I can save you some time.

Edit:

Changed these two areas to 00's didn't crash (didn't screw up the model either)

The first one messed with the damage hitbox, I can hit further and do damage on monsters without even pressing the attack key.
The second one handles the the distance jumped, or the amount I slide after running, etc. I made this all into 00 which made me jump nowhere (It just showed me the jump animation)

So basically these two are unrelated to bones.


I wrote sfxData because it changed the SFX based on some bytes within that area. I will change around some more values to see what would happen.

etc. (Goes on until the count of sizeTwo)
Seems interesting, any ideas what it could be?
## Post #36
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T03:53:56+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

you wanna know something, i don't even think this game uses skeletal animation lol.
even the meshes are named Bone13 lol.
oh in gr_bone there always appears to be 0x0B55 matrices, which is part of the header.

lol, a quick test you can take one of those sections of 0x0B55 matrices, and replace the translation component with like double the values. the model should animate as though it is going to split apart, but should be the same animation. funny shit hahhahahaha. i think that first 4 bytes before the actual matrices is like an animation ID or something.
## Post #37
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T03:55:25+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> you wanna know something, i don't even think this game uses skeletal animation lol.
even the meshes are named Bone13 lol.
oh in gr_bone there always appears to be 0x0B55 matrices, which is part of the header.

lol, a quick test you can take one of those sections of 0x0B55 matrices, and replace the translation component with like double the values. the model should animate as though it is going to split apart, but should be the same animation. funny shit hahhahahaha. i think that first 4 bytes before the actual matrices is like an animation ID or something.

Yeah I'm pretty sure it doesn't use skeletal animation either, since it goes through each frame and reads the matrices for that frame and updates the model based on that.
## Post #38
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T03:59:22+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

you want me to modify those translation values for you? i can do it pretty quickly using C++. i will take a whole set of those matrices and multiply the translation values by 10 hahahahaha. then u play the game and let me know what you see.
## Post #39
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T04:03:16+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> you want me to modify those translation values for you? i can do it pretty quickly using C++. i will take a whole set of those matrices and multiply the translation values by 10 hahahahaha. then u play the game and let me know what you see.
Sure,

also I've modified bone04's animation data and replaced some of the matrices with 00's
## Post #40
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T04:09:06+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

yeah, then all this talk about weights and so on is kind of moot then. i'm no expert on noesis, but if you have the model format already figured out you should be able to dump some of this matrix data into a collada file or something and test out the animations.
## Post #41
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T04:11:52+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> yeah, then all this talk about weights and so on is kind of moot then. i'm no expert on noesis, but if you have the model format already figured out you should be able to dump some of this matrix data into a collada file or something and test out the animations.

How would I map my current model import script to one keyframe's matrices for each bone in Noesis? Pretty sure that's what has to be done to make my model appear to look right.

Also, the four bytes before the actual matrices do nothing, I've changed them to 00's nothing happened.
## Post #42
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T04:15:55+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

yeah, it appears to be just an identifier of some sort.

you'll have to ask rich or look in his documentation... i'm just not sure. but you said you're a programmer, so try a format like collada hahahaha. have some balls; don't use Noesis or else you'll be like Rich, without any balls LOL (see some other thread to find out why hahahahahahahaha).
## Post #43
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T04:49:27+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

So yeah Rich/MrAdults (That is you right?), I think the only data I can work with to make my models have a proper "stance" is to use this data:

The matrices from one of the animation key frame. However, based on your posts, you implied there was a skeleton with weights, parent-child indexes etc, that this lacks. So I was wondering if there's a solution that can map just those matrices with my model?

Each model also have a list of bonenames (as string) that references the one in the skeleton file (I've tested this by changing the name on either file, resulting in a crash).

So how would I associate the bonename found in the model file, with that very same bone's first keyframe matrices data found in the skeleton file?

This is pretty much all I need, I can deal with animations in the future.
## Post #44
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T05:21:04+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

for gr_bone.bon, at offset 0x2034E, you have 0x40 bytes of pointer data. it consists of a null terminated mesh name, Bone07, followed by a bunch of 0xCDCDCDCD values (invalid pointer).

the next 4 bytes is the identifier

the next 0x2D540 bytes is 0xB55 matrices, which are used to transform the Bone07 mesh in some way.

then at offset 0x4D8D2 is the next item in the list, the matrices to modify Bone01.
## Post #45
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T05:29:56+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> for gr_bone.bon, at offset 0x2034E, you have 0x40 bytes of pointer data. it consists of a null terminated mesh name, Bone07, followed by a bunch of 0xCDCDCDCD values (invalid pointer).

the next 4 bytes is the identifier

the next 0x2D540 bytes is 0xB55 matrices, which are used to transform the Bone07 mesh in some way.

then at offset 0x4D8D2 is the next item in the list, the matrices to modify Bone01.

I know  I am already parsing it in my script (check first page).


Unless this is for MrAdults?
## Post #46
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T05:49:45+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

oh cool, let us know how it goes lol.
## Post #47
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T08:53:19+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Well I dealt with parsing few days ago already hence the code on the first page, like I have said before stuck on how to use this data to structure the model. I have tried with MrAdults suggested but to no avail. So I wont be able to make much progress until I can figure this out. I hope MrAdults has some clues to this issue.
## Post #48
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-02T09:59:13+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Apart from the coding problems: in lack of a skeleton I took some bones positions from their first frame each and tried to paint a skeleton.

```
Bone01 -0.113336   34.896465 10.198335       175 91
Bone02 0.138354   44.527958 11.276074        222.5	96.5
Bone03 0.049265   50.583954 12.362673		253  101.8
Bone04 -0.195766   58.654728 10.172757		293.5 90.85
Bone05 -0.465472   71.594223 10.358674		358	91.75
Bone06, head -0.724543   78.850624 8.867167		394	84.3
Bone16 -0.018533   94.250137 -7.828193		471	1
Bone17 -3.997004   106.748070 14.560293	534	112.8
Bone18 -15.395306   107.772560 34.416512	-> 539	212
```

from gr_bone.bon
ignoring the x position, so turning your head 90 degrees clockwise you'll find the peak being the head  :

[](http://www.pic-upload.de/view-19922304/bones_pos.jpg.html)

edit: hmm, well, no. The peak being Bone16, shxt

edit3: huuh, complete rewrite! Each bone having its own keyframe set in .x.

I'll try to create one...
## Post #49
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-02T12:11:30+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

It's no bother, I appreciate when people pick up Noesis. More users and more developers means more use and more opportunity to find and fix issues.

The vert skin function didn't do anything because you didn't provide weights. Use the line of code from my last post to generate a list of per-vertex bone indices from a single index. That is what this format is going to use, you can tell by looking at the model.

> Reply from howfie
>
> rich, you really love making things more complex than they really are . did you look at the bon file this guy posted? he's got more problems than just figuring out which noesis function to call lol.
You need to understand the core concepts of transform spaces and skinning to work with model formats. He's clearly new to this. lol, lol, hahahahaha, lol, and so on.

> Reply from howfie
>
> you wanna know something, i don't even think this game uses skeletal animation lol.
even the meshes are named Bone13 lol.
You know how the verts are untransformed, so they look like they're in a clump? And you know those things that help you transform that clump of verts? And there's a lot of that data beyond a single pose worth...as if it's, like animating? Well... that's what we call "skeletal animation". 

> Reply from Alsair
>
> How would I map my current model import script to one keyframe's matrices for each bone in Noesis? Pretty sure that's what has to be done to make my model appear to look right.
You have to bind bone indices like I mentioned above. Then use the skin function with your bone list. To bind bone indices, you have to know which chunk of verts goes to which bone. This could be implicit, if you have the same number of mesh chunks as bones, and I'm guessing you do. If that's so, you'd do something like this for each mesh:

```
boneWeights = noePack("f"*numVerts, *[1.0]*numVerts)
rapi.rpgBindBoneIndexBuffer(boneIndices, noesis.RPGEODATA_INT, 4, 1)
rapi.rpgBindBoneWeightBuffer(boneWeights, noesis.RPGEODATA_FLOAT, 4, 1)

```
Then you proceed to do your rpgCommitTriangles call as per usual.

Note that I haven't actually looked at these files at all.  I haven't been implying anything, I've just been telling you all of the common possibilities. In your case it's most likely what I just said, based on the pic of the model and your description of the data. The actual matrices may be flattened with no hierarchy. You'll have to figure out how to actually turn that anim data into matrices for it to look right, though. I'd take a glance at the hex, but I'm on my way to work, so you'll have to rely on the degenerate I'm about to quote for that part. Or on shakotay, who seems to be more interested in looking at and understanding the data than hahahaha lol'ing, which is a good start.

> Reply from howfie
>
> have some balls; don't use Noesis or else you'll be like Rich, without any balls LOL (see some other thread to find out why hahahahahahahaha). I appreciate your need to be retarded, but please don't encourage prospective Noesis users to also be retarded. hahahahaha lol.

It's trivial to push nothing but animation matrices to Noesis, and it will give you a stick figure displaying the animations. Just create the NoeModel with no mesh data, giving it your NoeAnim instead.
## Post #50
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-02T13:26:42+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

I used Noesis to export gr_trans_110.bsc as fbx.

Then converted it to ASCII-fbx; now at least having the damn bone names: 

```
	NodeAttribute: 34246792, "NodeAttribute::bone_RArm05x_skel", "LimbNode" {
	NodeAttribute: 34248064, "NodeAttribute::bone_LArm05x_skel", "LimbNode" {	
	NodeAttribute: 34249560, "NodeAttribute::bone_cutter01_skel", "LimbNode" {
	NodeAttribute: 34251248, "NodeAttribute::bone_RArm05x01_skel", "LimbNode" {
	NodeAttribute: 34252760, "NodeAttribute::bone_LArm05x01_skel", "LimbNode" {
	NodeAttribute: 34254272, "NodeAttribute::bone_root_skel", "LimbNode" {
	NodeAttribute: 34255984, "NodeAttribute::bone01_skel", "LimbNode" {
	NodeAttribute: 34257552, "NodeAttribute::bone01 Footsteps_skel", "LimbNode" {
	NodeAttribute: 34259080, "NodeAttribute::bone01 Pelvis_skel", "LimbNode" {
	NodeAttribute: 34260592, "NodeAttribute::bone01 Spine_skel", "LimbNode" {
	NodeAttribute: 34262104, "NodeAttribute::bone01 Spine1_skel", "LimbNode" {
	NodeAttribute: 34263648, "NodeAttribute::bone01 Neck_skel", "LimbNode" {
	NodeAttribute: 34265208, "NodeAttribute::bone01 Head_skel", "LimbNode" {
	NodeAttribute: 34266768, "NodeAttribute::bone_RArm01_skel", "LimbNode" {
	NodeAttribute: 34268304, "NodeAttribute::bone_RArm02_skel", "LimbNode" {
	NodeAttribute: 34270088, "NodeAttribute::bone_RArm03_skel", "LimbNode" {
	NodeAttribute: 34271728, "NodeAttribute::bone_RArm04_skel", "LimbNode" {
	NodeAttribute: 34273368, "NodeAttribute::bone_RArm05_skel", "LimbNode" {
	NodeAttribute: 34275088, "NodeAttribute::bone_LArm01_skel", "LimbNode" {
	NodeAttribute: 34276816, "NodeAttribute::bone_LArm02_skel", "LimbNode" {
	NodeAttribute: 34278536, "NodeAttribute::bone_LArm03_skel", "LimbNode" {
	NodeAttribute: 34280256, "NodeAttribute::bone_LArm04_skel", "LimbNode" {
	NodeAttribute: 34281976, "NodeAttribute::bone_LArm05_skel", "LimbNode" {
	NodeAttribute: 34283696, "NodeAttribute::bone01 L Thigh_skel", "LimbNode" {
	NodeAttribute: 34285376, "NodeAttribute::bone01 L Calf_skel", "LimbNode" {
	NodeAttribute: 34287096, "NodeAttribute::bone01 L Foot_skel", "LimbNode" {
	NodeAttribute: 34288816, "NodeAttribute::bone01 L Toe0_skel", "LimbNode" {
	NodeAttribute: 34290536, "NodeAttribute::bone01 R Thigh_skel", "LimbNode" {
	NodeAttribute: 34292256, "NodeAttribute::bone01 R Calf_skel", "LimbNode" {
	NodeAttribute: 34293976, "NodeAttribute::bone01 R Foot_skel", "LimbNode" {
	NodeAttribute: 34296400, "NodeAttribute::bone01 R Toe0_skel", "LimbNode" {
	NodeAttribute: 34298392, "NodeAttribute::bone_cutter02_skel", "LimbNode" {
	NodeAttribute: 34300112, "NodeAttribute::bone_RArm05x02_skel", "LimbNode" {
	NodeAttribute: 34301832, "NodeAttribute::bone_LArm05x02_skel", "LimbNode" {
	NodeAttribute: 34303552, "NodeAttribute::Bone99_skel", "LimbNode" {
	NodeAttribute: 34305192, "NodeAttribute::Bone98_skel", "LimbNode" {
```
## Post #51
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T13:44:10+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

well rich, you should have never said that one thing about your wife having your balls .

shakotay, did you get a good skeleton out of it? i tried yesterday loading what i thought was skeleton data in the gr_bone.bon file and this is what i got:
## Post #52
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T14:52:14+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

did you guys notice that there are also a lot of stray points in these models? in shakotay's gr_trans_110, half of the vertices are stray. i'm still not convinced this game uses skeletal animation, flattened hierarchies or otherwise (there's no blend indices or blend weights), seeing the models look like this. see that ring on the model? that's the "bone01 Spine1" mesh. you see now why i'm loling?
## Post #53
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-02T15:54:54+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> shakotay, did you get a good skeleton out of it?Nope.
I was just looking at Alsair's python file. Seems he tries to combine the bsc and the bon file data.
Well done, Alsair!

Maybe there's only a "trifle" missing.

But now it's my jogging time.
See u later, guys.
## Post #54
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T20:39:46+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Okay,  now I'm getting an "WARNING: Mesh contains bone weights, but the model has no skeleton." error, not sure how to solve it.

But one thing I know for sure this script is missing, is that there is no association with the bone names in the skeleton with the bone names in the actual model file (so I can associate the correct bone with each mesh piece), not sure how to do this either. Here's what I have so far:

There's also a lot of unused variables, I'll likely clean this code up after it's complete.

Edit:

Does this have to do with the Bone List being mapped? Because the game references the bones via string identifiers whereas here we're using the incremental id used in the for loop. Could it be it's referencing the wrong bones this way? Still I don't understand why it would get the "but the model has no skeleton" error. Weird.

Also, the actual mesh pieces appear to be scattered everywhere now. (Assuming that there is no real reference from the model's bone string to the string in the skeleton file)
## Post #55
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T22:05:45+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Made my own attempt on adding association with the skeleton to the mesh files, still no luck meshes is scattered in different places.
Edit:

I noticed that rapi.rpgBindBoneWeightBuffer had no effect on the transformation of the model, I commented it and saw no changes.
## Post #56
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T22:45:20+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

you are not calling

mdl.setBones(your bonelist)
## Post #57
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T23:15:44+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> you are not calling

mdl.setBones(your bonelist)

Pretty sure rapi.rpgSkinPreconstructedVertsToBones(bones) does that for me now.

edit:

Nvm, mdl.setBones(bones) didn't change the structure, but it allowed me to view the bones (via F6).
## Post #58
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-02T23:42:20+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

got a pic? which model u looking at? did you look at the vertex buffer and see valid blend weights and blend indices? cuz that's what you are binding in your noesis cose.
## Post #59
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-02T23:57:44+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from howfie
>
> got a pic? which model u looking at? did you look at the vertex buffer and see valid blend weights and blend indices? cuz that's what you are binding in your noesis cose.

Can't say for sure, but look at that model using that noesis script. the head and stuff are in the correct places, except the it's not pointing the right direction...
## Post #60
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-03T00:15:20+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

That's an easy fix. Don't plop the NoeMat44 data into a NoeMat43, use NoeMat44's toMat43() method instead. They aren't the same major, so it's not the same operation.
## Post #61
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-03T00:20:09+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> That's an easy fix. Don't plop the NoeMat44 data into a NoeMat43, use NoeMat44's toMat43() method instead. They aren't the same major, so it's not the same operation.

YES IT WORKS! Damn man, couldn't believe this was the issue. Kinda amazed.

Some models don't have the textures mapped correctly though... Dunno why, the UV positions are correct.
## Post #62
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-03T00:22:32+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Congratulations, and well done.
## Post #63
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-03T00:26:13+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> Congratulations, and well done.

Looks pretty good, now since all the animation data is stored in each key frame, implementing animation support wouldn't be too difficult in Noesis right?


What would be the best approach for this?
## Post #64
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-03T00:27:21+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

nice, i tell ya, you're amazing rich, despite having no balls lolololl hahahahahahah
## Post #65
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-03T00:31:19+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Okay, I got pretty much everything fixed and done. I was wondering if there is a way to import each keyframe as an animation into Noesis? Is there any particular method to use?
## Post #66
- Username: errno
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-03T03:30:42+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Yeah, it should be easy, especially since your hierarchy is flattened. You don't have to worry about whether or not the bones are local to their parents.

NoeAnims are basically just made up NoeMat43's, and a set of bones. You can give it the exact same set of bones you're currently attaching to your model. The matrices are expected to be ordered as yours already are, ( (matrix for each bone) * numframes ), as opposed to ( (matrix for each frame) * numbones ). So you can read all of your matrices into a flat list of NoeMat43 and do something like this:

```
#...
#run through here and build noemat43's for each bone in each frame and frameMats.append(mat) for each one
#...
#NoeAnim args are sequence name, NoeBone list for base skeleton (hierarchy is the only thing these bones are used for, their matrices aren't important), frame count, the whole batch of frame matrices for all bones and all frames, and framerate
anim = NoeAnim("singlesequence", modelBones, numFramesOfAnimation, frameMats, 30.0) 
#mdl is your already-constructed NoeModel
mdl.setAnims([anim])
```
## Post #67
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-03T03:45:23+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> Yeah, it should be easy, especially since your hierarchy is flattened. You don't have to worry about whether or not the bones are local to their parents.

NoeAnims are basically just made up NoeMat43's, and a set of bones. You can give it the exact same set of bones you're currently attaching to your model. The matrices are expected to be ordered as yours already are, ( (matrix for each bone) * numframes ), as opposed to ( (matrix for each frame) * numbones ). So you can read all of your matrices into a flat list of NoeMat43 and do something like this:
Code: Select allframeMats = []
#...
#run through here and build noemat43's for each bone in each frame and frameMats.append(mat) for each one
#...
#NoeAnim args are sequence name, NoeBone list for base skeleton (hierarchy is the only thing these bones are used for, their matrices aren't important), frame count, the whole batch of frame matrices for all bones and all frames, and framerate
anim = NoeAnim("singlesequence", modelBones, numFramesOfAnimation, frameMats, 30.0) 
#mdl is your already-constructed NoeModel
mdl.setAnims([anim])

Awesome, I gotta fix one thing though  

Seems like I'm not passing through all of that data correctly in some bones. So I'm going to take a further look at that and find a permanent solution to it.

Edit:  Ok I have fixed that issue as well.
Also I was wondering if theres a way to import multiple models into Noesis, like the head body and arms models all together to form a new combined model.

Oh and is it possible to add sound effects support with the anims?

Edit:

Okay, got animations implemented (and they're grouped the same way the model groups them near the header). Just need to figure out how to import SFX data, if that's even possible in Noesis? And is it possible to import collision data into Noesis?

Also, lets say I export my game model as .obj and then made some changes to the obj model, how/what would I have to do to export that obj model back to my game's format (via Noesis)? I have the entire structure of the file already, but I have no idea how to convert it back to normal. I was wondering, since Noesis is able to load all the supported model types, is it possible to read the model data drawn by Noesis and use that to write into the file, rather than parse the obj file directly? This way it would maximize compatibility? Also, would the bone names still be stored, since they are needed to be associated with the original skeleton file.
## Post #68
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-07-04T06:24:49+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from Alsair
>
> And is it possible to import collision data into Noesis?Since this is an unanswered question from your start post be informed that  in Noesis.dll you'll find:
-decalmesh - generates rendermodel collision/decal meshes
(well, "generate" does not mean "import" but that's all I found.)

Looks to me as if you wished to extend Noesis to a fully featured game engine (like Blender game?).
Maybe you should ask MrAdults whether he's interested in you becoming part of his Noesis project?

Btw on googling for setHandlerWriteModel I found
[http://noesis-plugins-official.googleco ... c/3/trunk/](http://noesis-plugins-official.googlecode.com/svn/!svn/bc/3/trunk/)


> Also, lets say I export my game model as .obj and then made some changes to the obj model, how/what would I have to do to export that obj model back to my game's format (via Noesis)?First thing imho would be to think about using noepyWriteModel() to export your imported *.bsc data to a bsc again.

The model changing part? Huh, well, would be interested in MrAdults opinion, too.
## Post #69
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-04T08:30:34+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from shakotay2
>
> Alsair wrote:And is it possible to import collision data into Noesis?Since this is an unanswered question from your start post be informed that  in Noesis.dll you'll find:
-decalmesh - generates rendermodel collision/decal meshes
(well, "generate" does not mean "import" but that's all I found.)

Looks to my as if you wished to extend Noesis to a fully featured game engine (like Blender game?).
Maybe you should ask MrAdults whether he's interested in you becoming part of his Noesis project?

Btw on googling for setHandlerWriteModel I found
http://noesis-plugins-official.googleco ... c/3/trunk/

Also, lets say I export my game model as .obj and then made some changes to the obj model, how/what would I have to do to export that obj model back to my game's format (via Noesis)?First thing imho would be to think about using noepyWriteModel() to export your imported *.bsc data to a bsc again.

The model changing part? Huh, well, would be interested in MrAdults opinion, too.
I was curious to know since the SFX data and Collision data are both handled within the .bon file. Also I tried importing the three models by loading the one bone file that all three share and then loading the model each and using mdlList.append on each model. Initially I would only see the first model that I appended until I realized I can cycle through models. When I pressed F6 I think it was, I would see the second model I appended with the distortion of the first model, then when I pressed F6 again I saw the third model perfectly fine; however the previous two models became distorted. So I am not sure why this is occuring but I can guarantee all three models are being transformed with the bone correctly independently, I just cant figure out why they appear correctly when all three models are appended.

I will look into the exporting to bsc stuff as well, any examples would be helpful.
## Post #70
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-04T12:56:30+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

For exporting, you just need to add an export handler, and write the data out from the common Noesis data structures. You can take a look at the __NPExample.txt file, it has import and export for the same format.

There's no specific handling for collision or sound data. You can handle that a couple of ways. You could dump it out next to files or a container next to the model using Python file functions and using rapi functions to get the export path, optionally putting a common RIFF/WAVE header on your sound data.

You could also get really fancy and write a DirectSound implementation as a native plugin that implements itself as a tool and a visualizer, and check the animation frames in your visualizer to know when to trigger your sounds. You could communicate the sound info from the importer to the plugin through a number of means - flat files, IPC (TCP, pipes, etc), or DLL calls. Flat files would be easiest, and should be reliable if you just want to make your own simple parseable format for the visualizer to parse on model load. You could write whatever data you need to that file, like keyframes and their associated sound events. Your plugin checks if the file exists for a model when the model is loaded, and if it does, it parses it, loads the sounds, and plays the sounds for the keyframes while the anim plays as appropriate. For collision, there's not much use of you don't have things to collide *with*, but you could certainly do whatever you want there using a visualizer as well.

This is all possible and fairly painless to do in the existing plugin framework, but it is somewhat advanced. So, remember, baby steps.
## Post #71
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-04T13:04:56+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Oh, and your model distortion issue is my fault. Apparently I broke weighting on multiple models in a recent update. Thanks for running into it! I'll put an update out to fix it today.
## Post #72
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-04T13:38:30+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

Nevermind, it wasn't my fault.  I broke GMO specifically, which is the only multi-model format I had laying around to test.

Not sure off the top of my head what your problem is then. It sounds like the weights don't match the bones, or the anims don't match the bones.
## Post #73
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-04T21:38:48+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from MrAdults
>
> Nevermind, it wasn't my fault.  I broke GMO specifically, which is the only multi-model format I had laying around to test.

Not sure off the top of my head what your problem is then. It sounds like the weights don't match the bones, or the anims don't match the bones.

That's funny because all three models load fine using the same skeleton independently, just not together.

As for the export handler, lets say I have a bsc converted to obj file, how would the obj file contain the same original bone name's? Since in order to convert it back to .bsc I would need that data as well.

The sound data itself, only contain references to the actual WAV files stored in the client directory, they're not written within the skeleton file as raw data. I believe it's similar with collision data, since when I altered the data there I was able to attack monsters regardless of what animation was running (usually it only attacks during the attack animation).

Basically, my plan is to completely rewrite the skeleton + bsc files from scratch with all the necessary data (although this would be the last step to do), my first aim is to get the new modified .obj files to convert back to .bsc with all of the proper bone names.

As for the multi-model import, I have PM'd you the code on how I've been attempting to load them. I recoded the entire plugin to make use of classes.
## Post #74
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-07-04T22:00:37+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from Alsair
>
> 
As for the export handler, lets say I have a bsc converted to obj file, how would the obj file contain the same original bone name's? Since in order to convert it back to .bsc I would need that data as well.
Is there a reason it has to be .obj and not .fbx or .dae?
You could create an extra NoeBitStream() and write the bone data into that one. Then write the buffer from that stream into a file.

Here's an example of how I rewrote custom texture into the format of a dds. (not what I should have done back then, but ignore that.)

```
        file=NoeBitStream()
        file.writeBytes(b"\x44\x44\x53\x20")
        file.writeBytes(noePack("<1i",self.header['defaultSize']))
        file.writeBytes(noePack("<1i",self.header['flags']))
        file.writeBytes(noePack("<1i",self.header['height']))
        file.writeBytes(noePack("<1i",self.header['width']))
        file.writeBytes(noePack("<1i",self.header['linearSize']))
        file.writeBytes(noePack("<1i",self.header['depth']))
        file.writeBytes(noePack("<1i",self.header['mipmapCount']))
        file.writeBytes(noePack("<11i",*self.header['reserved1']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['defaultSize']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['flags']))
        if "DXT" in self.header['pixelFormat']['fourCC']:
            file.writeBytes(b"\x44\x58\x54") #write "DXT"
            file.writeBytes(struct.pack('b',48+int(self.header['pixelFormat']['fourCC'][-1]))) #write 1-5
        else:
            file.writeBytes(b"\x00\x00\x00\x00")
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['RGBBitCount']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['RBitMask']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['GBitMask']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['BBitMask']))
        try:file.writeBytes(noePack("<1i",self.header['pixelFormat']['ABitMask']))
        except: file.writeBytes(b"\x00\x00\x00\xFF")
        file.writeBytes(noePack("<1i",self.header['caps1']))
        file.writeBytes(noePack("<1i",self.header['caps2']))
        file.writeBytes(noePack("<1i",self.header['caps3']))
        file.writeBytes(noePack("<1i",self.header['caps4']))
        file.writeBytes(noePack("<1i",self.header['reserved2']))
        self.Images[0].reverse()
        for l in range(self.Layers):
            for m in range(self.header['mipmapCount']):
                file.writeBytes(self.Images[l][m])
        return file
```


with this function you could for example write that buffer to a file with:

```
texture = open('texture.dds','wb')
texture.write(bitstream.getBuffer())
texture.close()

```


In inc_noesis.py you'll find: noePack = struct.pack
so for more info you can reference the struct module.

In order for this to work, in your export script(obj >bsc) you'll need to put a check where if the inputfile has extension .obj you open a prompt (ex: rapi.loadPairedFileOptional("Skeleton File","objskel") ) and read the skeleton from there or make it autoread it defined on whatever you wish.
That's how I would do it, not sure if it's the best method.
## Post #75
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-04T22:12:17+00:00
- Post Title: Re: [Noesis] Bone Mapping with Skeleton

> Reply from Demonsangel
>
> Alsair wrote:
As for the export handler, lets say I have a bsc converted to obj file, how would the obj file contain the same original bone name's? Since in order to convert it back to .bsc I would need that data as well.

Is there a reason it has to be .obj and not .fbx or .dae?
You could create an extra NoeBitStream() and write the bone data into that one. Then write the buffer from that stream into a file.

Here's an example of how I rewrote custom texture into the format of a dds. (not what I should have done back then, but ignore that.)
Code: Select alldef WriteFixedDDS(self):
        file=NoeBitStream()
        file.writeBytes(b"\x44\x44\x53\x20")
        file.writeBytes(noePack("<1i",self.header['defaultSize']))
        file.writeBytes(noePack("<1i",self.header['flags']))
        file.writeBytes(noePack("<1i",self.header['height']))
        file.writeBytes(noePack("<1i",self.header['width']))
        file.writeBytes(noePack("<1i",self.header['linearSize']))
        file.writeBytes(noePack("<1i",self.header['depth']))
        file.writeBytes(noePack("<1i",self.header['mipmapCount']))
        file.writeBytes(noePack("<11i",*self.header['reserved1']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['defaultSize']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['flags']))
        if "DXT" in self.header['pixelFormat']['fourCC']:
            file.writeBytes(b"\x44\x58\x54") #write "DXT"
            file.writeBytes(struct.pack('b',48+int(self.header['pixelFormat']['fourCC'][-1]))) #write 1-5
        else:
            file.writeBytes(b"\x00\x00\x00\x00")
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['RGBBitCount']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['RBitMask']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['GBitMask']))
        file.writeBytes(noePack("<1i",self.header['pixelFormat']['BBitMask']))
        try:file.writeBytes(noePack("<1i",self.header['pixelFormat']['ABitMask']))
        except: file.writeBytes(b"\x00\x00\x00\xFF")
        file.writeBytes(noePack("<1i",self.header['caps1']))
        file.writeBytes(noePack("<1i",self.header['caps2']))
        file.writeBytes(noePack("<1i",self.header['caps3']))
        file.writeBytes(noePack("<1i",self.header['caps4']))
        file.writeBytes(noePack("<1i",self.header['reserved2']))
        self.Images[0].reverse()
        for l in range(self.Layers):
            for m in range(self.header['mipmapCount']):
                file.writeBytes(self.Images[l][m])
        return file

with this function you could for example write that buffer to a file with:
Code: Select allbitstream = WriteFixedDDS()# ignore the fact the function was part of a class
texture = open('texture.dds','wb')
texture.write(bitstream.getBuffer())
texture.close()


In inc_noesis.py you'll find: noePack = struct.pack
so for more info you can reference the struct module.

In order for this to work, in your export script(obj >bsc) you'll need to put a check where if the inputfile has extension .obj you open a prompt (ex: rapi.loadPairedFileOptional("Skeleton File","objskel") ) and read the skeleton from there or make it autoread it defined on whatever you wish.
That's how I would do it, not sure if it's the best method.

Was using obj as an example, but I mean any could be fine. Also, how would I associate the bone names from the exported skeleton file back to the mesh pieces again? Wouldn't this association be lost after it's been exported into a new model format?
## Post #76
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-12T01:02:36+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

You probably want to use FBX as your main export target, it supports the most data types and material properties. When you're exporting back to your format, you just flatten the bone list (you can use the bone matrices as-is since they're in model space, but you have to use rpgMultiplyBones on animation bone sets because anims coming out of Noesis will be parent-relative, and you want to support exporting skeletons that *aren't* flattened to your format just to be nice)

What I would do is run through the model and build unique meshes from bone references. So each collection of triangles becomes a mesh based on which bones in the skeleton the weights for the verts for each triangle references. Your format can't support more than 1 weight per triangle, so when you encounter that, you can either barf and tell the user to fix the model, or you can try to handle it gracefully. By picking the bone index most referenced by the triangle, or just using the bone index from the first vertex of each tri, or whatever.

I would also store out your extraneous data that isn't supported directly (like anim keyframe events/sounds) to a file next to the exported model (when your importer is running and rapi.noesisIsExporting() returns non-0) in a format of your own specification. Then on export to bsc, your script should check if that file exists for the file that was imported, and if it does, parse it and write that data back out in the new bsc.

All of that combined will give you a clean path that allows you to go bsc->fbx->bsc with no data loss. And if you're robust enough, it will let you convert pretty much any model+anim to the format with no user intervention.
## Post #77
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-13T01:11:21+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

I see, you make it seem like it will be so simple, but it's going to be quite the task.

One thing I've noticed is, when I import the model, all of the meshes in the original .bsc file get merged into one in Noesis. This would mean if I were to export it (regardless of what format) there would always be 1 Mesh (as opposed to the multiple meshes in the original bsc file).

I would not only have to single out each mesh, but to associate it with the original names used to reference with the .bon file.

How would I go about on accomplishing this before continuing onto the next step?
## Post #78
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-13T03:33:38+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

You can use rapi.rpgSetName before you commit the triangles to associate the triangles with a unique mesh name. That'll prevent them from being merged into mesh buckets even though they share materials.

Although, your exporter shouldn't actually care if everything is 1 mesh or not. It should create its own mesh buckets based on unique materials and bone indices, that way it handles source models that aren't broken up as well as models that are.
## Post #79
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-13T22:41:46+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

> Reply from MrAdults
>
> You can use rapi.rpgSetName before you commit the triangles to associate the triangles with a unique mesh name. That'll prevent them from being merged into mesh buckets even though they share materials.

Although, your exporter shouldn't actually care if everything is 1 mesh or not. It should create its own mesh buckets based on unique materials and bone indices, that way it handles source models that aren't broken up as well as models that are.

When I export multiple models into lets say an fbx format, I would only get the model I originally selected, not all of the models currently loaded in Noesis.

For example:
1. Body file is selected in Noesis
2. The body, with the other arm and head files are loaded
- The animations and all the meshes for all three objects appear correct in Noesis
3. Export the model (as fbx) and re-open it in Noesis. Exports four files, texture file for each model, and one .fbx file.
4. Noesis loads everything fine, except for the fact it only loaded the body.
## Post #80
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-13T23:16:40+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

Yeah, when you export from a scene with multiple models, you have to specify the model index for the destination file using -modelindex. So from here, there are a number of approaches you can take.

1) Export each model using -modelindex #, then merge the FBX files together in your modeling app of choice. If you want to automate the export process, you could write a simple .bat file to run Noesis.exe ?cmode yourfile.bsc model00.fbx -modelindex 0, Noesis.exe ?cmode yourfile.bsc model01.fbx -modelindex 1, etc. sequentially.
2) Rework your script to just load all of the files with meshes, bones, anims, and textures you want into a single RPG context. This would probably actually work best for you, because your skeleton and anims are shared between files. That means you really just want to load them all into the same context, only set the skeleton and bones once, and only call rpgConstructModel once after all of your files are loaded into the context.
3) Use the model merging script: [https://code.google.com/p/noesis-plugin ... elmerge.py](https://code.google.com/p/noesis-plugins-official/source/browse/trunk/Rich/tool_modelmerge.py) It will scrape a directory for all models of a selected type, and combine them together. It does so by generating a .noesis file and loading it. If you want to export its merged results, you then use "Export from preview". Or you could modify the script to just export that .noesis file directly to .fbx if you wanted. When you use .noesis files to load multiple models, you can collapse them all into a single model/scene. It handles merging skeletons, animations, materials, and textures for you, so that you don't need to worry about any conflicts.
4) Write your own .noesis file to handle specific files, as the merger script would do for you. You can probably figure out how the .noesis file works by looking at the merger script.
## Post #81
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-14T04:10:35+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

While trying write export code, I noticed some values stored in the mesh aren't the same as the original file.

Here's what I mean:
Positions have different float values

e.g. Noesis would have it as:
(-2.5455565452575684, 78.94608306884766, -1.5863863229751587)
When it's actually:
(6.6151938, 1.8743709e-005, -2.1816142)

Normals have different values
e.g. Noesis would have it as:
(-0.1995614916086197, 0.6651973724365234, -0.7195051908493042)
When it's actually:
(0.9030363, 3.7814422e-007, -0.42956412)

UV's had correct values so I had no problems with that.

How would I obtain the correct values?

Edit:

It turns out when the skeleton is loaded the values are changed, however when the skeleton isn't loaded the values appear correctly.
I was wondering if there's a way to export it without the skeleton embedded within the fbx file like that. How would I unbind the skeleton already bound?

Edit 2:
I found a workaround but this has some downfalls. I made it so that I would check rapi.noesisIsExporting when the model is loading to check to see whether it's being exported. If it is, I made it so that it would not load the skeleton. The problem with this is that once it's in fbx format, the model will be junk of models in the middle and will be difficult to modify and re-export. Is it possible to make it so that fbx doesn't merge the skeletal data with the actual positions of each mesh?
## Post #82
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-14T23:00:02+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

Your vertices were in bone space on import, you put them in model space. So on export, you want to put them back in bone space. That can be accomplished by transforming your verts using inverse bone matrices.
## Post #83
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-14T23:05:43+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

> Reply from MrAdults
>
> Your vertices were in bone space on import, you put them in model space. So on export, you want to put them back in bone space. That can be accomplished by transforming your verts using inverse bone matrices.

I just want to remove the bone vertices that where skinned onto my model (basically what it would be like without the skeleton loaded), how would I accomplish this? If transforming the verts using inverse bone matrices does this, how would I accomplish this on export to bsc?
## Post #84
- Username: Alsair
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-07-14T23:21:14+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

Something like...

```
for bone in mdl.bones:
	invMats.append(bone.getMatrix().inverse())

for mesh in mdl.meshes:
	for i in range(0, len(mesh.positions)):
		#actually verifying that the mesh has positions/normals/weights here would be a good idea.
		#additionally, you'd have to do a weighted transform for models that actually use more than 1
		#weight per vert. but for yours, it doesn't matter.
		boneIndex = mesh.weights[i].indices[0]
		mesh.positions[i] = invMats[boneIndex].transformPoint(mesh.positions[i])
		mesh.normals[i] = invMats[boneIndex].transformNormal(mesh.normals[i])

```

I just wrote this up without testing it or even seeing if it's parseable, but you get the idea.
## Post #85
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-07-15T00:16:09+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

If I recall correctly, I'm quite sure mdl.bones is empty. I am not home so I can't test this out right now.


Edit:

Nvm, I was wrong. Anyways, I tried your code and it worked perfectly. For someone who doesn't even need to test his code, you sure do know a lot. 

btw you can't assign the .position / .normals variables since I guess they're read-only. So I just assigned it to a temporary local variable, and used that to write into the file.

Edit2:

Another problem, when I exported the .bsc into .fbx and imported that .fbx in Cinema 4D I modified the points and re-exported the file as .fbx. Using this fbx file, I tried exporting back to .bsc in Noesis and found out the Bone name references are associated with the wrong meshes. I think Cinema4D swapped them or something, but I am unsure as to why.

The .fbx exported from Noesis is perfectly fine and when exported back to .bsc is good too.

Edit3:
Made some changes to the import/export settings. It works perfectly now.
## Post #86
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-09-21T23:06:14+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

It turns out all of the models w/ animations uses Right Hand Coordinate System.

Is there a way to use this method of coordinate system in Noesis?

I'd assume there would be some sorta function or setting in Noesis that does this?
## Post #87
- Username: Alsair
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-24T14:16:08+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

You could use rapi.rpgSetOption(noesis.RPGOPT_SWAPHANDEDNESS, 1), and use mat = mat.swapHandedness() on all of your matrices. However, it should be noted that this actually flips the geometry itself. Which means you'd want to switch it back when exporting back to the format too. It might be preferable to leave it as-is, and just render it mirrored in whatever modeling app you're using to modify it before you export it back again.

Edit: Also, for animations, if you're performing the swap in local-space, you only need to do it on root bones. It'll naturally propagate down the transform chain.
## Post #88
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-09-24T19:38:03+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

Thank you for the help.

I did have a small issue though, but it's probably just an issue with the way I used it.

Upon using rapi.rpgSetOption(noesis.RPGOPT_SWAPHANDEDNESS, 1)

Some of the meshes appeared to be mis-aligned in the animations, but all of the meshes appeared to be the correct handedness.

I was able to fix that by removing it, and manually negating the X value of each vertices in the meshes.

mat.swapHandedness() worked perfectly for the animation clips though.


I have another quick question, is there a way to automatically turn off shading/face culling when done loading the model files?
## Post #89
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-09-25T06:29:18+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

RPGOPT_SWAPHANDEDNESS will also automatically swap handedness on bone and anim matrices, but only if they're set in the RPG context before constructing the model. So that might be happening, and maybe one of the matrix sets is getting double-swapped or something, it's hard to say.

To turn off shading and culling, if it's something you want as a default, it's probably best to make it a material property. You can use NoeMaterial.setFlags(noesis.NMATFLAG_TWOSIDED, 1) (the 1 is to also disable lighting, it's a separate parameter for silly internal legacy support reasons)
## Post #90
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-09-25T07:16:08+00:00
- Post Title: Re: [Noesis] Plugin to export to a new format

Ahh beautiful, thanks so much for the help!
