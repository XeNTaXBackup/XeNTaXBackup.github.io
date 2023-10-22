## Post #1
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-05-25T20:56:12+00:00
- Post Title: Diablo 3 Animation files

[out]
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-05-28T00:56:49+00:00
- Post Title: Diablo 3 Animation files

[out]
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-30T00:04:17+00:00
- Post Title: Diablo 3 Animation files

Hi guys, been breaking my head on this animation file format, almost have everything cleared out, yet the rotation seems to me like a blur...

I downloaded the Ultimate Unwrap 3D Pro demo to check what the result should be of a chest that has an Open animation.

With the ani file nearly figured out, I came across some issue to find the correct angle

in Max I use the following code: 

```
rotate $hinge eu 
```


this works, but this is data from Unwrap 3D,
now for the angle I have the following data in the ani file

```
 00 00   8F 7F   00 00   73 F5
   x         y       z       w
   0    0.996597    0    0.0824342


```

these x y z w, I think represent a quat

and if so they sould be converted to the number underneath them,
I mean

y= 8F 7F and should become 0.996597
w= 73 F5 and should become 0.0824342

Any help is appreciated !!

T.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-30T08:33:44+00:00
- Post Title: Diablo 3 Animation files

out of context noone can help you, I guess.

You're having 8 bytes to be converted into 4 values.
(what is the connection to the angles 180 -9.457 180?)

Firstly the format of the bytes is to be solved: is it half floats, is it words (unsigned16)?
edit: ok, it's signed, of course  

Secondly the required math conversion must be found.
Is it Euler angles to Quaternion for example?
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-30T09:34:12+00:00
- Post Title: Diablo 3 Animation files

Here is what I did:

I opened Unwrap 3D, and imported the app model file with the appropriate ani file. ( that would be the rare chest with the open animation )
and in Unwrap 3D, I get to see that the animation on the Hinge Bone is set to eulerangles (180 -9.457 180)

Everything seems to add up if I follow the structure in multiple animation file like position, rotation and scale.

here I mean that the number of frames etc match the data I find in Unwrap 3D....

the only thing that is missing, is that I have eight bytes , 
00 00 8F 7F 00 00 73 F5

which should represent, or be converted to, the eulerangles above :/

I know that the format of the app file is sometimes weird ( like the uv's, you need to substract 32767 and then devide it by 512 ... )

They are not half floats, I checked.

Now if I convert the above eulerangles to a quaternian,
it results in:

quat 0 0.996597 0 0.0824342

so I presume there must be a way to convert 8F7F to 0.996597 and 73F5 to 0.0824342

tried already lots of stuff, but, maybe I'm just not smart enough, cause the guys from Unwrap 3D did it ....

So,some more help would be hardly appreciated..

T.
## Post #6
- Username: timkango
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 12, 2011 4:16 pm
- Post datetime: 2013-12-30T11:26:32+00:00
- Post Title: Diablo 3 Animation files

TaylorMouse, I'm having some trouble following your post, so apologies if I've misread it.

The 8 byte data block looks like a quaternion stored as 4 signed 16 bit integers (divide by 32767 to get the quat).


From your sample:

XYZ Euler angles in degrees [180 -9.457 180] is XYZW quaternion [0.0000 0.9966 0.0000 -0.0824].

Data block [00 00   8F 7F   00 00   73 F5] is 4 signed shorts [0 32655 0 -2701]. Divide by 32767 -> [0.0000 0.9966 0.0000 -0.0824].
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-30T11:49:50+00:00
- Post Title: Diablo 3 Animation files

OMG, yes that is it, How could have been so f*** stupid!

well, it was 01:15 in the morning when I got to this 

I'll try that this evening!

thnks Timkango!

T.
## Post #8
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2013-12-30T22:37:43+00:00
- Post Title: Diablo 3 Animation files

Yep it works!!!

Next on my todo list, is read the ani file into Max
then apply the animations to the correct bone in the right frame 

Keep you guys posted

T.
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-01T23:25:50+00:00
- Post Title: Diablo 3 Animation files

Hi guys, done some progress...

I succeeded in importing and animating the Diablo III Rare chest.

Yet it only has 2 bones, and the root bone doesn't do anything, so I was really happy to see that work.

Then I went over to another model, adria.app ( included in the attachment )
ran the 2 scripts (both included in the attachment ), 
[*]One for importing the app file 
[*]One for importing the ani file

I tried the Adria Run animation file adria_run_01.ani ( included in the attachment ), she runs, but it looks like crap !!

I tried the same on the adria_walk_01.ani( included in the attachment ), it looks even more like crap!!!

Since this is my first tryout on making animations with 3DS Max scripts, I could really use some help here.

So please take a look at the scripts and tell me what I'm missing/doing wrong...

PS: script written in Max 2011 and it needs to work in 2011 or above

Thanks in advance

T.
[Adria.zip](https://xentaxbackup.github.io/file/6883_Adria.zip)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T08:54:24+00:00
- Post Title: Diablo 3 Animation files

from a first glance I found only the first bone having all frames;
the rest is like this:
(TranslationAnimation BoneId:2 KeyFrame:0 position:[0.0401016,0,0.143678])
(TranslationAnimation BoneId:2 KeyFrame:22 position:[0.0401016,0,0.143678])

Don't know whether this being an issue.
(Could you upload the Rare chest app&ani, please?)

btw: is it given somewhere or did you get the anim format all by yourself? 
      (if the latter: great work so far  )
## Post #11
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T09:00:10+00:00
- Post Title: Diablo 3 Animation files

Hey Chakotay2, thanks for the quick reply, I will do that this evening, since I'm at work for the moment.

What I tried additionally, was applying the rotation quaternion from the app file, but no luck there.

Question: I needed to add the parent position to the child bone position to get it right, do I need to do this with the rotation as well ?

T.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T09:25:49+00:00
- Post Title: Diablo 3 Animation files

> Reply from TaylorMouse
>
> What I tried additionally, was applying the rotation quaternion from the app file, but no luck there.you mean the q1 that isn't used in your uploaded Import Diablo III App.ms?

> Question: I needed to add the parent position to the child bone position to get it right, do I need to do this with the rotation as well ?would make sense, but I'm just a beginner with animations, so not sure.

from my previous (overlapping) edit:
could you upload the Rare chest app&ani, please?

btw: is it given somewhere or did you get the anim format all by yourself?
(if the latter: great work so far  )

edit: well, from this thread [viewtopic.php?f=16&t=7337](http://forum.xentax.com/viewtopic.php?f=16&t=7337)
it seems BoyC being the first one working on the app format.
## Post #13
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-02T09:57:25+00:00
- Post Title: Diablo 3 Animation files

[http://rghost.ru/51350599](http://rghost.ru/51350599)
it script for diablo 3 app/ani export. i'm not so good in max script. but it work. no materials/textures yet. i upload new script when i write some changes. feel free to modify.
Sorry for bad english
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T10:46:24+00:00
- Post Title: Diablo 3 Animation files

> Reply from ZeroGravity
>
> [...] but it work. no materials/textures yet. i upload new script when i writemesh import is fine. Which animation did you try?
For me Adria_walk_01.ani is a little bit better than with T.'s script:
[](http://www.pic-upload.de/view-21813246/Adria_walk.jpg.html)

(But may be due to my Max2013, which I broke using some outdated scripts/dll-plugins and couldn't fix again.  )

There's also different animation keyframes per bone:
BoneID 1: "keyfr. = 22"
BoneID 2: "keyfr. = 22"
"keyfr. = 22"
"keyfr. = 20"
"keyfr. = 21"
"keyfr. = 6"
"keyfr. = 5"
"keyfr. = 13"
"keyfr. = 10"
"keyfr. = 2"
"keyfr. = 18"
"keyfr. = 11"
"keyfr. = 16"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 15"
"keyfr. = 9"
"keyfr. = 8"
"keyfr. = 16"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 2"
"keyfr. = 22"
"keyfr. = 22"
"keyfr. = 22"
"keyfr. = 12"
"keyfr. = 22"
"keyfr. = 21"
"keyfr. = 22"
"keyfr. = 16"
boneID 40: "keyfr. = 21"

As I said I'm just an animation noob, but my experience tells me that there should be the same count of keyframes for every bone.

If we don't have enough we might create dummy frames with "no motion" but that's just a wild guess of mine.

Maybe an expert can give a statement?

edit: ok, silly me. I looked at the rotations only. For the positions it's the same count for all boneIDs (except for boneID 1, see my next post)
## Post #15
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-02T11:28:07+00:00
- Post Title: Diablo 3 Animation files

i use max 2009 and just tested it with adria
all good
[http://postimg.org/image/58joy12y9/](http://postimg.org/image/58joy12y9/)
[http://postimg.org/image/taz31k7rj/](http://postimg.org/image/taz31k7rj/)
and no bones have diferent count of keyframes
root bone have keyframes for every frame, but children bones can have even zero keyframes

Edit: found bug in skinning, first bone unskined

edit 2: fixed bug in skinning, script [http://rghost.ru/51353010](http://rghost.ru/51353010)
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T11:38:12+00:00
- Post Title: Re: Diablo 3 Animation files

> Reply from ZeroGravity
>
> i use max 2009 and just tested it with adria
all goodOk, thx. 

> and no bones have diferent count of keyframes
I got the counts from your function app_read_animations
by inserting a Print cmd:
...
for j = 1 to l_num_bones do (
..
xx = app_file_pos ofs ani_file
Print ("keyfr. = " + (an.ani_bones[j].num_keys_rot as string))
for k = 1 to an.ani_bones[j].num_keys_rot do (
..

and the Max script Listener output (see my previous post) tells me that they are different. edit: ok, me dumbo looked at the rotation only...  

edit: will have a look at the translation, wait a minute...

ok; for the position the keyframe count is 2 for all boneIDs (except for boneID1 it's 44)
I'll have to think about this... 

(where does my Max leave the 42 missing frames for the boneIDs 2..40???)

edit2: after deleting front_loinCloth I realized that the walk animation is working pretty well. Seems it's the skinning I've a problem with...
## Post #17
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-02T12:07:10+00:00
- Post Title: Re: Diablo 3 Animation files

[http://rghost.ru/51353091](http://rghost.ru/51353091)
script for 010 editor. out animation file in plain text.
it's old. i write it for open beta diablo 3
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T12:51:05+00:00
- Post Title: Re: Diablo 3 Animation files

> Reply from ZeroGravity
>
> script for 010 editor. out animation file in plain text.thx again!  

hmm, bt. I'll have to download the 010 editor's demo version -
but I guess it would make more sense to get my Max working again (really hate to reinstall it before knowing which dll plugin ruined it  ).
## Post #19
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T14:49:02+00:00
- Post Title: Re: Diablo 3 Animation files

@ZeroGravity

I see you use a AssumeSkinePose() and the Inverse methods, need to check them, maybe this could be the problem ...

@Chakotay2,

wel I based my animation knowledge on the second post in this thread by Wobbe, the rest I kinda broke my head on figured it out myself, very satisfying when that chest animated perfectly :p

Please do re-install MAX asap we need you dude !

When I get at home in a couple of hourse I'll post the chest and I'll test ZeroGravity's script

Thanx already guys

T.
## Post #20
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T16:52:41+00:00
- Post Title: Re: Diablo 3 Animation files

Hey Chakotay2, here is the file (chest) your requested with the ani files and the dds files included


Good luck :p

T.
[Chest.zip](https://xentaxbackup.github.io/file/6886_Chest.zip)
## Post #21
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T17:30:08+00:00
- Post Title: Re: Diablo 3 Animation files

YES !! It works!!

Learned some nice stuff from that script Zero Gravity wrote!!

AssumeSkinPose() --> Very important, never heard of it, not very well documented either

matrix.row = b.Pos --> apply the position to the matrix in stead of what I did, only apply the rotation (dumb ass)

with animation on at time <T> in coordsys parent bone.Position = AnimationPosition  --> which allows the position of the current bone in reference to the parent, in stead of doing some weird checks and calculations to achieve the right (or wrong) position

but I'm already happy I got this far on my own 

Thanks a bunch guys

I'll test some more animations and I'll post my adjusted script afterwards

T.
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-02T18:08:30+00:00
- Post Title: Re: Diablo 3 Animation files

Thx for chest and script!  
For the chest your script is working like Z.'s adjusted one with my strange Max2013.
(Although it looks like the lower part is moving while the lid doesn't, resp. in the wrong direction.)
[](http://www.pic-upload.de/view-21818461/chest.jpg.html)

btw: for the spelling of my nick see my signature!
## Post #23
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-02T20:54:01+00:00
- Post Title: Re: Diablo 3 Animation files

Hey Shak-otay ( sorry about the misspelling all the time I just look at your nick above your avatar )  

Thanks for all the help from you guys I was able to put together the last script ( animation script ) to a good end.

Included in the zip file are 2 scripts, one for importing the .app (3D Model) files and one for the .ani (animation) files

PS: Put the .app file in the texture directory and there is a possible way that the script picks up the correct diffuse texture ( not guaranteed thou)


Please test and any feedback is appreciated!

Cheers

T
[Diablo III Import Scripts.zip](https://xentaxbackup.github.io/file/6889_Diablo III Import Scripts.zip)
## Post #24
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-03T16:26:56+00:00
- Post Title: Re: Diablo 3 Animation files

update: for now script import model/texture coords/skin/bone/animation/hardpoints, you can add one  animation at time, but all anims stored continuous. Pleace give any advice about cloth system in 3dmax
[app_import.zip](https://xentaxbackup.github.io/file/6895_app_import.zip)
## Post #25
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-03T18:37:06+00:00
- Post Title: Re: Diablo 3 Animation files

Hey ZeroGravity, I've noticed that there are these HardPoints, but I ignored them up till now, what are they exactly?

I only used to test the plugin from Max Cloth when it first came out, don't know how to work with it from code thou.

T.
## Post #26
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-03T20:22:41+00:00
- Post Title: Re: Diablo 3 Animation files

I changed my Import D3 Ani Script

Added a Helper Dummy that has the animation names, start and end frame, for easy reference

Added a MessageBox that tells you how many frames are imported

Changed so that you no longer need to select the ani file, just select the folder that contains all the ani files you want to apply , limited to 100 ani files.

Added a config file that contains the last selected folder, so you don't need to browse to it every time

So how does it work:

Use the Import D3 App script to import a model

Put all the animation files for that model into a specific folder

Use the Improt D3 Ani script to select that folder and done

Hope you like it, learned a lot from this

and again thanks for the help guys!

T.
[Import Diablo III Ani.zip](https://xentaxbackup.github.io/file/6897_Import Diablo III Ani.zip)
## Post #27
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-03T21:05:05+00:00
- Post Title: Re: Diablo 3 Animation files

about animation files, they contain field with snoAppearence, if you look at my editor script you can filter animation by it and sno in app file, (but applying wrong animation can produse funny effects) and in .tex files exactly same thing you can read header and find right texture. as i see you use BoyC template as reference, normals some times are incorrect, i don't use this, 3dmax handle it by it's own, just try and you have more adequate results. how about patch files? as i think its aplayed after load raw data, and 7F is no apply, but i don't know offset to apply.
best regards to all of you. thanks
## Post #28
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-03T21:17:46+00:00
- Post Title: Re: Diablo 3 Animation files

and as i recall in you script app import, you not use rotation for last bone, so you can apply rotation without matrix, just like this bone.rotation = frame[j].rotation, and then positioning... hmmm or inverse rotation, i try many of them
## Post #29
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-03T22:46:43+00:00
- Post Title: Re: Diablo 3 Animation files

Created a little script to list the animations, start and end frame, so you don't need to look for them in the list of ani files and figure out where the start and end frame are:

```
(
	
	Button btnClose "Close"
	ListBox animationList "Animations" Width:400 

	on dialog open do
	(
		prop = GetUserPropBuffer (GetNodeByName "Animations")
		if(prop != undefined) then 
		(

		animationList.Items = filterString prop "\r\n"
		)
	)
	
	on btnClose PRESSED DO
	(
		DestroyDialog dialog
	)
	
	on dialog resized p2 DO
	(
		animationList.height = p2.Y - 50
		animationList.width = p2.X - 20
		
	)
)
clearListener()

utility Diablo3AniList "Diablo III Animation List"
(
	Button btnShowDialog "Show Animations"
	on btnShowDialog PRESSED do
	(
		CreateDialog dialog style:#(#style_titlebar, #style_minimizebox,#style_resizing) width:420
	)

)

```


T.
## Post #30
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-15T20:28:25+00:00
- Post Title: Re: Diablo 3 Animation files

Updated script, now support Reaper of Souls, app/ani versions
UPD: fixed
[app_import.zip](https://xentaxbackup.github.io/file/6920_app_import.zip)
## Post #31
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-01-17T13:58:59+00:00
- Post Title: Re: Diablo 3 Animation files

[out]
## Post #32
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-19T16:34:38+00:00
- Post Title: Re: Diablo 3 Animation files

[quote="Wobble"
For those who don't have access to the Reaper Of Souls beta version, where can we find some RoS app/ani files for testing?[/quote]

get ptr version, ros files are included
## Post #33
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-19T21:42:37+00:00
- Post Title: Re: Diablo 3 Animation files

Indeed, I also fixed my script on the beta (ptr) models, 

2 questions, 
1. Did you change the script for the animations too, or is that still the same
2. How did you convert the tex files to dds or tga or other?

T.
## Post #34
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-01-19T23:31:55+00:00
- Post Title: Re: Diablo 3 Animation files

Hey folks i got 2 noob questions and sorry for that: 1) How do i import textures with the model?
                                                                       2) Animations give me error: Call needs function or class, got:undefined
## Post #35
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-01-20T05:16:04+00:00
- Post Title: Re: Diablo 3 Animation files

@freakshow: Taylormouse's script has locations toward the bottom to put the textures.  Alternatively, I've been able to pretty much drag and drop onto the models.

@ Taylormouse: Is there something wrong with using D3Texconv to convert the textures?

I posted something in the .app file thread, but I wanted to know if anyone has gotten the character files to import with the various armor classes?
## Post #36
- Username: ZeroGravity
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Nov 27, 2011 5:29 am
- Post datetime: 2014-01-20T08:06:01+00:00
- Post Title: Re: Diablo 3 Animation files

@freakshow: as i remember, i fix this error in my lates script
@TaylorMouse: ani format changed, but i can't remember in what section, blizz add some zero bytes in it. And i managed to apply patches on files after some digging in internet, i post tool for that when it was done, so as on yesterday i find 2 new versions of app and ani formats (259; 260), tex files format not changed yet.
@LUBAR: yes, i import Barbarian_Male, Crusader_Male with all meshes and animations, but helmets and shoulders is separated files for each class
## Post #37
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-20T10:05:50+00:00
- Post Title: Re: Diablo 3 Animation files

@LUBDAR: no but for each conversion you need to press enter, so I wanted to mass convert all of the tex files. So it would be cool if there was not an export of the atlas file and no clicking after each conversion :/

@ZeroGravity: ok, then I need to change my ani script too.. thnx for keeping me up to date.


I was extually making a tex viewer, or at least when I click on the tex file, it would convert it to dds and open my dds viewer in c#

I ran into some problems, like a piece of c++ code that I'm unable to figure out....
Even if I try to recompile the c++ code, at runtime it crashes...

T.
## Post #38
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-01-20T17:48:52+00:00
- Post Title: Re: Diablo 3 Animation files

@Taylormouse:  ahh sounds good.  Previously I just ran d3texconv for the entire folder, but I suppose with RoS coming out I'd just have to do it again. Tex viewer/converter sounds pretty cool though, it'd reduce some of the guess work in matching up textures.
## Post #39
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-21T08:22:45+00:00
- Post Title: Re: Diablo 3 Animation files

Ok, finally got this thing working !!

C++ code has been recompiled, had to comment some stuff out, it no longer generates the atlas file, and no input from the user is required when conversion is done.

Next step is opening a dds viewer and show the dds image after double clicking the tex file...

T.
## Post #40
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-01-24T23:28:27+00:00
- Post Title: Re: Diablo 3 Animation files

Which MPQ are you guys looking into that has all tiers of armor models for character classes as well as animations.  I'm not on my personal machine, but instead of digging around aimlessly, I figured I'd ask if someone has already had luck with it.
I think off the top of my head the one I looked into was .../Diablo III/Data_D3/PC/MPQs/clientData.mpq for the app files and then I just pulled all the textures out of
.../Diablo III/Data_D3/PC/MPQs/Texture.mpq.

I noticed that when I go into the "base" folder or the "Cache" folder there are several other MPQs sometimes with a lot of .app files in their directories, but just wanted to know what other people were looking at.

-Thanks for your time.
## Post #41
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-26T18:04:44+00:00
- Post Title: Re: Diablo 3 Animation files

Yeah, well bad news is that I actually went through all of the mpq's and extracted app, tex and ani from all of them, but without keeping the path structure, so at the end I have lost of files, I did put them into textures, models and animation folder

T.
## Post #42
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-01-26T21:07:17+00:00
- Post Title: Re: Diablo 3 Animation files

Ahh that works out just as well, I'll just dump all of the app ani and tex into the same folder and hopefully the issue would resolve itself.  Although, I thought some files had the same name...  We'll find out...
## Post #43
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-28T21:28:12+00:00
- Post Title: Re: Diablo 3 Animation files

I think I just found an interesting model, he looks a lot like Griswold, is not textured, so no texture coordinates, there is no texture either, but from the looks of it, it could be griswold 

T.
[Griswold D3.PNG](https://xentaxbackup.github.io/file/6975_Griswold D3.PNG)
## Post #44
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-01-29T22:21:21+00:00
- Post Title: Re: Diablo 3 Animation files

Been braking my head (again) on mapping the textures to the models, anyone any idea where to find the mapping between the tex and the app files ? 

Cause I ain't finding it :/

I know it is possible cause with the model viewer CainsAide, it is done....


T.
## Post #45
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-02-13T02:59:47+00:00
- Post Title: Re: Diablo 3 Animation files

[out]
## Post #46
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-02-25T05:25:43+00:00
- Post Title: Re: Diablo 3 Animation files

Hi guys, I just wanted to see how the program operated for other people.  I have all the animations, and the .app file in the folder.  I have the texture file included as a .dds file in there also but it doesn't seem to automatically load.  It seems that I need to drag and drop the texture onto the model.  Is this the case for everyone else?
Thanks in advance
## Post #47
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-02-25T09:12:55+00:00
- Post Title: Re: Diablo 3 Animation files

@wobble : I'll see what I can upload tonight

@lubdar: yes it is for everyone, for now, 

I did write another script that searches in a hard coded path for textures based on the name of the model but it is not bullet proof. It works pretty fine for the non - animated models, but lacks its functionality for monsters and npc's :/

T.
## Post #48
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2014-02-26T18:54:40+00:00
- Post Title: Re: Diablo 3 Animation files

Ahhh thanks, that's good to know.  I think I should be alright, I moved everything into similar files and have just dumped similarly named files together and it works for the most part.  I got the dds files for all the textures loaded in one location, so it's a pretty simple name matching process at the moment.

Thanks again for everyone's work on this!
## Post #49
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-03-23T19:49:47+00:00
- Post Title: Re: Diablo 3 Animation files

I started writing some C++ code to parse .app files based on the maxscripts in this forum - tried parsing the bones and couldn't get it to match. The Bone-data should be (sizeBones/nBones = 13104 bytes / 42 bones = 310 bytes per bone). However none of the app_importers seemed to load that many. 

So, I finally noticed the Adria.zip posted on the first page of this thread and behold, it's a different format ( this file can be read with 010-edit ). Apparently the Adria.app file I extracted yesterday from my install has 320 bytes bone-data and is in the 260 format ( 010 edit only partially parses it ).

TaylorMouse code for reading the bones reads 236 bytes - which matches to the Adria attached in one of the first post by him ( which is version 247 ).

The app_import I found from zerogravity ( jan 15 2014) reads 280 bytes for version 258 ( and seems to have backward compatibility code for older version - note that checking for >=258 is probably better than ==258).

Does anyone have more recent importers / info on the fileformat changes for Reaper of Souls ?

Small Update: It looks like there is one more quad-vec3-scale element ( 5 now ). This is followed by 36 bytes, then the (already know) particle-id followed by yet another 4 bytes.

Regards
[Adria_v260.zip](https://xentaxbackup.github.io/file/7126_Adria_v260.zip)
## Post #50
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-03-23T22:01:33+00:00
- Post Title: Re: Diablo 3 Animation files

[out]
## Post #51
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-03-24T18:50:49+00:00
- Post Title: Re: Diablo 3 Animation files

> Reply from Wobble
>
> kalmiya wrote:I started writing some C++ code to parse .app files based on the maxscripts in this forum

This is the animation thread.  Diablo .app thread can be found here:
viewtopic.php?f=16&t=7337

Yes, .app format has slightly changed for v260.  Bones and geosets have some small changes.

Still waiting for someone to post some Adria .ani animation files from Reaper of Souls.
Thanks for the reference to the app-thread.

Concerning models, attached the walk/run adria-models, v118 (0x76). They are newer than the ones on the first page - those were v112 (0x70). Not sure if that these are in the RS format though.
[Adria-anim-v118.zip](https://xentaxbackup.github.io/file/7127_Adria-anim-v118.zip)
## Post #52
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2014-03-24T19:17:56+00:00
- Post Title: Re: Diablo 3 Animation files

[out]
## Post #53
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-21T02:15:37+00:00
- Post Title: Re: Diablo 3 Animation files

Unsure of what I'm doing wrong. I've tried running the script and I keep running into an error. I'm guessing because of the new format of the ROS models, but I'm unsure, as I downloaded his newest file.



Any help would be appreciated.

It works fine with the file that [TaylorMouse](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=37538) posted, but none of the files I've tried.
## Post #54
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-21T12:16:41+00:00
- Post Title: Re: Diablo 3 Animation files

My guess would also be that it's due to the new RoS format. Just take a look at the header, then you can see which fileversion it actually is - 
check out bytes 4-7 ( and convert those from hex to int ).

struct snoHeader 
{
    unsigned int tag;   // 0xDEADBEEF - bytes 0-3
    unsigned int ver;   // .app => d3-base=247, d3-rs (beta)=258, d3-rs 260 - bytes 4-7
    ...
};

d3-base .ani's have v112 and for RoS it's v118.
## Post #55
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-21T13:42:06+00:00
- Post Title: Re: Diablo 3 Animation files

You're always so helpful. I appreciate that.

I'm running into a new error after trying to come up with the fix:



0xDEADBEEF = There is no Cow Level ( Dead Beef )
## Post #56
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-21T17:58:47+00:00
- Post Title: Re: Diablo 3 Animation files

I'm parsing the boneid as an unsigned int (C++ parser), and here I have -1 for the first bone ( = 0xFFFFFFFF ).  Your value looks like minus-signed-int-max... 

Check how your bones are being numbered ( 0-n or 1-n) i.e. Either you are "off" on parsing ( and you are trying to interpret some "trash" as a bone-id) or you should add change the !=0 check. Maybe try >0 && < numbones - instead of !=0  ( again, without thoroughly looking at what the code does, I'm just guessing)...  Or maybe (as a debug-test) - just skip the first bone (to avoid the crash) and see if the values of the next bones make sense ( i.e. you would expect either 0 or 1 for the next parent-bone-id).
## Post #57
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-21T18:02:43+00:00
- Post Title: Re: Diablo 3 Animation files

Are you able to actually get the .app to work with the .ani files in 3ds Max? If so, I'd love to take a look at that parser code.

I'm at work so I can't test anything here. Will get back with you when I get home.
## Post #58
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-04-21T18:43:50+00:00
- Post Title: Re: Diablo 3 Animation files

I have a C++ parser which loads .app and .ani files into my little experimental engine - my goal is to see if I can get the bone-animation working. Made some progress, but nothing really usable yet. I have no experience with maxscript, so I can't help you there - besides giving some general advice. Maybe you should contact the original author of that script.
## Post #59
- Username: TheRealMethuselah
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Apr 13, 2014 1:19 am
- Post datetime: 2014-04-21T19:39:59+00:00
- Post Title: Re: Diablo 3 Animation files

I've PMd them with a question. Hopefully, within a few days, I'll receive a response. 

Keep us in the loop with what you come up with, my friend.

Can't wait until I can pose em'.



EDIT: Success!
## Post #60
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-06-06T20:38:22+00:00
- Post Title: Re: Diablo 3 Animation files

Didn't post updates for some time - too busy with other things - but anyway, I also got it working now. Code is still a bit hackish and instead of rendering it (for testing-purposes) I just exported a few frames in .obj format and imported those in blender. Doesn't look quite as impressive as the above screenshots, but the framework is there 

Here an example
## Post #61
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-06-08T08:51:32+00:00
- Post Title: Re: Diablo 3 Animation files

btw guys, did you download this from my assets at SC2Mapster, it contains the model import and the animation import into Max 2011 ?


[http://www.sc2mapster.com/assets/sc1-ra ... rt-script/](http://www.sc2mapster.com/assets/sc1-raynor-vulture/files/41-diablo-iii-reaper-of-souls-max-2011-import-script/)

T.
## Post #62
- Username: okami29
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Mar 09, 2017 8:57 pm
- Post datetime: 2018-11-26T17:01:27+00:00
- Post Title: Re: Diablo 3 Animation files

Hi TaylorMouse,
I successfully imported D3 Diablo Model with your script .However when trying to import an animation .ani I got this error :
call need function or class, got undefined.
I am using the script from SC2Mapster for Autodesk 2011, is there another version of the scripts ?
Thank you
[Sans titre.jpg](https://xentaxbackup.github.io/file/15243_Sans titre.jpg)
## Post #63
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2018-12-11T00:28:06+00:00
- Post Title: Re: Diablo 3 Animation files

I PM'd you

T.
## Post #64
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-12-12T19:34:10+00:00
- Post Title: Re: Diablo 3 Animation files

I am getting the same issue, could you please provide a fix TaylorMouse?
