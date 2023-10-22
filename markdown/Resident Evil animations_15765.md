## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T18:08:44+00:00
- Post Title: Resident Evil animations

Resident Evil 5 animations (test tool)

Usage: Re5Anims <LMT name> <MOD name>

Or you can just drop LMT file onto the tool. If you do that, or use only 1 parameter, it will search for file named model.mod for a model. Incorrect model will produce broken animations.

To attach animations to model, it must have bones named like bone0, bone1, etc. I used latest NOESIS export to FBX. You must create IK constraints connecting right toe to "atarget1" bone, left toe to "atarget2", with chain length 3, both position and rotation. So IK chain includes: toe, heel, knee. No idea how its done in maya or max, but hopefully the same as in blender.

Consider it a test tool, because not optimized, just interpolates all keys to all frames (which leads to bigger files), also many things are not supported:
- no scale. Some animations use scales, maybe muscle work, some monster fx, etc
- only one type of IK (legs). Some anims have hands IK, these will NOT work correctly, but I've only seen this is static poses
- no tag bones exported. These are for weapons or some other purposes.

I was also thinking about an option to export all motions as separate files. Let me know if will be useful.

Videos: [https://youtu.be/EhQ-6RW3sj0](https://youtu.be/EhQ-6RW3sj0) [https://youtu.be/X4tXTpJacXk](https://youtu.be/X4tXTpJacXk) [https://youtu.be/J9VyHnQ0crw](https://youtu.be/J9VyHnQ0crw) [https://youtu.be/te2Vvbex_hw](https://youtu.be/te2Vvbex_hw) [https://youtu.be/YZio9sT7CTc](https://youtu.be/YZio9sT7CTc) [https://youtu.be/WcU4mTFugKM](https://youtu.be/WcU4mTFugKM)




[Re5Anims.rar](https://xentaxbackup.github.io/file/12491_Re5Anims.rar)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-20T19:19:56+00:00
- Post Title: Resident Evil animations

Tool for DMC4, made in 2010 (not finished)

[viewtopic.php?p=41809#p41809](http://forum.xentax.com/viewtopic.php?p=41809#p41809)

Anyone who have max check if its working.
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2017-01-20T22:54:55+00:00
- Post Title: Resident Evil animations

This is on my Noesis todo list, but it's way down there below the Souls games under the "other people already did it" category. It's been on there for years, though, and I don't remember at all what gave me the notion that it was already done, and there are no format specs in my usual storage places. Do post the specs if you find them somewhere. (I don't have a valid Max license anymore myself, so can't test the above tool)
## Post #4
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-21T00:51:25+00:00
- Post Title: Resident Evil animations

> Reply from MrAdults
>
> This is on my Noesis todo list, but it's way down there below the Souls games under the "other people already did it" category. It's been on there for years, though, and I don't remember at all what gave me the notion that it was already done, and there are no format specs in my usual storage places. Do post the specs if you find them somewhere. (I don't have a valid Max license anymore myself, so can't test the above tool)
PMed
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T07:06:23+00:00
- Post Title: Resident Evil animations

> Reply from Gh0stBlade
>
> PMed

Note that these specs don't exactly corresppond to what I see in RE5 .lmt files. MotionInfo is different, and some types too.
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T11:06:28+00:00
- Post Title: Resident Evil animations

DMC4Motion works, BUT its not doing bone retarget. Model is exported from Noesis.

I tested it on DMC4 (original one), models with only one bone works fine.
I also tested it on Lost Planet but it seems Lost Planet have some new block types, so its not working, didn't tested it for RE5 yet.
## Post #7
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T11:57:30+00:00
- Post Title: Resident Evil animations

When I use Dmc4Motion on Mod2Max it works.
Dmc4Motion also converts ONLY some blocks from LMT.
## Post #8
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-21T13:30:31+00:00
- Post Title: Resident Evil animations

o my god, my wishes coming true:D


> Reply from daemon1
>
> I have all the information to start a tool to export animations. Now question is, which game to start from? 5? Or maybe other one will be better? I'm asking because I never know how much time I can spend on this.

please resident evil 5.

well i didnt know the tool of dmc animation to 3dmax already existed and worked...

sorry for the extra work. but can someone confirm the re5 animations are working with it?

i exported teh "SCRIPTS"(ms files) from the re5 model+motion

now how should i run the script, i should import a model first?

ahrgg i forgot the script to import mod files into max is not working for 3dmax2015 gotta try to get the 2013

> Reply from PredatorCZ
>
> When I use Dmc4Motion on Mod2Max it works.
Dmc4Motion also converts ONLY some blocks from LMT.
predator, is the script working for 2017 version? i mean the re5 model import script. or havent tried yet?
## Post #9
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T14:06:37+00:00
- Post Title: Resident Evil animations

I wouldn't count on dmc4motion, program was still in development, but it never got into some usefull stage.
Generated scripts are missing some vital parts, especially positions, global transformations and maybye more.

To successfully do the thing, first you need to import model script (it can take quite long, depends on size of generated ms), and then only ONE animation.
## Post #10
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-21T14:10:06+00:00
- Post Title: Resident Evil animations

> Reply from PredatorCZ
>
> I wouldn't count on dmc4motion, program was still in development, but it never got into some usefull stage.
Generated scripts are missing some vital parts, especially positions, global transformations and maybye more.

To successfully do the thing, first you need to import model script (it can take quite long, depends on size of generated ms), and then only ONE animation.
i got an error when running the script in 3dmax 2015. the script of one of the animations from re5.
## Post #11
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T14:12:56+00:00
- Post Title: Resident Evil animations

You need to use Mod2Max.exe to get propper model for animations to work.
## Post #12
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-21T14:14:01+00:00
- Post Title: Resident Evil animations

> Reply from daemon1
>
> Gh0stBlade wrote:PMed  

Note that these specs don't exactly corresppond to what I see in RE5 .lmt files. MotionInfo is different, and some types too.
Hi, 

What is different more specifically? That's strange cause those structs were directly obtained from the RE5 debugging symbols and is exactly what Capcom used. I also wrote a tool to read the animations based off this information which is where I quickly pulled them from. I "may" have made some small alterations but I'll get round to dumping the unaltered structs again.

Cheers.
## Post #13
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T14:18:57+00:00
- Post Title: Resident Evil animations

> Reply from Gh0stBlade
>
> 
RE5 debugging symbols

You mean like .pdb files? Becouse I know only theese files have those informations.
## Post #14
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-01-21T14:25:25+00:00
- Post Title: Resident Evil animations

> Reply from PredatorCZ
>
> Gh0stBlade wrote:
RE5 debugging symbols


You mean like .pdb files? Becouse I know only theese files have those informations.

Correct.

Anyway, it looks like I did alter the structs slightly and/or mixed up the facial anim structs with non-face anim structs. It looks like Capcom have two separate animation formats. One for face.lmt the rest for the remaining animations. I'll re-send out the unaltered structs.

Cheers.
## Post #15
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-21T14:27:11+00:00
- Post Title: Resident Evil animations

> Reply from PredatorCZ
>
> You need to use Mod2Max.exe to get propper model for animations to work.
did as you said, worked to import the model but the motion script.
[http://imgur.com/a/rbOWH](http://imgur.com/a/rbOWH) havent worked
## Post #16
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-21T14:29:24+00:00
- Post Title: Re: Resident Evil animations

Thats becouse Capcom uses sparated body and face models. So they have different lmt files.

Also do you know where I can get that .pdb beuty? 


> Reply from rubening
>
> 
did as you said, worked to import the model but the motion script.
http://imgur.com/a/rbOWH havent worked
You have diferent bone names or nonexistant bone in scene.
## Post #17
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-21T16:08:28+00:00
- Post Title: Re: Resident Evil animations

so defenitely this script is not working for re5 models. at the moment...
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-21T16:18:55+00:00
- Post Title: Re: Resident Evil animations

> Reply from Gh0stBlade
>
> Anyway, it looks like I did alter the structs slightly and/or mixed up the facial anim structs with non-face anim structs. It looks like Capcom have two separate animation formats. One for face.lmt the rest for the remaining animations. I'll re-send out the unaltered structs.

Yes, these new structs looks closer to lmt files I studied. But I don't think face/body animations are different. Maybe that was about ingame/cutscene difference?
## Post #19
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-23T19:12:17+00:00
- Post Title: Re: Resident Evil animations

Anyway, I decided to post my result of two days of staring into numbers.

Tested on DMC4, Lost Planet, RE5 and Lost Planet 2.

MT Framework 1.x format have almost every block researched exept bufferTypeID: 6 , this one is bugging me off, I can't read data right, Surveyor somehow managed to read those right.

MT Framework 2.x format have more unknown blocks, some are unchanged, but most are quantized, whinch is not big problem. bufferTypeID: 7 is even worse.
[lmt.zip](https://xentaxbackup.github.io/file/12270_lmt.zip)
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-23T20:21:39+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> bufferTypeID: 6

its 4 quaternion values each 14 bits, and 1 byte frame as you call it
## Post #21
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-23T20:41:07+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> PredatorCZ wrote:bufferTypeID: 6

its 4 quaternion values each 14 bits, and 1 byte frame as you call it

Yes, yes, I was hoping it would be bitwised, but I'm used to 3 quaternion, where 4th is computed. So I can bash my head against the wall now. Well now everything is in place, I think MT v1 LMT is fully researched atm.
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-23T21:06:54+00:00
- Post Title: Re: Resident Evil animations

where can i see MT 2 samples?
## Post #23
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-24T15:25:46+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> where can i see MT 2 samples?
It's detected automatically, version 56+, KeyframeDef_v2 struct.
MT 2 are games Lost Planet 2 +, So year 2010 to present.

Here is list of games and engine versions used.
[https://en.wikipedia.org/wiki/MT_Framew ... _Framework](https://en.wikipedia.org/wiki/MT_Framework#Games_using_MT_Framework)
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-24T15:38:05+00:00
- Post Title: Re: Resident Evil animations

ok i haven't seen any of type 7 in RE5 yet.

So I think you'll be able to export RE5 animations now, and my help is no longer needed?
## Post #25
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-24T15:54:39+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> ok i haven't seen any of type 7 in RE5 yet.

So I think you'll be able to export RE5 animations now, and my help is no longer needed?

I'm not who started this, I'm just random person who wanted to research LMT just in time when request in MGSV thread was made.
It's a quite coincidense I must say.
Also I'm interested in Lost Planet, maybye DMC4 and definitely Lost Planet 2, So I should try some booze to resolve what 7 is about.
## Post #26
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-25T12:54:06+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> daemon1 wrote:ok i haven't seen any of type 7 in RE5 yet.

So I think you'll be able to export RE5 animations now, and my help is no longer needed?

I'm not who started this, I'm just random person who wanted to research LMT just in time when request in MGSV thread was made.
It's a quite coincidense I must say.
Also I'm interested in Lost Planet, maybye DMC4 and definitely Lost Planet 2, So I should try some booze to resolve what 7 is about.

but could you get re5 animations imported in 3dmax?
## Post #27
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-25T18:24:44+00:00
- Post Title: Re: Resident Evil animations

Type 6 does not seem to be 14bit quaternion, however I can confirm its a struct of size 8 Bytes.

Values are probably additive to reference frame or previous frame, like I have noticed in greenorb.lmt::AniBlock[0]::Keyframe[0]::Data[0] where values exept frame are all zeroes.

However when I try compute 4th quat component from Dequant Local variable to check if it is valid quaternion, I get a different result or negative number (without sqrt), whinch in both cases is wrong, maybye Im doing something wrong with sign, or divider.
[lmt_samples.zip](https://xentaxbackup.github.io/file/12288_lmt_samples.zip)
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-25T18:49:57+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> Type 6 does not seem to be 14bit quaternion

It is. I read 4 14-bit values, compute square sum of them and its always 1.
Also the values correspond to 4 floats in the beginning of block description (which is i believe the initial frame rotation)
How can it be not quat?

But this is in RE5 files. Maybe you're looking into different game and its type 6 is different.
## Post #29
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-25T19:56:08+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> 
But this is in RE5 files. Maybe you're looking into different game and its type 6 is different.

Yes, you are right, it only applies on RE5 version (1.4).
DMC4 (1.3), LP (1.2) and LP2 (2.0) are using different (maybye same together) type 6 formats, aah what am I missing?

EDIT:
I just "cracked the code" sorta say, type 6 is just YPR or 3 component quaternion rotation where 1st and 2nd are 17 bits, 3rd is 19 bits, next 3 bits are sign flags and 8 bits are for frame as I call it. Its quite clever I must say, veeery clever.
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-30T17:29:15+00:00
- Post Title: Re: Resident Evil animations

As I understand, you're not going to do RE5/6 animations. I'm thinking... maybe start from RE7 ?
## Post #31
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-30T18:12:13+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> As I understand, you're not going to do RE5/6 animations. I'm thinking... maybe start from RE7 ?
I will try research RE5/RE6/DMC4/LP/LP2/RER if I figure out type 6 and 7 rotation blocks, where Im still stuck at.
RE7 does not use MT Framework, but RE Engine, if it uses same animation format is unknown to me, but I think not.
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-30T18:20:23+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> I will try research RE5/RE6/DMC4/LP/LP2/RER if I figure out type 6 and 7 rotation blocks, where Im still stuck at

I thought you found all the bits... You probably don't know the unpacking formula? It can be quite different from what I've seen in other games. The best way would be going to debugger and see how its actually unpacked.
## Post #33
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-01-30T18:33:47+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> 
I thought you found all the bits... You probably don't know the unpacking formula? It can be quite different from what I've seen in other games. The best way would be going to debugger and see how its actually unpacked.

I only assumed how it should have looked I only, know type 6 is 17/17/17/5/8 bits but have problem with seeing any nice result to reference quaternion in quat or euler, tried radtodeg, quat normalization with 4th component set on 1.f, I can only assume at this point.

As far as debug, I don't have nor can find any pdb symbols for any game, so debugging ~15MB exe is impossible task for me, since Im very lite beginner to debugging and without pseudocode plugin im hopeless to  find anything.
## Post #34
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-01-31T23:13:31+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> As I understand, you're not going to do RE5/6 animations. I'm thinking... maybe start from RE7 ?
lol no please. re7 animations are not as good as re5/6...

so its predator doing it or you? predator got anything working from re5??

lil bit offtopic here: do you know if mortal kombat x animations can be exported ? i tried to find in google but no results about animations, just models maybe you guys know something about that?
## Post #35
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-01T15:23:17+00:00
- Post Title: Re: Resident Evil animations

> Reply from rubening
>
> predator got anything working from re5??
As far for MTF v1 its scale, position and some rotations, far from finished yet.

> Reply from rubening
>
> do you know if mortal kombat x animations can be exported ?
This game uses Morpheme, right?
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-01T15:35:08+00:00
- Post Title: Re: Resident Evil animations

I'm not doing anything yet, because if PredatorCZ will do it, there's no reason to do it twice.

I did morpheme animation export before. Required some debugging for quat decompression and weird mix of global/local encoded bones.
## Post #37
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2017-02-04T22:58:01+00:00
- Post Title: Re: Resident Evil animations

I did not have much luck with RE5 bufferTypeID 6, I have tried both solutions posted here.
None of them gives me a valid quaternion, either the components are zero or they are greater than 1.0, making the quaternion not normalized, It is very possible that I'm doing something wrong tho...

I attached a dump file full of bufferTypeID 6 frames, If someone is willing to take a look.
[em84act_1.zip](https://xentaxbackup.github.io/file/12391_em84act_1.zip)
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T06:20:32+00:00
- Post Title: Re: Resident Evil animations

Ok I'll try making RE5 export myself.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T10:53:24+00:00
- Post Title: Re: Resident Evil animations

> Reply from Gistix
>
> I attached a dump file full of bufferTypeID 6 frames

I have no idea what are you doing, but i just took the first quat from this file, and its normalized.
## Post #40
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T14:24:57+00:00
- Post Title: Re: Resident Evil animations

ok this is what I'm getting after only 2 hours of work. Head/hands are moving correctly, but legs are wrong. It can't be just by accident. I think this is caused by wrong model export. I took pl0500.mod and applied one of pl00action.lmt animations to it. You can even see that one of his eyes and some pixels from palm and back are always in the rest pose.

[https://youtu.be/KO6sOwdPbEg](https://youtu.be/KO6sOwdPbEg)
## Post #41
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-05T19:22:55+00:00
- Post Title: Re: Resident Evil animations

What model converter are you using, does it do bone remap?
I recommend you use surveyors mod2max.exe, it applies bone remap.
Noesis does not use remap btw.

Anyway, yesterday I was looking into LP exe and luckily found upacking formula for both type 6 and type 7. But, its so weird to me I cant understand whats going on there. Funny thing they are using SSE instructions. Im not sure but they unpack it in render runtime whinch is interesting. Also type 6 formula is almost 1000 lines long, it uses at least 4 unpack cases.

Anyone familiar with this conversion formula?
I am posting sorta pseudocode I made today, its not comlete btw.

EDIT: Type 6 is now fully readable.
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T20:21:28+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> What model converter are you using, does it do bone remap?
I recommend you use surveyors mod2max.exe, it applies bone remap.
I applied bone remap myself, it only took 5 minutes.

Now I understand why RE5 animations were not done before. The problem here is they used IK on the feet. And its not easy to export. I had no time to build proper IK chain and just quickly connected heels to toes. Thus feet are distorted on this new video.

[https://youtu.be/jXinGPX6nrU](https://youtu.be/jXinGPX6nrU)



> Reply from PredatorCZ
>
> Funny thing they are using SSE instructions. Im not sure but they unpack it in render runtime whinch is interesting.
Its usual. Everybody's using SSE for rotation unpacking nowadays, and its always done on runtime. But RE5 animations are different from all other MT games. They decided to use already unpacked quats and add IK.
## Post #43
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-05T20:43:35+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> But RE5 animations are different from all other MT games. They decided to use already unpacked quats and add IK.

Ah, that explains why I got so weird rotation results. I wonder how IK can be baked into quat, are they somehow local?
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-05T20:48:23+00:00
- Post Title: Re: Resident Evil animations

> Reply from PredatorCZ
>
> I wonder how IK can be baked into quat, are they somehow local?

I have no idea what are you talking about 

They define global toe position, and heels must be calculated with IK constraint.
## Post #45
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-05T21:01:22+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> They define global toe position, and heels must be calculated with IK constraint.

That is what I was "talked" about. Sorry for any misunderstanding I was caused, I never looked into IK constraints before. Thanks for clarification.
## Post #46
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-06T20:40:02+00:00
- Post Title: Re: Resident Evil animations

i wish i knew so much like you guys do, this has to be amazing. apart from extracting and understanding the formats of animations, do you have animation knowledge too?.

 damn this (what you're doing) is so nice daemon! 

My wish coming true!! 

thats so niceee guys!

well soemthing has to do with the feet in game too because i remember with the trainer, when you use the command GHOST to walk through walls you can even go under the ground and in some level your feet can be as high as your hips xD looks kinda funny.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-06T21:35:21+00:00
- Post Title: Re: Resident Evil animations

I know something about animations, but not enough to setup IK constraints properly. Other people said blender is not as good in that as maya or max. So this is what I'm getting now.

[https://youtu.be/EIHqSm4Ya08](https://youtu.be/EIHqSm4Ya08)
## Post #48
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-06T21:46:13+00:00
- Post Title: Re: Resident Evil animations

> Reply from rubening
>
> feet can be as high as your hips xD looks kinda funny.
Thats looks like IK alright. In LP2, IK chains along with ragdoll definition are stored in tools/havok, they are stored in .mse whinch is general scripting format.
I did not found these files in RE5 archives so far, but maybye Im searching in wrong place.

Anyway I remember you had some similar post about LMT importer/converter on RE Modding forum, it was like 7 years ago, I found it, still no replys btw.
## Post #49
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2017-02-07T00:30:21+00:00
- Post Title: Re: Resident Evil animations

I have looked into RE3 animations in the past, some of them also make use of IK for feet placement. So far I have 
only got animations that does not use IK working right.

[https://youtu.be/U6RTqJDb5Mc](https://youtu.be/U6RTqJDb5Mc)
## Post #50
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-07T01:45:55+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> I know something about animations, but not enough to setup IK constraints properly. Other people said blender is not as good in that as maya or max. So this is what I'm getting now.

https://youtu.be/EIHqSm4Ya08
thats really nice! well if its too complicated, we can always fix the feet manually.
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-07T04:25:40+00:00
- Post Title: Re: Resident Evil animations

> Reply from rubening
>
> thats really nice! well if its too complicated, we can always fix the feet manually.

oh it was just a little mistake in code. Now it works:

[https://youtu.be/3ekfUd_oQv8](https://youtu.be/3ekfUd_oQv8)
## Post #52
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-07T13:12:00+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> rubening wrote:thats really nice! well if its too complicated, we can always fix the feet manually.

oh it was just a little mistake in code. Now it works:

https://youtu.be/3ekfUd_oQv8

NOOOOOOOOOOOOOOOOOO HAHAHAHA SOOO NICEEEEE DAEMON!! thank you so much for making me see this.

i hope to export those animations soon:D

about his right hand, thats being caused because he needs a weapon i think.
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-07T16:09:54+00:00
- Post Title: Re: Resident Evil animations

yes i think the tool will be ready very soon, at least some test version. May not export all anims, but at least some human ones.
## Post #54
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-07T17:36:04+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> yes i think the tool will be ready very soon, at least some test version. May not export all anims, but at least some human ones.
yeppa biped are the most important!.

thank you really! that was amazing.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-07T18:53:20+00:00
- Post Title: Re: Resident Evil animations

A taste of things to come. 1/5 of animations from action pack in one video:

[https://youtu.be/EhQ-6RW3sj0](https://youtu.be/EhQ-6RW3sj0)



I will publish the test tool today
## Post #56
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-07T19:27:10+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> A taste of things to come. 1/5 of animations from action pack in one video:

https://youtu.be/EhQ-6RW3sj0



I will publish the test tool today

dude i'm in love with re5 animations.. do you think they were made by motion capture? they look too real to be keyframe work!

great ill be checking the forum to download and give it a try:D

by the way , how you ported the model into blender? is there any tool to port it to 3dmax or maya instead?
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-07T20:14:47+00:00
- Post Title: Re: Resident Evil animations

Test tool  Now all node/compression types are supported, so some animations will look funny, some will fail in the middle. But most player animations are working correctly. Soon I will support more types.

Usage: drag .LMT file onto the tool (or use with 1 parameter from command line).
A model file named as model.mod must be in the same dir.

This will produce all animations combined in 1 SMD file.

To attach animations to model, it must have bones named like bone0, bone1, etc. I used latest NOESIS export to FBX. After connection, you must create IK constraints connecting right toe to "atarget1" bone, left toe to "atarget2", with chain length 3, both position and rotation. No idea how its done in maya or max, but hopefully the same as in blender.
## Post #58
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-08T00:57:22+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Test tool  Now all node/compression types are supported, so some animations will look funny, some will fail in the middle. But most player animations are working correctly. Soon I will support more types.

Usage: drag .LMT file onto the tool (or use with 1 parameter from command line).
A model file named as model.mod must be in the same dir.

This will produce all animations combined in 1 SMD file.

To attach animations to model, it must have bones named like bone0, bone1, etc. I used latest NOESIS export to FBX. After connection, you must create IK constraints connecting right toe to "atarget1" bone, left toe to "atarget2", with chain length 3, both position and rotation. No idea how its done in maya or max, but hopefully the same as in blender.

NICE THANK YOU MATE!, this is amazing. im gona try to find someone who can help me to do that attaching those bones. with chain length 3.
## Post #59
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-02-08T03:32:54+00:00
- Post Title: Re: Resident Evil animations

Great  work!

I tried loading a player .lmt into maya to test how to setup the solver:

[https://www.youtube.com/watch?v=k8zm1Ys ... e=youtu.be](https://www.youtube.com/watch?v=k8zm1YsaXVg&feature=youtu.be)

Still having some trouble with feet sliding and odd toe rotation, not sure if its the IK solver or the actual data, i will test more once i get time. But still amazing work as always
## Post #60
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-08T04:26:15+00:00
- Post Title: Re: Resident Evil animations

> Reply from Highflex
>
> Still having some trouble with feet sliding and odd toe rotation

These are because of unsupported data types. Don't try these yet.
## Post #61
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2017-02-08T22:08:39+00:00
- Post Title: Re: Resident Evil animations

Type 6 looks promising so far. What a horror it was to get it to work.
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-09T20:06:31+00:00
- Post Title: Re: Resident Evil animations

New version that will probably export ALL biped animations, including some biped things I've seen today. Never played this game btw. Its now hardcoded to make IK toe bones from tracks number 13 and 17. Which seems to be same for all bi-peds. The tool failed before because of some bones not remapped to the model. Strange.

It still lacks support for many unknown bone types.

> Reply from rubening
>
> im gona try to find someone who can help me to do that attaching those bones. with chain length 3.
Any luck with that?
## Post #63
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-02-10T03:34:32+00:00
- Post Title: Re: Resident Evil animations

Brilliant work. It's amazing to see so much progress in a few days after years.
Thanks also PredatorCZ for posting some structures, animations are new to me and I find them fascinating to research.

Could you share your new findings? Probably I can't contribute much new research, but I certainly want to understand the format and be able to export animations back to the game.
## Post #64
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2017-02-10T08:22:56+00:00
- Post Title: Re: Resident Evil animations

I second the motion! I would also like to know your new findings since I got stuck while trying to import this format myself, I'm still puzzled.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-10T15:32:32+00:00
- Post Title: Re: Resident Evil animations

Ok today I plan to add root rotation and static positions/rotations, this should fix the remaining problems and then I can explain you the "new findings".
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-11T08:18:18+00:00
- Post Title: Re: Resident Evil animations

Making some final tests. This pack is now fully working. Some animations include only upper or lower body half, or only fingers (like in the end). I had to include the initial pose before each motion to make it all export correctly.

[https://youtu.be/X4tXTpJacXk](https://youtu.be/X4tXTpJacXk)

Sheba action pack:

[https://youtu.be/J9VyHnQ0crw](https://youtu.be/J9VyHnQ0crw)
## Post #67
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-11T13:16:55+00:00
- Post Title: Re: Resident Evil animations

Ok, except some rare problems that sometimes happen with high heels, looks like everything's exporting fine. These are some examples of package em84. Probably cutscenes:
[https://youtu.be/te2Vvbex_hw](https://youtu.be/te2Vvbex_hw)
Some movements:
[https://youtu.be/YZio9sT7CTc](https://youtu.be/YZio9sT7CTc)
And some more actions:
[https://youtu.be/WcU4mTFugKM](https://youtu.be/WcU4mTFugKM)



I'm going to publish the new version soon. Need to make some final checks. I found that some anims have hands IK, these will NOT work correctly, but I've only seen this is static poses, so I hope this is not needed, at least for now.
## Post #68
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-11T15:55:02+00:00
- Post Title: Re: Resident Evil animations

Tool published at first post. Now its REALLY exports most animations properly.
## Post #69
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2017-02-11T16:20:12+00:00
- Post Title: Re: Resident Evil animations

Thanks a lot! I would just like to mention that em84 is a boss and that the animations inside em84evt are animations that actually play on the player when you interact with the boss.
## Post #70
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-11T16:38:53+00:00
- Post Title: Re: Resident Evil animations

> Reply from Gistix
>
> Thanks a lot! I would just like to mention that em84 is a boss and that the animations inside em84evt are animations that actually play on the player when you interact with the boss.

Oh, you never know. They look good on that girl.

So since I don't exactly know about "old findings" I'm not sure what "new findings" you'd like to know. As I said, rotations are saved as quats, 4 x 14 bits, signed integers. Divide each number by 4096, you get quat components.

From all bones, only toes are not normal bones, but actually IK targets for toes.

Bone -1 is root bone.
Bone -2 I'm not sure, maybe related to weapon or something, has many tracks, up to 8 or 9. I didn't try exporting it.
## Post #71
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2017-02-11T16:54:15+00:00
- Post Title: Re: Resident Evil animations

Awesome Work!

Animations are the cherry on the cake:)

I wonder if this will work on other RE titles
## Post #72
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2017-02-11T18:10:12+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Gistix wrote:Thanks a lot! I would just like to mention that em84 is a boss and that the animations inside em84evt are animations that actually play on the player when you interact with the boss.

Oh, you never know. They look good on that girl.

So since I don't exactly know about "old findings" I'm not sure what "new findings" you'd like to know. As I said, rotations are saved as quats, 4 x 14 bits, signed integers. Divide each number by 4096, you get quat components.

From all bones, only toes are not normal bones, but actually IK targets for toes.

Bone -1 is root bone.
Bone -2 I'm not sure, maybe related to weapon or something, has many tracks, up to 8 or 9. I didn't try exporting it.

Can't speak for Bastien but that is all I wanted to know really, I was thinking that rotations were stored in some weird half-float format...
## Post #73
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-12T14:43:39+00:00
- Post Title: Re: Resident Evil animations

thank you soooooooooooo much DAEMON! 
thank you for your time and effor! thank you really!!!
## Post #74
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-12T16:48:42+00:00
- Post Title: Re: Resident Evil animations

> Reply from rubening
>
> thank you soooooooooooo much DAEMON! 
thank you for your time and effor! thank you really!!!

I hope you will enjoy the animations. Also check it in RE6. Did you manage to get IK chains working?
## Post #75
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-12T18:23:14+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> rubening wrote:thank you soooooooooooo much DAEMON! 
thank you for your time and effor! thank you really!!!

I hope you will enjoy the animations. Also check it in RE6. Did you manage to get IK chains working?

i managed to open in maya but now the problem i have is,... i even created the ik of the toe to the calv bones, but i still need the locator and constrain ik target to it.


[https://youtu.be/ut9zwbYYAVE](https://youtu.be/ut9zwbYYAVE)

and i dont know why it has 2 knee bones for example.. bone 114 and 117 are in the same place. but 117 doesnt have children, same with the other leg..
## Post #76
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-13T16:30:01+00:00
- Post Title: Re: Resident Evil animations

This is a video tutorial how to do it in blender. Hope this helps.

[https://youtu.be/URf49Eo8B0U](https://youtu.be/URf49Eo8B0U)



The second bone next to knee is helper bone to make more natural body twists.
## Post #77
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-13T21:27:30+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> This is a video tutorial how to do it in blender. Hope this helps.

https://youtu.be/URf49Eo8B0U



The second bone next to knee is helper bone to make more natural body twists.

i get error , version 6100 unsupported, must be 7100 or later. what does this mean? the fbx version?.

strange i just exported the fbx with the noesis last version as you said...
## Post #78
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-13T22:16:31+00:00
- Post Title: Re: Resident Evil animations

use this export option in Noesis:
-fbxnewexport - exports current fbx format instead of legacy.
## Post #79
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-13T22:33:33+00:00
- Post Title: Re: Resident Evil animations

> Reply from volfin
>
> use this export option in Noesis:
-fbxnewexport - exports current fbx format instead of legacy.
sorry couldnt find that.


checking, the re5 anims tool i get this message ->

[http://imgur.com/a/j3bcG](http://imgur.com/a/j3bcG)

is it normal? to get that many unsupported tracks? , here thers no error , ican export and i can even load it in noesis. 

but

i tried to export the pl03action.lmt

and i get this error 

[http://imgur.com/a/rYluV](http://imgur.com/a/rYluV)


, about to get the smds separatedly of each animation i think will be usefull. if its not too much work than you already did.
## Post #80
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-14T02:57:21+00:00
- Post Title: Re: Resident Evil animations

you enter it in the export pane.  the "Advanced Options" button lists all the possible advanced options, it's in there.  If not, might be your Noesis needs updated.
## Post #81
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-14T11:16:06+00:00
- Post Title: Re: Resident Evil animations

> Reply from volfin
>
> 

you enter it in the export pane.  the "Advanced Options" button lists all the possible advanced options, it's in there.  If not, might be your Noesis needs updated.

aha! Cool , i found it! thank you!
## Post #82
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-14T20:29:46+00:00
- Post Title: Re: Resident Evil animations

Yes, its normal to get that many unsupported tracks. As I said, many bones are not supported.

but pl03action.lmt error is not. I'll check it later.
## Post #83
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-16T12:10:30+00:00
- Post Title: Re: Resident Evil animations

[http://imgur.com/a/wgkdZ](http://imgur.com/a/wgkdZ)

i first imported the fbx of the model chris. then i do make new armature on the smd import of the animation, it takes a time but its imported 90degree rotated. and the chris was correctly imported.  i dont know what to do ...
## Post #84
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-16T15:13:09+00:00
- Post Title: Re: Resident Evil animations

> Reply from rubening
>
> http://imgur.com/a/wgkdZ

i first imported the fbx of the model chris. then i do make new armature on the smd import of the animation, it takes a time but its imported 90degree rotated. and the chris was correctly imported.  i dont know what to do ...

you need to rotate skeleton like i showed it in the video. Also scale the model or skeleton with "S" key and hold CTRL to make it precise.
## Post #85
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-18T06:06:03+00:00
- Post Title: Re: Resident Evil animations

New version that will not fail on pl03action.lmt
## Post #86
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-19T17:46:16+00:00
- Post Title: Re: Resident Evil animations

Hey, first thing first:
Thank you very much for this! it's like a dream come true ^^

But I must be doing something wrong. Whenever i try to use it i get an error like this:

```
SystemOverflowException in Re5Anims.Re5Anims.Main<String[] args>
```


Tried in win7 and win8.1 dunno if that's a problem? but get the same error in both.
This is the line i tried to use

```
re5anims pl0200_00.lmt pl0200.mod
```


Tried with some others LMTs but still the same error.
## Post #87
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T18:10:26+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> Thank you very much for this! it's like a dream come true ^^
I wish I could make more such dreams. This one only took a week to make 

> Reply from Meguido
>
> But I must be doing something wrong. Whenever i try to use it i get an error like this:
No idea. Your command is correct. Its supposed to work like this. I have win7.
## Post #88
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2017-02-19T19:44:23+00:00
- Post Title: Re: Resident Evil animations

I'm curious, will this work for other MT Framework games with the .lmt motion files?
## Post #89
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T19:47:17+00:00
- Post Title: Re: Resident Evil animations

> Reply from MarioSonicU
>
> I'm curious, will this work for other MT Framework games with the .lmt motion files?

As I understand from Predator's messages, other (than RE) games use different type of rotation compression, so no, this will only work with RE.
## Post #90
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-19T20:00:53+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> No idea. Your command is correct. Its supposed to work like this. I have win7.

Hmm    Maybe the file type? I mean this works with every version of RE5? PC, XB, PS3? Which one did you tested it with?

> Reply from daemon1
>
> As I understand from Predator's messages, other (than RE) games use different type of rotation compression, so no, this will only work with RE.

So this should work with re4 and 6 too?
## Post #91
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T20:10:33+00:00
- Post Title: Re: Resident Evil animations

Tested on PC version. But considering the error message youre getting, its probably not the case. Where do you run it from? Command line or some commander?

> Reply from Meguido
>
> So this should work with re4 and 6 too?

In theory. Maybe some tool update will be needed.
## Post #92
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-19T20:16:27+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Tested on PC version. But considering the error message youre getting, its probably not the case. Where do you run it from? Command line or some commander?

I'm runnning it from command line. Tried with and without admin rights. Same result. I tested it with xbox files.
## Post #93
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-19T20:31:58+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> I tested it with xbox files.

That must be the problem.
## Post #94
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-20T13:15:21+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> That must be the problem.

And yeah, it was that 
Tested it with pc files and got "a1.smd"
I tried to import it in maya using the mesa plugin but even when it started to import it and could see an skeleton moving around it got frozen after some time without finishing importing. So i guess i have to use blender to import it.

______________

Edit:
Ok so after making some tests with Pl0200.mod and Pl0200_00.lmt looks like I had to find one that isn't working as it should. atarget1 and atarget2 are both in a too high position to be the correct one. When i set the ik constraints this is what i get:
[](https://1.bp.blogspot.com/-XWehEKM2h1I/WKr_2gGF5NI/AAAAAAAAAFw/eUy0SbK618cfIMR-QpvWJrAcyyKODfowACLcB/s1600/errorconstraint.jpg)
(Click to enlarge)
## Post #95
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-20T15:46:00+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> Ok so after making some tests with Pl0200.mod and Pl0200_00.lmt

Yes, I was expecting this. The root bone is not always bone 0. I'll have to make some corrections to make these working.
## Post #96
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-20T16:14:03+00:00
- Post Title: Re: Resident Evil animations

Here's the new version. I hope you can find some time to check if its now working with this and other animations previously working. Let me know.

p.s. Interesting that for cutscene animations they still have IK in effect.
[Re5Anims.rar](https://xentaxbackup.github.io/file/12481_Re5Anims.rar)
## Post #97
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-20T16:43:11+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Here's the new version. I hope you can find some time to check if its now working with this and other animations previously working. Let me know.

p.s. Interesting that for cutscene animations they still have IK in effect.

You're really fast! thank you! I'll be testing it again asap (as soon as i go back home in a few hours)

Btw is there a list anywhere to know which files are what? I mean how do you know pl0200_00.lmt is for cutscenes?
## Post #98
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-20T17:30:22+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> I mean how do you know pl0200_00.lmt is for cutscenes?

I'm not familiar with RE series and never played any of them. I have no idea how files are organized. I think these are cutscenes only because the global positions are as big as 2000 or 3000 which usually only happens in cutscenes.
## Post #99
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-20T21:11:52+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> I'm not familiar with RE series and never played any of them. I have no idea how files are organized. I think these are cutscenes only because the global positions are as big as 2000 or 3000 which usually only happens in cutscenes.

Oh yeah you're right, silly me didn't realized that huge translation offsets were caused because of that 

Btw i'm testing it now and it's working flawlesly now. With other LMTs too (like pl0203action.lmt).

So are you going to add the option to export every animation to separate smd files?

Btw, another question: what would you need to do to make it workable with RE6 and RE4?
## Post #100
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-21T15:30:29+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> So are you going to add the option to export every animation to separate smd files?

Btw, another question: what would you need to do to make it workable with RE6 and RE4?

1. maybe later. Also tag bones can be useful.

2. First thing I'd need is some LMT files.
## Post #101
- Username: rubening
- Rank: beginner
- Number of posts: 38
- Joined date: Tue Jun 29, 2010 1:47 am
- Post datetime: 2017-02-22T00:23:02+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Meguido wrote:So are you going to add the option to export every animation to separate smd files?

Btw, another question: what would you need to do to make it workable with RE6 and RE4?

1. maybe later. Also tag bones can be useful.

2. First thing I'd need is some LMT files.

ill try to upload some for you
## Post #102
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-22T13:07:47+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> 2. First thing I'd need is some LMT files.

I've been searching a bit about re4 files. The original one wasn't even made on mt framework. But supossedly the uhd edition got ported to it. 
But there's no .arc files and no .lmt animations files. The format is .FCV.
So do you want to take a look at any .FCV file or just ignore re4 and only try re6?
## Post #103
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-22T14:18:42+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> or just ignore re4 and only try re6?

You have to choose what is more important to you. Choose wisely  Because at any moment I can find something more interesting for me and move to some other projects and never return to RE.
## Post #104
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-23T16:39:08+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> You have to choose what is more important to you. Choose wisely  Because at any moment I can find something more interesting for me and move to some other projects and never return to RE.

Ok, so I just sent you a pm (sorry it's a bit long but i tried explaining everything) with the files.
## Post #105
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-24T12:22:18+00:00
- Post Title: Re: Resident Evil animations

Checked RE6 files. Unfortunately they are too much changed. They are not simple anymore, like it was in RE5.

So probably I will not be able to convert anything in near future.
## Post #106
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-24T18:27:22+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Checked RE6 files. Unfortunately they are too much changed. They are not simple anymore, like it was in RE5.

So probably I will not be able to convert anything in near future.

Oh, that's a shame  But you still did a great job with RE5 so thank you very much.

Ps. I guess RE4's are even more different than 6's
## Post #107
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-02-25T01:12:31+00:00
- Post Title: Re: Resident Evil animations

Hey daemon1, where do you get the locations from? I could get the rotations right thanks to PredatorCZ template and your tip about dividing by 4096.

Also, this data is not associated with a bind pose, right? I don't know how animations work in video games, but if you animate in a 3d software all rotations will be relative to the bind pose so mostly only rotations are needed.
My final goal is to be able to export animations back to the game, so I need to understand the format pretty well. Probably I have to start reading a lot about how game engines work.
## Post #108
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-25T06:35:24+00:00
- Post Title: Re: Resident Evil animations

> Reply from Meguido
>
> Ps. I guess RE4's are even more different than 6's
They are not "more" different, but probably simpler. Anyway, RE6 is still quite possible, but to do that I need to do more research and install the game myself. So maybe later. In addition to split body parts they have many compression types and arm IK-chains too (which I could expect).

> Reply from Bastien
>
> Hey daemon1, where do you get the locations from? I could get the rotations right thanks to PredatorCZ template and your tip about dividing by 4096.

Also, this data is not associated with a bind pose, right? I don't know how animations work in video games, but if you animate in a 3d software all rotations will be relative to the bind pose so mostly only rotations are needed.
My final goal is to be able to export animations back to the game, so I need to understand the format pretty well. Probably I have to start reading a lot about how game engines work.
Locations are plain floats. There are only a few locations: root, origin, and toe locations (because they are IK drivers). I don't know how animations work in 3d software, but I don't think you need "reading a lot", because in games its all very simple. I'm not sure what do you mean by "associated with a bind pose", but if you give me some example, I can try explaining it.
## Post #109
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-02-25T15:16:47+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> 
RE6 is still quite possible, but to do that I need to do more research and install the game myself.
There's a [free](http://store.steampowered.com/app/229950/) benchmark/demo.

> Reply from daemon1
>
> 
Locations are plain floats. There are only a few locations: root, origin, and toe locations (because they are IK drivers).

I was looking at id/figdata/fig01/fig01.lmt from fig01.arc. It's a static pose, and time 0 has all locations and no rotations. I can't seem to find where to get that info while parsing.
I know from PredatorCZ template that some keyframes are of type 'location', and those are the ones that change in time 1.

```
end
skeleton
time 0
0  0.000000 0.000000 0.000000  0 0 0
1  0.000000 114.000000 0.000000  0 0 0
2  0.000000 1.000004 -0.001327  0 0 0
3  0.000000 17.000000 -1.338673  0 0 0
4  -0.000002 24.000020 -2.100001  0 0 0
5  -0.000002 8.999998 1.100000  0 0 0
6  -2.839997 7.362676 9.415515  0 0 0
7  2.840005 7.362280 9.415408  0 0 0
<snip>

```


I think once I can reproduce the SMD output you get I can explain the 'bind pose' problem better.
## Post #110
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-25T16:09:27+00:00
- Post Title: Re: Resident Evil animations

> Reply from Bastien
>
> I know from PredatorCZ template that some keyframes are of type 'location'

I'm not using templates, but there are no such thing as separate location keyframes. There are location tracks, each track may have many keyframes, and they all will be location keyframes.

The fig01.lmt file contains 3 location tracks: for root and 2 toes. And a lot of rotation tracks for all bones, including root and toes. Time 0 is the frame I'm using for initial pose which is taken completely from the model. It has all rotations as zero, because models in RE5 are all made that way.

Now at time 1 I'm combining first frames all of animation tracks that are present, leaving the missing bones in default position/rotation.
## Post #111
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-02-26T01:48:21+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> Time 0 is the frame I'm using for initial pose which is taken completely from the model.

Got it, thanks. I was able to reproduce your SMD output.

Now, the problem I'm trying to figure out is this:



The left is imported from SMD, the right is imported directly from the .mod + applying the pose.
* Same bone hierarchy, same rotations in all bones, however the pose is clearly wrong
* The skeleton from SMD has no 'bind pose', e.g. going to edit mode in the skeleton shows the bone all in the origin.
* The skeleton on the right has a bind pose, so the locations are not part of the pose

I have a feeling why this happens (different spaces in bones), but that's the part where I have to investigate a little more before posting conclusions. Any help is appreciated.
[fig01.blend.zip](https://xentaxbackup.github.io/file/12526_fig01.blend.zip)
## Post #112
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T16:05:23+00:00
- Post Title: Re: Resident Evil animations

> Reply from Bastien
>
> The skeleton from SMD has no 'bind pose'
Sorry, I don't understand what it means... Can't help.
## Post #113
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-26T16:39:05+00:00
- Post Title: Re: Resident Evil animations

It's customary in a lot of animation formats that the first frame of the animation is the default pose the skeleton is in when not animated. 

For example in the SMD spec it mentions ( [https://developer.valvesoftware.com/wik ... a#Skeleton](https://developer.valvesoftware.com/wiki/Studiomdl_Data#Skeleton) ) :

> Position data for each bone in each animation frame. In a reference SMD there is only one frame, which contains the model's default posture. 

This is called the rest pose by some, and seems 'bind pose' is a Maya term.  Maya's description of "bind pose':

> The bind pose is the pose that the skeleton is in when you bind skin. When you pose a character's skeleton after skinning, the skeleton's actions cause deformations to the skin. The only pose that does not cause deformations to the skin is the bind pose.

So basically the animation conversions may not have this initial rest/bind pose frame, but a lot of tools and formats expect it.
## Post #114
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T17:33:05+00:00
- Post Title: Re: Resident Evil animations

He's talking about something different. Because that SMD skeleton surely has bind pose in these terms.
## Post #115
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-02-26T18:17:51+00:00
- Post Title: Re: Resident Evil animations

> Reply from daemon1
>
> He's talking about something different. Because that SMD skeleton surely has bind pose in these terms.

Indeed every SMD skeleton imported from RE5 has a bind pose of one frame for every animation (inside the same SMD file). So yeah he's probably talking about something different.
## Post #116
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2017-02-26T18:46:07+00:00
- Post Title: Re: Resident Evil animations

Yes, SMD has a first frame defining the rest/bind pose. However, that's not how you'd animate in Blender, so there are some transformation to be applied if I want to be able to export animations back to the game.
I just realized I should read the code for exporting SMD. I'll post back when I have more info/a solution. Sorry for the noise.

A simpler question for daemon1 is: did you figure out all uknowns in the structure? That also will be necessary to export back animations.

```
 {
	uint offset;
	uint bonecount;
	uint framecount;
	uint unk;
	float ufl;
	float ufl;
	float ufl;
	uint unk;
	uint unk;
	uint unk;
	uint unk;
	float ufl;
	uint unk;
	uint unk;
       // There's more here before seeking to the offset
 }AniBlockHeader

```
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-26T19:21:19+00:00
- Post Title: Re: Resident Evil animations

There are 8 floats, for additional rotation and position for whole animation.

After that, 2 sets of notifications or "events". For sounds probably. Or something else too.

Each set is offset for notification track, count, and 32 event IDs. 32 because events are triggered by bits in 32-bit words, allowing up to 32 different events in every set. Events timing is usual, same as for animation tracks.
## Post #118
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2017-02-26T20:11:39+00:00
- Post Title: Re: Resident Evil animations

Ok I get what he's talking about then. It's described here:
[http://peyman-mass.blogspot.com/2013/09 ... acter.html](http://peyman-mass.blogspot.com/2013/09/what-is-binding-pose-in-character.html)
I'm not positive but I think you should just be able to use the correct skeleton and transfer the animation to it. That's what Blender's pose library is for.
## Post #119
- Username: Meguido
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 07, 2014 8:33 pm
- Post datetime: 2017-03-06T14:21:01+00:00
- Post Title: Re: Resident Evil animations

Sorry to ask but,
Any progress on the research for RE6 @daemon1?
## Post #120
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-06T16:26:21+00:00
- Post Title: Re: Resident Evil animations

I'm not working on this anymore. Maybe i will return to it someday, but as I said, it will not be in near future.
## Post #121
- Username: billbanks
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 13, 2017 2:38 pm
- Post datetime: 2017-03-13T09:04:02+00:00
- Post Title: Re: Resident Evil animations

Can you reverse the format of RE4 UHD PC animation FCV file:
I found this thread in 2008 talked about RE4 FCV file, but that probably are older version of PC or Wii/GC version
It took me a long time but not figured it out.

[viewtopic.php?f=22&t=2979](http://forum.xentax.com/viewtopic.php?f=22&t=2979)


FCV notes

-------------------------------------------------------------------------
Short = 2byte (4digit) hex number with lowest value first ie: CD AB is read as AB CD

uint = 4byte(8digit) unsigned hex number with lowest value first ie: 78 56 34 12 is read as 12 34 56 78

float = IEEE-754 float, 4 bytes read in binary as 1= sign 00000000=exponent  (1.)0000000000=radiant
(note this float is -0, which is non existent... NAN (not a number))

-------------------------------------------------------------------
known stuff

0xB0 bytes   header   #0x4C (uint) is always the length of the file

#positioning data
for amount of bones moving at different times: #undetermined as to how this is known
   uint      how many bones

   for bone index in how many bones:
      short      index of bone in PMD file currently being used

   for bone position in how many bones:
      float      new x coordinate
      float      new y coordinate
      float      new z coordinate
#end this point in time

uint      time flag?   #all is judged on the truth in this statement
uint      current time
uint * 6   0      #definitely padding

refer to positioning data

--------------------------------------------------------------------------
notes:

-Sometimes x,y,z floats aren't floats, but i think this is just hexworkshop interpreting the floats backwards (3f 80 00 00 is NAN to them)

-I think the 0x00 to 0x4c values are just importing the PMD info
   -very repetitive
   -always similar with small variations

-0x4c - 0xB0 lists a bunch of pointers that point to SOME of the positioning data (refer to "known stuff")
## Post #122
- Username: mwesten1
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jul 09, 2016 3:27 am
- Post datetime: 2017-05-23T05:31:33+00:00
- Post Title: Re: Resident Evil animations

did anyone try to do that in 3ds max? did it work?
## Post #123
- Username: IAmError
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 02, 2017 3:01 pm
- Post datetime: 2018-07-17T16:46:58+00:00
- Post Title: Re: Resident Evil animations

Awesome work! I can port some things now, but i have problem. When i try to port Wesker (uEm81) i get crash message and press "Close program". Error look like 

```
RE5Anims.RE5Anims.Main<Strings[] args>
```

Sadly...
