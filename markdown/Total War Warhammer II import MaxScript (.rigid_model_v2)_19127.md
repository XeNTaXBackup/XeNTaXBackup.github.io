## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-12-01T14:52:58+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Hi guys! Here's maxscript to import [PC] Total War: Warhammer II character's/monster's models with bones and weights (3ds max 2009-2016). 


[Warhammer_Total_War_2.7z](https://xentaxbackup.github.io/file/15262_Warhammer_Total_War_2.7z)
## Post #2
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2018-12-06T21:10:48+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot
>
> Hi guys! Here's maxscript to import [PC] Total War: Warhammer II character's/monster's models with bones and weights (3ds max 2009-2016).

wow!!! finally!!! thx u very much!!!
## Post #3
- Username: lumekano
- Rank: advanced
- Number of posts: 59
- Joined date: Sat Feb 25, 2012 9:20 pm
- Post datetime: 2018-12-09T17:16:21+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

some model error like (hu9) get wrong bone transformations, look like this:  



here simple:
[http://www.mediafire.com/file/r000im1v9 ... n.rar/file](http://www.mediafire.com/file/r000im1v9q4lbzl/zborken.rar/file)
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-12-09T20:50:43+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Cool! Thanks, I'll take a look and fix it if I can, when I will have time
## Post #5
- Username: j61009123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 09, 2016 5:26 pm
- Post datetime: 2019-08-18T19:00:58+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Can this script imports weapon and building models from Total War: Warhammer II as well ? 
I can't seems to get it right. 

here is the sample
https://drive.google.com/file/d/17KEqZh ... sp=sharing
## Post #6
- Username: willemsen
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 12, 2019 6:35 am
- Post datetime: 2019-09-12T16:57:07+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Any new updates on the script?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-09-12T18:06:57+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from j61009123 ↑Mon Aug 19, 2019 3:00 am at Mon Aug 19, 2019 3:00 am
>
> 
Can this script imports weapon and building models from Total War: Warhammer II as well ? 
I can't seems to get it right.I don't have 3dsmax installed but a script fix shouldn't be too hard:
.



lzd_saurus_warriors_club_1h_01-rigid_model_v2.png (75.04 KiB) Viewed 677 times

(highest LOD of 4)
## Post #8
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-09-28T21:54:09+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Any new updates on the script?

i just made a noesis script that supports static and skinned meshes, it is heavily based on zaramot maxscript - meaning i couldnt have done it without his script   

heres the link to thread:
[viewtopic.php?f=16&t=21167&p=156627#p156627](https://forum.xentax.com/viewtopic.php?f=16&t=21167&p=156627#p156627)
## Post #9
- Username: j61009123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 09, 2016 5:26 pm
- Post datetime: 2019-11-07T16:32:00+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from jayn23 ↑Sun Sep 29, 2019 5:54 am at Sun Sep 29, 2019 5:54 am
>
> 

i just made a noesis script that supports static and skinned meshes, it is heavily based on zaramot maxscript - meaning i couldnt have done it without his script   

heres the link to thread:
viewtopic.php?f=16&t=21167&p=156627#p156627
Thank you. Your Noesis script for Total War: Warhammer II works great for characters and weapons. However, the UV seems to be broken when I tried to export building. Here's the screenshot:

Here's the sample file:
[https://drive.google.com/file/d/1yK8abA ... sp=sharing](https://drive.google.com/file/d/1yK8abAri3yxspTedM-lQmxyDy-_VZ2_s/view?usp=sharing)
## Post #10
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-07T18:20:13+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Hey

I'll work on a fix in the next few days, just need to finish up something else i am working on before.
## Post #11
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-09T19:51:06+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Thank you. Your Noesis script for Total War: Warhammer II works great for characters and weapons. However, the UV seems to be broken when I tried to export building

Hi i looked over the sample you provided, and looks to me like something is corrupted in the data, i couldn't find the correct uv data for that 
model, and i tried literally every combination.

i reinstalled the game and  tried loading other building and they seemed to work:
Please note that if you have my latest version of the script it also loads textures if they are in the same folder as the model.



for xentax.JPG (80.13 KiB) Viewed 555 times



could you please check a few more building models and post samples if they also have bad uv, thanks
## Post #12
- Username: j61009123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 09, 2016 5:26 pm
- Post datetime: 2019-11-10T06:28:51+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

When I tried to open the same building as you do using your latest script, I always got this error in the debug log 
"WARNING: Weight contains an out of range bone index. Discarding model". 
Maybe I loaded the wrong .anim file. What .anim file you use when exporting building ?
## Post #13
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-10T11:28:19+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

When loading a static mesh like  a building it does not use a .anim file, when asked to pick a .anim file just press cancel, you will then be asked to choose a .V2 rigid model.

if you want i already made a custom script without skin support , you will be able to batch export all static meshes with it
PM me if you do and ill send it to you.
## Post #14
- Username: Zeratul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 23, 2019 7:22 pm
- Post datetime: 2019-12-24T03:12:27+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

I've been scratching my head trying to figure out why the skeletons are reversed in the max script, and found a quick fix, that was before I realized jay23 had a noesis script for it so I'm gonna give it a shot...

Anyway, when I read the script "and I have no knowledge whatsoever of reading script or programming of any sort" I found it having a "-vx" value in line 340 and 389, when I removed the "-" from just 1 of them, it wouldn't fix anything, but when I remove it from both the skeleton would now allign perfectly, and moving the handles moves the correct corresponding bone, and not the mirrored one.

This causes another issue however, where for some reason all the meshes have their normals reversed, but it's an easy fix after everything is loaded
## Post #15
- Username: Morgengrat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 24, 2019 3:08 pm
- Post datetime: 2019-12-26T23:56:32+00:00
- Post Title: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Thank you for your hard work for making those scripts! 
As someone who never worked with models or 3D im a bit confused about how to make those work. 
Basically, I have 3DMax 2013 and trying to import Buildings from WH2 to it. The thing is, I don't even know where to place the script, and what exact files should be imported from WH2 folder to 3Dmax. Could anyone link a guide or give a small tutorial for those like me, please?
## Post #16
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T20:24:15+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

I'm using a maxscript script to load models from Warhammer into 3DS Max, but none of the weapons I tried worked.... Any new one?
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-09T20:34:21+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

[viewtopic.php?f=16&t=21167](https://forum.xentax.com/viewtopic.php?f=16&t=21167)
## Post #18
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T21:17:00+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot ↑Mon Feb 10, 2020 4:34 am at Mon Feb 10, 2020 4:34 am
>
> 
viewtopic.php?f=16&t=21167

Thanks but I have absolutely no ideia how to use Noesis. Using 3DS because I found a tutorial for it
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-09T21:27:53+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

You will figure out it very fast, 3ds max much harder than this tool! You need to copy .py plugin into program's folder and pretty much that's all! I could add support for weapons, but since there's a nice alternative already - why not to try it xD
## Post #20
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T21:34:00+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot ↑Mon Feb 10, 2020 5:27 am at Mon Feb 10, 2020 5:27 am
>
> 
You will figure out it very fast, 3ds max much harder than this tool! You need to copy .py plugin into program's folder and pretty much that's all! I could add support for weapons, but since there's a nice alternative already - why not to try it xD

Actually got Noesis plugin working, but the tutorial I found that uses Noesis needs a first step I can't make work. 
It uses NinjaRipper to import the information from Warhammer, but  I always get an error when trying to use it that's why I learned how to use 3DS. I open NinjaReaper, open the game, go to battle, press the designated key and the game crashes...
## Post #21
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T22:03:57+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot ↑Mon Feb 10, 2020 5:27 am at Mon Feb 10, 2020 5:27 am
>
> 
You will figure out it very fast, 3ds max much harder than this tool! You need to copy .py plugin into program's folder and pretty much that's all! I could add support for weapons, but since there's a nice alternative already - why not to try it xD

Is there a way to extract the info and export a workable file from this using Noesis?: tmb_sepulchral_stalkers_halberd_2h_01.rigid_model_v2
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-09T22:05:08+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Sure lol, if you attach this file here - I'll try to help you with it.
## Post #23
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T22:10:53+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot ↑Mon Feb 10, 2020 6:05 am at Mon Feb 10, 2020 6:05 am
>
> 
Sure lol, if you attach this file here - I'll try to help you with it.

I found the Export into FBX option, loaded the Anim and then skeleton file,m but it gives an error - WARNING: Weight contains an out of range bone index. Discarding model.
## Post #24
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2020-02-09T22:15:30+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Well, script - plugin is to trying read it as a rigged model, maybe it's not supported yet, this type of mesh. As I said, you could attach here samples, I can't do anything - I don't have the game.
## Post #25
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T22:29:57+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from zaramot ↑Mon Feb 10, 2020 6:15 am at Mon Feb 10, 2020 6:15 am
>
> 
Well, script - plugin is to trying read it as a rigged model, maybe it's not supported yet, this type of mesh. As I said, you could attach here samples, I can't do anything - I don't have the game.

This are the files I need (extracted from the .pak). thanks for any help


[https://wetransfer.com/downloads/26d3e2 ... 844/da18c8](https://wetransfer.com/downloads/26d3e2796924a8fc35cd2ba05030cb6a20200209222844/bdec3eab6ec271b7b4c9d042358e291220200209222844/da18c8)
## Post #26
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-02-09T22:44:09+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> loaded the Anim and then skeleton file,m but it gives an error - WARNING: Weight contains an out of range bone index. Discarding model.

well my script has an order, first load the skeleton, then load the mesh and then animation
## Post #27
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-09T22:47:58+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from jayn23 ↑Mon Feb 10, 2020 6:44 am at Mon Feb 10, 2020 6:44 am
>
> 
loaded the Anim and then skeleton file,m but it gives an error - WARNING: Weight contains an out of range bone index. Discarding model.

well my script has an order, first load the skeleton, then load the mesh and then animation

Sorry. Skeleton is here. I don't have anything more..

[https://wetransfer.com/downloads/26484f ... 708/fc7033](https://wetransfer.com/downloads/26484f85b7f601ff725b36ebfc27c6f320200209224708/e8b36d21d90e42a5b84aa899d558ee9520200209224708/fc7033)
## Post #28
- Username: tasanhalas
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Feb 10, 2020 4:13 am
- Post datetime: 2020-02-10T13:07:55+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from jayn23 ↑Mon Feb 10, 2020 6:44 am at Mon Feb 10, 2020 6:44 am
>
> 
loaded the Anim and then skeleton file,m but it gives an error - WARNING: Weight contains an out of range bone index. Discarding model.

well my script has an order, first load the skeleton, then load the mesh and then animation

Found a script for props and made it work. Thanks for the help!
## Post #29
- Username: ephla442
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 15, 2020 2:37 am
- Post datetime: 2020-03-15T07:50:42+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Hi there, I'm new to modding Total War Warhammer 1 & 2, I'm unsure if it's been covered already so please forgive me if it has!  I have 3dsmax 2013 (I bought that version as it was the only one I could use when I created mods for Fallout 4 and Skyrim) I was wondering if there was a script to import the rigid_models_v2 for Warhammer 1 (I tried using this script to import Minotaurs from the beastmen faction but it wasn't able to), I want to convert the RMV2's into OBJ format so I can 3d paint my retextures using Mudbox, then further texture (mainly painting new normals) in Quixel.  Many thanks for any help or advice you are able to give with this question!
## Post #30
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-03-16T22:07:28+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> I was wondering if there was a script to import the rigid_models_v2 for Warhammer 1 (I tried using this script to import Minotaurs from the beastmen faction but it wasn't able to), I want to convert the RMV2's into OBJ format so I can 3d paint my retextures using Mudbox, then further texture (mainly painting new normals) in Quixel. Many thanks for any help or advice you are able to give with this question!

Hi, zaramot script for 3ds max should work for what you are trying, post file sample so someone can take a look.

also you can check my noesis script at [viewtopic.php?f=16&t=21167&start=30](https://forum.xentax.com/viewtopic.php?f=16&t=21167&start=30) if this dosent work for some reason
## Post #31
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-03-17T17:45:19+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

Hello!
Can someone give me the priests and paladins?
I wanna make cosplay suit, but can't find them.
Thanks!
## Post #32
- Username: Slava
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 06, 2020 6:37 am
- Post datetime: 2020-05-24T20:57:35+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from jayn23 ↑Sun Nov 10, 2019 7:28 pm at Sun Nov 10, 2019 7:28 pm
>
> 
When loading a static mesh like  a building it does not use a .anim file, when asked to pick a .anim file just press cancel, you will then be asked to choose a .V2 rigid model.

if you want i already made a custom script without skin support , you will be able to batch export all static meshes with it
PM me if you do and ill send it to you.

jayn23, when I press chancel, i gеt error: --Unable to convert: undefined to type: Filename. 
Or it is problem of max 2021?
## Post #33
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-26T21:30:19+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> jayn23, when I press chancel, i gеt error: --Unable to convert: undefined to type: Filename.
>
> Or it is problem of max 2021?

sorry for the late response i missed it somehow,

3DS max plugin was not made by me, it was made by zaramot.
his script works great on 3dsmax 2018 which is what i use, dont know about 2021, his script supports mesh + skeleton.
for any advice you should contact him, he is very helpful i am sure he will help you.
## Post #34
- Username: Slava
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 06, 2020 6:37 am
- Post datetime: 2020-05-28T13:54:03+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

> Reply from jayn23 ↑Wed May 27, 2020 5:30 am at Wed May 27, 2020 5:30 am
>
> 
jayn23, when I press chancel, i gеt error: --Unable to convert: undefined to type: Filename.
Or it is problem of max 2021?

sorry for the late response i missed it somehow,

3DS max plugin was not made by me, it was made by zaramot.
his script works great on 3dsmax 2018 which is what i use, dont know about 2021, his script supports mesh + skeleton.
for any advice you should contact him, he is very helpful i am sure he will help you.

Thank you very much!
## Post #35
- Username: h3ro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 10, 2020 5:12 am
- Post datetime: 2020-08-27T18:45:42+00:00
- Post Title: Re: Total War: Warhammer II import MaxScript (*.rigid_model_v2)

I had a look at the script, but I am struggling to understand how the normals are extracted. Can someone give me some pointers? Its been a very long time since I have been any max related programming

Edit: 
The script does not extract normals. If anyone wants them, they are stored like this for vertexType == 196608
                    vertex.Normal_X = (vertexChunck.ReadByte() / 255.0f * 2.0f) - 1.0f;    //byte 12 in vertex
                    vertex.Normal_Y = (vertexChunck.ReadByte() / 255.0f * 2.0f) - 1.0f;    //13
                    vertex.Normal_Z = (vertexChunck.ReadByte() / 255.0f * 2.0f) - 1.0f;    //14
