## Post #1
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-07-09T15:16:22+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

Hello!

Me and my buddy are making seperate Dead Space mods for Left 4 Dead 2 and G-mod.

We have the tools to open the .str, .sbk, .snu and .exa files of all the three games but no way to open the model files.

There is a tutorial explaining how to extract the models of Dead Space 2 on Facepunch but you apparently need 3D Max to make it work and it costs quite a lot.

So I was wondering if there is a way to open them on Blender?

I personally need just the models and textures for my L4D2 mod (because you can't add custom animations for the infected, or that's what I've heard) but my friend needs the animations as well along with the models and textures for his gmod modification.

Here are the files of an enemy from Dead Space 2 just for an instance with all the files that were unpacked with the .str unpacker that came with BigViewer:
[http://www.mediafire.com/download/bdna6 ... rmorph.rar](http://www.mediafire.com/download/bdna6u1s1p3p16x/Ubermorph.rar)


If anyone is kind enough to help out, that'd be nice.

Thank you for reading!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T15:56:07+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

models are simple - uvs require some fiddeling though:



0059_mesh_body-geo.jpg (157.52 KiB) Viewed 1184 times
## Post #3
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-07-09T16:15:26+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from shakotay2
>
> models are simple - uvs require some fiddeling though:
0059_mesh_body-geo.jpg
???????????

> Reply from shakotay2
>
> models are simple - uvs require some fiddeling though:
0059_mesh_body-geo.jpg
Where can I find the download link for that program?

And also is it possible to open the models in Blender?

Edit: nevermind I found the download link, but my question above remains.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-09T19:45:53+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

use File/SaveAs mesh to create a wavefront obj file
## Post #5
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-07-10T08:30:41+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from shakotay2
>
> use File/SaveAs mesh to create a wavefront obj file
It kinda looks like the models have very low polygons as well as you can't get the textures nor animations. I'm going to try some other method. Thanks for this anyways.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-10T13:49:38+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from MaZTeR
>
> It kinda looks like the models have very low polygonsthat's not a matter of hex2obj
## Post #7
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-14T22:38:16+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from shakotay2
>
> MaZTeR wrote:It kinda looks like the models have very low polygonsthat's not a matter of hex2obj

Can you add me on steam [http://steamcommunity.com/id/frogs13/](http://steamcommunity.com/id/frogs13/) I require some serious help in terms on dead space models with animations is there a possible script that can import these models and if not can you create one? Obviously if you cant hexing will be our only option.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-15T19:08:20+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from Braintwistah
>
> Can you add me on steamthat's no option, sry. I'm going to reduce my online activity rather than increasing it.  

> in terms on dead space models with animations is there a possible script that can import these models and if not can you create one?For Death Space 2 animations are hkx (hkx.win). There's a lot of posts concerning hkx in this forum. Read them, please.

Best results so far I got using the Havok Standalone tool. Rename hkx.win to hkx to test it.
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-15T19:42:23+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

I made script for Dead Space 1-3 models with bones and weights long ago, though I lost them   Shakotay saying right things like always, for animation you could try .hkx tool, .hkx versions in Dead Space's games are old, you will get animation I'm sure. I could help you with texture converter, I'll upload it soon, texture format and model format almost like in other game I worked on not long ago. 

[](http://hostingkartinok.com/show-image.php?id=19f8de843d67839895660b66717caba6)
## Post #10
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-16T02:52:59+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from zaramot
>
> I made script for Dead Space 1-3 models with bones and weights long ago, though I lost them   Shakotay saying right things like always, for animation you could try .hkx tool, .hkx versions in Dead Space's games are old, you will get animation I'm sure. I could help you with texture converter, I'll upload it soon, texture format and model format almost like in other game I worked on not long ago.

Thanks for the insight from both of you zaramot mind adding me on steam

EDIT: Also tried renaming the animation so it was only .hkx instead of .hkx.WIN I had no luck
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-16T08:52:17+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

I don't have steam, well I have but I'm such rare online there - so, it's almost like I don't have it xD If you want to ask me about format of 3d models you can send me PM, or maybe on Skype.
## Post #12
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-16T13:06:05+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from zaramot
>
> I don't have steam, well I have but I'm such rare online there - so, it's almost like I don't have it xD If you want to ask me about format of 3d models you can send me PM, or maybe on Skype.

Yeah Im just looking for alittle bit of guidance also Im gonna need that model and texture converter
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-16T14:09:14+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

> Reply from Braintwistah
>
> EDIT: Also tried renaming the animation so it was only .hkx instead of .hkx.WIN I had no luckno luck with what? (Would be really nice if you could be more precise.  )

Indeed that 21 kB hkx.win you provided crashes Havok Tools Standalone, 2013.1.0.1 

Reason is probably because it contains hkpPhysicsSystem and Ragdoll data.
Guess you don't need that, do you?

Why not provide a hkx.win with hkaSkeleton for example?
(Or hkaAnimationContainer, hkaInterleavedUncompressedAnimation.)

btw: you'll need a skeleton before handling animations makes any sense
## Post #14
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-16T14:53:14+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

Zaramot, you think you can find that old script of yours? Or atleast whip us out a quick one for ds1? We need those models skinned for the animations to work, and your script could help a lot.
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-16T15:08:14+00:00
- Post Title: Ripping Dead Space 1-3 models with animations and textures.

I'm afraid I can't find old scripts , though I can remake script I made for other game with similiar 3d format. Ufortunatelly, I don't have time for this at the moment, I'm playing MMO Black Desert when I have free from work time.
## Post #16
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-16T17:08:51+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Alright, thanks anyways. Maybe when you have some time you could fix us a basic script, if it is not asking much.
Have fun in black desert for now, it looks pretty interesting from what I've seen.
## Post #17
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-16T17:17:40+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Just post a link to your script on here when you have eithier found it or had the time to make a new one
## Post #18
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-07-16T20:54:39+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

So many posts I've missed, why haven't I gotten any email notifications even though I'm subscribed??
## Post #19
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-07-16T23:07:18+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Iv'e also made a script for dead space 2-3 long ago. Everything's working except the skinning. I never could figure it out but its better than starting from scratch. 
[deadspace.7z](https://xentaxbackup.github.io/file/11293_deadspace.7z)
## Post #20
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-17T12:01:43+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

So I presume it will not work with ds1?
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-17T14:23:48+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> Iv'e also made a script for dead space 2-3 long ago. Everything's working except the skinning. I never could figure it out but its better than starting from scratch.thanks for sharing!  

I got some trouble with DS2, 0059_mesh_body_dism.geo 'til I realized that it seems to require 0060_mesh_body_dism.geo 
(which I don't have) which contains the uvs as external data, right?
Finally loaded without uvs:



0059_mesh_body_dism.JPG (13.15 KiB) Viewed 300 times
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-18T01:40:21+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> I got some trouble with DS2, 0059_mesh_body_dism.geo 'til I realized that it seems to require 0060_mesh_body_dism.geo 
(which I don't have) which contains the uvs as external data, right?
yeah the mesh files are in the "Mesh" folder
and the UV files for each mesh file are in the "MeshVolatile" folder
the headerless texture files are in the "tg4d" folder
and the header files for each texture file is in the "tg4h" folder
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-18T16:47:30+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> and the UV files for each mesh file are in the "MeshVolatile" folderthx! Well sometimes I'm a real dumbo - cruising through the eternal universe with my big ears
## Post #24
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-18T18:58:36+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Any news on a dead space 1 import script were waiting semi patiently XD
## Post #25
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2016-07-19T18:13:18+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur


## Post #26
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-20T19:55:47+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from Mr.Mouse
>
> 

Explains how we are with these models right now we get passed something and then there's another wall kicking our ass.
## Post #27
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-22T17:08:23+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Any news on this topic?
## Post #28
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-07-26T18:04:15+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

bump
## Post #29
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-01T12:37:05+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Anything new?
## Post #30
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-08-04T04:38:53+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Bump
## Post #31
- Username: Braintwistah
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Jul 05, 2016 9:45 pm
- Post datetime: 2016-08-12T15:03:30+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

BUMP
## Post #32
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-08-22T12:09:34+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Is this completely abandoned?

I really could use some models right now :/
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-08T01:07:28+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Here are the files of an enemy from Dead Space 2 just for an instance with all the files that were unpacked with the .str unpacker that came with BigViewer:
http://www.mediafire.com/download/bdna6 ... rmorph.rar

*updated May 7, 2018*
i made a Noesis python script to open your tg4h/tg4d texture pair samples  
*updated to support Dead Space 1,2,3 textures from PC, PS3 and X360 platforms*


 tex_DeadSpace123_PC_PS3_X360_tg4h.zip
(1.22 KiB) Downloaded 187 times


supports dxt1, dxt5, rgba32, L8 and maybe L8A8 (may need more testing)

open the tg4h file and the script will find the corresponding tg4d file.
you can dump the tg4h and tg4d files all in the same folder not named "tg4h"
or you can keep them in their original tg4h/tg4d folders, as long as they
are side by side the script will find everything.

this script was a lesson in opening file pairs with different names from different 
folders at the same time.
## Post #34
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-09-24T10:32:59+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:Here are the files of an enemy from Dead Space 2 just for an instance with all the files that were unpacked with the .str unpacker that came with BigViewer:
http://www.mediafire.com/download/bdna6 ... rmorph.rar

i made a Noesis python script to open your tg4h/tg4d texture pair samples  
tex_DeadSpace2_tg4h.zip

supports dxt1 and dxt5 because those were the only types in the samples.
you open the tg4h file and the script will find the corresponding tg4d file.
you can dump the tg4h and tg4d files all in the same folder or keep them 
in their original tg4h/tg4d folders, as long as they are side by side it will work.

this script was a lesson in opening file pairs with different names from different 
folders at the same time.
Sorry for the very late response and thanks but I have no clue how to open it
## Post #35
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-18T16:19:11+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

I've finally figured out how to extract the models from DS2 and DS3 but I still don't know how to get the textures extracted without using 3D Ripper DX.
## Post #36
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-18T16:20:31+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from zaramot
>
> I made script for Dead Space 1-3 models with bones and weights long ago, though I lost them  :( Shakotay saying right things like always, for animation you could try .hkx tool, .hkx versions in Dead Space's games are old, you will get animation I'm sure. I could help you with texture converter, I'll upload it soon, texture format and model format almost like in other game I worked on not long ago.
I could really use that texture converter right now :)
## Post #37
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-18T16:29:04+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> I could really use that texture converter right now
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)
## Post #38
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-18T16:54:30+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:I could really use that texture converter right now 
viewtopic.php?p=122302#p122302
Oh yeah, I tried to download it today but for some reason the download link to that converter doesn't work.

Edit: I think I actually found a correct one.
## Post #39
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-18T17:07:27+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

It works!!!!!!!

It works!!!!

Thank you!
## Post #40
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-19T20:22:58+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hey, the Noesis script you made works with Dead Space 2 textures but it doesn't work with Dead Space 3 ones.

[https://www.dropbox.com/s/wqslwmt9hbh7a ... r.rar?dl=0](https://www.dropbox.com/s/wqslwmt9hbh7abq/DS3Regenerator.rar?dl=0)

That contains the textures of a Dead Space 3 enemy.
## Post #41
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-19T21:47:48+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> https://www.dropbox.com/s/wqslwmt9hbh7a ... r.rar?dl=0
That contains the textures of a Dead Space 3 enemy.
okay i updated the "Dead Space 2" texture script to support "Dead Space 3" textures too  
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)
## Post #42
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-20T09:57:10+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:https://www.dropbox.com/s/wqslwmt9hbh7a ... r.rar?dl=0
That contains the textures of a Dead Space 3 enemy.
okay i updated the "Dead Space 2" texture script to support "Dead Space 3" textures too  
viewtopic.php?p=122302#p122302
Thanks but I'm getting a weird error with DS2 Slasher textures.

It says: "Traceback (most recent call last):
File
"C\Users\Me\Noesis\plugins\blablabla\tex_DeadSpace2and3_tg4h.py", line 58, in noepyLoadRGBA
wtf = NoeBitStream(rapi.loadIntoByteArray(texName))
RuntimeError: Unable to load file."

Here's an example where it gives that error:
https://www.dropbox.com/s/pfn4zgp5pklni ... d.rar?dl=0

Nevermind I fixed it.
## Post #43
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-20T10:42:08+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

None of the mesh scripts work on Dead Space models.

Can someone take a look at this model and maybe reverse-engineer a script for meshes from the first game?

[https://www.dropbox.com/s/9fjf5xkopdahu ... e.zip?dl=0](https://www.dropbox.com/s/9fjf5xkopdahuje/ds1%20brute.zip?dl=0)
## Post #44
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-20T21:46:58+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Can someone take a look at this model and maybe reverse-engineer a script for meshes from the first game?seems people who could, are too busy or the game is too old to raise more interest...



0085_mesh_body_dism-geo.JPG (41.54 KiB) Viewed 481 times

(unsure about uvs)
## Post #45
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-20T23:14:13+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> MaZTeR wrote:Can someone take a look at this model and maybe reverse-engineer a script for meshes from the first game?seems people who could, are too busy or the game is too old to raise more interest...
0085_mesh_body_dism-geo.JPG(unsure about uvs)
It's a shame, there are a ton of models awaiting :/

Just have to wait and see. Someone on my Facepunch thread managed to get the Advanced Soldier RIG along with textures from the first game:
[https://facepunch.com/showthread.php?t= ... st51225505](https://facepunch.com/showthread.php?t=1538229&p=51225505&viewfull=1#post51225505)

The script AceWell made for Noesis extracts the textures from the first game but without the models, they're no use for me.
## Post #46
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-21T12:29:37+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

the format looks pretty simple (just looked at the wrong place for the uvs  ):



0085_mesh_body_dism-geo-UVs.JPG (42.39 KiB) Viewed 358 times



For some models uvs still unsure, though:
[viewtopic.php?f=16&t=14622&p=120255&hil ... ng#p120255](http://forum.xentax.com/viewtopic.php?f=16&t=14622&p=120255&hilit=fiddeling#p120255)
## Post #47
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-22T00:38:05+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

here is Noesis python script to open your "brute" samples  
*updated Jan 30, 2017*


 fmt_DeadSpace1_geo.zip
(1.31 KiB) Downloaded 268 times


supports geometry and UVs, nothing fancy

strange looking fellow..


looks like the difference between DS1 and DS2/3 models is DS1 stores the UV data 
with the model where DS2/3 store it in a separate file in the "MeshVolatile" folder.
## Post #48
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-22T10:21:47+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> here is Noesis python script to open your "brute" samples  
fmt_DeadSpace1_geo.zip
supports geometry and UVs, nothing fancy

strange looking fellow..


looks like the difference between DS1 and DS2/3 models is DS1 stores the UV data 
with the model where DS2/3 store it in a separate file in the "MeshVolatile" folder.
hey, thanks!
## Post #49
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-22T11:45:09+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

It seems that your script flips the UVs so that the textures are wrong.
## Post #50
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-22T12:42:32+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> It seems that your script flips the UVs so that the textures are wrong.
no, Noesis flips the UVs unless you export as fbx, otherwise you have to tick the flip uv option when exporting,
either that or you can just flip the textures, doesn't really matter as long as they both match
## Post #51
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-22T17:36:17+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:It seems that your script flips the UVs so that the textures are wrong.
no, Noesis flips the UVs unless you export as fbx, otherwise you have to tick the flip uv option when exporting,
either that or you can just flip the textures, doesn't really matter as long as they both match
Okay, well, I got that fixed by just assambeling the parts into one model and then flipping that model's UVs.

Also another problem with that is that the models are really small, and I have to resize them in 3D Max.
## Post #52
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2016-10-23T08:28:05+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> here is Noesis python script to open your "brute" samples  
fmt_DeadSpace1_geo.zip
supports geometry and UVs, nothing fancy

.

Will this work with the other files of DeadSpace 1? and plan to do the other 2 dead space?
## Post #53
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-23T09:33:35+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from Nexus Elite
>
> AceWell wrote:here is Noesis python script to open your "brute" samples  
fmt_DeadSpace1_geo.zip
supports geometry and UVs, nothing fancy

.

Will this work with the other files of DeadSpace 1? and plan to do the other 2 dead space?
So far his texture script has worked on all DS2 and 3 textures, so presumably yes it should work on all the models.

For the other games, please see my tutorial for all the files found from this thread and some other pages used in the extracting process:
[https://facepunch.com/showthread.php?t= ... st51222401](https://facepunch.com/showthread.php?t=1538229&p=51222401&viewfull=1#post51222401)

With it, you can extract the models, textures and skeletons from all the games combined with the script for DS1. However, the models will not be rigged so you need to rig them again to the skeleton. The skeleton is the .rcb.win file.
## Post #54
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-23T09:50:25+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Could anyone take a look at the animations for example for the Brute from Dead Space 2?

I'll provide everything here:
[https://www.dropbox.com/s/uurmhyhbwwsm8 ... t.rar?dl=0](https://www.dropbox.com/s/uurmhyhbwwsm8y5/BruteDS2Test.rar?dl=0)
## Post #55
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-23T14:49:49+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

I need a script for the health + stasis bar textures. Preferably added to the already existing ds1,2 and 3 script.
[bars.rar](https://xentaxbackup.github.io/file/11827_bars.rar)
## Post #56
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-24T03:18:08+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> I need a script for the health + stasis bar textures. Preferably added to the already existing ds1,2 and 3 script.
you'll need to include the corresponding tg4d files too because i have no idea how to treat "L8A8" textures
## Post #57
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T04:49:13+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:I need a script for the health + stasis bar textures. Preferably added to the already existing ds1,2 and 3 script.
you'll need to include the corresponding tg4d files too because i have no idea how to treat "L8A8" textures
Ah, here are all the files of the Advanced RIG.

[https://www.dropbox.com/s/361rpbqg5o2ad ... d.rar?dl=0](https://www.dropbox.com/s/361rpbqg5o2adr7/Uniadvanced.rar?dl=0)
## Post #58
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-24T07:00:35+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated the script here for L8A8, it might not be right but it works   
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)
i'm not sure why you need those tiny textures but at least now you can open them, enjoy!
## Post #59
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T10:10:02+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> okay i updated the script here for L8A8, it might not be right but it works   
viewtopic.php?p=122302#p122302
i'm not sure why you need those tiny textures but at least now you can open them, enjoy!
Thanks, I'll try it later.

And I don't think I need those tiny textures, I have no clue what they are even used. They came in with the other files as I just dragged and dropped everything extracted from the game files to the .rar
## Post #60
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T13:13:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

It opens the files and exports them with no problem but there's nothing appearing. Everything is transparent.
## Post #61
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T13:47:28+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Also another glitch in your ds1 geo file script is that it combines some parts with other parts, for example a part of the upper torso model of a RIG suit gets put with the lower body, so the textures will look weird and force me to manually separate them. Can you possibly fix this?
## Post #62
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T14:47:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

It's always this part that gets put with the lower body:
## Post #63
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-10-24T14:54:16+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> It's always this part that gets but with the lower body:just an assumption of a problem: it's a first submesh or last one.
## Post #64
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-24T15:01:12+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from Tosyk
>
> MaZTeR wrote:It's always this part that gets but with the lower body:
just an assumption of a problem: it's a first submesh or last one.
That part is made of that clothed first layer and those armor pieces. And the armor pieces have multiple sides.
## Post #65
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-25T03:25:37+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> It opens the files and exports them with no problem but there's nothing appearing. Everything is transparent.
you have to upload samples you think isn't working or else there is nothing i can do.
i test export all the samples uploaded to see the result in another program.
also if a texture opens in Noesis without error but is invisible, it really is there it just
has a layer of transparency you can't turn off or disable in Noesis, or at least i have not
figured out where the setting is.  

> Reply from MaZTeR
>
> Also another glitch in your ds1 geo file script is that it combines some parts with other parts, for example a part of the upper torso model of a RIG suit gets put with the lower body, so the textures will look weird and force me to manually separate them. Can you possibly fix this?
sorry there is nothing more i can do with that script you just have to deal with it or wait
for the next guy to make a better script or tool.
## Post #66
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-25T14:56:11+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Yep, the health bars do not work.

One texture appears black and yellow and the others just pitch black (or transparent).

The sample is in the Advanced Suit one I sent earlier. It's the same in all the models.
## Post #67
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-25T16:39:42+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Yep, the health bars do not work.

One texture appears black and yellow and the others just pitch black (or transparent).

The sample is in the Advanced Suit one I sent earlier. It's the same in all the models.
i don't know what you expect from them, looks to me like the image data matches what you see.  
those are tiny images anyway, not sure why you even need them, if you think they are wrong you 
can always recreate them the way you think they should be. you don't have to be an artist to make an 
all-black or all-white texture etc.
## Post #68
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-25T19:15:10+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:Yep, the health bars do not work.

One texture appears black and yellow and the others just pitch black (or transparent).

The sample is in the Advanced Suit one I sent earlier. It's the same in all the models.
i don't know what you expect from them, looks to me like the image data matches what you see.  
those are tiny images anyway, not sure why you even need them, if you think they are wrong you 
can always recreate them the way you think they should be. you don't have to be an artist to make an 
all-black or all-white texture etc.
Wait what? That's it? They're supposed to look something like this:
## Post #69
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-25T19:18:47+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

I get the same error as before the DS1 rig textures now with the DS2 rig textures.

Here they are:
[bars_ds2.rar](https://xentaxbackup.github.io/file/11839_bars_ds2.rar)
## Post #70
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-25T19:45:55+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

you have to include the corresponding tg4d files, those hold 
the actual image data, the tg4h files store only the header.
## Post #71
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-25T20:47:05+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

AceWell, now I see, that you amazinly kind person with such patience omg, I admire that.
## Post #72
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-25T21:31:38+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

That should do it. There are bunch of other texture files I can extract but I just pasted everything there.
[https://www.dropbox.com/s/o09bbzyfaw348 ... s.rar?dl=0](https://www.dropbox.com/s/o09bbzyfaw348pf/ds2_bars.rar?dl=0)
## Post #73
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T09:03:52+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated the script here for rgba32 textures   
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)

i would take another look at the L8A8 samples but you removed them  
anyone else have some of those samples from this game?
## Post #74
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-26T13:43:53+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> okay i updated the script here for rgba32 textures   
viewtopic.php?p=122302#p122302

i would take another look at the L8A8 samples but you removed them  
anyone else have some of those samples from this game?
Oh, woops. Okay, I'll post it again.
## Post #75
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-26T13:50:11+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Alright here, this is a freshly extracted Advanced Soldier RIG:

[https://www.dropbox.com/s/97d73ma4g2c8k ... G.rar?dl=0](https://www.dropbox.com/s/97d73ma4g2c8kln/Advanced%20Soldier%20RIG.rar?dl=0)
## Post #76
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-26T13:57:19+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

The Dead Space 2 script works now.

However, I have no clue how to make the textures properly worked. The RIG zipper textures come in blue, yellow, orange, red, pink and violet colors. As well as there is this file called "Healthbargradient", which has red, yellow and light blue colors.

In Dead Space 2 and 3, the RIG's kind of like glow and change colors constantly, but I'm pretty sure that is something the game has, not the model.
## Post #77
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T17:33:58+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

you must remember that some textures will look different when viewed outside
the game because they are used along with shaders inside the game.

anyway, i played around with the L8A8 texture data and have done my best   
with the information i gathered from here
[https://msdn.microsoft.com/en-us/librar ... er_content](https://msdn.microsoft.com/en-us/library/windows/desktop/bb943991%28v=vs.85%29.aspx#common_dds_file_resource_formats_and_associated_header_content)
i'm not a programmer so i don't know if my interpretation is 100% correct
but i updated the script again with minor changes to the L8A8 format
## Post #78
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-26T18:12:45+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> you must remember that some textures will look different when viewed outside
the game because they are used along with shaders inside the game.

anyway, i played around with the L8A8 texture data and have done my best   
with the information i gathered from here
https://msdn.microsoft.com/en-us/librar ... s.85).aspx
i'm not a programmer so i don't know if my interpretation is 100% correct
but i updated the script again with minor changes to the L8A8 format
Now some of the DS1 RIG textures appear either as red or just completely transparent :/
## Post #79
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-27T11:21:57+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Now some of the DS1 RIG textures appear either as red or just completely transparent :/
show me what you think they are supposed to look like
## Post #80
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-27T13:04:36+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:Now some of the DS1 RIG textures appear either as red or just completely transparent :/
show me what you think they are supposed to look like
Okay here's how it is supposed to look like:

[https://facepunch.com/showthread.php?t= ... st51250212](https://facepunch.com/showthread.php?t=1538229&p=51250212&viewfull=1#post51250212)

except it is supposed to be blue.

In-game, the health bar and the stasis are supposed to look like this:
## Post #81
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-27T14:44:01+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Okay here's how it is supposed to look like:
https://facepunch.com/showthread.php?t= ... st51250212
except it is supposed to be blue.
the image posted there is incorrect, even if it was blue, which it isn't no matter how
you arrange the channels, it still has a gradient. and the header states rgba8 so that's
how the script is set to read it.

> Reply from MaZTeR
>
> In-game, the health bar and the stasis are supposed to look like this:
i don't know what i'm supposed to be looking at here, but if you mean
that light greenish color, you could make that yourself in image editor in 2 seconds.
and i'm pretty sure game shaders work with the texture there to make an effect work.
nothing more i can do here, enjoy!
## Post #82
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-10-27T16:57:00+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:Okay here's how it is supposed to look like:
https://facepunch.com/showthread.php?t= ... st51250212
except it is supposed to be blue.
the image posted there is incorrect, even if it was blue, which it isn't no matter how
you arrange the channels, it still has a gradient. and the header states rgba8 so that's
how the script is set to read it.
MaZTeR wrote:In-game, the health bar and the stasis are supposed to look like this:

i don't know what i'm supposed to be looking at here, but if you mean
that light greenish color, you could make that yourself in image editor in 2 seconds.
and i'm pretty sure game shaders work with the texture there to make an effect work.
nothing more i can do here, enjoy!
Alright, well, thanks
## Post #83
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-11-06T11:22:48+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Can anyone help me with this script?

[http://www.scriptspot.com/3ds-max/scrip ... portimport](http://www.scriptspot.com/3ds-max/scripts/batch-exportimport)

Whenever I try to run the import option, I get a syntax error called:

"Syntax error: at end of script, expected end of string
In line #C:\BlaBlaBla\CharacterModelName\BlaBla\0120_mesh_shadereyer_dism_files\\0120_mesh_shadereyer.obj"

It started doing this about week ago after I was importing some characters from the first Dead Space. And I have no clue how to fix this. It gives me this error every time I open that import script.

I have redownloaded the script maybe 10 times with the same result. I need that script as 3D max for some reason does not support importing multiple files by default.
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-06T14:10:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

here's a simple solution for processing multiple files in maxscript:
[viewtopic.php?f=13&t=10744&p=110490&hil ... le#p110490](http://forum.xentax.com/viewtopic.php?f=13&t=10744&p=110490&hilit=maxscript+multiple#p110490)
## Post #85
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-11-15T17:50:44+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> here's a simple solution for processing multiple files in maxscript:
viewtopic.php?f=13&t=10744&p=110490&hil ... le#p110490
I'm kinda newby, how do I set that up? Creating just a 3D max script doesn't work with that.
## Post #86
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-11-15T21:45:12+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

As you can see from the "resulting listener output" it worked.

You've to change the path (K:\\...) so that it points to your model files' folder, of course and set the model_type.
## Post #87
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-11-16T07:52:30+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> As you can see from the "resulting listener output" it worked.

You've to change the path (K:\\...) so that it points to your model files' folder, of course and set the model_type.
Just that? Okay I'll try it later.
## Post #88
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-15T17:17:17+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> Iv'e also made a script for dead space 2-3 long ago. Everything's working except the skinning. I never could figure it out but its better than starting from scratch.
I don't know if you'll respond but from what i have messed around with different skeletons, it seems that the script is only using the red weights and is missing the other colored weights. If that gets fixed by just adding the other colors, you don't have to further mess around with the skeleton. Everything that is read in the envelope editor is fine as they are, the parts that have no color but should have need to be fixed
## Post #89
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-15T20:05:16+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

If all weights are red it's couldn't be correct, as far as I remember dead space games using 4 bones and 4 weights per vertex, maybe all 4 are rarely used but not one bone+weight for sure xD
## Post #90
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-16T13:49:01+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from zaramot
>
> If all weights are red it's couldn't be correct, as far as I remember dead space games using 4 bones and 4 weights per vertex, maybe all 4 are rarely used but not one bone+weight for sure xD
No it's not all red, I'll send picturse of how it looks like and how it should look like with some tweakings.
## Post #91
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-16T13:51:49+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Alright so here is the Ubermorph with the skeleton extracted with your script.

Here's how it looks like unmodified:



Here's my modification of how the claws should look like:



And here's an image of how the weights are incorrectly placed as the upperarm bone movement affects the static torso meshes. It should affect only the arm mesh where the claw is attached:
## Post #92
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-16T13:53:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Another interesting thing is that the reason why the top image happens is because in that part, only the claw bone affects the mesh in that area, when the forearm bone should also affect the joint area of the claw, not just the claw bone.

The same thing applies to other areas of the body like the knees and the thighs. In the two later images, I fixed the upper and the forearms with the same method, as before the upper arm affected only the base of the arm meanwhile the forearm controlled the rest of the arm, making movement glitchy.
## Post #93
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-31T00:09:22+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:Okay here's how it is supposed to look like:
https://facepunch.com/showthread.php?t= ... st51250212
except it is supposed to be blue.
the image posted there is incorrect, even if it was blue, which it isn't no matter how
you arrange the channels, it still has a gradient. and the header states rgba8 so that's
how the script is set to read it.
I was searching for more models from the first game and noticed new, unconvertable files.

Here they are:
[https://www.dropbox.com/s/ey6jqlha40bzq ... e.rar?dl=0](https://www.dropbox.com/s/ey6jqlha40bzqqg/ds1modelsunconvertable.rar?dl=0)
## Post #94
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-01T09:43:25+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

i looked at your new samples and the vertex stride could be 12 or 32 and the UV 
stride could be 8 or 20 or 28 and the file could have submeshes which means i can't
read the data in a single array, the extended table in some of these is confusing to me.
if there is only a few not-working models i think it would be quicker for you
to just use Hex2obj to get these meshes than for me to try and figure out
any flags and pointers to modify the script to support these.
## Post #95
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-01T11:05:34+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> if there is only a few not-working models i think it would be quicker for you
to just use Hex2obj to get these meshes than for me to try and figure out
any flags and pointers to modify the script to support these.guess he will not as long as there's people who are doing all the work for him 



0425_kellion_chair.JPG (121.12 KiB) Viewed 130 times
## Post #96
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-01T20:11:55+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> i looked at your new samples and the vertex stride could be 12 or 32 and the UV 
stride could be 8 or 20 or 28 and the file could have submeshes which means i can't
read the data in a single array, the extended table in some of these is confusing to me.
if there is only a few not-working models i think it would be quicker for you
to just use Hex2obj to get these meshes than for me to try and figure out
any flags and pointers to modify the script to support these.
These are level meshes so there are a ton of these kinds of files. Also as far as I am certain, the only files I can't open are the LODs and the level meshes themselves only so if the script is edited to open those, I think it works on all of them.

Oh and I have really no clue how to use Hex2obj and also if I have to get all the files one by one with that tool, it will take an eternity.

And also if I wait for someone else to get the models for me, well, it will take even longer.
## Post #97
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-02T01:35:29+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> None of the mesh scripts work on Dead Space models.

Can someone take a look at this model and maybe reverse-engineer a script for meshes from the first game?

https://www.dropbox.com/s/9fjf5xkopdahu ... e.zip?dl=0
this samples link is not working, i want to compare the new samples with the originals. most of
your new samples will open just not export, i think i can make those work easily, but the ones
with submeshes like 0426_opt_model1.geo will be a problem for me at my experience level.
## Post #98
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-02T10:55:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:None of the mesh scripts work on Dead Space models.

Can someone take a look at this model and maybe reverse-engineer a script for meshes from the first game?

https://www.dropbox.com/s/9fjf5xkopdahu ... e.zip?dl=0
this samples link is not working, i want to compare the new samples with the originals. most of
your new samples will open just not export, i think i can make those work easily, but the ones
with submeshes like 0426_opt_model1.geo will be a problem for me at my experience level.
I think the opt models are the level meshes actually, which is what I'm looking for mainly and why I asked for help. And that model spesifally is the USG Kellion and its interior from the intro of the first game (if I remember correctly where I got those files).

Oh and these are the files that need to be worked on:
[https://www.dropbox.com/s/ey6jqlha40bzq ... e.rar?dl=0](https://www.dropbox.com/s/ey6jqlha40bzqqg/ds1modelsunconvertable.rar?dl=0)

I'll probably post more files so we can make all the models exportable (well, if you can make that work with your experience).

And I suggest maybe taking a look at the 3D Max scripts from here zaramot has made for ds2 and 3 for reference as they can be used to open the level meshes from the newer games:
[https://www.dropbox.com/s/n4lyc37w04u3w ... -3.ms?dl=0](https://www.dropbox.com/s/n4lyc37w04u3wye/deadspace%202-3.ms?dl=0)

[https://www.dropbox.com/s/rtrof1xjrraw2 ... ch.ms?dl=0](https://www.dropbox.com/s/rtrof1xjrraw2mi/deadspace%202-3%20batch.ms?dl=0)

And another thing is that I found a texture that could not be opened a while back. I'll post it here
[yay.rar](https://xentaxbackup.github.io/file/12147_yay.rar)
## Post #99
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-02T11:00:38+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Once all the models and textures and everything are openable, the only things remaining are the animations. Wish someone could take a look at the files.

Apparently they are similar to the animations from Skyrim and Battlefield.
## Post #100
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-02T11:47:00+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

no i need the samples from that link i quoted so i can compare working to not-working ones. 
and that tg4h file you uploaded is just a header for the tg4d data, i would need that file too.
## Post #101
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-02T13:38:25+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Oh sorry, there.

And here is a working model:
[https://www.dropbox.com/s/g7c8d9yav7236 ... g.rar?dl=0](https://www.dropbox.com/s/g7c8d9yav7236sd/bruteds1working.rar?dl=0)
[yay.rar](https://xentaxbackup.github.io/file/12148_yay.rar)
## Post #102
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-03T06:35:04+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated the texture script here for that texture
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)

that texture sample looks like it should be used with a flipbook shader
if you look at it in TextureFinder with 32 width the colors will fade in
and out like it should be animated or scrolling frame to frame.   



and updated the model script here best i could do
[viewtopic.php?p=123701#p123701](http://forum.xentax.com/viewtopic.php?p=123701#p123701)

it works with all but 2 of your samples, 0419_ishimura.geo and 
0426_opt_model1.geo, those have submeshes.
give it a try, no promises though
## Post #103
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-03T10:52:25+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> okay i updated the texture script here for that texture
viewtopic.php?p=122302#p122302

that texture sample looks like it should be used with a flipbook shader
if you look at it in TextureFinder with 32 width the colors will fade in
and out like it should be animated or scrolling frame to frame.   



and updated the model script here best i could do
viewtopic.php?p=123701#p123701

it works with all but 2 of your samples, 0419_ishimura.geo and 
0426_opt_model1.geo, those have submeshes.
give it a try, no promises thoughI think the texture is actually the shader for the bloody screen that appears whenever you die in the game.

And as for the model script, it does open everything but only the models with one mesh open normally. Everything else that have sub-meshes are just big piles of different shapes.

Sadly, they are the level meshes which I really want. Is there possibly a way you could somehow take a look at the 3D Max scripts and see how they are made and maybe put the code into your script? They can be used to open submeshes like the ones I gave you.
## Post #104
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-05T07:15:13+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

0426_opt_model1.geo is not too hard; had to split the first submesh because hex2obj can't handle more than 65535 tristripped FIs at once:



0426_opt_model1.JPG (107.64 KiB) Viewed 74 times



Seems there's 37 more submeshes; good luck.
## Post #105
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-05T10:38:49+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> 0426_opt_model1.geo is not too hard; had to split the first submesh because hex2obj can't handle more than 65535 tristripped FIs at once:
0426_opt_model1.JPG

Seems there's 37 more submeshes; good luck.
Yeah the level meshes have many details
## Post #106
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-15T15:08:59+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

It seems that the script breaks some of the models' UVs. For example, the LODs' UVs are broken, as seen here:



[https://www.dropbox.com/s/uihsjheqcumpj ... 2.rar?dl=0](https://www.dropbox.com/s/uihsjheqcumpjnv/kendra%27s%20pistol%20ch12.rar?dl=0)
## Post #107
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-15T15:12:27+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Also I think the same problem is with the Dead Space 2-3 models script. All the level meshes and LODs are broken like that. Except the dismembering meshes.
## Post #108
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-15T19:46:21+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated the script here   
[viewtopic.php?p=123701#p123701](http://forum.xentax.com/viewtopic.php?p=123701#p123701)
again no promises, and i may have broken other models
## Post #109
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-16T13:11:32+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> okay i updated the script here   
viewtopic.php?p=123701#p123701
again no promises, and i may have broken other models
That pistol model works now, but I have yet to see if anything else is broken. Thanks anyways.

I also saw some other LOD models that wouldn't allow me to open them but I forgot where I found them and also the level meshes do work still work.
## Post #110
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-16T13:14:44+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Oh and someone in my facepunch thread said that you can make the model match the scale of the bones by adding a -scale 174 parameter to the model when exporting in Noesis. Could you perhaps add that to the script so that is no longer necessary?
## Post #111
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-16T21:13:06+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated the script again to scale all axis by 174   
[viewtopic.php?p=123701#p123701](http://forum.xentax.com/viewtopic.php?p=123701#p123701)
give it a try
## Post #112
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-17T12:00:14+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> okay i updated the script again to scale all axis by 174   
viewtopic.php?p=123701#p123701
give it a try
thanks
## Post #113
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-20T23:41:35+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> Iv'e also made a script for dead space 2-3 long ago. Everything's working except the skinning. I never could figure it out but its better than starting from scratch.
Could you please fix how your script doesn't correctly produce working UVs for level meshes and LOD models?

So far I've required to rip anything related to those.
## Post #114
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-30T16:10:04+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hey AceWell, is it possible that you could modify your .geo script so that the files retain the names instead of using "mesh001"?

The thing is that most models have over 30 pieces and when I import them to 3D max, it asks me to rename every single piece one by one so I have to spam OK for 1 minute.

Another thing is that now the script makes it so that I have to flip the UVs twice of a model. Meaning I have to build the model from the pieces, then export it as FBX or OBJ in 3D Max, then export it in Noesis and flip the UVs and flip one more time the UVs of that exported model once again. Could you make it so that it automatically puts the UVs in their correct position when I activate batch export or export a singular model?
## Post #115
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-30T16:50:15+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

i updated the script here for the mesh naming thing  
[viewtopic.php?p=123701#p123701](http://forum.xentax.com/viewtopic.php?p=123701#p123701)
the mesh name is now the filename without extension 

i don't know why you flip the UVs so much but in the batch export
for the uv flipping you should be using this "Advanced Command" 
in the "Additional Parameters" box or just export as fbx instead
-flipuv



noesis_batch_export.PNG (11.71 KiB) Viewed 158 times
## Post #116
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-30T19:21:37+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> i updated the script here for the mesh naming thing  
viewtopic.php?p=123701#p123701
the mesh name is now the filename without extension 

i don't know why you flip the UVs so much but in the batch export
for the uv flipping you should be using this "Advanced Command" 
in the "Additional Parameters" box or just export as fbx instead
-flipuv
noesis_batch_export.PNG
Thanks for that.

And as for the flipping, after it is done exporting the files, when I open them on 3D Max and apply the textures, they are flipped. So, what I've done is that I've exported the whole model as FBX, then opened it on Noesis, exported that as OBJ and also flipped the UVs. However, the UVs are still flipped so I have to flip them one more time. Before I only had to flip them just once. Is there a way you could just make it so that it automatically puts the UVs in their correct positions?
## Post #117
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-30T19:36:41+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> And as for the flipping, after it is done exporting the files, when I open them on 3D Max and apply the textures, they are flipped. So, what I've done is that I've exported the whole model as FBX, then opened it on Noesis, exported that as OBJ and also flipped the UVs. However, the UVs are still flipped so I have to flip them one more time. Before I only had to flip them just once. Is there a way you could just make it so that it automatically puts the UVs in their correct positions?
again i don't understand why you are flipping the UVs so much, this makes no sense to me.   
it should be one and done. what do you mean by "Before I only had to flip them just once.",
before what? i have done nothing to the script that affects UV orientation at any point.
if you forgot to flip them during export in Noesis you could just flip them in 3dsmax, surely it
has tools to do that?
## Post #118
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-21T13:52:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:And as for the flipping, after it is done exporting the files, when I open them on 3D Max and apply the textures, they are flipped. So, what I've done is that I've exported the whole model as FBX, then opened it on Noesis, exported that as OBJ and also flipped the UVs. However, the UVs are still flipped so I have to flip them one more time. Before I only had to flip them just once. Is there a way you could just make it so that it automatically puts the UVs in their correct positions?
again i don't understand why you are flipping the UVs so much, this makes no sense to me.   
it should be one and done. what do you mean by "Before I only had to flip them just once.",
before what? i have done nothing to the script that affects UV orientation at any point.
if you forgot to flip them during export in Noesis you could just flip them in 3dsmax, surely it
has tools to do that?
This is a very late reply, but wanted to explain it anyways.

Yeah so basically, in order to fix the UVs being flipped, I have to use the flip function of Noesis two times.

Meaning when I first get a model, I assemble it on 3D Max. However, because the UVs are flipped, I have to open it on Noesis (once I have assembled the parts together into a one whole model on Max). In order to get them fixed, once I have the assembled model opened on Noesis, I have to use the flip UVs function and then export it. However, if I open that exported model on 3D Max, the UVs still aren't normal, so i have to open that exported model on Noesis again, where I used the "flip UVs" function and again flip the UVs with the function and that's when they finally work. So there's something wrong with your script. It would be easier if the UVs were built correctly during the initial .geo-to-whateverformat -conversion

Hope this cleared out what I was trying to say.
## Post #119
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-21T14:17:42+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> So there's something wrong with your script....
nothing wrong with the script, just your converting process!   
export from Noesis as fbx if you don't want to mess with flipping.
## Post #120
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-02-21T17:42:53+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from AceWell
>
> MaZTeR wrote:So there's something wrong with your script....
nothing wrong with the script, just your converting process!   
export from Noesis as fbx if you don't want to mess with flipping.
Ah okay, I'll try that next time I get more models.
## Post #121
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-01-18T16:50:46+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hey, someone managed to crack open the PS3 version of the first Dead Space and get access to the files. The person gave me the files of the Standard Astronaut RIG and I managed to convert the .str archive but by the looks of it, all the files inside it are using some PS3 format, so I can't convert them.

Here's everything related to that model:
[https://www.dropbox.com/s/k0e3wsxfjyxp7 ... n.zip?dl=0](https://www.dropbox.com/s/k0e3wsxfjyxp7h9/standard%20astronaut%20rig%20ds1%20ps3%20edition.zip?dl=0)
## Post #122
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-01-18T23:25:34+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from MaZTeR
>
> Hey, someone managed to crack open the PS3 version of the first Dead Space and get access to the files. The person gave me the files of the Standard Astronaut RIG and I managed to convert the .str archive but by the looks of it, all the files inside it are using some PS3 format, so I can't convert them.

Here's everything related to that model:
https://www.dropbox.com/s/k0e3wsxfjyxp7 ... n.zip?dl=0

I only had the DLC models to play with when I wrote this, so there may be some issues.
[deadspace console.zip](https://xentaxbackup.github.io/file/13814_deadspace console.zip)
## Post #123
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-01-19T07:10:51+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> MaZTeR wrote:Hey, someone managed to crack open the PS3 version of the first Dead Space and get access to the files. The person gave me the files of the Standard Astronaut RIG and I managed to convert the .str archive but by the looks of it, all the files inside it are using some PS3 format, so I can't convert them.

Here's everything related to that model:
https://www.dropbox.com/s/k0e3wsxfjyxp7 ... n.zip?dl=0

I only had the DLC models to play with when I wrote this, so there may be some issues.
Do those scripts work with all the DS1 models from PC or just the console version?

Also, I'm not sure if you were the one who made the scripts for DS2 and DS3 but could you perhaps fix the LOD models' UVs from breaking when they are imported to Max? I would greatly appreciate as well if you could fix the UVs of level geometry models from breaking as well. I ported Isaac's apartment last summer and it was a pain to rip everything from Dead Space 3. It would've made life a whole lot easier if I could've just got everything to 3D Max directly without having to sort out 3-5 different layers of clones of each mesh.

I can provide whatever samples you need if you can fix one or all of those issues listed above. There were few other models which have importing issues as well. Can't remember exactly all of them right now but I'll see if I can find some samples at some point.

Edit: Almost forgot there's still the textures which need to be converted.
## Post #124
- Username: Sinnery32
- Rank: n00b
- Number of posts: 13
- Joined date: Thu Jan 05, 2017 3:24 pm
- Post datetime: 2018-01-19T10:59:43+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Thank you.
It helped)
[Screenshot_2.png](https://xentaxbackup.github.io/file/13816_Screenshot_2.png)
## Post #125
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-01-21T02:19:52+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

The script only works for the console version, I didn't see the point of making a pc version since AceWell had already done that. Yeah I'm the one who originlly posted the deadspace 2-3 scripts. I've recently been working on an update to it but I'm still figuring out the issue of the uv's being broken sometimes. The script guesses the offset of the mesh's uv's instead of going by an explicitly given one. I modified AceWell's script to work with console tg4h files but I can't release it without his permission first.

EDIT: I added the updated script. It doesn't like xbox 360 tg4h files for some reason, they appear broken but it works fine for the ps3 equivalent.
[tex_DeadSpace123_tg4h.zip](https://xentaxbackup.github.io/file/13833_tex_DeadSpace123_tg4h.zip)
## Post #126
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-21T02:44:02+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> I modified AceWell's script to work with console tg4h files but I can't release it without his permission first.
you don't need permission, do what you like, i don't own any of this stuff, not the alphanumeric system, not python, not Noesis, not tg4h/tg4d format etc.
## Post #127
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-01-21T12:32:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> The script only works for the console version, I didn't see the point of making a pc version since AceWell had already done that. Yeah I'm the one who originlly posted the deadspace 2-3 scripts. I've recently been working on an update to it but I'm still figuring out the issue of the uv's being broken sometimes. The script guesses the offset of the mesh's uv's instead of going by an explicitly given one. I modified AceWell's script to work with console tg4h files but I can't release it without his permission first.
Yeah I figured that out myself. Too bad. Well, at least there's one for the first game even though it works only with Noesis.

And for the other scripts, glad to hear you are still working on them.
## Post #128
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-01-23T13:31:00+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from killercracker
>
> The script only works for the console version, I didn't see the point of making a pc version since AceWell had already done that. Yeah I'm the one who originlly posted the deadspace 2-3 scripts. I've recently been working on an update to it but I'm still figuring out the issue of the uv's being broken sometimes. The script guesses the offset of the mesh's uv's instead of going by an explicitly given one. I modified AceWell's script to work with console tg4h files but I can't release it without his permission first.

EDIT: I added the updated script. It doesn't like xbox 360 tg4h files for some reason, they appear broken but it works fine for the ps3 equivalent.
Thanks for the script
## Post #129
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2018-04-26T03:24:18+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hi, im currently trying to rip some textures from ds1 (More specifically, console DLC pack suits, like scorpion and elite suits) with the noesis tool, but when I try to open in noesis I get these errors: 



Im assuming it's not working because I did some "hacky" thing by unpacking it with the ds2 visceral viewer, but it was the only way I was able to do it. I found no other way to unpack ds1 .str files.

Any help would be greatly appreciated.
## Post #130
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-26T06:36:22+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

which console platform samples are you trying to open, Xbox 360 or PS3?
killercracker's modified script for PS3 is here 
[viewtopic.php?p=137282#p137282](http://forum.xentax.com/viewtopic.php?p=137282#p137282)
do you have the tg4h and tg4d files in the same folder?
if you need it updated for X360 samples i might can do it,
post some tg4h/tg4d sample pairs for examination please
## Post #131
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2018-04-26T12:29:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hi, thanks for the reply. I am currently using X360 for this.
I uploaded the scorpion armor tg4h/tg4d files to check for you here: [https://www.dropbox.com/s/fc0zg3ep5rg1y ... ed.7z?dl=0](https://www.dropbox.com/s/fc0zg3ep5rg1yso/uniScorpion_unpacked.7z?dl=0)
if you are able to update for X360 that would be great. Thanks.

Edit: Out of curiosity I tried using the script above, it lets me preview/export the files but it's corrupted:


Edit 2: After some more searching, I found a ps3 version of the pack and managed to successfully open and rip the textures, but thank you for the help with finding the script to open ps3 pack.
If anyone needs help figuring out how I did it, feel free to ask! I know how much work it is to find out how it works, so I will try to help where I can too.
## Post #132
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-04-26T23:04:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

can you upload some PS3 tg4h/tg4d sample pairs too?  
i think i see the real platform id in the tg4h files and i want to try update my original script to support all 3 platforms. 

edit
i found some PS3 samples in this post 
[viewtopic.php?p=137218#p137218](http://forum.xentax.com/viewtopic.php?p=137218#p137218)
## Post #133
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2018-05-07T20:44:08+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Ok so it seems I might need a fixed Xbox360 version of the script after all. If you are able to.
I need to open the textures in this folder but they are all corrupted in the noesis viewer like before. 


Here is file downloads: [https://www.dropbox.com/s/arh1w9v7yaicl ... ed.7z?dl=0](https://www.dropbox.com/s/arh1w9v7yaicl9p/uniMicrosoft_unpacked.7z?dl=0)
Includes texture files +  packed .str file and all that.
## Post #134
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-08T00:34:56+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

okay i updated my original script here to support all 3 platforms   
[viewtopic.php?p=122302#p122302](http://forum.xentax.com/viewtopic.php?p=122302#p122302)
## Post #135
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2018-05-08T08:24:27+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Thank you!
## Post #136
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-06-05T17:20:00+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Would it be possible if the ds2-3 batch mesh script could import LODs as well? At the moment, I have to individually extract for example a single dismembered mesh, export  that to something and then do the same thing with 10 or 15 others.
## Post #137
- Username: Alexstr525
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 7:06 am
- Post datetime: 2018-09-21T10:39:41+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Howdy howdy, don't mean to bump this thread again seeing as it's pretty dead in space. Was wondering if anything related to animation research has been cracked? If anything the hkx.win seriously stumps me, if the files were to go to HKX i could use the same method i used to grab the Dark Souls 3 animations as well as the method for Dark Souls 1 animations. Considering they'd be in 32bit i don't think getting them with root motion would be too hard, especially since we have tools to convert 32bit hkx files. Would love to know if anyone has any answers or input to the animations so far?
## Post #138
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2018-09-21T10:48:22+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from Alexstr525
>
> Howdy howdy, don't mean to bump this thread again seeing as it's pretty dead in space. Was wondering if anything related to animation research has been cracked? If anything the hkx.win seriously stumps me, if the files were to go to HKX i could use the same method i used to grab the Dark Souls 3 animations as well as the method for Dark Souls 1 animations. Considering they'd be in 32bit i don't think getting them with root motion would be too hard, especially since we have tools to convert 32bit hkx files. Would love to know if anyone has any answers or input to the animations so far?
Nope, no progress has been made, at least no one has given updates on that publicly. As for the animations, the HKX apparently only contain collision models and stuff like that, the bnk files are the actual animations.

I don't think anyone's going to willingly do this for free, which is a shame since the games are pretty old and at this point, a lot of similarly old games have already been cracked open fully.
## Post #139
- Username: lAin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 10, 2009 1:48 am
- Post datetime: 2019-01-29T09:25:16+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Is there a quick way to make the extracted texture compressed back to this TG4 header-less format (TG4D and TG4H) once exported with Noesis?
## Post #140
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2019-02-04T00:24:55+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Guys im trying to open the big files that i think are whole rooms from Dead Space 1.Im using scripts for noesis that i got from here and they work for most small models but not for the big ones.My link below contain 1 of thouse big geo files as an example and the 2 noesis scripts.I dont know which one is the important one but if someone update them to be able to open the big file please send me update noesis scripts.Thanks in advace! 

[https://mega.nz/#!IoVxkKDK!RrMin3C1NCDL ... S8YYof5Z6Q](https://mega.nz/#!IoVxkKDK!RrMin3C1NCDLJWBX6WqPftWc9Ol7gf4QoS8YYof5Z6Q)
## Post #141
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-04T13:23:57+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from ginev
>
> but if someone update them to be able to open the big file please send me update noesis scripts.Thanks in advace!
As the name tells this one is for the geometry: fmt_DeadSpace1_geo.py
I don't have the time to update the script, used a fixed value for the face indices count (FCount = 126841).

You'll need to fiddle around with the code so that the offsets and counts are correctly read from the "magic table" (at 0x19680 here).
(Dunno "what is what", guess vertex count is at 0x19684 and the value at 0x19694 is uvs count.
After the counts the sizes follow, dec. 12 (v) and 28 (uv) which makes sense.)



0503_opt_model1-geo.jpg (165.07 KiB) Viewed 291 times



edit: FI count is dec. 102874, so the value at offset 0x196E4
You need to loop through the 3 submeshes, that's what the original script doesn't handle.
## Post #142
- Username: ginev
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Feb 15, 2016 6:53 pm
- Post datetime: 2019-02-04T13:54:06+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from shakotay2
>
> ginev wrote:but if someone update them to be able to open the big file please send me update noesis scripts.Thanks in advace! 
As the name tells this one is for the geometry: fmt_DeadSpace1_geo.py
I don't have the time to update the script, used a fixed value for the face indices count (FCount = 126841).

You'll need to fiddle around with the code so that the offsets and counts are correctly read from the "magic table" (at 0x19680 here).
(Dunno "what is what", guess vertex count is at 0x19684 and the value at 0x19694 is uvs count.
After the counts the sizes follow, dec. 12 (v) and 28 (uv) which makes sense.)
0503_opt_model1-geo.jpg

edit: FI count is dec. 102874, so the value at offset 0x196E4
You need to loop through the 3 submeshes, that's what the original script doesn't handle.

Please forgive me for my lack of knowledge in this things.Maybe when you have time you can update the scripts?I can wait long time its not a problem.It seems no one else will help me so i can wait.
## Post #143
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-04T15:19:34+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from ginev
>
> Please forgive me for my lack of knowledge in this things.Knowledge can be gained; for understanding simple Noesis scripts start reading here from "codelines":
[viewtopic.php?f=16&t=18869&p=144765&hil ... es#p144765](http://forum.xentax.com/viewtopic.php?f=16&t=18869&p=144765&hilit=+codelines#p144765)

There's a tutorial thread here:
[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
## Post #144
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2019-10-22T02:57:45+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Hello, im not sure if this really falls under this thread properly, but I hope it's ok I ask, since it's related to ripping, and dead space.

I have been working on trying to rip models from Dead Space Mobile, I tried using NinjaRipper and Nox, which did not present very good results, or sometimes none at all. 

What I been trying to look for/do now, is open the files directly, the files are .m3g, and I can't find any way to convert them to a usable model, like obj or fbx. 

I did find a .m3g viewer, but it did not like the file type, And I can't find any other scripts to open/import it with blender, or other modeling programs.
There was also this program, but it only works with specific games (m3g2fbx) [viewtopic.php?t=11095](https://forum.xentax.com/viewtopic.php?t=11095)

Would anyone happen to know, or be able to take a look into how I could convert these? Much thanks in advance!

Here is three samples to take a look at [https://www.dropbox.com/sh/d84lxvfu94zk ... S6H0a?dl=0](https://www.dropbox.com/sh/d84lxvfu94zkmyv/AABlojT07HYKUnwEoCetS6H0a?dl=0)




As an update, these are the results I get, running Nox with Ninjaripper in DX mode, not very good.  UV's are messed up.
## Post #145
- Username: TyapLyap
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 01, 2019 4:37 am
- Post datetime: 2019-12-02T12:21:15+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Anyone have script deadspace import/export.ms for 3ds max,one time i see in facepunch forum,this script posted ¨Jacob Danik¨,but i cant open this forum because has been closed by Garry.
Format models .geo
## Post #146
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-02T13:30:51+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

> Reply from Ethosaur ↑Tue Oct 22, 2019 10:57 am at Tue Oct 22, 2019 10:57 am
>
> Would anyone happen to know, or be able to take a look into how I could convert these? Much thanks in advance!Seems there's no way around to do it the hard way (much fiddeling around included  ):
.



isaac-m3g-pointcloud.png (124.82 KiB) Viewed 173 times

(couldn't get the idea behind the structuring - one vertex start address for all sub/lod meshes?)

@Ethosaur: well, seems you tagged this thread, did you?
## Post #147
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-03T10:19:45+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

well, I was 2 bytes off with the vertex start:
.



better.png (141.95 KiB) Viewed 166 times
## Post #148
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2019-12-03T14:22:12+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

How hard is it to get it, with intact UV map? Thanks again for looking into it.
## Post #149
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-03T15:33:22+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Once you know how it works (more or less) it's no so hard - but I didn't get the uv map so far. 4 MB are rather big to scan and I'm too busy with my own projects so may take a while. (Maybe you can provide a smaller .m3g sample?)
.



Isaac_armor.png (60.47 KiB) Viewed 158 times
## Post #150
- Username: Ethosaur
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Apr 26, 2018 10:41 am
- Post datetime: 2019-12-21T21:17:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textur

Apologies for such a late reply, I appreciate you taking your time to look into it!

Here are some more samples I could find. I have all the textures for these models, if I could somehow get a model with working UV's, I would be all set.

[https://www.dropbox.com/sh/dnup51ihul8m ... tS_ha?dl=0](https://www.dropbox.com/sh/dnup51ihul8m53g/AAABUJW-erb86FTLO3ZztS_ha?dl=0)

Thanks again.
## Post #151
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-13T23:36:29+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Hello guys, the files before facepuch was down to extract dead space files from 1-3 I have those saved, so I will upload them so it can help you guys.

Notes:

Dead space 1 (you can extract everything from the characters and textures(PC-PS3-XBOX) DLC textures too, animations( I never try them), just scenery can not be extracted from the game with these files)

Dead space 2-3 (extract everything from the games without problem) DLC too. 

Maybe I can do it tonight, but surely tomorrow you gonna get the files.

I am really interested in the dead space mobile 3d files, what you need to learn to create a scripts that can extract game models from PC or consoles? (I don't know where to start learning).
## Post #152
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-14T14:54:59+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

as promised, the files are in the link below:

[https://drive.google.com/open?id=1wWuTd ... cAWiS1a_LU](https://drive.google.com/open?id=1wWuTd_Qqw8mh7ZKR1B69AecAWiS1a_LU)

it comes with the manual in microsoft word document, i was checking if it actually extract animations(attacks, movement) but i can't really tell, but DMG animations are actually there.
[Imagen2.png](https://xentaxbackup.github.io/file/17711_Imagen2.png)
## Post #153
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-03-15T21:36:38+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from satademon7 ↑Sat Mar 14, 2020 7:36 am at Sat Mar 14, 2020 7:36 am
>
> 
Hello guys, the files before facepuch was down to extract dead space files from 1-3 I have those saved, so I will upload them so it can help you guys.

Notes:

Dead space 1 (you can extract everything from the characters and textures(PC-PS3-XBOX) DLC textures too, animations( I never try them), just scenery can not be extracted from the game with these files)

Dead space 2-3 (extract everything from the games without problem) DLC too. 

Maybe I can do it tonight, but surely tomorrow you gonna get the files.

I am really interested in the dead space mobile 3d files, what you need to learn to create a scripts that can extract game models from PC or consoles? (I don't know where to start learning).

Do you happen to have the extracted DLC suits and skins for DS1? Would love to have access to them.
## Post #154
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-16T19:19:05+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

For the moment I don't have them, but maybe this week can I get the DLC from Xbox and PS3:

Astronaut DLC(game model, weapons skins)
Obsidian DLC for PS3(game model, weapons skins)
Scorpion DLC(game model, weapons skins)
Tank DLC for Xbox(game model, weapons skins)
Military DLC(weapons skins)

You can find here the Astro Suit, If you have 3ds max you can already start with that model, if not, don't worry maybe by the end of the week I will upload the models and weapons models and skins.

Just wondering, have somebody been able to extract scenery from Dead Space 1?
## Post #155
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-03-17T18:54:37+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from satademon7 ↑Tue Mar 17, 2020 3:19 am at Tue Mar 17, 2020 3:19 am
>
> 
For the moment I don't have them, but maybe this week can I get the DLC from Xbox and PS3:

Astronaut DLC(game model, weapons skins)
Obsidian DLC for PS3(game model, weapons skins)
Scorpion DLC(game model, weapons skins)
Tank DLC for Xbox(game model, weapons skins)
Military DLC(weapons skins)

You can find here the Astro Suit, If you have 3ds max you can already start with that model, if not, don't worry maybe by the end of the week I will upload the models and weapons models and skins.

Just wondering, have somebody been able to extract scenery from Dead Space 1?

Yeah, I require the astro suit model and the textures for every other dlc thingie. I looked in the thread but I did not find the link for the astro suit model.

I am also interested in the DS1 levels, but unfortunately I am still trying to get the tool to work. Update me if you find anything.
## Post #156
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-19T15:19:24+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from Portugalotaku ↑Wed Mar 18, 2020 2:54 am at Wed Mar 18, 2020 2:54 am
>
> 
satademon7 wrote: ↑Tue Mar 17, 2020 3:19 am
For the moment I don't have them, but maybe this week can I get the DLC from Xbox and PS3:

Astronaut DLC(game model, weapons skins)
Obsidian DLC for PS3(game model, weapons skins)
Scorpion DLC(game model, weapons skins)
Tank DLC for Xbox(game model, weapons skins)
Military DLC(weapons skins)

You can find here the Astro Suit, If you have 3ds max you can already start with that model, if not, don't worry maybe by the end of the week I will upload the models and weapons models and skins.

Just wondering, have somebody been able to extract scenery from Dead Space 1?


Yeah, I require the astro suit model and the textures for every other dlc thingie. I looked in the thread but I did not find the link for the astro suit model.

I am also interested in the DS1 levels, but unfortunately I am still trying to get the tool to work. Update me if you find anything.

I been trying with the levels, rigth now what's working is ninja ripper and dx ripper(only extract fractions of the map) 

Astronaut suit(done)
Tank suit(done)
Obsidian suit(done)
Scorpion suit(done)
Weapons(still pending)
[IMG_20200319_091708.png](https://xentaxbackup.github.io/file/17741_IMG_20200319_091708.png)
## Post #157
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-03-20T20:51:37+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from satademon7 ↑Thu Mar 19, 2020 11:19 pm at Thu Mar 19, 2020 11:19 pm
>
> 
Portugalotaku wrote: ↑Wed Mar 18, 2020 2:54 am
satademon7 wrote: ↑Tue Mar 17, 2020 3:19 am
For the moment I don't have them, but maybe this week can I get the DLC from Xbox and PS3:

Astronaut DLC(game model, weapons skins)
Obsidian DLC for PS3(game model, weapons skins)
Scorpion DLC(game model, weapons skins)
Tank DLC for Xbox(game model, weapons skins)
Military DLC(weapons skins)

You can find here the Astro Suit, If you have 3ds max you can already start with that model, if not, don't worry maybe by the end of the week I will upload the models and weapons models and skins.

Just wondering, have somebody been able to extract scenery from Dead Space 1?


Yeah, I require the astro suit model and the textures for every other dlc thingie. I looked in the thread but I did not find the link for the astro suit model.

I am also interested in the DS1 levels, but unfortunately I am still trying to get the tool to work. Update me if you find anything.


I been trying with the levels, rigth now what's working is ninja ripper and dx ripper(only extract fractions of the map) 

Astronaut suit(done)
Tank suit(done)
Obsidian suit(done)
Scorpion suit(done)
Weapons(still pending)

Great work, but what about the elite suit?
## Post #158
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-22T23:55:27+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from Portugalotaku ↑Sat Mar 21, 2020 4:51 am at Sat Mar 21, 2020 4:51 am
>
> 
satademon7 wrote: ↑Thu Mar 19, 2020 11:19 pm
Portugalotaku wrote: ↑Wed Mar 18, 2020 2:54 am


Yeah, I require the astro suit model and the textures for every other dlc thingie. I looked in the thread but I did not find the link for the astro suit model.

I am also interested in the DS1 levels, but unfortunately I am still trying to get the tool to work. Update me if you find anything.


I been trying with the levels, rigth now what's working is ninja ripper and dx ripper(only extract fractions of the map) 

Astronaut suit(done)
Tank suit(done)
Obsidian suit(done)
Scorpion suit(done)
Weapons(still pending)


Great work, but what about the elite suit?

i was looking for the Elite DLC(xbox), still haven't found anything yet, if someone could have it and send it would be great, right now just waiting to finish uploading to share the link, the DLC's included are:

Astronaut DLC(suit and weapons)
Tank DLC(suit and weapons)
Obsidian DLC(suit and weapons)
Scorpion DLC(suit and weapons)
Big Gun DLC(weapons)
Heavy DMG DLC(weapons)
Hotrod DLC(weapons)
Marine DLC(weapons)
Pedestrian DLC(weapons)
Speed Kills DLC(weapons)

the only one missing right now is the Elite DLC(still pending) it would be great if anyone could help finding that dlc its the last one.
## Post #159
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-23T04:18:33+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

here are the files:

[https://drive.google.com/open?id=1ithVn ... IJ3nEWb3wt](https://drive.google.com/open?id=1ithVnx9Nox4G0btCaC0tf9IJ3nEWb3wt)
## Post #160
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-03-23T04:24:33+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

here are the files:

[https://drive.google.com/open?id=1ithVn ... IJ3nEWb3wt](https://drive.google.com/open?id=1ithVnx9Nox4G0btCaC0tf9IJ3nEWb3wt)
## Post #161
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-03-26T12:00:54+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from satademon7 ↑Mon Mar 23, 2020 12:24 pm at Mon Mar 23, 2020 12:24 pm
>
> 
here are the files:

https://drive.google.com/open?id=1ithVn ... IJ3nEWb3wt

Thanks a lot friend.

Though the models you sent are in obj. You couldn't find the astro suit skeleton and rig?
## Post #162
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2020-04-09T00:56:58+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from satademon7 ↑Mon Mar 23, 2020 12:24 pm at Mon Mar 23, 2020 12:24 pm
>
> 
here are the files:

https://drive.google.com/open?id=1ithVn ... IJ3nEWb3wt

It seems like that, apart from the skeletons missing, several textures are missing as well. Each model should have a _c, _s, _n and _o texture, but in the ones you sent me, only _c is available in most cases.
## Post #163
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-04-17T02:30:26+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Oh yeah, I have those too, I can upload them, the bones are in .geo ps3 format, tomorrow I will be uploading them.
## Post #164
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-04-17T22:46:18+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

here is the link where you can download all de DLC's from dead space 1-3:

[https://psndl.net/packages/250?orderBy= ... xt_search=](https://psndl.net/packages/250?orderBy=name&order=desc&txt_search=)#

and here is the .pkg unpacker(the format from the file):

[https://sites.google.com/site/theleeche ... -extractor](https://sites.google.com/site/theleecherman/psnpkgdecryptor-extractor)

download the last one from the bottom of the page, sorry, i couldn't upload them, but today the internet isn't working at its fullest, this is all you need  for the dead space games dlc's,plus Rickviceral files to convert the models.
## Post #165
- Username: kuiks
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Oct 13, 2014 2:31 am
- Post datetime: 2020-05-14T20:14:45+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Hello please dead space 3 awakened str repack
## Post #166
- Username: kodikat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 03, 2016 12:22 am
- Post datetime: 2020-09-28T07:47:49+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Using Noesis v4.433. The majority of the models are fine but some models just look wrong, like the triangles were built incorrectly.



DS1_badTris.png (227.14 KiB) Viewed 426 times



And on some other models, Noesis gives me a python error:
Traceback (most recent call last):
  File "F:\Noesis\plugins\python\fmt_DeadSpace1_geo.py", line 82, in noepyLoadModel
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
RuntimeError: Position buffer would have been read out of bounds by provided indices.

Has anyone else encountered this?  Did you have a fix or workaround?
## Post #167
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-06-06T22:07:08+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from kodikat ↑Mon Sep 28, 2020 3:47 pm at Mon Sep 28, 2020 3:47 pm
>
> 
Using Noesis v4.433. The majority of the models are fine but some models just look wrong, like the triangles were built incorrectly.
DS1_badTris.png

And on some other models, Noesis gives me a python error:
Traceback (most recent call last):
  File "F:\Noesis\plugins\python\fmt_DeadSpace1_geo.py", line 82, in noepyLoadModel
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
RuntimeError: Position buffer would have been read out of bounds by provided indices.

Has anyone else encountered this?  Did you have a fix or workaround?

id-daemon was unable to make the Noesis script work with the level assets, so they appear as random triangles like that. Too bad, I would really like if someone could make a proper script for everything from the three main games.
## Post #168
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-06T22:53:24+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from kodikat ↑Mon Sep 28, 2020 3:47 pm at Mon Sep 28, 2020 3:47 pm
>
> 
Using Noesis v4.433. The majority of the models are fine but some models just look wrong, like the triangles were built incorrectly.
DS1_badTris.png

And on some other models, Noesis gives me a python error:
Traceback (most recent call last):
  File "F:\Noesis\plugins\python\fmt_DeadSpace1_geo.py", line 82, in noepyLoadModel
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
RuntimeError: Position buffer would have been read out of bounds by provided indices.

Has anyone else encountered this?  Did you have a fix or workaround?Without the sample in question nothing will happen, I guess...  

Also, which fmt_DeadSpace1_geo.py did you use? Is it the original from here (click up arrow to view):

> Reply from Acewell ↑Sat Oct 22, 2016 8:38 am at Sat Oct 22, 2016 8:38 am
>
> 
---------------------------------------
.

> Reply from MaZTeR ↑Mon Jun 07, 2021 6:07 am at Mon Jun 07, 2021 6:07 am
>
> Too bad, I would really like if someone could make a proper script for everything from the three main games.You're dreaming of this since 5 years, don't you?
## Post #169
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-06-07T14:45:58+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from shakotay2 ↑Mon Jun 07, 2021 6:53 am at Mon Jun 07, 2021 6:53 am
>
> 
kodikat wrote: ↑Mon Sep 28, 2020 3:47 pm
Using Noesis v4.433. The majority of the models are fine but some models just look wrong, like the triangles were built incorrectly.
DS1_badTris.png

And on some other models, Noesis gives me a python error:
Traceback (most recent call last):
  File "F:\Noesis\plugins\python\fmt_DeadSpace1_geo.py", line 82, in noepyLoadModel
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_SHORT, FCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
RuntimeError: Position buffer would have been read out of bounds by provided indices.

Has anyone else encountered this?  Did you have a fix or workaround?
Without the sample in question nothing will happen, I guess...  

Also, which fmt_DeadSpace1_geo.py did you use? Is it the original from here (click up arrow to view):
Acewell wrote: ↑Sat Oct 22, 2016 8:38 am
---------------------------------------
.
MaZTeR wrote: ↑Mon Jun 07, 2021 6:07 amToo bad, I would really like if someone could make a proper script for everything from the three main games.You're dreaming of this since 5 years, don't you?
Hold on, I'll post level geometry related samples from each three games.
## Post #170
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-06-07T15:03:50+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Alright, here, samples from all three games.

The atrium from the bridge level in Dead Space, the flight lounge and I believe the Ishimura model you see outside in Dead Space 2 and Isaac's apartment from Dead Space 3 which I have actually ripped in its entirety from the game a few years ago and ported to Source Filmmaker:
[https://www.mediafire.com/file/d3vrme56 ... 1.zip/file](https://www.mediafire.com/file/d3vrme56q25ahe5/deadspacesamples_7.6.21.zip/file)

There's also a script for DS2-3 which does infact extract level geometry from those two games, but the UVs are completely messed up. It can extract npcs, weapons and level related entities like say the Store or Bench somewhat fine. But it breaks the normals and flips the models 180 degrees backwards, I've been using it to port quite a lot of models in the past to SFM, along with a script which also extracted the skeletons but not weights.

There also is a script for getting at least some skeletons with weights from 2 and 3, but a lot of models I think do not work and you are required to extract each mesh one by one, meanwhile the models in the game consist of at worst dozens of parts. Good luck doing that.
## Post #171
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-07T19:40:18+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from MaZTeR ↑Mon Jun 07, 2021 11:03 pm at Mon Jun 07, 2021 11:03 pm
>
> 
Alright, here, samples from all three games.well, thanks. But you wouldn't expect me to care for all those samples of all three games?  

What I ask for was a DeadSpace 1 sample which caused the script to display a weird mesh.

And what do I have to say? The underlying problem can be tracked down very quickly with a basic understanding of (Noesis) python scripting:
for 0460_lodmodel03.geo it's just that the script's tristrips check fails.

So simply replace
    checkTri = int(FCount % 3)                            #check if FCount is evenly divisible by 3,
by
    checkTri = 1# forcing triangle strips to be used.

See image for result:
.



460_lodmodel3.png (138.98 KiB) Viewed 321 times



Yeah, I know, you want to have it corrected automatically.
No time to search for a flag, or something like that.
## Post #172
- Username: SUNN
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 05, 2022 1:19 am
- Post datetime: 2022-10-18T21:02:36+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Please, anyone know how to convert an exported file back to .t4gd?
## Post #173
- Username: Alexstr525
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 7:06 am
- Post datetime: 2023-01-30T03:49:20+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Not sure how dead the thread is, but after managing to get the havok files; they don't seem to be in a "readable" format, the error it spits on loading them via the content tools (preview tool) is this:


This was done via, shakotay2's suggestion from earlier in the thread:

> For Death Space 2 animations are hkx (hkx.win). There's a lot of posts concerning hkx in this forum. Read them, please.
>
> 
>
> Best results so far I got using the Havok Standalone tool. Rename hkx.win to hkx to test it.

Below are some sample files from the brute itself; if they can be properly formatted, maybe they'd be possible to load. I've been speaking with [PredatorCZ](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=45121) about this as well.

EDIT* I'd like to clarify this is from Dead Space 2, I'm not sure if Dead Space 3 or Dead Space one follow suit--as far as the animation files are concerned. Can anyone take a look at these and hopefully provide some good news on the subject?

EDIT** To further clarify, I've ran this by [PredatorCZ](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=45121) and will be in contact with him tomorrow morning 1/30/23 to further discuss the animation format if it's at all possible to really get them working. I'll provide any further details on this hopefully soon.
[HKX.zip](https://xentaxbackup.github.io/file/23360_HKX.zip)
## Post #174
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-01-30T06:03:09+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

havok in dead space is only used for physics. The animation should be included in bnk.win.

I think dead space is a popular title, but it is very unfortunate that the format has hardly been reverse engineered, including mods.

Considering the fact that even in this remake, similar motions were created from scratch without using past formats, I can assume that the format is relatively difficult to reverse.
Of course, it is possible that past assets were not useful to accommodate more advanced graphics. Frankly, in parts, the 2008 version has better animations, so it would be interesting to be able to swap when the remake animation mod becomes available. That's just idealistic though.
## Post #175
- Username: Alexstr525
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 22, 2016 7:06 am
- Post datetime: 2023-01-30T06:52:53+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from einherjar007 ↑Mon Jan 30, 2023 2:03 pm at Mon Jan 30, 2023 2:03 pm
>
> 
havok in dead space is only used for physics. The animation should be included in bnk.win.

I think dead space is a popular title, but it is very unfortunate that the format has hardly been reverse engineered, including mods.

Yeah I had noticed the bnk file list as well, I've already forwarded that to PredatorCZ too. I figured the Havok data was mostly reliant on physics based stuff rather than animation. I've included samples here if someone wants to take a look?

[Brute BNK file list](https://drive.google.com/file/d/1BU2ciKd3vAQjl7dsSMWRRkPfMqezNfbi/view?usp=sharing) googledrive link

EDIT* Included the RCB file that stores the bone/skeletal data
[0137_brute.rcb.rar](https://xentaxbackup.github.io/file/23361_0137_brute.rcb.rar)
## Post #176
- Username: MeltyPlayer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 16, 2021 12:38 pm
- Post datetime: 2023-04-21T02:42:12+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Hello! I've actually been working on trying to figure out these formats, too, as part of my generalized model/rig/animation-ripping tool: [https://github.com/MeltyPlayer/FinModelUtility](https://github.com/MeltyPlayer/FinModelUtility)

Here's a photo of a model within my viewer:



Capture.PNG (197.6 KiB) Viewed 114 times



I've made some progress on Dead Space 1 in terms of models/skeletons, and minor progress in terms of textures/materials, but I'm still incredibly lost on how this animation format works. I'll summarize what I've figured out so far below:

Here's the start of a sample animation:

```
01 00 00 00 05 4C 3D 2B BD 00 00 00 00 00 00 00
01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00
DC 0B DC 0B DC 0B DD 0B DC 0B DC 0B DC 0B 25 00
47 0A E6 88 3E BF 8F 36 C3 D1 04 D5 9F DA 8A E1
CF E8 A6 EF 79 F5 DF F9 86 FC 13 FD 93 FB 59 F8
45 F3 44 EC 70 E3 23 D9 FE CD E2 C2 DD B8 0A B1
35 AB 64 A6 6A A2 14 9F 39 9C BD 99 95 97 C3 95
50 94 4A 93 DA 92 16 93 E9 93 8B 95 64 97 8F 99
F5 9B 7F 9E 1B A1 B3 A3 95 A6 07 AA F1 AD 38 B2
BF B6 63 BB FF BF 65 C4 65 C8 C7 CB A7 CF D9 D4
B5 DA 8C E0 A9 E5 58 E9 DF EA 87 E9 98 E4 5B DB
6E CB 74 B4 F7 98 8E 7B 82 5E 94 43 14 2C 0D 19
6F 0B 27 04 43 01 00 00 33 00 B8 01 6C 04 2D 08
D9 0C 4D 12 67 18 FF 1E EC 25 02 2D 12 34 E8 3A
4E 41 0B 47 E4 4B 9C 4F F7 51 FD 50 DC 4B 1E 44
48 3B BF 32 C8 2B 91 27 46 27 33 2A B4 2E 96 34
...

```


The top three lines make up a header (though there's also a separate header that defines this animation above):

```
01 00 00 00 05 4C 3D 2B BD 00 00 00 00 00 00 00
01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00

```


And then the part below encodes the animation:

```
47 0A E6 88 3E BF 8F 36 C3 D1 04 D5 9F DA 8A E1
CF E8 A6 EF 79 F5 DF F9 86 FC 13 FD 93 FB 59 F8
45 F3 44 EC 70 E3 23 D9 FE CD E2 C2 DD B8 0A B1
35 AB 64 A6 6A A2 14 9F 39 9C BD 99 95 97 C3 95
50 94 4A 93 DA 92 16 93 E9 93 8B 95 64 97 8F 99
F5 9B 7F 9E 1B A1 B3 A3 95 A6 07 AA F1 AD 38 B2
BF B6 63 BB FF BF 65 C4 65 C8 C7 CB A7 CF D9 D4
B5 DA 8C E0 A9 E5 58 E9 DF EA 87 E9 98 E4 5B DB
6E CB 74 B4 F7 98 8E 7B 82 5E 94 43 14 2C 0D 19
6F 0B 27 04 43 01 00 00 33 00 B8 01 6C 04 2D 08
D9 0C 4D 12 67 18 FF 1E EC 25 02 2D 12 34 E8 3A
4E 41 0B 47 E4 4B 9C 4F F7 51 FD 50 DC 4B 1E 44
48 3B BF 32 C8 2B 91 27 46 27 33 2A B4 2E 96 34
...

```


At first this just looks like a random sequence, but notice how "DC 0B" repeats multiple times? If you look above in the header, you'll see the sequence "05 4C 3D 2B BD 00 00 00". The "BD" in that sequence impacts those repeated "DC 0B" blocks--those seem to actually be shorts set to "0BDC". Based on what I've seen across multiple animation files, the last nibble (in this case, "C") appears to be some kind of enum or opcode. I've been suspecting these are essentially "commands" in the animation format. I haven't noticed any consistent patterns for these other than for commands with the value "0" (e.g. "D0 0B"/"0BD0"), which is consistently followed by three float values (possibly encoding a position or rotation?). At the end of commands, it seems to either go into a new "DX 0B" command or what I've been referring to as "subcommands", which encode additional information and follow a separate format. I haven't really found any useful patterns here yet, but I've noticed some subcommands use a series of bytes that smoothly transition in value, and some subcommands follow the sequence byte/float/byte/float/etc.

I think I've exhausted the "breakthroughs" I can have by simply staring at this data and brute forcing things, haha, so I'm interested to hear if any of you have found anything new? If not, I think the only other way to make forward progress will be to try decompiling the animation logic via Ghidra.
## Post #177
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2023-04-21T14:47:09+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

> Reply from MeltyPlayer ↑Fri Apr 21, 2023 10:42 am at Fri Apr 21, 2023 10:42 am
>
> 
Hello! I've actually been working on trying to figure out these formats, too, as part of my generalized model/rig/animation-ripping tool: https://github.com/MeltyPlayer/FinModelUtility

Here's a photo of a model within my viewer:
Capture.PNG

I've made some progress on Dead Space 1 in terms of models/skeletons, and minor progress in terms of textures/materials, but I'm still incredibly lost on how this animation format works. I'll summarize what I've figured out so far below:

Here's the start of a sample animation:
Code: Select all3F CC 08 49 00 00 00 09 01 00 00 00 3F 7E 00 00
01 00 00 00 05 4C 3D 2B BD 00 00 00 00 00 00 00
01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00
DC 0B DC 0B DC 0B DD 0B DC 0B DC 0B DC 0B 25 00
47 0A E6 88 3E BF 8F 36 C3 D1 04 D5 9F DA 8A E1
CF E8 A6 EF 79 F5 DF F9 86 FC 13 FD 93 FB 59 F8
45 F3 44 EC 70 E3 23 D9 FE CD E2 C2 DD B8 0A B1
35 AB 64 A6 6A A2 14 9F 39 9C BD 99 95 97 C3 95
50 94 4A 93 DA 92 16 93 E9 93 8B 95 64 97 8F 99
F5 9B 7F 9E 1B A1 B3 A3 95 A6 07 AA F1 AD 38 B2
BF B6 63 BB FF BF 65 C4 65 C8 C7 CB A7 CF D9 D4
B5 DA 8C E0 A9 E5 58 E9 DF EA 87 E9 98 E4 5B DB
6E CB 74 B4 F7 98 8E 7B 82 5E 94 43 14 2C 0D 19
6F 0B 27 04 43 01 00 00 33 00 B8 01 6C 04 2D 08
D9 0C 4D 12 67 18 FF 1E EC 25 02 2D 12 34 E8 3A
4E 41 0B 47 E4 4B 9C 4F F7 51 FD 50 DC 4B 1E 44
48 3B BF 32 C8 2B 91 27 46 27 33 2A B4 2E 96 34
...


The top three lines make up a header (though there's also a separate header that defines this animation above):
Code: Select all3F CC 08 49 00 00 00 09 01 00 00 00 3F 7E 00 00
01 00 00 00 05 4C 3D 2B BD 00 00 00 00 00 00 00
01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00


And then the part below encodes the animation:
Code: Select allDC 0B DC 0B DC 0B DD 0B DC 0B DC 0B DC 0B 25 00
47 0A E6 88 3E BF 8F 36 C3 D1 04 D5 9F DA 8A E1
CF E8 A6 EF 79 F5 DF F9 86 FC 13 FD 93 FB 59 F8
45 F3 44 EC 70 E3 23 D9 FE CD E2 C2 DD B8 0A B1
35 AB 64 A6 6A A2 14 9F 39 9C BD 99 95 97 C3 95
50 94 4A 93 DA 92 16 93 E9 93 8B 95 64 97 8F 99
F5 9B 7F 9E 1B A1 B3 A3 95 A6 07 AA F1 AD 38 B2
BF B6 63 BB FF BF 65 C4 65 C8 C7 CB A7 CF D9 D4
B5 DA 8C E0 A9 E5 58 E9 DF EA 87 E9 98 E4 5B DB
6E CB 74 B4 F7 98 8E 7B 82 5E 94 43 14 2C 0D 19
6F 0B 27 04 43 01 00 00 33 00 B8 01 6C 04 2D 08
D9 0C 4D 12 67 18 FF 1E EC 25 02 2D 12 34 E8 3A
4E 41 0B 47 E4 4B 9C 4F F7 51 FD 50 DC 4B 1E 44
48 3B BF 32 C8 2B 91 27 46 27 33 2A B4 2E 96 34
...


At first this just looks like a random sequence, but notice how "DC 0B" repeats multiple times? If you look above in the header, you'll see the sequence "05 4C 3D 2B BD 00 00 00". The "BD" in that sequence impacts those repeated "DC 0B" blocks--those seem to actually be shorts set to "0BDC". Based on what I've seen across multiple animation files, the last nibble (in this case, "C") appears to be some kind of enum or opcode. I've been suspecting these are essentially "commands" in the animation format. I haven't noticed any consistent patterns for these other than for commands with the value "0" (e.g. "D0 0B"/"0BD0"), which is consistently followed by three float values (possibly encoding a position or rotation?). At the end of commands, it seems to either go into a new "DX 0B" command or what I've been referring to as "subcommands", which encode additional information and follow a separate format. I haven't really found any useful patterns here yet, but I've noticed some subcommands use a series of bytes that smoothly transition in value, and some subcommands follow the sequence byte/float/byte/float/etc.

I think I've exhausted the "breakthroughs" I can have by simply staring at this data and brute forcing things, haha, so I'm interested to hear if any of you have found anything new? If not, I think the only other way to make forward progress will be to try decompiling the animation logic via Ghidra.

I don't know if it helps with the reverse engineering, but here are all the Noesis and 3D Max model and texture scripts for Dead Space 1, 2 and 3 I've collected from here, Zenhax and somewhere else if you want to take a look at their code.

[viewtopic.php?f=16&t=21530](https://forum.xentax.com/viewtopic.php?f=16&t=21530)
## Post #178
- Username: MeltyPlayer
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 16, 2021 12:38 pm
- Post datetime: 2023-07-03T07:38:55+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

I've had some breakthroughs! Finally figured out a large amount of the animation structure, I'll document my findings here:

Animation files are split up into two main types of chunks: what I've been referring to as "definitions" and "data blocks". 

Definition
Each definition corresponds to a certain animation. It first points to a name string, and then to a branching tree structure. Below is a simple definition:

```
0x0080 | 67 72 69 70 5F 70 6F 73 65 00 5F 5F 5F 5F 5F 5F | "grip_pose"
0x0090 | 02 01 00 00 A0 00 00 00 00 00 00 00 B0 00 00 00
0x00A0 | 00 00 00 00 00 00 00 00 5F 5F 5F 5F 5F 5F 5F 5F
0x00B0 | 16 00 01 00 C0 00 00 00 00 00 00 00 D0 00 00 00
0x00C0 | 00 00 00 00 00 00 00 40 00 00 00 40 5F 5F 5F 5F

```


Between 0x0090 and 0x00CF is the sample tree; the two nodes in the tree start with 0x0201 and 0x1600. The first byte in each node is the type--a few types I've discovered so far are 0x02 (the root), 0x05 (a parent node), and 0x16 (an animated node). The second byte in each node is the number of children, which will then be defined at the end of the node (notice that line 0x0090 ends with 0xB0, the address of its child). Animated nodes are special in that they also (or perhaps instead?) have an pointer to a data block at the end. So in this case, the animated node points to a data block at 0xD0. In this way, it's possible for a single definition to point to multiple data blocks.

Data blocks
Each data block defines some keyframes for the animation; naturally, this is where the bulk of the animation file comes from. It first starts with three lines of header, and then it goes into keyframes. Below is a simple data block:

```
0x00E0 | FF FF FF FF 3D 72 94 8B 02 00 00 00 00 00 00 00
0x00F0 | 01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00
0x0100 | 2C 00 2C 00 2C 00 2D 00 2C 00 2C 00 2C 00 2C 00
0x0110 | 2C 00 2C 00 2D 00 2C 00 20 00 8B ED AF 2C 00 5F

```


I still don't actually understand most of the header, haha. But the most important thing is the integer 0x3D72948B from the second line. This actually corresponds to data from the corresponding RCB file:

```
0x0170 | 00 00 00 00 7C 01 00 00 00 00 00 00 84 01 00 00
0x0180 | 02 00 00 00 03 00 00 00 00 00 00 00 90 01 00 00

```


As you can see, the first line contains the same integer, 0x3D72948B! The value immediately after this points to the tuple (0x0184, 0x02), which itself points to 0x03. It's not necessarily clear from this example, but 2 is the number of bones in this model, and 3 is a bitmask for the bones that will have keyframes defined in this data block. Since 3 in binary is just "11", this effectively means that all 2 bones in the model will have definitions in the current data block.

After the header in the data block, it then goes right into animation data. This is the part that starts with some 0x2C values. I had been referring to these as "commands" before, but it turns out that this is actually frame data for each axis! Specifically, it lists out the XYZW quaternion axes, and then the XYZ position axes for each bone in the bitmask mentioned above.

Frame data can be listed out as either singletons or as multiple keyframes.

Singletons
Singletons, i.e. single keyframes, will start with the 3 nibbles that immediately comes after the important integer mentioned above. In the example above, the 3 nibbles immediately after 0x3D72948B are 0x020 (i.e. 0x002). (The endianness makes it a bit hard to read, but you just kind of have to flip the order around in your head) As you can see, the above example exclusively contains singletons: 0x2C00, 0x2D00, 0x2000. It's important to note that this 3-nibble prefix doesn't necessarily need to start with 0s; it can be arbitrary hex.

The value to use in the single keyframe is identified by the last nibble:
- 0xC: 0
- 0xD: 1 (primarily used for the W axis of the quaternion)
- 0x0: The reader will step back a byte and then read a 4-byte float. Since it steps back, this float will actually contain part of the 3-nibble prefix mentioned above!

So here's how you can interpret the above animation data:

```
  - Quaternion X: 0 (0x2C00) 
  - Quaternion Y: 0 (0x2C00) 
  - Quaternion Z: 0 (0x2C00) 
  - Quaternion W: 1 (0x2D00) 
  - Position X: 0 (0x2C00) 
  - Position Y: 0 (0x2C00) 
  - Position Z: 0 (0x2C00) 
- Bone 2:
  - Quaternion X: 0 (0x2C00) 
  - Quaternion Y: 0 (0x2C00) 
  - Quaternion Z: 0 (0x2C00) 
  - Quaternion W: 1 (0x2D00) 
  - Position X: 0 (0x2C00) 
  - Position Y: -4.320881e-10 (0x20008BEDAF) 
  - Position Z: 0 (0x2C00) 

```

Multiple keyframes
From what I've seen, lists of multiple keyframes will start with some nibble and then 5, i.e. 0xB500. The first nibble actually corresponds to the number of keyframes that will be defined--in this case, it would be 11 (0xB). It then lists out the keyframes immediately afterward. Below is an example of a data block that contains an axis with multiple keyframes:

```
0x01D0 | FF FF FF FF 39 B5 AF 45 C2 01 00 00 00 00 00 00
0x01E0 | 01 00 00 80 00 00 00 00 00 00 00 00 00 00 00 00
0x01F0 | 2C 1C 2C 1C 2C 1C 2D 1C 2C 1C 2C 1C 2C 1C 2C 1C
0x0200 | 2C 1C 2C 1C 2D 1C 2C 1C 2C 1C 2C 1C 2C 1C B5 00
0x0210 | 23 03 01 D2 34 E5 19 B8 9C 80 BB 89 7E BB 23 03
0x0220 | C4 A5 34 08 B3 37 B6 9A BB FC 73 BE 23 03 D4 2C
0x0230 | 35 09 AC B7 79 0A 39 E4 C3 BE 22 03 D3 F8 37 3C
0x0240 | 2A 3B D6 B3 BE 23 03 39 63 B4 6C 92 37 92 AC 3B
0x0250 | 50 1D BE 22 03 8F E0 B7 CB BA 3B CB F6 3D 82 02
0x0260 | 81 36 B8 86 3E 3B 51 AB 3E B0 00 EF C3 3E 23 03
0x0270 | E7 95 34 F9 90 B8 B2 C5 39 BF C3 3E 93 03 8D CA
0x0280 | 34 3F E7 B7 94 8E BB 0F 89 3E 21 00 44 7C BB 44
0x0290 | 7C 3B 2C 1C 95 00 22 03 E1 56 B7 56 26 38 F7 7F
0x02A0 | 3F 23 03 7F 89 34 B0 13 B7 DC 95 BA 9E 78 3F 23
0x02B0 | 03 68 82 34 12 F3 B6 D2 1D 38 88 6C 3F 22 03 14
0x02C0 | 7B B5 B9 94 3A 87 6F 3F 22 03 2F 85 B7 9D 64 3A
0x02D0 | EC 7C 3F 22 03 77 80 B6 F8 64 BA 51 7E 3F 23 03
0x02E0 | 7D 18 B4 E1 C9 37 83 9F BA 5E 71 3F 23 03 01 7F
0x02F0 | B4 5F 05 38 A4 3F B9 90 6C 3F A2 03 3E 4C B7 B4
0x0300 | AF 3A 8C 76 3F 20 1C 00 40 3D 20 1C EF DA 3D 20
0x0310 | 1C 87 FF 3D 5F 5F 5F 5F 5F 5F 5F 5F 5F 5F 5F 5F

```


In this case, the multiple keyframes begin on line 0x200, with 0xB500. (To be explicitly clear, this is a substitute for a singleton; this clump of multiple keyframes will all be used within a single axis.) I haven't fully worked out the keyframes format, but I've noticed some key patterns. They start with two nibbles: one for the number of frames corresponding to their length, and another for the type of keyframe. Then, it lists off some data, and finally the value of the keyframe. I'm not entirely sure what this extra data means, but I'm assuming it's things like tangents for easing.

In the above example, the keyframes after 0xB500 look like this:

```
23   03 C4 A5 34 08 B3 37 B6 9A   BB FC 73 BE 
23   03 D4 2C 35 09 AC B7 79 0A   39 E4 C3 BE 
22   03 D3 F8 37 3C 2A            3B D6 B3 BE 
23   03 39 63 B4 6C 92 37 92 AC   3B 50 1D BE 
22   03 8F E0 B7 CB BA            3B CB F6 3D 
82   02 81 36 B8 86 3E            3B 51 AB 3E 
B0                                00 EF C3 3E 
23   03 E7 95 34 F9 90 B8 B2 C5   39 BF C3 3E 
93   03 8D CA 34 3F E7 B7 94 8E   BB 0F 89 3E 
21   00 44 7C                     BB 44 7C 3B

```


As mentioned above, the first nibble of each row is the length of the keyframe and the second is the type. The data immediately after is presumably for things like easing--the amount of extra data depends on the type. A type of 0 has no extra data, 1 has 3 bytes, 2 has 6 bytes, and 3 has 9. The last four bytes are the float value for that keyframe.

I'm currently working on a parser for this format and will continue researching this to see what else I find out, but I thought I might as well share my findings for posterity. Hopefully this all made sense and is useful to you folks!
## Post #179
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-07-03T07:55:03+00:00
- Post Title: Re: Ripping Dead Space 1-3 models with animations and textures.

Really great research, Dead Space has a number of cutscenes that seem to have been lost in all series as far as the internal text data is concerned.
I don't know if any of those animations are still inside, but that will become clear when you or someone else is able to analyze the animations someday!
Originally this game has some of the best animations of any TPS game of its time. I am very much looking forward to the new news!
