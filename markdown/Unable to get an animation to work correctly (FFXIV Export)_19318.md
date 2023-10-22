## Post #1
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-13T21:20:36+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

Hey Guys,

I've extracted FFXIV Models and Animations and currently trying to get them to work correctly.

Unfortunately they are a bit buggy using the Models extracted.
The character is like "floating" and it's anchor point is somewhere near the hips (bone: n_hara isn't moving as it should).
The stretch animation (like all others) look weird because of this.
Here's a video of how it currently looks.
[https://www.youtube.com/watch?v=K6n5yFKMvZw](https://www.youtube.com/watch?v=K6n5yFKMvZw)

Here's a video of how it should be animated (feet should be on almost the same position while animation runs).
If you just import that animation (fbx) into 3dsmax, blender or maya, the Animation still works.
[https://www.youtube.com/watch?v=OJTEEY55ZGA](https://www.youtube.com/watch?v=OJTEEY55ZGA)

But as soon as you try to use that animation on your character (built from the dae files), the animation isn't working as intended anymore.

Hopefully you're able to get it to work + be able to explain, how to do it.

Here's a downloadlink for the models as DAE and the animation as FBX.
[https://cdn.discordapp.com/attachments/ ... tretch.zip](https://cdn.discordapp.com/attachments/430169321168306177/534073901483819021/Models_and_Animation_stretch.zip)

Would be great if you could help me out!

Also here's a Blender file which contains the models as one big object with armature and the animation_fbx:
[https://res.cellenseres.de/Model_with_Animation.zip](https://res.cellenseres.de/Model_with_Animation.zip)
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-14T12:21:59+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

admit I don't know in knowledge, may be a problem of just scaling.
If the scale is incorrect, the hip bone may be in the wrong location.

and what does it mean that animation doesn't work?
I tried mapping this animation and armature to another model, but it works fine.

The DAE file seems to be a body in parts, but it needs to be concatenated correctly.
I have knowledge of animation, but I don't know well about meshes, so sorry I can't help it.
## Post #3
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-14T12:30:25+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> admit I don't know in knowledge, may be a problem of just scaling.
If the scale is incorrect, the hip bone may be in the wrong location.

and what does it mean that animation doesn't work?
I tried mapping this animation and armature to another model, but it works fine.

The DAE file seems to be a body in parts, but it needs to be concatenated correctly.
I have knowledge of animation, but I don't know well about meshes, so sorry I can't help it.

Well, the Animation does in fact work. I've recorded even a video about it 
[https://www.youtube.com/watch?v=K6n5yFKMvZw](https://www.youtube.com/watch?v=K6n5yFKMvZw)

But the problem is, no matter what I do, the character looks like she's floating (the feet aren't stand on the same position) because the hip bone "n_hara" isn't moving as it should.
And I just don't get that to work as it should.

This video (just uploaded) shows what I mean:
[https://youtu.be/AFBggycCd1o](https://youtu.be/AFBggycCd1o)

And sorry, english isn't my native language, hope you understand^^'
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-14T14:29:20+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

there, finally I can open in the blender.

I do not know the detail because there is no mesh file, 
but after all I think that it is a problem of scaling. 

Is your uploaded hkx included in FF14?
I think I will download FF14 and try it.
[walk.PNG](https://xentaxbackup.github.io/file/15468_walk.PNG)
## Post #5
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-14T14:32:30+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> I tried to send confirmation PM to you, but it seems that it is censored and can't sent them.

there, finally I can open in the blender.

I do not know the detail because there is no mesh file, 
but after all I think that it is a problem of scaling. 

Is your uploaded hkx included in FF14?
I think I will download FF14 and try it.

FF14 contains sklb and pap files (skeleton and animation) which can be converted to hkx files.
With some tricks you're able to convert a skeleton and a animation file to one armature with Animation as FBX.

This works fine, the FBX is perfectly animated and the hip-bone (n_hara) is moving like it should.
But as soon as I want to use FF14's Models on it (exported as dae using FFXIV-TexTools), the animation of the n_hara bone (hip) is locked for whatever reason.

That's why I'm asking for your help x3


EDIT:
I don't really think it's the scaling. If it would, everything else shouldn't be animated so smoothly as it is.
The Problem I CAN see is, that the Hip bone isn't moving even if it should.
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-14T14:43:36+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

anyway, I don't have a mesh so I although it is not certain,
it is not locked, but because the scale is wrong, the location distance is wrong.

Does hk have multiple animations?
I played the motion those things walks like this time, are there other inclusions included?
## Post #7
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-14T14:46:14+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> anyway, I don't have a mesh so I although it is not certain,
it is not locked, but because the scale is wrong, the location distance is wrong.

Does hk have multiple animations?
I played the motion those things walks like this time, are there other inclusions included?

No they don't.
But there's a way to extract all animatios from a pap file by splitting them manually with a hex editor.
Do you think you can fix that bone scaling thing?
## Post #8
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-14T15:07:16+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

I tried with the blender mesh you uploaded.
sorry, mesh is missing because it is my playback system, but I think hip bone is fixed.

finally I thought scaling is a problem.
I corrected this manually, but should look for the correct answer with more verification.
[ff14.gif](https://xentaxbackup.github.io/file/15469_ff14.gif)
## Post #9
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-14T17:15:13+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> I tried with the blender mesh you uploaded.
sorry, mesh is missing because it is my playback system, but I think hip bone is fixed.

finally I thought scaling is a problem.
I corrected this manually, but should look for the correct answer with more verification.

Could you add a Grid/Floor underneath the feet? Or probably upload a video/gif with more fps? x3
what have you done exactly?
## Post #10
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-15T17:27:16+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

Since I downloaded FF14 (too big 30GB), I will continue verification.
you said, It seems like you can split the animation by editing htx, how do you do it?
Details are necessary.
## Post #11
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-16T09:21:26+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

All character animations are in separate hkx files (pap files before extracted).
you cab find them in "chara/human/c**001/animaion/a0001/bt_common/" (FFXIV Explorer, a tool you can download online. These files are in "SquareEnix\FINAL FANTASY XIV - A Realm Reborn\game\sqpack\ffxiv\040000.win32.index")

You only need to split monster animations (which is pretty difficult to explain).,


I guess I did it.
Fuckin complicated process, tho:
[https://youtu.be/Eq9UwdZvToc](https://youtu.be/Eq9UwdZvToc)
## Post #12
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-16T12:03:56+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

Yeah, I guess that is not easy. Especially, I could not find a header specific.

It's not for sure, but I think that I can understand the sample, if it exists.
I prepared a file that seems to contain multiple animations. Please try splitting this up.
if that too long story, you can send me a PM.

I do not know how to combine with the mesh(dae), 
but if I do a lot of exams I will know the correct answer as to which scale to give.
[FF14.zip](https://xentaxbackup.github.io/file/15489_FF14.zip)
## Post #13
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-17T13:30:10+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> Yeah, I guess that is not easy. Especially, I could not find a header specific.

It's not for sure, but I think that I can understand the sample, if it exists.
I prepared a file that seems to contain multiple animations. Please try splitting this up.
if that too long story, you can send me a PM.

I do not know how to combine with the mesh(dae), 
but if I do a lot of exams I will know the correct answer as to which scale to give.

heyhey o/
Sorry, but I can't get the .dae for your animation (DemiHuman => ID 1003).
Have you extacted that one, too?
## Post #14
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-17T13:39:20+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

DAE is necessary for the final join, but it is not necessary for the current stage. 
There are also models with other DAEs, so all you need is animation cutting information.
I download more than 30 GB files, so I can do verification with most of them.
## Post #15
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-17T13:44:32+00:00
- Post Title: Unable to get an animation to work correctly (FFXIV Export)

> Reply from einherjar007
>
> DAE is necessary for the final join, but it is not necessary for the current stage. 
There are also models with other DAEs, so all you need is animation cutting information.
I download more than 30 GB files, so I can do verification with most of them.

Try to save your hkx as hkx (xml format).
As you can see, your animation contains more than one animation.
The welcome.hkx (one of mine) contains only one.


Gonna try a cutdown for ya when I'm back from work.

EDIT:

check for this part: it will help finding your animations

```
				#0055 #0053 #0052 #0051 #0050
			</hkparam>
			<hkparam name="bindings" numelements="5">
				#0049 #0048 #0047 #0046 #0045
			</hkparam>
```


EDIT 2:
Noticed it's pretty easy to "split" the animations.
I just removed #0055, #0053, #0051, #0050, #0049, #0048 #0047 #0046 and #0045.
Had #0052 Animation with #0047 Animation Binding.

This is the result:
[https://youtu.be/IllrZjyba94](https://youtu.be/IllrZjyba94)


EDIT 3:
here are your animations for d1003

[https://youtu.be/clXqozSIomk](https://youtu.be/clXqozSIomk)
[d1003_all_animations.zip](https://xentaxbackup.github.io/file/15499_d1003_all_animations.zip)
## Post #16
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-17T23:53:08+00:00
- Post Title: Re: Unable to get an animation to work correctly (FFXIV Expo

Thanks for the details. I will examine it based on these information. 
Perhaps by properly changing either scale before combining mesh and animation you should get the correct result.
I'll report it when I can find the correct scale.

----
Edit.

FFXIV TexTool is not suitable for finding files, I can not find the same file as FFXIV Explorer.
But I admit, Textool, Explorer, a difference in interpretation of the scale between the two.

Probably the file output by Explorer (hkx) is small. Textool's DAE is much bigger.(sorry, may be the opposite)
It seems to be played correctly though the scale is different because bones move by angle instead of location, except than n_hara.

How do you finally combine mesh (DAE) and animation (hkx or fbx)?
Good results can be obtained by fitting to the appropriate scale before joining.

----

The explanation may be bad.
Rather than enlarging the scale, change the magnification.
For example, if the location  is 0.2, it is 2, 10times(This is just an example).

I make BVH to do this hand correction, or otherwise convert it to a pseudo vmd (mmd animation) and give the magnification.

Perhaps there may be a way to easily realize it, but I am specialized in playing animation on my playback system, so I am lacking in universal knowledge.
## Post #17
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2019-01-20T11:48:42+00:00
- Post Title: Re: Unable to get an animation to work correctly (FFXIV Expo

> Reply from einherjar007
>
> Thanks for the details. I will examine it based on these information. 
Perhaps by properly changing either scale before combining mesh and animation you should get the correct result.
I'll report it when I can find the correct scale.

----
Edit.

FFXIV TexTool is not suitable for finding files, I can not find the same file as FFXIV Explorer.
But I admit, Textool, Explorer, a difference in interpretation of the scale between the two.

Probably the file output by Explorer (hkx) is small. Textool's DAE is much bigger.(sorry, may be the opposite)
It seems to be played correctly though the scale is different because bones move by angle instead of location, except than n_hara.

How do you finally combine mesh (DAE) and animation (hkx or fbx)?
Good results can be obtained by fitting to the appropriate scale before joining.

----

The explanation may be bad.
Rather than enlarging the scale, change the magnification.
For example, if the location  is 0.2, it is 2, 10times(This is just an example).

I make BVH to do this hand correction, or otherwise convert it to a pseudo vmd (mmd animation) and give the magnification.

Perhaps there may be a way to easily realize it, but I am specialized in playing animation on my playback system, so I am lacking in universal knowledge.

I've already fixed that problem^^ Got it to work perfectly in Unity and in Blender:
[https://youtu.be/gN7rCY60-vo](https://youtu.be/gN7rCY60-vo)
and
[https://youtu.be/T8iGxdmOcfc](https://youtu.be/T8iGxdmOcfc)

I loaded both, animation+skeleton and the Model exported with TexTools in Blender. I resized the animation to 1, 1, 1 and the Model to 0.1, 0.1, 0.1.
They now have the same size.
But both in "Rest Pose" and removed all bones from the Model.
After that, I've separated all bones from the skeleton+animation one and joined them to the model.

As you can see, it works perfectly for me
## Post #18
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-01-20T12:39:20+00:00
- Post Title: Re: Unable to get an animation to work correctly (FFXIV Expo

finally your get good results, I'm glad hear that.
