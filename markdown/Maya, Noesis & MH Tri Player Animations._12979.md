## Post #1
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-23T22:49:32+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

Hey Community,

 I've got a question about Noesis and Autodesk Maya regarding the player animations for Monster Hunter TRI. I've already exhausted quite abit of research on the topic and avenues on how to accomplish what I need so i'm turning to you guys for some help.

 I'm using the BRRES viewer to look at the animations from the game that I pulled with Wii Scrubber. Now, all of the animations work beautifully EXCEPT the player/npc animations (bummer!). That is until I select the option to "Play Rotations Only" which in the read-me says it does the following.

"Play Rotations Only" option. It will prevent the model from being translated when playing an animation. This option can also have other uses."

 Alright. No problem. I then go to extract the animation from the BRRES viewer as a MD5Anim which is loaded up just fine in Noesis... except one issue. The skeleton is clearly there and when I export it to maya it is still there. The issue is that most of the hierarchy of the skeleton seems to have clumped up. I should also mention that in the BRRES viewer that if that option isn't selected it does the same thing.

[http://postimg.org/image/kfmf2c4xx/](http://postimg.org/image/kfmf2c4xx/)

Now, I looked around abit and I came across this post here by Mr.Adults...

[viewtopic.php?p=90014](http://forum.xentax.com/viewtopic.php?p=90014)

I'm not sure if it would fix the problem but... I am not even sure how to do what he suggested. So I guess my question is... how do I fix the animations from grouping up like this either with Noesis or Maya and is there an option in Maya to play the "Rotations Only"? Anyways, thanks guys I appreciate the help.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-24T07:22:12+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

- .brres sample?

- what's the actual version of the BRRES Viewer? 1.2?
## Post #3
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-24T09:01:51+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> - .brres sample?

- what's the actual version of the BRRES Viewer? 1.2?

BRRES Version 1.3.1.

[https://drive.google.com/file/d/0B2IyNC ... sp=sharing](https://drive.google.com/file/d/0B2IyNC1BPn5Qdjg1VWpWZWNLTlU/view?usp=sharing) The NPC sample.

[https://drive.google.com/file/d/0B2IyNC ... sp=sharing](https://drive.google.com/file/d/0B2IyNC1BPn5QVXlFdW90LWpkcXM/view?usp=sharing) The animation sample.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-24T12:09:17+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

thx for uploading the brres files!

npc001.brres and mot_plcom.brres
first one is the skeleton with mesh, 2nd one the ani file, correct?

Seems I can't follow some of your explanations from the OP:

> Reply from SaucyMonkey
>
> I then go to extract the animation from the BRRES viewer as a MD5Anim which is loaded up just fine in Noesis... except one issue. The skeleton is clearly there and when I export it to maya it is still there. The issue is that most of the hierarchy of the skeleton seems to have clumped up.
I can't export the animations with BRRES viewer as MD5Anim, only as PSA.

npc001 skeleton can be exported as MD5Mesh and be loaded into Noesis, as you wrote.
Converted to smd it can be imported to blender where the hierarchy seems to be ok:



npc001.JPG (17.9 KiB) Viewed 366 times



> I should also mention that in the BRRES viewer that if that option isn't selected it does the same thing.don't understand. Where is that option to be set in the viewer 1.3.1?
## Post #5
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-24T19:08:33+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> thx for uploading the brres files!

npc001.brres and mot_plcom.brres
first one is the skeleton with mesh, 2nd one the ani file, correct?

Seems I can't follow some of your explanations from the OP:
SaucyMonkey wrote:I then go to extract the animation from the BRRES viewer as a MD5Anim which is loaded up just fine in Noesis... except one issue. The skeleton is clearly there and when I export it to maya it is still there. The issue is that most of the hierarchy of the skeleton seems to have clumped up.
I can't export the animations with BRRES viewer as MD5Anim, only as PSA.

npc001 skeleton can be exported as MD5Mesh and be loaded into Noesis, as you wrote.
Converted to smd it can be imported to blender where the hierarchy seems to be ok:
npc001.JPG
I should also mention that in the BRRES viewer that if that option isn't selected it does the same thing.don't understand. Where is that option to be set in the viewer 1.3.1?

Wait a moment. So do you have the animations working outside of the BRRES viewer? Because that is the issue I am currently running into at the moment. I'd like to do the following:

1) Take the model and place it into Maya (Done)
2) Take an animation and put it into Maya (Done)
3) Stop the animation from getting clumped up like in the screenshot
4) Play the animation on the model.


The option in the BRRES Viewer that needs to be selected for the animations to play is "Play Rotations Only" otherwise the joints start to clump up together. Though I wish I knew the official term for it. Even when I export as PSA I seem to run into the same issue. Thanks by the way for the effort. Hopefully we'll be able to figure this out.

[http://postimg.org/image/v5t9umnf7/](http://postimg.org/image/v5t9umnf7/) - Play Rotations Only is On

[http://postimg.org/image/yotkykky1/](http://postimg.org/image/yotkykky1/) - Play Rotations Only is Off
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-24T20:36:39+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> Wait a moment. So do you have the animations working outside of the BRRES viewer?nope - I moved the bones manually in blender's posing mode.

> The option in the BRRES Viewer that needs to be selected for the animations to play is "Play Rotations Only"well, ok, I'd to load the anim and the model, then select them to have the Animation menu point being ungrayed.

> as a MD5Anim which is loaded up just fine in Noesis
all I get is moving red bones...
## Post #7
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-24T20:41:36+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> SaucyMonkey wrote:Wait a moment. So do you have the animations working outside of the BRRES viewer? nope - I moved the bones manually in blender's posing mode.
The option in the BRRES Viewer that needs to be selected for the animations to play is "Play Rotations Only"well, ok, I'd to load the anim and the model, then select them to have the Animation menu point being ungrayed.

With the BRRES Viewer there is an option to export the animations as an MD5 with the BRRES Viewer version 1.3.1. Hopefully that helps. If you need a download link to the latest viewer i'll upload it and send it if you can't find it.

The animation menu will be ungrayed when you load up a model first and then you select the animations from the list.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-24T20:52:39+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

yeah, I know that. But as you can read from my "simultaneous" edit  in my previous post
I don't get the md5anim working in Noesis except moving white dots connected by red lines (not the bones I guess).

So what does

> as a MD5Anim which is loaded up just fine in Noesisexactly mean?
## Post #9
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-24T22:11:37+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> yeah, I know that. But as you can read from my "simultaneous" edit  in my previous post
I don't get the md5anim working in Noesis except moving white dots connected by red lines (not the bones I guess).

So what does
as a MD5Anim which is loaded up just fine in Noesisexactly mean?

Well, it means that Noesis can read the MD5Anim. Not that the skeleton is actually doing what it should be doing. In one of my previous images I posted here it shows what the skeleton is doing.

If I upload into Maya as a PSA then I don't get any information but as an MD5 I can at least see the skeleton but the problem remains that the joints are bunched up together and I simply don't know how to fix that problem in Maya.

In the BRRES viewer it's fixed by using the "Play Rotations Only" option but I don't think Noesis or Maya have that same function and if they do then i'd love to know where it is.

The Red Line is the skeleton information. The dot represents the joints.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-25T09:07:20+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> In one of my previous images I posted here it shows what the skeleton is doing.yep, I saw the pics.

> but as an MD5 I can at least see the skeleton but the problem remains that the joints are bunched up togethertalking about Noesis, too?

> The Red Line is the skeleton information. The dot represents the joints.
From the md5anim file we can see that there's 25 joints, maybe 1 or two are helpers, one is root:
hierarchy {
	"npc001" -1 63 0
	"NULL" 0 63 6
	"COG" 1 63 12
	"BD-00" 2 63 18
	"BD-01" 3 63 24
	"AL-00" 4 63 30
	"AL-01" 5 63 36
	"AL-02" 6 63 42
	"AL-03" 7 63 48
	"AR-00" 4 63 54
	"AR-01" 9 63 60
	"AR-02" 10 63 66
	"AR-03" 11 63 72
	"NK-00" 4 63 78
	"HD-00" 13 63 84
	"ROBE-00" 4 63 90
	"ROBE-01" 15 63 96
	"WST-00" 2 63 102
	"LL-00" 17 63 108
	"LL-01" 18 63 114
	"LL-02" 19 63 120
	"LR-00" 17 63 126
	"LR-01" 21 63 132
	"LR-02" 22 63 138
	"KISERU" 0 63 144
}
From this pic you can see there's only 5 joints. 



Noesis-co_0002.JPG (14.12 KiB) Viewed 334 times

For me this is far from "loaded fine".

Or did you mean "loaded but with the joints bunched up"?

(Maybe try another md5anim importer?)
## Post #11
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-25T10:21:59+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> SaucyMonkey wrote:In one of my previous images I posted here it shows what the skeleton is doing.yep, I saw the pics.
but as an MD5 I can at least see the skeleton but the problem remains that the joints are bunched up together talking about Noesis, too?
The Red Line is the skeleton information. The dot represents the joints.
From the md5anim file we can see that there's 25 joints, maybe 1 or two are helpers, one is root:
hierarchy {
	"npc001" -1 63 0
	"NULL" 0 63 6
	"COG" 1 63 12
	"BD-00" 2 63 18
	"BD-01" 3 63 24
	"AL-00" 4 63 30
	"AL-01" 5 63 36
	"AL-02" 6 63 42
	"AL-03" 7 63 48
	"AR-00" 4 63 54
	"AR-01" 9 63 60
	"AR-02" 10 63 66
	"AR-03" 11 63 72
	"NK-00" 4 63 78
	"HD-00" 13 63 84
	"ROBE-00" 4 63 90
	"ROBE-01" 15 63 96
	"WST-00" 2 63 102
	"LL-00" 17 63 108
	"LL-01" 18 63 114
	"LL-02" 19 63 120
	"LR-00" 17 63 126
	"LR-01" 21 63 132
	"LR-02" 22 63 138
	"KISERU" 0 63 144
}
From this pic you can see there's only 5 joints. 
Noesis-co_0002.JPGFor me this is far from "loaded fine".

Or did you mean "loaded but with the joints bunched up"?

(Maybe try another md5anim importer?)

Baby steps is how I looked at it when I said that it "loaded fine". Better then not loading at all but... still if I can't get the animation to stop scrunching up then it may as well not load at all.

The joints are actually there but they're literally balled up together at a particular spot for some reason. From your picture that is what we're left with in Noesis. Again Mr.Adults hits the nail on the head here with this post: [viewtopic.php?p=90014](http://forum.xentax.com/viewtopic.php?p=90014) but I just don't know how to do what he suggested.

You can test this by placing it into Blender or Maya and simply looking through the bone hierarchy.

I'm going to go ahead and try a different md5anim importer but... I can almost promise the results will be the same since this is how it loads up in maya as an FBX as well. Also, I want to say thank you for spending the time on working with me on this. The answer is somewhere! Anywho, i'll report back if another md5anim importer works or not.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-25T20:31:11+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> Again Mr.Adults hits the nail on the head here with this post: viewtopic.php?p=90014 but I just don't know how to do what he suggested.nor do I - that's a known problem with some of MrAdult's comments  (because often advanced knowledges is required to understand him)

btw: just to inform you, the numverts of the three meshes in npc001.md5mesh
seem to be wrong for some reason:

7521 -> 1792
234 -> 57
84 -> 32

I've found a MD5Modelloader project on my harddisk. Animation is clumped as with brres viewer with Play rotations only
unchecked but here we have a C-source:



MD5Modelloader.JPG (24.13 KiB) Viewed 315 times
## Post #13
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-25T23:57:16+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> SaucyMonkey wrote:Again Mr.Adults hits the nail on the head here with this post: viewtopic.php?p=90014 but I just don't know how to do what he suggested.nor do I - that's a known problem with some of MrAdult's comments  (because often advanced knowledges is required to understand him)

btw: just to inform you, the numverts of the three meshes in npc001.md5mesh
seem to be wrong for some reason:

7521 -> 1792
234 -> 57
84 -> 32

I've found a MD5Modelloader project on my harddisk. Animation is clumped as with brres viewer with Play rotations only
unchecked but here we have a C-source:
MD5Modelloader.JPG

Wait a sec. Were you getting clumped animations with the BRRES Viewer option "Play Rotations Only" on? Because that shouldn't happen.

 Well at this point we can safely assume then that the exporter is working fine truthfully. We know that the bones are there... I also came across something interesting for Maya.

[http://download.autodesk.com/us/maya/20 ... =d0e335174](http://download.autodesk.com/us/maya/2009help/index.html?url=Skeleton__Retargeting__Retarget_Skeleton.htm,topicNumber=d0e335174)

Except...THE OPTION ISN'T THERE FOR MAYA 2014 under skeleton! I highly doubt they deprecated it but if someone knows where the Joint Rotations Only option is then please list it!
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-26T07:00:58+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> Wait a sec. Were you getting clumped animations with the BRRES Viewer option "Play Rotations Only" on?nope. Unchecked means: 'off'
## Post #15
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-26T12:01:54+00:00
- Post Title: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> SaucyMonkey wrote:Wait a sec. Were you getting clumped animations with the BRRES Viewer option "Play Rotations Only" on?nope. Unchecked means: 'off'

Gotcha. What we really need is someone to decrypt what Mr.Adults said here.

[viewtopic.php?p=90014](http://forum.xentax.com/viewtopic.php?p=90014)

It's evident that this must be the key.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-27T11:15:57+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> What we really need is someone to decrypt what Mr.Adults said here.yeah, the mighty "someone" - heard of him sometimes.   But who is? fatduck for example has left the forum.

On the other hand the problem might be just related to absolute/relative coordinates.
I changed the translation of 6 bones (offset= -30.0) and you can see the right leg. 
But the shoe is located at the knee so the bones/joints obviously need different offsets:



shoeKnee.JPG (17.38 KiB) Viewed 271 times
## Post #17
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-27T22:30:21+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> SaucyMonkey wrote:What we really need is someone to decrypt what Mr.Adults said here.yeah, the mighty "someone" - heard of him sometimes.   But who is? fatduck for example has left the forum.

On the other hand the problem might be just related to absolute/relative coordinates.
I changed the translation of 6 bones (offset= -30.0) and you can see the right leg. 
But the shoe is located at the knee so the bones/joints obviously need different offsets:
shoeKnee.JPG

Progress! You're beautiful or handsome shakotay2, you get to decide which. Now were you changing the translation in a renderer or notepad and was this before or after it was loaded up? I want to help contribute and this has been a good learning experience for me and I cannot wait until we can get this figured out.

That's too bad about FatDuck though.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-27T23:16:19+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> Now were you changing the translation in a renderer or notepadI changed Kentilan's old mdlviewer source which was uploaded by chrrox [viewtopic.php?f=3&t=3636](http://forum.xentax.com/viewtopic.php?f=3&t=3636)
(which doesn't contain the "play rotations only" feature nor an export option)

Sadly it's not as easy as I thought: translation offsets only work for 2 of the 6 bones I changed
because  most of the bones in the co_0002.brcha animation file don't have translations.
(LL= leg left, LR= leg right)

"LL-00" no transl
"LL-01" no transl
"LL-02" no transl

>	"LR-00" fixed
>	"LR-01" fixed
"LR-02" no transl

LR-02 should be the right foot and the transl offset didn't apply.

Have to think about how to change the code but before I've to understand why LL has no transl and LR has fixed ones. That's totally weird.

I'll try to simply put the offsets into the none translation path. That's a stupid approach but might work. 

edit: well, cool idea:



legs_ok.JPG (15.43 KiB) Viewed 254 times

(sometimes I ask myself why I need so much time to solve very simple things  )
## Post #19
- Username: shakotay2
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-06-27T23:58:04+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

Having given myself absolutely no context for what you guys are really talking about here, what was meant by that comment over in the FF13 thread is that some of FF13's animations (like 12's) are additive. In order to apply them, you take any old pose in any old space you like (joint local or model space, doesn't matter, since the animtion's transforms are relative to another transform), then you do a matrix multiply with every joint transform in that pose with every joint transform from the additive animation. The idea behind these things is typically to blend multiple animations together at runtime, often done via some kind of state machine.

I haven't looked at any of the things or data you're tossing around here, so I couldn't say if you're dealing with additive anims, but it doesn't really sound like it. Also, md5anims only have animation data, that's why Noesis is drawing lines and points for you. Load the md5mesh, then drag the md5anim file from an Explorer window or something over the Noesis model preview pane and apply it to the scene when it asks if you want to see the md5anim with the md5mesh. There are 50 other ways to accomplish that in Noesis too, but this is probably the simplest one.
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-28T00:15:47+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from MrAdults
>
> I haven't looked at any of the things or data you're tossing around here, so I couldn't say if you're dealing with additive anims, but it doesn't really sound like it.guess so. Thx for your input - it's appreciated.

@SaucyMonkey: I think I got to know why the model is clumped when playing the anims with "Play Rotations Only" off: in Kentilan's old source the translations are set to 0.0 (if they don't have fixed values).
Guess "Play Rotations Only" simply doesn't set translations to 0.0.

So we would need the translation values/bones' positions for the initial pose, apply them once at animation startup then play rotations only.
## Post #21
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-28T02:21:56+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> MrAdults wrote:I haven't looked at any of the things or data you're tossing around here, so I couldn't say if you're dealing with additive anims, but it doesn't really sound like it. guess so. Thx for your input - it's appreciated.

@SaucyMonkey: I think I got to know why the model is clumped when playing the anims with "Play Rotations Only" off: in Kentilan's old source the translations are set to 0.0 (if they don't have fixed values).
Guess "Play Rotations Only" simply doesn't set translations to 0.0.

So we would need the translation values/bones' positions for the initial pose, apply them once at animation startup then play rotations only.

So if I understand you correctly then you basically want the translation values for the t-pose of the model right? Otherwise, for each md5anim could easily grab this data by opening it up in notepad++. 

But if what you're saying is correct about the translations being set to 0 then there must be an option someplace in Maya to unlock the translation data? In which case that should essentially set it? I'll look into this. As usual if it works i'll let you know. If it doesn't well... you won't see any progress reports or updates from me on that avenue.




baseframe {
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( -0.000002 0.000000 15.400000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000002 3.999998 35.000031 ) ( 0.000000 0.000000 0.000000 )
	( -2.000002 18.499989 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000002 46.000000 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000002 72.000000 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000002 -4.000000 35.000008 ) ( 0.000000 0.000000 0.000000 )
	( -2.000000 -18.499994 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000000 -46.000000 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -2.000000 -72.000000 37.000000 ) ( 0.000000 0.000000 0.000000 )
	( -5.500000 0.000000 38.099998 ) ( 0.000000 0.000000 0.000000 )
	( -2.000001 0.000000 50.899994 ) ( 0.000000 0.000000 -0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000001 10.000000 -18.600019 ) ( 0.000000 -0.000000 0.000000 )
	( -0.000006 10.000000 -58.600021 ) ( 0.000000 -0.000000 0.000000 )
	( -0.000011 10.000000 -94.600006 ) ( 0.000000 -0.000000 0.000000 )
	( 0.000002 -10.000000 -18.600019 ) ( 0.000000 0.000000 0.000000 )
	( 0.000007 -9.999999 -58.600021 ) ( 0.000000 0.000000 0.000000 )
	( 0.000021 -9.999994 -94.599991 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
}

frame 0 {
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 101.843102 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.011005 0.036401 0.298739
	0.000000 0.000000 0.000000 -0.002493 -0.060985 -0.022419
	0.000000 0.000000 0.000000 0.092230 -0.058328 -0.037949
	0.000000 0.000000 0.000000 0.498011 -0.037359 0.055284
	0.000000 0.000000 0.000000 0.001835 -0.009354 0.192299
	0.000000 0.000000 0.000000 0.093313 0.161747 -0.057168
	0.000000 0.000000 0.000000 -0.090120 -0.075983 0.023701
	0.000000 0.000000 0.000000 -0.487344 -0.075616 -0.120168
	0.000000 0.000000 0.000000 -0.002702 -0.012517 -0.210908
	0.000000 0.000000 0.000000 -0.076162 0.137793 0.097818
	0.000000 0.000000 0.000000 -0.021082 -0.039192 -0.132213
	0.000000 0.000000 0.000000 0.046912 0.004220 -0.129363
	0.000000 0.000000 0.000000 0.002587 0.044243 0.296169
	0.000000 0.000000 0.000000 -0.128622 0.041779 -0.214465
	0.000000 0.000000 0.000000 0.000000 -0.141305 0.000000
	0.000000 0.000000 0.000000 0.104586 0.034039 0.067742
	0.000001 0.000000 0.000000 0.157238 -0.056802 0.154204
	0.000000 -0.000001 0.000000 0.000000 -0.061023 0.000000
	0.000000 0.000000 0.000000 -0.141781 0.050978 0.012833
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
}

> Reply from MrAdults
>
> Having given myself absolutely no context for what you guys are really talking about here, what was meant by that comment over in the FF13 thread is that some of FF13's animations (like 12's) are additive. In order to apply them, you take any old pose in any old space you like (joint local or model space, doesn't matter, since the animtion's transforms are relative to another transform), then you do a matrix multiply with every joint transform in that pose with every joint transform from the additive animation. The idea behind these things is typically to blend multiple animations together at runtime, often done via some kind of state machine.

I haven't looked at any of the things or data you're tossing around here, so I couldn't say if you're dealing with additive anims, but it doesn't really sound like it. Also, md5anims only have animation data, that's why Noesis is drawing lines and points for you. Load the md5mesh, then drag the md5anim file from an Explorer window or something over the Noesis model preview pane and apply it to the scene when it asks if you want to see the md5anim with the md5mesh. There are 50 other ways to accomplish that in Noesis too, but this is probably the simplest one.

Hey there, thanks for chipping in. Getting this worked out means quite abit to me so I wanted to say thank you. I understood the context behind your post just the methodology behind performing it was where I was lost. 

Yeah, the drag in worked just fine. But now we're back to the same issue we had in the BRRES viewer which is the clumped up bone/joint data. Now, we know the data itself works when we use the "Play Rotation Only" option in the BRRES viewer. What we're trying to figure out however is why it clumps together the way that it does which we're pinning it down somewhat.




_____________

Edit:

[http://postimg.org/image/xbnoc61ct/](http://postimg.org/image/xbnoc61ct/)

I couldn't help but notice that regardless of the frame. The translation data says it is set (But then why the clumping?) but oddly it also says that the rotation data isn't actually rotating at all which is quite odd.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-28T08:41:17+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from SaucyMonkey
>
> So if I understand you correctly then you basically want the translation values for the t-pose of the model right? Otherwise, for each md5anim could easily grab this data by opening it up in notepad++.yep, but since we're not sure about the exported anim data it's more safe to take the positions directly from the model, imho. (assuming npc001.md5mesh is being exported correctly by Kentilan's viewer)

> baseframe {
>
> 	( 0.000000 0.000000 0.000000 ) ( 0.000000 0.000000 0.000000 )
>
> ...which model does this animation belong to? Is it for npc001?
Since this baseframe uses 26 bones. It should be 25 (or 25 plus 3x not-a-bone).

Anyway this is the skeleton with baseframe data (from co_0002.md5anim) included.
It's a little bit different from the one directly taken from npc001.md5mesh
plus wrong scaling so maybe I better take the data from the original skeleton, but not sure:



baseframe-skeleton.JPG (32.77 KiB) Viewed 236 times
## Post #23
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-30T10:19:46+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

No, it isn't npc001. I was playing around with NPC007. Though the animation works for him as well (They all fit the same animations.)

I've managed to get the base frame uploaded into Maya which is nice. But ONCE the animation plays it balls up. We're getting very, very close to figuring this out though which makes me happy.
## Post #24
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-06-30T14:04:02+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from MrAdults
>
> 

I haven't looked at any of the things or data you're tossing around here, so I couldn't say if you're dealing with additive anims, but it doesn't really sound like it.

Are you sure? 

frame 3 {
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	-0.002204 0.009674 101.832855 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.010844 0.036425 0.300306
	0.000000 0.000000 0.000000 -0.002271 -0.061667 -0.022055
	0.000000 0.000000 0.000000 0.091645 -0.058319 -0.038153
	0.000000 0.000000 0.000000 0.499344 -0.036828 0.054540
	0.000000 0.000000 0.000000 0.002534 -0.010428 0.193826
	0.000000 0.000000 0.000000 0.091635 0.162315 -0.056667
	0.000000 0.000000 0.000000 -0.090831 -0.075987 0.023168
	0.000000 0.000000 0.000000 -0.486145 -0.075716 -0.122385
	0.000000 0.000000 0.000000 -0.002773 -0.010851 -0.209870
	0.000000 0.000000 0.000000 -0.078590 0.139531 0.097064
	0.000000 0.000000 0.000000 -0.020938 -0.037603 -0.133265
	0.000000 0.000000 0.000000 0.046961 0.004526 -0.130254
	0.000000 0.000000 0.000000 0.002326 0.045083 0.297579
	0.000000 0.000000 0.000000 -0.128313 0.040577 -0.214606
	0.000000 0.000000 0.000000 0.000000 -0.141558 0.000000
	0.000000 0.000000 0.000000 0.104667 0.034728 0.066526
	0.000001 0.000000 0.000000 0.158354 -0.055691 0.153948
	0.000000 -0.000001 0.000000 0.000000 -0.063909 0.000000
	0.000000 0.000000 0.000000 -0.141843 0.052074 0.011168
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
	0.000000 0.000000 0.000000 0.000000 0.000000 0.000000
}

The translate data is 0.0 and it makes sense. When played in Maya or Noesis it sets the joints to 0 which causes the disfigurement.

> Reply from MrAdults
>
> In order to apply them, you take any old pose in any old space you like (joint local or model space, doesn't matter, since the animtion's transforms are relative to another transform), then you do a matrix multiply with every joint transform in that pose with every joint transform from the additive animation.

.


How exactly is this done? Any more information on being able to do this? Thank you.
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-30T22:45:08+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

I think we've just to recalculate the anims (i.e. add the transitions):



baseframe_trans.JPG (35.88 KiB) Viewed 211 times


It's totally ugly because I took the baseframe transitions (see pic in my previous post) for three test frames (md5anim).

(If I had taken the data from the t-pose noone would have seen that it works (should work  ).)

The transitions of the NULL bone must be left unchanged, I think, because they vary for each frame.

(Other than for the legs I couldn't find the correct offsets for the arms for some weird reason
 when changing Kentilan's old viewer code.)
## Post #26
- Username: SaucyMonkey
- Rank: n00b
- Number of posts: 13
- Joined date: Wed Jun 24, 2015 6:38 am
- Post datetime: 2015-07-01T02:14:33+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> I think we've just to recalculate the anims (i.e. add the transitions):
baseframe_trans.JPG
It's totally ugly because I took the baseframe transitions (see pic in my previous post) for three test frames (md5anim).

(If I had taken the data from the t-pose noone would have seen that it works (should work  ).)

The transitions of the NULL bone must be left unchanged, I think, because they vary for each frame.

(Other than for the legs I couldn't find the correct offsets for the arms for some weird reason
 when changing Kentilan's old viewer code.)

That's great to hear. I also tossed it into Unreal Engine 4 and retargeted the skeleton and it also fixed the clumped up animations inside of UE4. Though i'd like to have it unclumped for Maya or Blender as well.

I'd like to see your progress for the normal T-pose. Let me know how that goes! Sheesh... all of this work when Maya or Blender could simply have a "Play Rotations Only" option.
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-03T13:08:29+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

got it:
[](http://www.pic-upload.de/view-27564146/walkInNoesis.jpg.html)
I've attached an MD5anim file where I've replaced the transitions by the ones from npc001.md5mesh
Load the mesh into Noesis then drag the MD5anim onto it and answer 'No' to the message box popping up.


 co_0002-trans.zip
(28.14 KiB) Downloaded 39 times



edit: of course I forgot to leave the NULL bone's transitions as they are - so the indian moves his legs
but he doesn't proceed - funny  .
## Post #28
- Username: kimsama
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 13, 2014 3:23 pm
- Post datetime: 2016-09-23T14:43:01+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

> Reply from shakotay2
>
> I've replaced the transitions by the ones from npc001.md5mesh

How can I replace the transitions from the .md5mesh? 

Could you explain about that for more detail? 

Thanks,
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-23T17:18:40+00:00
- Post Title: Re: Maya, Noesis & MH Tri Player Animations.

sry. I won't dig up this 14 months old thread.

the initial idea, iirc, was:
"So we would need the translation values/bones' positions for the initial pose, apply them once at animation startup then play rotations only."

Get the npc brres sample from the post as of Jun 24, 2015, 10:01 am. Create a md5mesh file from it and compare it to the md5anim file from my last post.

This way it should be plain to see what I've changed.
