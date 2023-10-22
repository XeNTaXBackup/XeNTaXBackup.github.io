## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-24T00:48:55+00:00
- Post Title: Ninja Ripper

Utility to extract / ripping 3d models (mesh), textures, shaders directly from the running game.
(It's new version of [dx ripper](http://forum.xentax.com/viewtopic.php?f=33&t=9282))

Author: blackninja

Features:
Extracting all available vertex information of the models (position, all the texture coordinates, normals, weights, BLENDWEIGHT, BLENDINDICES, BINORMAL, TANGENT), indices, textures, shaders. Theoretically all extracted information could be import in the 3D editor!
Support for D3D11, D3D9, D3D8 (processed, however not all methods/techniques, but should work for 95% of all games).

[](https://discord.gg/2PMeU2R)
I've made a Discord channel for quick chatting about ninja ripper. Russian forum is still official help place for feature/problems discussions.
Click on Discord logo to join or [here](https://discord.gg/2PMeU2R).

[Ripper page](http://cgig.ru/ninjaripper/)  |  [English Instructions](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/)  |  [Official author's website](http://blackninja2000.narod.ru/rus/directx_ripper.html)  |  [Official support page](http://cgig.ru/forum/viewtopic.php?f=5&t=224)

Hitman: Absolution  |  Agent 47:

[](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/ninja_ripper/img/hitman_prev001.png) [](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/ninja_ripper/img/hitman_prev002.png)
[](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/ninja_ripper/img/hitman_prev003.png) [](https://dl.dropbox.com/u/9919707/cg.forexperts.ru/forum/tools/special/ninja_ripper/img/hitman_prev004.png)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-24T02:57:45+00:00
- Post Title: Ninja Ripper

i see no options for anything besides verts normals and uv's.
where are the weighting / bone import options.
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-24T03:26:29+00:00
- Post Title: Ninja Ripper

> Reply from chrrox
>
> i see no options for anything besides verts normals and uv's.
where are the weighting / bone import options.there is no options to do that, because our (blackninja and my) knowledges in max scripting is poor
## Post #4
- Username: nizarwldl97ba
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-24T03:30:44+00:00
- Post Title: Ninja Ripper

i can help with the project if you tell me what you guys need.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-24T03:46:52+00:00
- Post Title: Ninja Ripper

> Reply from chrrox
>
> i can help with the project if you tell me what you guys need.well, as i understand ripper can save all vertices information, including information about weights, but we don't know how to generate skeleton, because loading of weights means the binding of weights with something.
I have a thoaghts about generating default skeleton or bunch of bones and binding loaded weight info with a random bone, but it's silly.
Of course will be cool to load all ripped information into 3ds max and play with it.

If you can help it will be great.
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-24T03:52:43+00:00
- Post Title: Ninja Ripper

but bones are just an abstract concept for animation - you can't get any bone information from directx as it only knows about the vertex data - transformed way before the rendering stage
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-10-24T04:09:17+00:00
- Post Title: Ninja Ripper

> Reply from WRS
>
> but bones are just an abstract concept for animation - you can't get any bone information from directx as it only knows about the vertex data - transformed way before the rendering stageyes, you right.
And in case of 3d tool bone it's nothing, just a "word". Vertices of the model could be binded with "anything" (a dot/helper), and it's good to get coordinates of this "something" to bind with.
i'm not sure we can do this, but what we can do is messing with 3ds max, just need to think what we can do

p.s.: btw, plugin for Noesis will be very usefull too
p.p.s: also will be cool to have an option to load all pairs of uv into 3ds max one by one in uv channels in one time
## Post #8
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-10-24T08:37:53+00:00
- Post Title: Ninja Ripper

> Reply from Tosyk
>
> 
p.s.: btw, plugin for Noesis will be very usefull too
p.p.s: also will be cool to have an option to load all pairs of uv into 3ds max one by one in uv channels in one time
I second that! I am really getting upset with 3dsmax scripts, as this isnt exactly faster way of ripping than was dxrip (ripping, previewing rip files in noesis and exporting - simple as that).

I hope Noesis plugin will be updated and Ninja Ripper to include DDraw Wrapper aswell 

EDIT: OMG 

This tool finally works with TCLA and TCNY, and Dolphin, great job!! It does really need Noesis plugin right now
## Post #9
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-27T01:53:34+00:00
- Post Title: Ninja Ripper

Hi!

I tried this tool with the Sleeping Dogs demo. F9 works and puts out a textures file, but F10 doesn't cause anything to happen. No models are saved. Any suggestions?
## Post #10
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-10-27T05:13:25+00:00
- Post Title: Ninja Ripper

Did you assigned the capture key to F10? Try assigning it to F9 or F12 instead.
## Post #11
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-10-27T06:13:38+00:00
- Post Title: Ninja Ripper

> Reply from RacingFreak
>
> Did you assigned the capture key to F10? Try assigning it to F9 or F12 instead.

Yes, I tried this. I tried assigning both to F9 and I got only textures. Then I tried making textures F10 and models F9, and it was the same result where the textures were grabbed but the models were not.

Is it possible this is running in dx10 and not dx11?
## Post #12
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-10-29T11:36:20+00:00
- Post Title: Ninja Ripper

I have the same issue with Dark Souls. If running with the default method (intruder) neither key is functional. (no textures, no rips)

If running with DX9 method, it works, but only textures are able to be captured, trying to rip meshes results in a slight pause, but no rip is produced.

It guess it seems that some games don't work with it.
## Post #13
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2012-11-02T16:52:02+00:00
- Post Title: Ninja Ripper

@tosyk 

man, did you manually put all the mesh together? because when i import all rip file, it comes with different parts. is that correct?
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-11-02T16:58:47+00:00
- Post Title: Ninja Ripper

> Reply from omfgpota
>
> @tosyk 

man, did you manually put all the mesh together? because when i import all rip file, it comes with different parts. is that correct?yes, it's almost all manualy, this is the way how ripper works
## Post #15
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2012-11-03T10:16:05+00:00
- Post Title: Ninja Ripper

Is there a general reason why a game would fail to produce a rip or otherwise fail to hook? I'm trying to rip from Dark Souls, but as I said earlier in the thread using the default Intruder DLL doesn't work (it doesn't hook or something apparently, neither key works) and using the D3D9 wrapper only allows textures, trying to capture a frame results in a slight 1 second pause, but produces no rip, only empty folders.

I suspect the problem was GFWL, but disabling its memory protection has no result, Intruder.dll fails to hook and rips still cannot be captured.
## Post #16
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-11-03T12:48:37+00:00
- Post Title: Re: Ninja Ripper

looks like ripping process is dependent on pc specs, some of peoples got a pink textures, for some people the ripper doesn't working at all

and your logs would help
## Post #17
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-03T12:54:45+00:00
- Post Title: Re: Ninja Ripper

Well it works just fine on both my XP PC and Win 7 Laptop, but still awaiting for Noesis script.
## Post #18
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-11-04T12:48:30+00:00
- Post Title: Re: Ninja Ripper

How much does the output differ from dx ripper's output?
## Post #19
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-11-04T13:40:34+00:00
- Post Title: Re: Ninja Ripper

> Reply from Demonsangel
>
> How much does the output differ from dx ripper's output?new .rip format has been completely remade
## Post #20
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-11-04T16:44:00+00:00
- Post Title: Re: Ninja Ripper

Mind giving the new format so a new noesis script can be made.
## Post #21
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-05T12:00:36+00:00
- Post Title: Re: Ninja Ripper

Yeah Noesis script will be simply the best thing, I am having a headache from loading even 1000 models one by one (group feature doesnt work) in 3DSMAX, not even to say its easier to just load and export as OBJ in Noesis 

Hope that can be made soon
## Post #22
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2012-11-14T01:38:23+00:00
- Post Title: Re: Ninja Ripper

Would be awesome if someone with the skills could convert this 3dsmax script to noesis

[http://cgig.ru/forum/lincounter.php?lin ... _beta6.zip](http://cgig.ru/forum/lincounter.php?link=tools/3dmax-scripts/ninja_ripper/ninja_ripper_1.3_beta6.zip)
## Post #23
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-17T00:12:39+00:00
- Post Title: Re: Ninja Ripper

Has anyone tried Call of Duty Black Ops 2 ?
## Post #24
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-17T07:26:26+00:00
- Post Title: Re: Ninja Ripper

I tried NFS Most wanted 2012
but the rips turn out like this
## Post #25
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-17T07:33:09+00:00
- Post Title: Re: Ninja Ripper

lol just wait till Oleg is done with his NFSMW2012 filter.
## Post #26
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-17T07:35:10+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> lol just wait till Oleg is done with his NFSMW2012 filter.
Filter? can you explain more?
## Post #27
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2012-11-17T13:43:07+00:00
- Post Title: Re: Ninja Ripper

> Reply from cra0
>
> RacingFreak wrote:lol just wait till Oleg is done with his NFSMW2012 filter.
Filter? can you explain more?
Yep - [http://forum.zmodeler3.com/viewtopic.php?f=22&t=5851](http://forum.zmodeler3.com/viewtopic.php?f=22&t=5851)
## Post #28
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-18T09:27:38+00:00
- Post Title: Re: Ninja Ripper

Tried ripping from cod black ops 2 but textures appear all purple
## Post #29
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2012-11-19T18:23:12+00:00
- Post Title: Re: Ninja Ripper

Are you runing the game on DX11 or DX9? i ask because i have the same problem but with Deus Ex Human revolution i turn-off DX11
and select DX9 so when i rip again the models the rips was ok and the textures arent pink anymore.
## Post #30
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2012-11-29T11:05:04+00:00
- Post Title: Re: Ninja Ripper

Hi. Im author of NinjaRipper

Here beta version 1.1.2 with fixed "purple" textures in Dx11 and gamma in Dx9

[http://blackninja2000.narod.ru/files/ninjaripper112.7z](http://blackninja2000.narod.ru/files/ninjaripper112.7z)
## Post #31
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-29T11:25:34+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi. Im author of NinjaRipper

Here beta version 1.1.2 with fixed "purple" textures in Dx11 and gamma in Dx9

http://blackninja2000.narod.ru/files/ninjaripper112.7z

oh great however it now crashes before the game runs
## Post #32
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2012-11-29T12:42:35+00:00
- Post Title: Re: Ninja Ripper

cra0
Put log file
## Post #33
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-30T01:32:58+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> cra0
Put log file

Error


Log
[https://dl.dropbox.com/u/10798900/DUMPB ... xe.log.txt](https://dl.dropbox.com/u/10798900/DUMPBOX/t6sp.exe.log.txt)
## Post #34
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2012-11-30T06:49:31+00:00
- Post Title: Re: Ninja Ripper

cra0
Its' original version of COD without crack ?
With protected games ripper may crash
And I not recommend run under ripper online games. Ripper may be appear as cheat tool -> ban
## Post #35
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2012-11-30T08:25:11+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> cra0
Its' original version of COD without crack ?
With protected games ripper may crash
And I not recommend run under ripper online games. Ripper may be appear as cheat tool -> ban

I tried with the original and the cracked version and same problem and plus no this isn't the multilayer its single player
## Post #36
- Username: afrokid
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jul 11, 2011 5:20 pm
- Post datetime: 2012-12-05T18:14:19+00:00
- Post Title: Re: Ninja Ripper

Is there anyway to rip into .obj files or open them in any program that isnt 3dsmax. I dont have access to 3dsmax.
## Post #37
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2012-12-06T07:24:42+00:00
- Post Title: Re: Ninja Ripper

afrokid
At this time only 3d max import supported. May be in future versions will be added

But ".rip" format is open and anybody can write any format importer
## Post #38
- Username: MCDMaker
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 7:55 pm
- Post datetime: 2012-12-06T14:52:21+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> afrokid
At this time only 3d max import supported. May be in future versions will be added

But ".rip" format is open and anybody can write any format importer

Hi! I tryed to rip a game but it only created a Log file D:
## Post #39
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2012-12-27T17:55:26+00:00
- Post Title: Re: Ninja Ripper

So far I had no luck to get models from HMA (HitmanAbsolution) I guess I got most of the errors covered in this topic, but the models won't rip, but I get perfectly fine the textures...
## Post #40
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2012-12-30T19:49:48+00:00
- Post Title: Re: Ninja Ripper

Haven't tried the tool, but seems pretty neat, thank you.

> Reply from blackninja
>
> afrokid
At this time only 3d max import supported. May be in future versions will be added

But ".rip" format is open and anybody can write any format importer

Is there any english documentation on the .rip format? I couldn't find it in the website. Would be faster to have that than figuring out by reading the max script.
## Post #41
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-01-02T06:19:02+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> afrokid
At this time only 3d max import supported. May be in future versions will be added

But ".rip" format is open and anybody can write any format importer

I don't know why but I tried everything possible to get the textures working for this building ripped from bf3 but no luck  any advice
## Post #42
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-02T07:32:24+00:00
- Post Title: Re: Ninja Ripper

try to search for different uv-pair, and maybe this mesh is not actual for rendering diffuse texture, maybe this mesh is for an ambient occlusion map only, or some other effect or something totaly different stuff like Collision Model, so try to search similar model in the same folder
## Post #43
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-01-02T07:48:27+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> try to search for different uv-pair, and maybe this mesh is not actual for rendering diffuse texture, maybe this mesh is for an ambient occlusion map only, or some other effect or something totaly different stuff like Collision Model, so try to search similar model in the same folder
No I'm sure it uses a diffuse map because look at this screenshot without and other shader params
## Post #44
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-02T07:52:59+00:00
- Post Title: Re: Ninja Ripper

give me your rip directory, and tell me name of the needed file
i'll search around your rips
## Post #45
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2013-01-02T08:33:02+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> give me your rip directory, and tell me name of the needed file
i'll search around your rips

Thankyou!!!

I added you on steam btw

[https://dl.dropbox.com/u/10798900/DUMPBOX/BF3_RIP.7z](https://dl.dropbox.com/u/10798900/DUMPBOX/BF3_RIP.7z)

its Mesh_34
## Post #46
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-01-03T23:45:46+00:00
- Post Title: Re: Ninja Ripper

Any reason why meshes come are ripped like this? Is there any fix or it's just how ripper works on HMA?
## Post #47
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-04T00:10:08+00:00
- Post Title: Re: Ninja Ripper

> Reply from CMihai
>
> it's just how ripper works on HMA?correct, there is nothing we can do about that
## Post #48
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2013-01-04T10:25:12+00:00
- Post Title: Re: Ninja Ripper

CMihai

All vertex data ripped "as is". Model is deformated before rendering on GPU

Use scale X/Y/Z modifier in max and everithing will fine
## Post #49
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-01-04T12:11:46+00:00
- Post Title: Re: Ninja Ripper

Yep, used the scale last night to "fix" some of them, but I thought that I did something wrong.
## Post #50
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-09T02:33:02+00:00
- Post Title: Re: Ninja Ripper

Ninja .rip importer is updated to beta 7 now. What's new:

2013.01.09 (1.3 beta7):
- added uv Scale function ("Scale" in "Transformations" group)
- improved model Scale function  ("UV x" in "Transformations" group)

can be downloaded from ninja ripper's [support page](http://cgig.ru/forum/viewtopic.php?f=5&t=224)
## Post #51
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-09T16:03:38+00:00
- Post Title: Re: Ninja Ripper

Excellent
## Post #52
- Username: psychclw
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 26, 2012 11:23 pm
- Post datetime: 2013-01-09T18:05:04+00:00
- Post Title: Re: Ninja Ripper

Great job! but what bout Noesis script?
## Post #53
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-11T07:38:11+00:00
- Post Title: Re: Ninja Ripper

> Reply from psychclw
>
> Great job! but what bout Noesis script?
Would love to see finally one!
## Post #54
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-11T08:49:36+00:00
- Post Title: Re: Ninja Ripper

you guys really need to ask about that finale00, 'cause he is one who wrote script for dxripper .rip files
## Post #55
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-12T18:37:54+00:00
- Post Title: Re: Ninja Ripper

I hope he sees that thread.
## Post #56
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-20T09:55:56+00:00
- Post Title: Re: Ninja Ripper

Hey folks,

I made a small neosis-plugin [[download](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)]
Only default-settings like the 3DSMax-Importer, but should works with the most games. No materials/textures cuz to complicated for me at the moment.  
If you want the see the texture-names for the loaded model, remove the # in line 19 (noesis.logPopup()) to enable the debug-window.

Hint: if you have the fmt_dxripper_rip.py installed, remove it to prevent file confusion with older dxripper-".rip"-files. Maybe finale00 want to merge both versions. Feel free to modify.
## Post #57
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-20T10:21:31+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> I made a small neosis-pluginthank you for that
## Post #58
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-20T11:47:48+00:00
- Post Title: Re: Ninja Ripper

Holy crap you made it! So close to having the perfect game ripping setup
## Post #59
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-20T13:18:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Hey folks,

I made a small neosis-plugin [download]
Only default-settings like the 3DSMax-Importer, but should works with the most games. No materials/textures cuz to complicated for me at the moment.  
If you want the see the texture-names for the loaded model, remove the # in line 19 (noesis.logPopup()) to enable the debug-window.

Hint: if you have the fmt_dxripper_rip.py installed, remove it to prevent file confusion with older dxripper-".rip"-files. Maybe finale00 want to merge both versions. Feel free to modify.

[](http://postimage.org/image/dd0pr6zfr/)

ugh, not really what I had expected.

Mine .rip file:
[http://rghost.ru/43179686](http://rghost.ru/43179686)

Max script import model correctly.
## Post #60
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-20T18:34:11+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> 
ugh, not really what I had expected.
Thx for bug-reporting. Some meshes couldn't be loaded. They had another file-structure then the game-models I have tested.
I have updated my script now [[download](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)] Still not perfect, but it loads your sunglasses.
If you have more corrupt meshes, please uploading two or three .rip files
## Post #61
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-20T19:01:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Sanya wrote:
ugh, not really what I had expected.

Thx for bug-reporting. Some meshes couldn't be loaded. They had another file-structure then the game-models I have tested.
I have updated my script now [download] Still not perfect, but it loads your sunglasses.
If you have more corrupt meshes, please uploading two or three .rip files
yeah, works pretty nice   

[http://rghost.ru/43190242](http://rghost.ru/43190242)

another rip. There's no such mess, just inverted normals. Just havent lots of games ATM, tested on few. All rips from this game has this problem.


And about UVs. Anyway to change it like in max import plugin (maybe in python script, if there's no way to make popup menu)? Models itself are correct, but UVs are not. 

Noesis script is way better, since it take no time at all to load + faster preview. I think every user of ninja ripper would appriciate your work   .
## Post #62
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-21T08:51:13+00:00
- Post Title: Re: Ninja Ripper

Excelleenntt, waiting for UV mapping
## Post #63
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-21T09:19:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> yeah, works pretty nice   

http://rghost.ru/43190242

another rip. There's no such mess, just inverted normals. Just havent lots of games ATM, tested on few. All rips from this game has this problem.


And about UVs. Anyway to change it like in max import plugin (maybe in python script, if there's no way to make popup menu)? Models itself are correct, but UVs are not. 

Noesis script is way better, since it take no time at all to load + faster preview. I think every user of ninja ripper would appriciate your work   .
As far as I know, neosis had no possibilities for popups per plugin. 

I had no problems with the UVs or Face-Normals on my own game models. But every game produces other rip files with different data-structure.  Its not really possible to make an automated version, which load every type of model. See the [ninjaripper-instructions](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/) to understand the problem. 

As far as I can see, your car .rip has no valid UV-data, or maybe I cannot figured out, how the data is stored. 
The 3DSMax-Importer is not be able to load the correct UVs, too. I see 3 floats for the vertices and then a row of integers, but no UV-floats, maybe half-floats, I don't know.
(-56.753353118896484 | -24.916292190551758 | 37.73585510253906 | -1.0 | 255 | 255 | 255 | 255 | 129 | 48 | 195 | 55 | 214 | 131 | 34 | 63 | 38 | 164 | 45 | 63)

The car-.rip has TEXCOORD-Blocks, but they filled with these useless integer-vales (index 8-11 =  129 | 48 | 195 | 55 and index 16-19 =  38 | 164 | 45 | 63), but this should be floats between 0|1. 
214 | 131 | 34 | 63 is declared to be Normals-Data, but should be floats, too. Dont know why - blackninja should take a look at this and tell us how the data is stored. 
index 4-7 (255 | 255 | 255 | 255) is a COLOR-block - pure white. If blackninja could make the correct changes for the 3DSMax-Importer, then I can update the plugin for this type of models.

For your sunglasses-rip its a similar problem. It has UVs but the 3DSMax-Importer is reading the false block (0|1), instead of 10|11. That is why you can change the parameters manually in the 3DSMax-Importer. 
If you want to load the correct UVs in neosis for this game-models you have change this variables in the plugin:

```
g_Tc0_U_Idx = 10 # default 6
g_Tc0_V_Idx = 11 # default 7
```

I rewrote the plugin to speed it up a little bit to prevent to many vertices-loops. [[download](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)]
## Post #64
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-21T09:41:19+00:00
- Post Title: Re: Ninja Ripper

> As far as I know, neosis had no possibilities for popups per plugin.
Sad.

> I had no problems with the UVs or Face-Normals on my own game models. But every game produces other rip files with different data-structure. Its not really possible to make an automated version, which load every type of model. See the ninjaripper-instructions to understand the problem.
That's what I mean by "if there's a way to make popup menu for changing this thing". Now I see that it's not. Btw, does noesis has UV map preview? I dont think so, but can be wrong.

> As far as I can see, your car .rip has no valid UV-data, or maybe I cannot figured out, how the data is stored.
I'd ask it on ninja ripper's forum.

> g_VertexFormatRecog = 1 # default 0
>
> g_Tc0_U_Idx = 10 # default 6
>
> g_Tc0_V_Idx = 11 # default 7

what I was looking at. But what's the first cmd?
## Post #65
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-21T10:43:25+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> That's what I mean by "if there's a way to make popup menu for changing this thing". Now I see that it's not. Btw, does noesis has UV map preview? I dont think so, but can be wrong.
No, neosis has no UV-preview, only UV-coords in the data-viewer

> Reply from Sanya
>
> g_VertexFormatRecog = 1 # default 0
g_Tc0_U_Idx = 10 # default 6
g_Tc0_V_Idx = 11 # default 7

what I was looking at. But what's the first cmd?
The first cmd disables the "offset auto-detection" for the blocks (vertices, normals, uvs), so you can specify the blocks manually. I saw meshes with only 8 blocks and meshes with up to 25 blocks. Anything is possible  The auto-detection works good on many older games, but on newer games, it doesnt work very well.
## Post #66
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-21T11:02:31+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> No, neosis has no UV-preview, only UV-coords in the data-viewer

Just checked out Data Viewer. There's UV viewer. Data Viewer -> Model -> Meshes -> UV view.

But I cant affect UV by changing 

```
g_Tc0_V_Idx = 11
```


UVmap is same: looks like snapshot of the front model. Even I do any number (from 1 to 100), re-load/re-run noesis/re-export - UV doesnt change at all. Had export to Maya tho, but nothing happend. UVs like in noesis - same.

[](http://postimage.org/image/vx3ft21ij/)

[](http://postimage.org/image/5dauqx0yz/)
## Post #67
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-21T11:53:44+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> Just checked out Data Viewer. There's UV viewer. Data Viewer -> Model -> Meshes -> UV view.
Good catch.. never clicked on the values, lol

> Reply from Sanya
>
> But I cant affect UV
you have to set g_VertexFormatRecog to 1? In your screenshots I see 0.
## Post #68
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-21T12:06:32+00:00
- Post Title: Re: Ninja Ripper

> you have to set g_VertexFormatRecog to 1? In your screenshots I see 0.

yep, that's it. Now I can just open script, jump over UV values, change/save script and reload plugins from tools menu and look at what's going on. For some reasons I cant load UV at 10/11 as in max, but 11/12 works fine.
## Post #69
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-21T12:49:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> For some reasons I cant load UV at 10/11 as in max, but 11/12 works fine.
Hmm 10/11 should work, 11/12 its 90° rotated, but technically its a wrong pair.. every vertex has 4 UV pairs on this model: 10/11, 12/13, 14/15, 16/17 - all the same. Don't know why it need the same UV-data four times..mayme separate UVs for diffuse, specular, normal, occlusion
## Post #70
- Username: Andrakann
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-01-21T15:09:54+00:00
- Post Title: Re: Ninja Ripper

Noesis has a number of ways you can do popups/user queries. Native plugins allow you to do any kind of custom interface you want (see the Binary Find in Files plugin), otherwise Python offers a variety of prompting functionality, and there is noesis.userPrompt. You can also register advanced command options to allow the user to specify options that way, which is preferable when you have workable defaults so that the user can batch-process files without getting a dialog shoved in their face for each one. (the user can also batch-process with non-default options this way, by specifying those options for their batch export)

Noesis can preview UV's, as mentioned, Tools->Data viewer->Model #->Meshes->Mesh #->UV view.

Noesis can also preview embedded textures, Tools->Data viewer->Model #->Textures->Texture #.

To modify UV's, you need to check View->Verts/tris in data view, then you will have Tools->Data viewer->Model #->Meshes->Mesh #->Vertices. You can expand that to modify any of the UV values.
## Post #71
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-21T18:23:36+00:00
- Post Title: Re: Ninja Ripper

> Reply from MrAdults
>
> Noesis has a number of ways you can do popups/user queries. Native plugins allow you to do any kind of custom interface you want (see the Binary Find in Files plugin), otherwise Python offers a variety of prompting functionality, and there is noesis.userPrompt. You can also register advanced command options to allow the user to specify options that way, which is preferable when you have workable defaults so that the user can batch-process files without getting a dialog shoved in their face for each one. (the user can also batch-process with non-default options this way, by specifying those options for their batch export)
Any example-scripts or tutorials about the neosis-phyton-advanced-command-register-options-stuff? I never saw such stuff in other python-plugins.

Btw, is it possible the toggle the culling flag by default via python? Or a global function in neosis to set this by default? I hate it, when it turned off every time I load a new model from the list. The program should remember my current setting until I close it.
## Post #72
- Username: Acewell
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-01-21T20:25:02+00:00
- Post Title: Re: Ninja Ripper

noesis.addOption, noesis.optWasInvoked, and/or noesis.optGetArg are the methods you want. It isn't used in any of the included scripts, but it's documented in the Python readme. Here's example usage:

```
import rapi

def registerNoesisTypes():
	handle = noesis.register("Your model format", ".yourfmt")
	noesis.setHandlerTypeCheck(handle, yourFormatCheck)
	noesis.setHandlerLoadModel(handle, yourModelLoad)
	noesis.addOption(handle, "youroption", "you can use this option to do something", noesis.OPTFLAG_WANTARG) #use 0 instead of OPTFLAG_WANTARG if your option doesn't need parameters

def yourFormatCheck(data):
	return 1

def yourModelLoad(data, mdlList):
	if noesis.optWasInvoked("youroption"):
		optArg = noesis.optGetArg("youroption")
		#parse optArg or otherwise do something with it here
	return 1

```


If it's appropriate to never backface-cull something, I recommend setting noesis.NMATFLAG_TWOSIDED on the material flag(s). Otherwise, there is rapi.setPreviewOption, but it doesn't have backface culling exposed currently. I can give you an option for that if you really want it. In most cases, per-material twosidedness is more appropriate.
## Post #73
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-22T07:03:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from MrAdults
>
> noesis.addOption, noesis.optWasInvoked, and/or noesis.optGetArg are the methods you want. It isn't used in any of the included scripts, but it's documented in the Python readme.
If I copy your source, neosis is crashing on startup. (newest version)
Whats wrong?

> Reply from MrAdults
>
> Otherwise, there is rapi.setPreviewOption, but it doesn't have backface culling exposed currently. I can give you an option for that if you really want it.
Would be nice, if you can implement this. Its useful for model-previews with no materials/textures.
## Post #74
- Username: Andrakann
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-01-22T19:21:01+00:00
- Post Title: Re: Ninja Ripper

Oh, I forgot you need a "-" before the option name or it fails. And the Python code wasn't checking for a NULL pointer on return. I made it fail with a proper error for the next build. Here is the fixed code:

```
import rapi

def registerNoesisTypes():
   handle = noesis.register("Your model format", ".yourfmt")
   noesis.setHandlerTypeCheck(handle, yourFormatCheck)
   noesis.setHandlerLoadModel(handle, yourModelLoad)
   noesis.addOption(handle, "-youroption", "you can use this option to do something", noesis.OPTFLAG_WANTARG) #use 0 instead of OPTFLAG_WANTARG if your option doesn't need parameters

def yourFormatCheck(data):
   return 1

def yourModelLoad(data, mdlList):
   if noesis.optWasInvoked("-youroption"):
      optArg = noesis.optGetArg("-youroption")
      #parse optArg or otherwise do something with it here
   return 1

```


Also, I forgot, it is demonstrated in an existing script. The Quake 2 WAL script included in Noesis.
## Post #75
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-23T06:25:36+00:00
- Post Title: Re: Ninja Ripper

Ah, okay, now it works, thx MrAdults.

@Sanya
I have uploaded a [new plugin-version](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py), which is trying to detect the correct UV-Block.. works for your sunglasses-.rip, so you don't have to modify the source at the moment.

But Ninjaripper is still buggy with UVs. I have tried 20 (older) games now. 70% of all .rips just contain no UV-data - only 12byte-blocks with vertex-positions (3x4 floats for x/y/z). 
Other rips (from newer games) have other additional data (NORMAL, COLOR, TANGENT, BLENDINDCIES, BLENDWEIGHT), but still no UVs. 
Some .rips have corrupt UVs for some vertices and some data just make no sense (like in your car-.rip). And unfortunately there are no materials-groups for multiple textures.
I hope, blackninja is updating the tool in the near future.

I would be glad, if some people could upload 2-3 .rips of miscellaneous games and tell me the name of the game, so I can analyse more models and implement a better automatic process to detect the correct data structure for upcoming plugin-updates. Doesn't matter, if the .rip or UVs load correctly with the current plugin. Just upload 2-3 model-rips of every game you have.
## Post #76
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-23T09:02:58+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Just upload 2-3 model-rips of every game you have.

Love your work. I have uploaded two Diablo 3 models and two Guild Wars 2 models for you with texture 

[http://filebeam.com/99aff7897a017aa94ddc80b8ec6ed530](http://filebeam.com/99aff7897a017aa94ddc80b8ec6ed530)

EDIT:

Some more rips for you. SonicGeneration, StreetFighterIV, TheWalkingDead

[http://filebeam.com/46466a62793735e3afa3db75a9ddff39](http://filebeam.com/46466a62793735e3afa3db75a9ddff39)
## Post #77
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-23T11:48:27+00:00
- Post Title: Re: Ninja Ripper

Alright I will take some rips asap
## Post #78
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-23T15:14:38+00:00
- Post Title: Re: Ninja Ripper

Very sorry, doesnt have anything at the moment. Call of Duty 4 with unsupported UV data (well, it's not really nessasary to me, since 3dx doing its work well with that game seria), and Serious Sam 3 (sunglasses are from this one).

Script works well, thank for your job
## Post #79
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T09:09:03+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Love your work. I have uploaded two Diablo 3 models and two Guild Wars 2 models for you with texture 
Some more rips for you. SonicGeneration, StreetFighterIV, TheWalkingDead
Thx  I never really scripted something in python before, so I'm glad my source works  

I rewrote the plugin again and included a new uv_parser-function to have the flexibility to add game-specific UV-Parser-routines for games with UV-Integer-values.
Because every game has other calculations, I need to add them manually for every game. I started with your Diablo 3 .rips.

[](http://postimage.org/image/q00m7szyt/)

> Reply from Sanya
>
> Call of Duty 4 with unsupported UV data (well, it's not really nessasary to me, since 3dx doing its work well with that game seria), and Serious Sam 3 (sunglasses are from this one).I think Call of Duty 4 has UV data.. there are integer-Values inside the .rip, but the problem is to figure out, how to decode them.

Example-Values.. 4 Numbers per row must be decode to two floats (between 0 and 1). If anyone has an idea, let me know 

```
129 | 48 | 169 | 55 
255 | 116 | 33 | 195 
255 | 116 | 33 | 195 
129 | 48 | 169 | 55 
129 | 48 | 195 | 55 
158 | 45 | 228 | 52 
115 | 45 | 228 | 52 
78 | 45 | 228 | 52 
138 | 45 | 52 | 53
181 | 45 | 51 | 53 
101 | 45 | 52 | 53 
126 | 45 | 82 | 53 

```

[Download new Plugin v1.07](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)
## Post #80
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T09:37:39+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Download new Plugin v1.07

Amazing, great work.

Looks like the Diablo 3 fix works on the Guild Wars 2, Sonic Generations, Street Fighter 4 and The Walking Dead models. You just have to rename the other texture files inside the walking dead model to Tex_1913_0.dds.

Street Fighter 4 rips done before Ninja Ripper 1.1.2 aren't working, but the ones done after 1.1.2 works. So if people are having trouble with the UV's do a re-rip with 1.1.2
## Post #81
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T10:01:36+00:00
- Post Title: Re: Ninja Ripper

The diablo-fix has nothing to do with the texture-display. You don'thave to rename anything. It autoloads the first texturename, found in the .rip file. 
Cuz the .rip-files have no material-groups, its not possible the support meshes with multiple textures. I can only display one texture for the whole model.
## Post #82
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T10:09:04+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> The diablo-fix has nothing to do with the texture-display. You don'thave to rename anything. It autoloads the first texturename, found in the .rip file. 
Cuz the .rip-files have no material-groups, its not possible the support meshes with multiple textures. I can only display one texture for the whole model.

Yeah that's what I meant on the Walking Dead model, because I only included the diffuse texture, and it looks like the normal map is the one Noesis loads on default 

I did a re-rip on sonic. All the doodads work, but the characters are messed up. Kinda weird since the Tails model I uploaded earlier works just fine.
[http://filebeam.com/f1c847672cff52303ac70611f78f63ec](http://filebeam.com/f1c847672cff52303ac70611f78f63ec)
## Post #83
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-24T10:44:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Cuz the .rip-files have no material-groups, its not possible the support meshes with multiple textures. I can only display one texture for the whole model.rip files has only one texture per mesh
## Post #84
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T11:26:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Sammie wrote:Cuz the .rip-files have no material-groups, its not possible the support meshes with multiple textures. I can only display one texture for the whole model.rip files has only one texture per mesh
Yes diffuse, but the .rip has sometimes normals, speculars, lightmaps and so on in the texture-list.. and I see no possibility to determine automatically, which .dds-file is which texture, or is there a specific scheme, sort-order or something?

> Reply from deadca7
>
> I did a re-rip on sonic. All the doodads work, but the characters are messed up.
Looks fine for me, make a screenshot pls
## Post #85
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-24T11:37:34+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> or is there a specific scheme, sort-order or something?no, 'cause for ninja ripper it's just a data flow
so sometimes on the first (_0.dds) place there could be diffuse and sometimes a normal map
## Post #86
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T11:40:23+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Looks fine for me, make a screenshot pls
## Post #87
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-01-24T11:49:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Sammie wrote:Looks fine for me, make a screenshot pls
just flip uv on export
## Post #88
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T11:51:09+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> just flip uv on export

Ahhh, stupid me. Thanks :p
## Post #89
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T12:21:16+00:00
- Post Title: Re: Ninja Ripper

@deadca7
hmm.. maybe I uploaded a wrong version. Set g_flipUV = 1 in the script, to fix that.

> Reply from Tosyk
>
> no, 'cause for ninja ripper it's just a data flow
so sometimes on the first (_0.dds) place there could be diffuse and sometimes a normal map
hmm, too bad..

> Reply from deadca7
>
> Yeah that's what I meant on the Walking Dead model, because I only included the diffuse texture, and it looks like the normal map is the one Noesis loads on default
Download the script again. I inserted a little file-exist check. So if you delete (or move) your unnecessary files (normal, specular..) out of the folder, its loading only the diffuse now.
## Post #90
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T14:20:30+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Download the script again.

The plugin works with almost everything I have tested today, great work man.

These are the two rips I got right now that still does not work.
[http://filebeam.com/1c6541ab934bb3a37e5e5aec840c4abb](http://filebeam.com/1c6541ab934bb3a37e5e5aec840c4abb)

It's the doodads in Diablo 3 and LEGO The Lord Of The Rings

Edit:

Looks like Dead Island has problems too.
[http://filebeam.com/5e0e842b7bdd1d30fc1b5c91c6d1afc8](http://filebeam.com/5e0e842b7bdd1d30fc1b5c91c6d1afc8)
## Post #91
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T14:50:32+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Sammie wrote:Download the script again.

The plugin works with almost everything I have tested today, great work man.

These are the two rips I got right now that still does not work.
http://filebeam.com/1c6541ab934bb3a37e5e5aec840c4abb

It's the doodads in Diablo 3 and LEGO The Lord Of The Rings

Edit:

Looks like Dead Island has problems too.
http://filebeam.com/5e0e842b7bdd1d30fc1b5c91c6d1afc8
Fixed your Diablo and LEGOLOTR .rips. 

Add special UV-parsing for Dead Island.
[](http://postimage.org/image/8os0ule8n/)

Also add support for manual texture-names. Replace the _0 / _1 of your texture_names with _diff, _norm, _spec if available.
If your Mesh has the name "Mesh_0123.rip", rename the textures to "Tex_0123_diff.dds" and "Tex_0123_norm.dds"

[[Download new plugin v1.10](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)]
## Post #92
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T15:43:45+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> [Download new plugin v1.10]

Damn you work fast, thank you. I have tried 6 more games and the plugin works like a charm. Gonna try some more.

I took a look through the Diablo 3 models again, there are still some that are messed up.
[http://filebeam.com/167e3c90d32784b314cc27dcd3091c5e](http://filebeam.com/167e3c90d32784b314cc27dcd3091c5e)
## Post #93
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T16:19:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Sammie wrote:[Download new plugin v1.10]

Damn you work fast, thank you. I have tried 6 more games and the plugin works like a charm. Gonna try some more.

I took a look through the Diablo 3 models again, there are still some that are messed up.
http://filebeam.com/167e3c90d32784b314cc27dcd3091c5e

Yeah, I see.. its a tricky calculation, but I think, now I have the correct formula. [[Download again](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)].
Check more Diablo-.rips. If something looks weird, upload again pls. But if the number-range for the calculation is getting to high I must implement a better game-detection.
## Post #94
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-24T16:30:50+00:00
- Post Title: Re: Ninja Ripper

Brilliant work! I will test it over the weekend with no doubt
## Post #95
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T16:37:28+00:00
- Post Title: Re: Ninja Ripper

I went through 350 Diablo 3 models, and these three roofs were the only ones messed up.

[http://filebeam.com/e94a8169cddb6373a78b05157602f53c](http://filebeam.com/e94a8169cddb6373a78b05157602f53c)
## Post #96
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-24T16:43:54+00:00
- Post Title: Re: Ninja Ripper

[http://cgig.ru/forum/viewtopic.php?f=5& ... =550#p3424](http://cgig.ru/forum/viewtopic.php?f=5&t=224&start=550#p3424)
[http://cgig.ru/forum/viewtopic.php?f=5& ... 3467#p3467](http://cgig.ru/forum/viewtopic.php?f=5&t=224&p=3467#p3467)

2 posts about Diablo 3.

Main idea:

Diablo's UV are stored with extra offset, which can be simply restored to usual format with function:

```
        {
            float rez = 0; //flag=128
            if (flag == 129) rez += 0.5f;
            rez += 0.5f / 255 * b1;
            return rez;
        }

```

Or some sort of. I'm not really familiar with all of these stuffs. :{
## Post #97
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T16:52:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> 
Diablo's UV are stored with extra offset, which can be simply restored to usual format with function:
Code: Select allfloat Decode(byte b1, byte flag)
        {
            float rez = 0; //flag=128
            if (flag == 129) rez += 0.5f;
            rez += 0.5f / 255 * b1;
            return rez;
        }

Or some sort of. I'm not really familiar with all of these stuffs. :{

The formula doesnt fit for all models, cuz there is not only a 129 flag.. its a range between 123 and 133 (128 +/- 5). 
You have to add extra 0.5 for every number above 128 and subtract 0.5 for every number below 128.
The flag-line should be: if(flag != 128) rez -= ((128-flag)*0.5f 


@deadca7
fixed, download again
## Post #98
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-24T17:01:39+00:00
- Post Title: Re: Ninja Ripper

> Доброго времени суток
>
> Еще раз хочу поблагодарить создателя программы за столь крутой инструмент.
>
> Возвращаясь к теме импорта из Dyablo3 (моя запись на 56стр, к сожалению не понял как туда сделать линк), упаковка оказалась довольно простой - 4 и 12 байты, как я и думал, являются флагом, в даннонм случае 128 - значения до 0,5f, 129 - больше 0,5f, тоесть с этим флагом они получают двойную байтовую точность - 512 - что очевидно им хватает.
>
> готовая функция

Hello all. 
I'd say thank the author of this program.
Back to Diablo 3. After several reseach I found that it's pretty simple: 4 and 12 bytes, as I thouht, are flag, in this case 128 - value to 0.5f, 129 - more than 0.5f. And as you see, with this flag they get (tex coords?) double byte accuracy - 512 - what they exactly need. Here's the ready func: (from post above).



I dunno, but this guy talking about it very reliable x) At least I tried to help
## Post #99
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T17:06:01+00:00
- Post Title: Re: Ninja Ripper

hehe, yes - his formula is correct (for 129 only) but incomplete for all other numbers 123-133.
## Post #100
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T17:10:34+00:00
- Post Title: Re: Ninja Ripper

Looks like Battlefield 3 is messed up.

[http://filebeam.com/6c8cf969b7b245d69bbeb474cf1452c0](http://filebeam.com/6c8cf969b7b245d69bbeb474cf1452c0)

I have noticed that every Unreal Engine model has the normals flipped. Is that something that could be fixed in the script ? Have to press F4 in Noesis to enable face cull, to see the models.

Look at this Medal of Honor Warfighter head !
## Post #101
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T17:36:24+00:00
- Post Title: Re: Ninja Ripper

Funny eyes   

Added new rules for your crappy head
[](http://postimage.org/image/tojfgatgd/)
## Post #102
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-24T18:00:13+00:00
- Post Title: Re: Ninja Ripper

I have noticed that every Unreal Engine model has the normals flipped. Is that something that could be fixed in the script ? Have to press F4 in Noesis to enable face cull, to see the models.

eh, what's a point to rip from UE games, when we have umodel? x)
## Post #103
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T18:15:49+00:00
- Post Title: Re: Ninja Ripper

I just find it easier to capture the model there and then, instead of looking through the .upk files for the model. Guess it's called lazy 

Edit 1:
I thought Max Payne 3 had some messed up UV, but it was the texture. Removed link. Looks like the plugin is really solid now.

Edit 2:
Looks like I was wrong about Diablo 3, did three more rips, and there are still messed up models.
[http://filebeam.com/128af0847584640a8c5dc9825c9c8a6c](http://filebeam.com/128af0847584640a8c5dc9825c9c8a6c)
## Post #104
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T18:52:20+00:00
- Post Title: Re: Ninja Ripper

Not really.. code is fine.. but this diablo-models have another blocksize

search for "self.BlockSize == 92" and replace through "(self.BlockSize == 92 or self.BlockSize == 104 or self.BlockSize == 120)"
I really should rewrite this whole part in the next days  Different mesh-types in one game is bad.
## Post #105
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-24T19:16:18+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> I just find it easier to capture the model there and then, instead of looking through the .upk files for the model. Guess it's called lazy 

Edit 1:
I thought Max Payne 3 had some messed up UV, but it was the texture. Removed link. Looks like the plugin is really solid now.

Edit 2:
Looks like I was wrong about Diablo 3, did three more rips, and there are still messed up models.
http://filebeam.com/128af0847584640a8c5dc9825c9c8a6c

little advice:use shotcuts with comands like:  -meshes -nostat (models with skeleton only). Almost of player models are in _P archives, or in common data one. So it's not that hard, instead of looking at whole level/rip/export and take alook finally
## Post #106
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-01-24T21:24:16+00:00
- Post Title: Re: Ninja Ripper

> eh, what's a point to rip from UE games, when we have umodel?
Exactly. Gildor has the Unreal Engine games figured out already, no need to rediscover anything unless you're trying to get the terrain or something procedural. The focus of this plugin should shift toward rips from other game engines. I think the ultimate tool would be to combine Noesis, UEViewer and Ninja Ripper into a single app.
## Post #107
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-24T21:53:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from AceWell
>
> eh, what's a point to rip from UE games, when we have umodel?
Exactly. Gildor has the Unreal Engine games figured out already, no need to rediscover anything unless you're trying to get the terrain or something procedural. The focus of this plugin should shift toward rips from other game engines. I think the ultimate tool would be to combine Noesis, UEViewer and Ninja Ripper into a single app.

The main reason I asked was because there are a lot of games out there that have the normals flipped. Like Street Fighter, Prototype, Darksider, Unreal games (which has umodel), WoW (which has model viewer) and more. So if there is a way to detect if the normals are flipped, and flip them in the script. It would save us time over all.
## Post #108
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-24T22:12:38+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> ...there are a lot of games out there that have the normals flipped. Like Street Fighter, Prototype, Darksider, Unreal games (which has umodel), WoW (which has model viewer) and more. So if there is a way to detect if the normals are flipped, and flip them in the script. It would save us time over all.
Upload some of the .rips 

I've uploaded a new plugin-version. [[Download v1.14](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)]
Removed all UV-detection-stuff for single games and replaced it with a game-detection based on hash-keys from the .rip-struct.
So we have faster loading and easier updates for specific games. Send me new .rips and I can update the game-list inside the plugin.
## Post #109
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-25T00:34:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Upload some of the .rips 

I've uploaded a new plugin-version.

Nice work man, will upload some flipped rips tomorrow.
## Post #110
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-25T11:51:32+00:00
- Post Title: Re: Ninja Ripper

As promised yesterday, 9 game rips.

[http://filebeam.com/188a455dfccdbeb83aef70652170cefd](http://filebeam.com/188a455dfccdbeb83aef70652170cefd)
## Post #111
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-25T17:36:14+00:00
- Post Title: Re: Ninja Ripper

Thx for the .rips. I will script something tonight.

The shape of the Trine2-model seems to be badly distorted.
When I look on the texture it should be a guy, but the model looks like a long space vehicle  
Dont know if this can be fixed. Can you upload an additional character-.rip from this game?

Edit:

New Version online
Added support for: Deus Ex, Street Fighter IV, Super Mario Galaxy, Zelda Wind Waker, Metro 2033, Prototype, Sonic 4 and Tropico 3
No UV-Support for Trine 2 at the moment, but shape fixed.

UV-Format for Trine 2 is stored as 4 signed integers. If somebody has an idea how to decode this to two floats, let me know 

```
30343 | -18329 | -26449 | -6175 
29733 | -18145 | -26339 | -7117
18244 | -8381 | -29707 | -10995 
23718 | -21261 | -24890 | 1450 
1241 | -23411 | -22925 | -117 
9427 | -20562 | -21358 | -13952 
-21162 | -10837 | -29326 | -9806 
3939 | 22337 | -23596 | -4232
15353 | -5391 | -18252 | 26673 
-8702 | -10804 | 8098 | 29855 
15610 | -5186 | -18811 | 26322 
-29424 | 1719 | -29532 | -14090
-26248 | 1893 | -26745 | -18834
-22711 | 1648 | -22991 | -23288
10293 | -8915 | -13150 | -28657
8279 | -7002 | -19516 | -25372 
```


Edit2: 
Added option to disable detection via game-list
Added option to swap normals for manual values

 [[download v.1.17](https://www.dropbox.com/s/78dmlurg2ew2o66/fmt_ninjaripper_rip.py)]
## Post #112
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-25T21:59:55+00:00
- Post Title: Re: Ninja Ripper

Nice ! I wont be home until tomorrow, cant wait to try it out.
## Post #113
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-26T08:09:51+00:00
- Post Title: Re: Ninja Ripper

I confirm it works 100% with DRIV3R, even better than the original rip plugin did. Thanks so much Sammie!!
## Post #114
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T10:21:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> I confirm it works 100% with DRIV3R, even better than the original rip plugin did. Thanks so much Sammie!!
Can you upload some DRIV3R-rips, too? Because its still possible, that some games share the same .rip-structure, but need separate calculation for the UVs.
To prevent this behaviour I have to collect as many game-.rips as possible, to include special rules for this games. It doesn't matter if your rip work properly -  I need everything.
## Post #115
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-26T12:04:01+00:00
- Post Title: Re: Ninja Ripper

Two new rips, gonna see if I can do a couple more before I have to afk.

Included Mario Galaxy DX11 rip, the one I posted yesterday is DX9.

[http://filebeam.com/3d12f8e1abad94641e7da37b9413ea8a](http://filebeam.com/3d12f8e1abad94641e7da37b9413ea8a)

Edit:

Looks like the Mario rip is the same as DX9, the texture was corrupt. Had to re save it, and it became blue. I get this error with every DX11 rip.
If I open the DX11 textures in IrfanView they look fine, but the alpha goes to hell. If I open the dds in Photoshop they become blue. Noesis just gives error. Looks like diff from IrfanView + Alpha from Photoshop is the way to go.

Edit:

Two new rips, including Trine 2 re-rip.
[http://filebeam.com/a319aa09866655ebf91bdaf541470570](http://filebeam.com/a319aa09866655ebf91bdaf541470570)

Edit:

Crysis2
[http://filebeam.com/04621c875835680e08431265b257dda7](http://filebeam.com/04621c875835680e08431265b257dda7)

Edit:
Batman Arkham City
[http://filebeam.com/87eb88262298b1982fb25096eeb385b4](http://filebeam.com/87eb88262298b1982fb25096eeb385b4)
## Post #116
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T13:18:05+00:00
- Post Title: Re: Ninja Ripper

Added support for Lara Croft, Crysis 2, Batman Arkham City and Alan Wake's American Nightmare

Dont know whats wrong with the DX11 blue dds-files.. maybe a bug in ninjaripper? 
Looks like red/blue channels are inverted
## Post #117
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-26T13:35:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> RacingFreak wrote:I confirm it works 100% with DRIV3R, even better than the original rip plugin did. Thanks so much Sammie!!
Can you upload some DRIV3R-rips, too? Because its still possible, that some games share the same .rip-structure, but need separate calculation for the UVs.
To prevent this behaviour I have to collect as many game-.rips as possible, to include special rules for this games. It doesn't matter if your rip work properly -  I need everything.
With pleasure - the rip I tested and it worked all right: [http://www.solidfiles.com/d/5929b50da2/](http://www.solidfiles.com/d/5929b50da2/)

I will post DSF, DPL and some more rips once I get to them (as I remember DPL had problems with DXRip as far I remember)
## Post #118
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T14:02:10+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> With pleasure - the rip I tested and it worked all right: http://www.solidfiles.com/d/5929b50da2/

I will post DSF, DPL and some more rips once I get to them (as I remember DPL had problems with DXRip as far I remember)

There are flipped Normals on your Driv3r-Rips. Added Driv3r to the game list to fix that.

@deadca7
As I said, red<->blue channels are swapped
Example from the Metro 2033 Texture:
[](http://postimage.org/image/uaksprc1n/)[](http://postimage.org/image/9rwalw8hp/)
This is how the "Avatar"-movie was made
## Post #119
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-26T14:52:24+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> This is how the "Avatar"-movie was made
haha  
I only tried to invert them, I'll make a quick action script in Photoshop to swap them. Thanks 

3 new games
[http://filebeam.com/da06c8423322650943e46ea2330eca8c](http://filebeam.com/da06c8423322650943e46ea2330eca8c)

Batman need 'swap': 'X'

Edit:
GTA4
[http://filebeam.com/d47ff230f7c06cc6486750f155be5988](http://filebeam.com/d47ff230f7c06cc6486750f155be5988)
## Post #120
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T15:32:08+00:00
- Post Title: Re: Ninja Ripper

Can you upload some better Mario64 & Zelda Models? Can't check the UVs if the textures are too small. Should be at least 256px or higher. Some ingame-characters would be nice
## Post #121
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-26T15:40:02+00:00
- Post Title: Re: Ninja Ripper

Looks like 64x64 is the biggest they had back in 1996 

Edit:
or maybe not, I found some in SSB, wait a sec and I'll upload.

Edit:
Here [http://filebeam.com/06f5964c1094387258ebb7c79ae5f7a1](http://filebeam.com/06f5964c1094387258ebb7c79ae5f7a1)
## Post #122
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T15:56:54+00:00
- Post Title: Re: Ninja Ripper

lol..  

Zelda & Mario sharing the same .rip-struct.. I hope they use the same UV-calculation, too.
Tried something with this N64-Games, but can't really see, if its correct.

I have some other older games with idendical .rip-struct, but different UV-calculations. I don't know if its possible to detect this automatically.

Edit: Added support for Tomb Raider Underworld and GTA4.
## Post #123
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-26T16:17:20+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Edit: Added support for Tomb Raider Underworld and GTA4.

Wish we will see same for new Tomb Raider  Lara model looks kick ass, lol. Btw, most of these games has exporters. Still cant get what's a point to add their support.
## Post #124
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-26T16:27:56+00:00
- Post Title: Re: Ninja Ripper

Black Ops 2
[http://filebeam.com/aba41f389d2cceba517e0151aed8ddbd](http://filebeam.com/aba41f389d2cceba517e0151aed8ddbd)

I'm going afk, downloading 10 more games on steam while I'm afk.
## Post #125
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-26T16:38:27+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> Btw, most of these games has exporters. Still cant get what's a point to add their support.
Just because we can do it, lol. Its just easier to browse through the .rip-models in noesis, instead of searching for specific exporters for every single game. Most of this games are not supported by noesis itself, so its useful to have one plugin, which can handle the most game-models-rips for quick previews without extra converting.
## Post #126
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-26T18:46:16+00:00
- Post Title: Re: Ninja Ripper

Just a side question - how do you rip N64 models?
## Post #127
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-26T23:49:14+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Just a side question - how do you rip N64 models?
I used Dolphin. I guess you can do it with a N64 emu if you find a dx9 video plugin that works, I know Rice used to be dx9 but now it's dx8. Please give me a word if you find a dx9 plugin that works.

Edit:
Bionic Commando rip
[http://filebeam.com/07708cdc8eb8d6a2aaba66517e7436f2](http://filebeam.com/07708cdc8eb8d6a2aaba66517e7436f2)

Uploading some more rips tomorrow
## Post #128
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T08:32:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Uploading some more rips tomorrow

Take your time. I'm away after tomorrow for 2-3 days.  

Btw: which tool can rip models from UPLAY-games like Far Cry 3 or Assassins Creed III on x64-systems? Had no luck with 3D Ripper DX or NinjaRipper.
Or does anybody know extractors+converters for this games? Far Cry 3 has an extractor (Gibbed Tools Dunia 2) but can't find anything to extract the meshes.
## Post #129
- Username: Sanya
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Mar 17, 2011 5:36 pm
- Post datetime: 2013-01-27T09:19:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> deadca7 wrote:Uploading some more rips tomorrow

Take your time. I'm away after tomorrow for 2-3 days.  

Btw: which tool can rip models from UPLAY-games like Far Cry 3 or Assassins Creed III on x64-systems? Had no luck with 3D Ripper DX or NinjaRipper.
Or does anybody know extractors+converters for this games? Far Cry 3 has an extractor (Gibbed Tools Dunia 2) but can't find anything to extract the meshes.

eh, FC3 is rippable by ninja. Only one problem is that UV are very big, so you need scale it down. For AC there is ForgeX, but I dont know if author did support for newer one.
## Post #130
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T10:02:14+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sanya
>
> eh, FC3 is rippable by ninja. Only one problem is that UV are very big, so you need scale it down. For AC there is ForgeX, but I dont know if author did support for newer one.

If I start FC3 with NinjaRipper only a message appears with a "cant inject"-Text. Tested all wrappers and the alternative indruder, but got always the same error-message.  
And ForgeX doesnt work for me. The Tool is crashing after clicking the .exe on Win7 x64. Tried to run it on a virtual 32bit XP.. but crashing too.
## Post #131
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-27T10:06:23+00:00
- Post Title: Re: Ninja Ripper

Haven't tried FC3 yet, but when I rip AC3 I get some textures and a lot of wiggly flat 3d planes.

Duke Nukem Forever
[http://filebeam.com/d2d685be2e810e42f18ce2f9d1757c0e](http://filebeam.com/d2d685be2e810e42f18ce2f9d1757c0e)

Hitman Absolution - Weird geo and some textues are pink.
[http://filebeam.com/1b68da17ed314fb0e36ca3da0135038a](http://filebeam.com/1b68da17ed314fb0e36ca3da0135038a)

Singularity
[http://filebeam.com/ac79fbcbd98a11c51a76b175e7dac56c](http://filebeam.com/ac79fbcbd98a11c51a76b175e7dac56c)

Shadow Harvest
[http://filebeam.com/c1d523cef1d331e192f59a1ec0f99612](http://filebeam.com/c1d523cef1d331e192f59a1ec0f99612)

Need for Speed Hot Pursuit
[http://filebeam.com/b224754524c17f31e5a849a45e9289ef](http://filebeam.com/b224754524c17f31e5a849a45e9289ef)

Dragon Age
[http://filebeam.com/2f59a689e807ff50d30cfe4317c6f541](http://filebeam.com/2f59a689e807ff50d30cfe4317c6f541)

and Batman need 'swap':'X'

Googled AC3 dx, looks like the game is using a mix of DX10 and DX11. NinjaRipper does not support DX10.

Are you leaving today or monday ?
## Post #132
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T10:19:45+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> when I rip AC3 I get some textures and a lot of wiggly flat 3d planes.
I got nothing. Only a empty _Ripper-folder. 

> Reply from deadca7
>
> Are you leaving today or monday ? depends on your timezone, lol. In ~10h.
## Post #133
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-27T11:22:19+00:00
- Post Title: Re: Ninja Ripper

Thanks deadca7 for the great help, I have aswell got Wii64 rips, but they are a bit screwed up, here's a sample from Automobili Lamborghini: [http://www.solidfiles.com/d/5d22c72964/](http://www.solidfiles.com/d/5d22c72964/)

I also confirm NinjaRipper COMPLETELY rips textures from PCSX2, only needed is to flip RGB > BGR 

Not sure if something can be done about models.

EDIT: NinjaRipper WORKS with PCSX2 in DX11!! But all im receiving are parts of objects, weighing about 3-12kb
## Post #134
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T12:02:57+00:00
- Post Title: Re: Ninja Ripper

@deadca7
Added your games. The Hot Pursuit UVs are a little bit crappy. But the textures are too bad to fix that. Maybe search for a better model with colurful textures, not 90% black 

Hitman Absolution has some special kind of UV data. Some kind of offset-shifting.
## Post #135
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-27T12:17:52+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
>  But all im receiving are parts of objects, weighing about 3-12kb
No prob. Looks like the same mess that you get from n64 games.

> Reply from Sammie
>
> Added your games.
Thanks again

Mafia - Works fine, but maybe you want the data
[http://filebeam.com/d9cbca9b54a08449446981d0262af5e9](http://filebeam.com/d9cbca9b54a08449446981d0262af5e9)
## Post #136
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T13:02:23+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> Mafia - Works fine, but maybe you want the data
http://filebeam.com/d9cbca9b54a08449446981d0262af5e9
The telephone with mirrored dial plate is correct? 
Maybe the developers of mafia made a mistake on the uv-layout. Can you check if the dial plate is mirrored in the game too?
## Post #137
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-27T13:31:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> The telephone with mirrored dial plate is correct?

I didn't notice that :p Looks like the whole model is flipped.
## Post #138
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T14:27:36+00:00
- Post Title: Re: Ninja Ripper

Hm, thats bad. For this bug I have to flip the model without flipping the normals or need a separate flip-normals function. Can't find such a function in noesis at the moment. Whatever.. you can't have everything.
## Post #139
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-27T15:05:28+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Whatever.. you can't have everything.
True true, thanks for trying though.

FEAR
[http://filebeam.com/d60bd5e4770316d2f48ed033a0e83b52](http://filebeam.com/d60bd5e4770316d2f48ed033a0e83b52)
## Post #140
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T16:16:46+00:00
- Post Title: Re: Ninja Ripper

Tried to flip the Normals manually through the faces-parser now. 
Works for the telephone, but should be tested on more Mafia-Models. For the telphone I have to swap the x-z vertices additionally to mirror the whole thing.
You send me two Mafia-Models and the other one was not flipped - so I can't say if its really nescessary to mirror all models.
I used the new function for the other flipped models (mario, zelda, streetfighter) and removed the Transformation-Matrix.
## Post #141
- Username: Andrakann
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-01-27T16:25:29+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> Hm, thats bad. For this bug I have to flip the model without flipping the normals or need a separate flip-normals function. Can't find such a function in noesis at the moment. Whatever.. you can't have everything.

you can flip normals or faces or uv's. you can try 

rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1)

you can also pack and unpack buffers and do whatever math you want to them
if you need an example of that let me know.
## Post #142
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-27T16:28:07+00:00
- Post Title: Re: Ninja Ripper

> Reply from chrrox
>
> you can also pack and unpack buffers and do whatever math you want to them
if you need an example of that let me know.
did it my own way 
but okay, rewrite to RPGOPT_TRIWINDBACKWARD, cuz its shorter - thx chrrox
## Post #143
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-27T17:10:38+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> did it my own way 
but okay, rewrite to RPGOPT_TRIWINDBACKWARD, cuz its shorter - thx chrrox

Nice, you did it!

Wolfenstein
[http://filebeam.com/f3735013c06fef9f4d2888fd9c41880a](http://filebeam.com/f3735013c06fef9f4d2888fd9c41880a)

Serious Sam 3
[http://filebeam.com/587f2a971799178930b826babf738bcb](http://filebeam.com/587f2a971799178930b826babf738bcb)

Painkiller Recurring Evil
[http://filebeam.com/627df38f8313d740db5373da99ebc405](http://filebeam.com/627df38f8313d740db5373da99ebc405)
## Post #144
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-01-28T03:52:46+00:00
- Post Title: Re: Ninja Ripper

Hi people. I dont really know where to ask for help, but i saw a guy having the same problem as i have in this topic, so i try here.

i ripped a scene using "3d ripper dx" from Driver: San Francisco game, cause i want to render some scenes and that map is perfect for me. models are perfect and some textures are seem to be okay, but other textures uvw map coordinates are all messed up. problem is with buildings mostly. a lot of objects are in a single mesh, the mesh has a multi/sub-object with 8 sub-material (i dont really know why, they only use the first one i believe). the first sub-material is a 4096*4096 texture atlas (i think its called like that). ive tried now a few things to fix the problem, but i arrived to the point where i start to cry when i even think about it  Please help me if you can.

EDIT: today i tried Ninja Ripper too, got the same result on the buildings, tried changing the UV coordinates when importing, it had some effect but i didnt find the correct settings 

here is what it looks like in the game:



this is how it looks when i import the scene to 3ds max and render:



this is how the UVW map looks like, selected the stairs (the 4096*4096 texture is somewhere in the middle of the mess T_T):



zoomed in to show how bad the UVW coordinates are:



here the multi/sub-object:



and the first sub-material (4096*4096 texture atlas):





im really desperate to solve this problem, help me out if you can please. thanks for reading
## Post #145
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-28T07:17:14+00:00
- Post Title: Re: Ninja Ripper

Rescale the UV? Also there's a new 3D Ripper DX version 1.8.2.

My best bet is that its just like that, so, just remap them yourself.
## Post #146
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-01-28T07:27:20+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Rescale the UV? Also there's a new 3D Ripper DX version 1.8.2

im using that version (also tried 1.8, was the same)

i tried rescaling the UV, but there are elements (for example when there is 3 same window on a building) that supposed to use the same part of the texture, but they are placed next to each other and if i simply rescale, one window is good, but the other two is not. so the problem is with the coordinates, i just dont know what causes it. the ripper gets the wrong coordinates or they get messed up at importing :S

something like this happenes when i rescale:
## Post #147
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-28T07:48:05+00:00
- Post Title: Re: Ninja Ripper

> Reply from muroko
>
> i tried rescaling the UV, but there are elements (for example when there is 3 same window on a building) that supposed to use the same part of the texture, but they are placed next to each other and if i simply rescale, one window is good, but the other two is not. so the problem is with the coordinates, i just dont know what causes it. the ripper gets the wrong coordinates or they get messed up at importing :S
Upload some of the Ninjaripper .rip-Files + .dds-Textures
## Post #148
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-01-28T09:17:16+00:00
- Post Title: Re: Ninja Ripper

I don't know if these are bad rips, or the vertices are loaded wrong.

[http://filebeam.com/a8c70fc7e86a6d022067d06dfd5873b6](http://filebeam.com/a8c70fc7e86a6d022067d06dfd5873b6)
## Post #149
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-01-28T09:47:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> muroko wrote:i tried rescaling the UV, but there are elements (for example when there is 3 same window on a building) that supposed to use the same part of the texture, but they are placed next to each other and if i simply rescale, one window is good, but the other two is not. so the problem is with the coordinates, i just dont know what causes it. the ripper gets the wrong coordinates or they get messed up at importing :S
Upload some of the Ninjaripper .rip-Files + .dds-Textures

Thanks for looking into it, im really stressed for days now -_-

[http://www.mediafire.com/?4zgbldbnyx6acqq](http://www.mediafire.com/?4zgbldbnyx6acqq)

file : Mesh_0377_rip.zip
contents: 
- Mesh_0377.rip            - several building-parts in one single mesh
- Mesh_0377_rip.log       - part of the log file created by ninja ripper
- Tex_0312_0.dds          - 4096*4096 texture atlas (basically the texture applied to the mesh)
- Tex_0312_1.dds          - random textures , i dont know why they are even here lol
- Tex_0316_6.dds
- Tex_0323_3.dds
- Tex_0323_4.dds
- Tex_0375_2.dds
## Post #150
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-28T10:34:41+00:00
- Post Title: Re: Ninja Ripper

I still don't get what's the deal with these stairs  
Just remap them to this texture:
[](http://i.snag.gy/BiNYe.jpg)
Problem solved?
## Post #151
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-01-28T11:37:33+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> I still don't get what's the deal with these stairs  
Just remap them to this texture:

Problem solved?

the problem is not the stairs only, but the whole scene. the scene contains around 1000 meshes (and its not like one building is one mesh, a mesh can be for example all the front sides of several buildings), i would say about 10 percent of the meshes are textured with a solo texture (mostly the ground and road , cars seem to be okay too), the other 90% (buildings and stuff) are mapped on this one texture atlas. i replaced the texture atlas with simple red texture to show which part of my scene is wrong mapped, and i made the stairs green to show the size of this thing lol ... im about to cry if i think about remapping everything that is wrong.

check out this image to see how big the problem is:
[http://i.imgur.com/jiSizlP.jpg](http://i.imgur.com/jiSizlP.jpg) (size is too big to post it here i guess)

and yeah i could make the scene smaller, cut the parts i dont need and remap the remaining buildings myself, but i plan to render more stuff using this map, since its very realistic and san francisco matches the theme of my project
## Post #152
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-01-28T13:05:58+00:00
- Post Title: Re: Ninja Ripper

Ok, not really related to the thread...

I will suggest you to rip the map from the shift mode instead.
## Post #153
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-28T15:33:23+00:00
- Post Title: Re: Ninja Ripper

I think its not possible to fetch the correct UV-Coords from this file, cuz there is no info about how to use the atlas-texture.
The TEXCOORD-Block has 4 floats.. the last two are secondary UVs for Lightmap. I'am able to convert this values to match with the lightmap-texture.
The first two values have to be the regular UV Coords, but every face is centered nearly to 0|0-Point in UV-Space.. so we need another x/y value which is describing the position on the texture-atlas. And as far as I can see this info is not in the .rip-file.
## Post #154
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-01-28T16:33:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Ok, not really related to the thread...

I will suggest you to rip the map from the shift mode instead.

I tried that, there was indeed a difference, when i ripped from shift mode, the meshes got a single standard texture instead of the multi/sub-object. still the outcome is the same 

> Reply from Sammie
>
> I think its not possible to fetch the correct UV-Coords from this file, cuz there is no info about how to use the atlas-texture.
The TEXCOORD-Block has 4 floats.. the last two are secondary UVs for Lightmap. I'am able to convert this values to match with the lightmap-texture.
The first two values have to be the regular UV Coords, but every face is centered nearly to 0|0-Point in UV-Space.. so we need another x/y value which is describing the position on the texture-atlas. And as far as I can see this info is not in the .rip-file.

thanks again for looking into it, so basically there is little chance that this can be solved by other than manual remapping every single face?
## Post #155
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-01-28T20:11:07+00:00
- Post Title: Re: Ninja Ripper

Its easier to make the scene by yourself. The buildings are really primitve and often duplicated over the scene. Just fix uv-textures for 4-5 different buildings, and copy the buildings again over your scene. All you have to do is to move the UVs for the other buildings in the atlas-texture to create many different-looking buildings.
## Post #156
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-01-29T17:38:32+00:00
- Post Title: Re: Ninja Ripper

Most games will set program variables to scale+bias the UV's on a per-draw basis for texture atlases. Ninja Ripper should be updated to dump those for each draw as well. (it shouldn't be much overhead since the wrapper can detect which ones are actually used)
## Post #157
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-02-02T11:32:30+00:00
- Post Title: Re: Ninja Ripper

Sorry, i have problems with Hitman Absolution,  the mesh are like flat.. how are the correct x-y-z coordinates to import 
and also problems with the textures uv's ..
also the textures are a kind of blue... 

please help! and sorry for my english
## Post #158
- Username: deadca7
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Jun 19, 2010 1:59 pm
- Post datetime: 2013-02-02T12:06:49+00:00
- Post Title: Re: Ninja Ripper

> Reply from fil1969
>
> Sorry, i have problems with Hitman Absolution,  the mesh are like flat.. how are the correct x-y-z coordinates to import 
and also problems with the textures uv's ..
also the textures are a kind of blue... 

please help! and sorry for my english

To fix the blue textures you need to swap the red channel with the blue channel.
Here's my quick and dirty Photoshop script that does the job for you [http://filebeam.com/349161abf2095301b9f2c1cf1002c0d6](http://filebeam.com/349161abf2095301b9f2c1cf1002c0d6)
Almost every DX11 game I have ripped with NinjaRipper has this channel bug.

To fix the mesh you need to upload the rips so Sammie can take a look at it
## Post #159
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-02-02T12:15:26+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> fil1969 wrote:Sorry, i have problems with Hitman Absolution,  the mesh are like flat.. how are the correct x-y-z coordinates to import 
and also problems with the textures uv's ..
also the textures are a kind of blue... 

please help! and sorry for my english

To fix the blue textures you need to swap the red channel with the blue channel.
To fix the mesh you need to upload the rips so Sammie can take a look at it

Thank you very much.. i'm done with textures.. about the meshes, i see on the first post that the model is perfect..  so maybe he can tell me how are the coordinates...
## Post #160
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-02-02T14:21:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from fil1969
>
> about the meshes, i see on the first post that the model is perfect..  so maybe he can tell me how are the coordinates...
Many games have different meshes with different blocksizes and uv-coordinates. And some of them have no clear float-uv coordinates or need special UV-calcluation.
Upload the mesh + textures and I will take a look.
## Post #161
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-02-02T14:31:36+00:00
- Post Title: Re: Ninja Ripper

> Reply from Sammie
>
> fil1969 wrote:about the meshes, i see on the first post that the model is perfect..  so maybe he can tell me how are the coordinates...   
Many games have different meshes with different blocksizes and uv-coordinates. And some of them have no clear float-uv coordinates or need special UV-calcluation.
Upload the mesh + textures and I will take a look.

Ok Sammie, thank you for your reply

here the 2 meshes: [http://www.mediafire.com/?eelybospz4tsglv](http://www.mediafire.com/?eelybospz4tsglv)
are arms and gloves..  as you can see are almost flat..  i can scale them in Max is not a problem, but why some parts are good like the pants or the jiacket and some are all messed up?
## Post #162
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-02-02T15:25:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from fil1969
>
> are arms and gloves..  as you can see are almost flat..  i can scale them in Max is not a problem, but why some parts are good like the pants or the jiacket and some are all messed up?Its a good question... The Vertex-X-values are to small (should be multiplied with 3 or something). Maybe a ripper-bug or had to do with the T-Pose on DX11 Games. Or the vertices need weights (relationship of vertices to bones) to move to their correct position. Difficult to say..   The .rip files doesn't contain any bone-infos, so it is impossible to test it. 

> Reply from Tosyk @ cgig.ru
>
> videoadapter rendering only veretices/triangles and not animation/skeleton/bones, so you can't rip what don't even exist
## Post #163
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-02-10T15:06:56+00:00
- Post Title: Re: Ninja Ripper

Hi, I've encountered normals issues and UV mapping not working in El Matador and Assassin's Creed II. Here are samples:

AC2: [http://www.solidfiles.com/d/fb9c3c057c/](http://www.solidfiles.com/d/fb9c3c057c/)

El Matador: [http://www.solidfiles.com/d/21704c3880/](http://www.solidfiles.com/d/21704c3880/)

I hope you make a fix for them! Thanks
## Post #164
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-02-11T16:07:46+00:00
- Post Title: Re: Ninja Ripper

found a strange issue :
when capturing several frames , the textures come in the textures folder but the texture name in the rip file have a "_0" or "_1" added to the filename so they need to be reassignated manually in max, would be better to rip the all textures on a frame basis,
like frame0000 , textures0000 and so on so the captured filename match the one in the rip file, the conter for textures is already incrementing so on the second textures rip filenames won't match anymore...

anyway nice tool you got here
## Post #165
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-02-13T16:59:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Hi, I've encountered normals issues and UV mapping not working in El Matador and Assassin's Creed II. Here are samples:

AC2: http://www.solidfiles.com/d/fb9c3c057c/

El Matador: http://www.solidfiles.com/d/21704c3880/

I hope you make a fix for them! Thanks Aside from the fact that the UVs are wrong, most of rips have no texture-names, or wrong texture-names.
Cant find any model with the correct texturename inside, so its hard to fix the UVs. Have you tried another wrapper?
Btw: you can take a look into [ForgeX](http://forum.xentax.com/viewtopic.php?f=10&t=6617&start=90) to extract AS2-meshes.
## Post #166
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-02-16T03:43:10+00:00
- Post Title: Re: Ninja Ripper

Two quick notes on Ninja Ripper:

First, both Ghost Recon Online and Ghost Recon Future Soldier can be ripped, but the models come out squished into a cube. I've worked with meshes that are distorted on one axis, but this GR models are quite unusable. Is there anything that can be done to fix this?

Second, what is the solution for when Ninja Ripper does not respond to ripping meshes? On certain games... Rogue Warrior and Red Faction Armageddon, for example... the textures rip just fine when using the hotkey for textures, but nothing happens at all when I use the hotkey for ripping the scene. I've tried swapping the hotkeys between the scene and textures, but I get the same results. Any help would be very appreciated.

Thanks!
## Post #167
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2013-02-17T09:40:42+00:00
- Post Title: Re: Ninja Ripper

some fix for dead island pc rip files
add this to the game list hash list:

```
	#****************DEAD ISLAND RIP FILES FORMATS FIX *****************************
	'6e7a202e7d5ffbd0885e9589eea83cdc': {'name':'Dead Island 0001','data':[0,1,2,13,14,15,11,12,-1,-1],'func':'div_4096'},# 84
	
	'f367d4a20746efadeddfcc6ae767544e': {'name':'Dead Island 0002','data':[0,1,2,18,19,20,16,17,-1,-1],'func':'div_4096'},# 136
	'8bb23fd3e3e1bf371afaef9f8a7f17b5': {'name':'Dead Island 0004','data':[0,1,2,18,19,20,16,17,-1,-1],'func':'div_4096'},# 136
	'dd16df118ad14662e40abb16c124795a': {'name':'Dead Island 0010','data':[0,1,2,18,19,20,16,17,-1,-1],'func':'div_4096'},# 136
	'be884a934bad0465fd9142464c1a0b48': {'name':'Dead Island 0015','data':[0,1,2,18,19,20,16,17,-1,-1],'func':'div_4096'},# 168
	
	'43799d79a2f337d1d7a735aa57ad4ce2': {'name':'Dead Island 0003','data':[0,1,2,17,18,19,15,16,-1,-1],'func':'div_4096'},
	
	'b17225a8de64252e2d79d74792668539': {'name':'Dead Island 0005','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},
	'355ae0f6b6cd190deaf00eb6a6401995': {'name':'Dead Island 0007','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},
	'90e632eda192862a21a7e52d4f2d5922': {'name':'Dead Island 0008','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},
	'bfa3d20a38fd966c2e98e3af1802e4c9': {'name':'Dead Island 000A','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},
	'c21e7aff9729d4ca8e02e1a18370fed1': {'name':'Dead Island 000D','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},	
	
	'b2d59290d281aacb80218a1af52e014d': {'name':'Dead Island 000B','data':[0,1,2,9,10,11,7,8,-1,-1],'func':'div_4096'},
	
	'092d5d99c1b066ab61b2ea12dfb01386': {'name':'Dead Island 000C','data':[0,1,2,14,15,16,12,13,-1,-1],'func':'div_4096'},# 112
	'f6328e74df479654dc9e2e40dd8932b3': {'name':'Dead Island 000E','data':[0,1,2,14,15,16,12,13,-1,-1],'func':'div_4096'},# 112
		
	'3e745432fd038b17e6bb38fb091eba4c': {'name':'Dead Island 0009','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 120
	'7c93acecbebdedd0ce7f969c697778f4': {'name':'Dead Island 000F','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 120
	'47bdaa63d764f467983cb37358fed9e7': {'name':'Dead Island 0011','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 128
	'7a1d60e12091aec35d6f76e29a8cd96b': {'name':'Dead Island 0012','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 104
	'b6dad306481432386b224517f99907cf': {'name':'Dead Island 0014','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 104
	
	'7dd68b6e784263063402e2ef6a5f03f2': {'name':'Dead Island 0013','data':[0,1,2,14,15,16,8,9,-1,-1],'func':'div_4096'},# 88
	
	'13580398fc475cced5ac1f41be8c61f7': {'name':'Dead Island 0018','data':[0,1,2,10,11,12,4,5,-1,-1],'func':'div_4096'},# 144
	'206c4fd3be76dc96e5596e2bb932d09e': {'name':'Dead Island 0017','data':[0,1,2,10,11,12,8,9,-1,-1],'func':'div_4096'},# 72
	
	'a05ff63b36d94bd1b9c1d01a110dc241': {'name':'Dead Island 0016','data':[0,1,2,6,7,8,4,5,-1,-1],'func':'div_4096'},# 48  (only pos and bones data, no uv or normals)
	#****************DEAD ISLAND RIP FILES FORMATS FIX  END *****************************

```


it will fix several mesh vertex def with pos, normal and uv correct, only texture need to be set manually.
## Post #168
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2013-02-20T19:01:52+00:00
- Post Title: Re: Ninja Ripper

What if the Game it self has its own DX3d9_##.dll (in my case D3DX9_41.dll)? who whould i amke its leak form that the Old DXRipper wokred on NiGHTS (Steam Version) Before but got oddly culled  xflipped posed models this one dose not respond with it other then occasionally ripping textures
## Post #169
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2013-02-25T07:23:14+00:00
- Post Title: Re: Ninja Ripper

Hi

New version here (For tests only. After test will moved to cgig.ru)
+ No mesh rip bug fix 

[http://blackninja2000.narod.ru/files/ninjaripper114.7z](http://blackninja2000.narod.ru/files/ninjaripper114.7z)
## Post #170
- Username: Chezy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 02, 2011 11:57 pm
- Post datetime: 2013-02-27T15:31:41+00:00
- Post Title: Re: Ninja Ripper

Hey! Just discovered your beautiful tool, but I'm having a problem. I can't rip from L.A. Noire. When I run the .exe with the intruder mode, nothing happens when I press F10. When I try to start the game with the D3D9-Wapper, the game crashes. Here is a screenshot:

[](http://postimage.org/image/nuh9mhjv3/)

Now, as far as I know, Tosyk has already used your tool to rip from L.A. Noire, so please tell me what I'm doing wrong
## Post #171
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2013-02-28T03:23:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi

New version here (For tests only. After test will moved to cgig.ru)
+ No mesh rip bug fix 

http://blackninja2000.narod.ru/files/ninjaripper114.7z

I was excited to see this, but I'm afraid I'm still experiencing the no mesh rip bug. I've seen you say before that it may be related to my computer's setup rather than the program itself. Anything you suggest checking on specifically?
## Post #172
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2013-03-03T23:31:01+00:00
- Post Title: Re: Ninja Ripper

I read the guide and readme you posted,said about wrapper mode.here[http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/)

> wrapper modes - a modes in which ripper will copy d3dX.dll in to a folder containing the executable file of the application/game, after this ripper windows can be closed, then you can start the game from any location, copied d3dX.dll will automatically clinging into the game. Thus no longer need to run the ripper himself for this game

For the game like Aion,I've done this trick,but it doesn't work.Because it's launcher and game executables are different.
Did i do anything wrong?When i choose "D3D9 wrapper" then next should i push "Run" button once to activate this mode?
I tried,but it doesn't rip aion's model.
I know there are other way to rip models from aion,but i use this game's character creation to shape a face,so i hope i can rip my customized character face out.Thx:)
## Post #173
- Username: muroko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jun 28, 2011 3:22 am
- Post datetime: 2013-03-04T02:20:18+00:00
- Post Title: Re: Ninja Ripper

i think you can run Aion without the launcher if you rename the aion.bin to aion.exe
## Post #174
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2013-03-04T02:45:57+00:00
- Post Title: Re: Ninja Ripper

ya,,but i don't know the server ip
here is an Aug parameter we suppose to use 

> -ip:xxx.xxx.xxx.xxx-port:2106 -cc:2 -noauthgg -noweb -lang:enu

Ip is different now,,i don't know it's current ip.Even if i know the ip.
I can not input all of these parameters in Ninja Ripper's Aug section.
Current version only allow u input 50 chars including space.
There are more than 50 to launch it manually,,,Can i launch my customized bat file instead?

Edit:bat launch doesn't work for ninja ripper.
Can u make next update have more than 50 chars in Aug section?
## Post #175
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-03-04T06:29:10+00:00
- Post Title: Re: Ninja Ripper

I have modified the 3DS Max script. It now includes a progress bar and can import over 2,000 objects in little over a minute on my computer.

Changes that I made:

You can now flip on the XZ axis if your models appear inverted!
Added progress bar
Removed a lot of unnecessary information being printed
End of script will show a popup message with how long it took to import
"Debug" mode allows you to turn on useless print messages, VERY SLOW.
Program no longer hangs when importing many objects 
Imports are now 50 - 75% faster. I was able to import 2,001 objects in 1 minute and 30 seconds!

Download: [https://dl.dropbox.com/u/69162797/misc/ ... b7_cl69.ms](https://dl.dropbox.com/u/69162797/misc/ninja_importerb7_cl69.ms)
Script modified with 3ds Max 2011!

Please leave bug reports or feedback here in this current thread. I may consider feature requests if it is feasible and within my capabilities.

 Enjoy!
## Post #176
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2013-03-05T05:31:33+00:00
- Post Title: Re: Ninja Ripper

> Reply from falconcool
>
> For the game like Aion,I've done this trick,but it doesn't work.
I think your problem is anticheat blocking ripper injection.
Try on "free shard" servers, they do not use advanced anticheat system.
## Post #177
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-03-10T08:19:28+00:00
- Post Title: Re: Ninja Ripper

So, can someone give me some advice in ripping models from Hitman Absolution, well all know they come in pieces, not just one mesh or however they were modeled. Some UV coords, Vertex or w/e else which could help me, because plain like that without settings, UVs are to hell, hands lets say come in two different meshes, getting the UV right is...well a pain in the ass.
## Post #178
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2013-03-10T08:44:36+00:00
- Post Title: Re: Ninja Ripper

> Reply from CarLuver69
>
> I have modified the 3DS Max script. It now includes a progress bar and can import over 2,000 objects in little over a minute on my computer.

Changes that I made:

You can now flip on the XZ axis if your models appear inverted!
Added progress bar
Removed a lot of unnecessary information being printed
End of script will show a popup message with how long it took to import
"Debug" mode allows you to turn on useless print messages, VERY SLOW.
Program no longer hangs when importing many objects 
Imports are now 50 - 75% faster. I was able to import 2,001 objects in 1 minute and 30 seconds!

Download: https://dl.dropbox.com/u/69162797/misc/ ... b7_cl69.ms
Script modified with 3ds Max 2011!

Please leave bug reports or feedback here in this current thread. I may consider feature requests if it is feasible and within my capabilities.

 Enjoy!

thank you very much for your script, it works great on max 2013.. but i want ask, is possible make it for old max versions? like max 2009? i use very often that one! thank you!
## Post #179
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2013-03-10T15:21:54+00:00
- Post Title: Re: Ninja Ripper

nice program and script. thank you.

I've used on tomb raider 2013 and works fine.
I've try on agrar simulator 2013 and it does'nt export any data,but log have no error.Can put me in right way?
## Post #180
- Username: tomatofarmer
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu May 17, 2012 7:54 pm
- Post datetime: 2013-03-10T17:39:48+00:00
- Post Title: Re: Ninja Ripper

I second that request for a 2009 compatible script if possible.
## Post #181
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2013-03-11T00:33:08+00:00
- Post Title: Re: Ninja Ripper

i've try some games,and i understand why in some game doesn't work.
It's works only if game executable is in exe file you select,but some game use exe to check key and run game by a dll.
Is possible to fix it?
## Post #182
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2013-03-11T14:36:46+00:00
- Post Title: Re: Ninja Ripper

devilkkw May be in next versions
## Post #183
- Username: devilkkw
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Mar 10, 2013 4:21 pm
- Post datetime: 2013-03-11T17:18:46+00:00
- Post Title: Re: Ninja Ripper

Thank you so much
## Post #184
- Username: Sammie
- Rank: veteran
- Number of posts: 106
- Joined date: Wed Apr 25, 2012 7:27 pm
- Post datetime: 2013-03-12T08:49:07+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> devilkkw May be in next versions
Is it possible to integrate the name of the exe, a exe-checksum or something else in the .rip files in the next version?
This would be easier for identifying games and making specific rules for all importer-plugins.
## Post #185
- Username: Chezy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 02, 2011 11:57 pm
- Post datetime: 2013-03-25T18:12:02+00:00
- Post Title: Re: Ninja Ripper

Don't want to bother or to be annoying, but I'm still having this problem, so I'd be very glad if someone could help me out, please! 

> Reply from Chezy
>
> Hey! Just discovered your beautiful tool, but I'm having a problem. I can't rip from L.A. Noire. When I run the .exe with the intruder mode, nothing happens when I press F10. When I try to start the game with the D3D9-Wapper, the game crashes. Here is a screenshot:



Now, as far as I know, Tosyk has already used your tool to rip from L.A. Noire, so please tell me what I'm doing wrong
## Post #186
- Username: pkmnmstr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 05, 2012 3:55 am
- Post datetime: 2013-03-26T09:56:57+00:00
- Post Title: Re: Ninja Ripper

I can't get NinjaRipper working at all.
I'm using Windows 7 and I've tried running it on Counter-strike in DX9 mode and the Dolphin emulator in DX9 and DX11 modes.
I've tried changing the hotkey and folder but nothing happens in any case.

Any tips?
## Post #187
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2013-04-01T08:05:00+00:00
- Post Title: Re: Ninja Ripper

Run as Administrator or/and disable antivirus.
## Post #188
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-04-02T08:51:11+00:00
- Post Title: Re: Ninja Ripper

I have a question to peoples who try to rip models from PCSX2: are ripped models in T-pose or not (as I know models ripped from Dolphin are T-posed)?
And also: anybody tryed to rip models from Chankast (or other Dreamcast emulator) with Ninja Ripper? If yes, the models are T-posed?
## Post #189
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-04-02T10:40:44+00:00
- Post Title: Re: Ninja Ripper

NinjaRipper didnt work in any DC emulator last time i tried, and as PCSX2 is improving, models are being in T-pose now, but still with a lot problems. Maybe the Noesis script can be further developed?
## Post #190
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-04-10T10:44:31+00:00
- Post Title: Re: Ninja Ripper

Are you tryed to rip DC scenes with stereoscopic PVR plug-in (3D Ripper DX for example can make normal (non-flat) 3D rips only with this plug-in)?
## Post #191
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-04-10T17:22:58+00:00
- Post Title: Re: Ninja Ripper

Have you got it to work properly? I never managed to do so, PM me if you have working NullDC build with this plugin and I will try to test. Interesting!
## Post #192
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-04-10T20:33:18+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> NinjaRipper didnt work in any DC emulator last time i tried, and as PCSX2 is improving, models are being in T-pose now, but still with a lot problems. Maybe the Noesis script can be further developed?

Wait NinjaRipper also works on PCSX2? wich version and wich Graphic plugin you need to test ?

And for NullDC i tried using the stereoscopic PVR plug-in on the new versions but i only get the textures and no mesh if i use 3Dripper
i get a flat rip (Iam on windows 7 x64)
## Post #193
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-04-11T05:30:37+00:00
- Post Title: Re: Ninja Ripper

Should work on any revision with the GSdx plugin.

Also I cant confirm for T-pose as last time I tried it, was on a car from The Getaway.
## Post #194
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2013-04-18T15:44:36+00:00
- Post Title: Re: Ninja Ripper

great ripper! thanks for it!
 my experiences with it so far:

LA Noire:
rips textures and meshes, but the screen goes black, and freezes. i have to restart a game every time i try to rip something.

Battlefield 3:
works as expected. Although there is a noesis plugin related problem: the meshes have no texure in the viewer.
## Post #195
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2013-04-20T20:48:49+00:00
- Post Title: Re: Ninja Ripper

> Reply from AceVentura
>
> the screen goes black, and freezes. i have to restart a game every time i try to rip something.
Try Alt-Tab then back, works for me in Dead Space 2 and 3 (no T-pose in both, so i prefer 3DRipperDX for ripping).
## Post #196
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-04-21T03:21:47+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Should work on any revision with the GSdx plugin.

Also I cant confirm for T-pose as last time I tried it, was on a car from The Getaway.
I don't know what installments of PCSX2 to use, and which DirectX to use. (9 or 11)
## Post #197
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2013-04-22T10:12:40+00:00
- Post Title: Re: Ninja Ripper

Latest SVN; DX11 SW preferably.
## Post #198
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2013-04-22T15:05:18+00:00
- Post Title: Re: Ninja Ripper

> Reply from RacingFreak
>
> Latest SVN; DX11 SW preferably.
I'm sorry but do you mind, lending a hand with a tutorial? I'm on SW DX11 on the latest SVN, yet the frames don't show rip files.
## Post #199
- Username: Chezy
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Oct 02, 2011 11:57 pm
- Post datetime: 2013-04-22T15:44:38+00:00
- Post Title: Re: Ninja Ripper

NinjaRipper is working with my L.A. Noire now. But when I import the models, they are strechted like this:

[](http://postimg.org/image/om9pys1sf/)

I could just scale them right, but the problem is that other parts, such as the engine or the doors, are scaled and positioned differently than the body, so it's impossible for me to put them together correctly. Can somebody help me out with this? Is it maybe because of some wrong monitor settings? Thanks in advance
## Post #200
- Username: Natan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 10, 2012 10:06 pm
- Post datetime: 2013-04-23T11:58:19+00:00
- Post Title: Re: Ninja Ripper

Hi to all,
I just found this great tool....
I have two quick questions:
1: someone ever tried to rip models from Wargame european escalation?
I managed to get models and textures, but I can not find the right parameters for the UV mapping.
I had tested the different possibilities,but none of them work ....

Here is the file rip a 3d model with texture, if someone can give me good UV ....

model :
[http://www.sendspace.com/file/0ttzw9](http://www.sendspace.com/file/0ttzw9)
texture :
[http://www.sendspace.com/file/sl46ze](http://www.sendspace.com/file/sl46ze)

2. I can easily rip models from World in conflict and imported it into 3d studio max 2013, 
but I can not import them into Noesis.
how do I change the scale of the UV map as the plug in 3dmax? "UV-x" option .... I need to scale the UV to 0.001
sorry for my bad english ....
Natan
## Post #201
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2013-04-23T20:14:00+00:00
- Post Title: Re: Ninja Ripper

So, I want to try a game called Warframe. It's a steam game so the shortcut for it is to and exe but with an argument. I can't seem to get it to work. I point to a .exe and choose same argument as the shortcut but does not work. It's a free to play game. Does anyone have it installed and tried?
## Post #202
- Username: Tedfs
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 25, 2013 4:26 pm
- Post datetime: 2013-04-26T05:45:14+00:00
- Post Title: Re: Ninja Ripper

Thank you everyone for all the hard work on making these tools.

I've used them on Battlefield 3 and Medal of Honor Modern Warfighter successfully.
There is an odd instancing issue though as it seems there are duplicates of most meshes in rips of both games.
Not sure if there is a setting I need to change on my end or not. Doubles the checking but most of the duplicates
are the exact same KB and consecutively numbered so they are easy to spot.

Still very cool to be able to check things out in other engines to see how they render.
## Post #203
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2013-04-27T10:10:51+00:00
- Post Title: Re: Ninja Ripper

I just tryed the latest PCSX2 with Ninja Ripper - well, it's a bad news! No game which I tested (Tekken 4, Zombie Zone 2, Sonic Gems Collection - Sonic R) gave T-posed rips - only game actual poses
## Post #204
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-04-27T15:05:08+00:00
- Post Title: Re: Ninja Ripper

> Reply from Doronetty
>
> I just tryed the latest PCSX2 with Ninja Ripper - well, it's a bad news! No game which I tested (Tekken 4, Zombie Zone 2, Sonic Gems Collection - Sonic R) gave T-posed rips - only game actual poses

Not only that in some games dont even rip the uv´s and yea the rips are more clean that the ones you get with the DX9 plugin on SW mode but dont rip anything on  T pose =/ , but still its good to know that works on PCSX2.
## Post #205
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2013-04-28T03:25:03+00:00
- Post Title: Re: Ninja Ripper

I too recently tried PCSX2 and ninja-ripper. While I realize others have already commented on the compatibility issue, I noticed no one has thoroughly documented the actual behavior. So here is what I have been able to confirm in my own tests.

The settings are very important. PCSX2 appears to require GSDX11 with Software render mode in order to rip. The rips it produces are also somewhat dependent on the actual PS2 game you are trying to rip. 

.hack//GU for example, does not rip well at all, and if there is an object that rips, it is generally heavily distorted by the camera distance transformation. Metal Gear Solid 3 rips a lot more objects, and does seem to rip them in proper proportion, but only sometimes, and still not everything in the visible scene. Also the rips do not contain any UV, skeleton, rigging, or bind pose information. They are simply geometry in the shape of a person or grass or rocks...Statues essentially.

The program attempts to rip in GSDX9 software mode, but the folder frame remains empty. In any Hardware rendered mode, not even a folder is generated to show that it has attempted to rip at all.

This is all using the No Wrapper option, however the results are mirrored by the Wrapper versions respectively for dx9 and dx11.

This is using PCSX2 version 1.0.0 r5350, which is the current release build. I also tried using an older version: 0.9.7, and the results were even less fortunate. Simply put: Nothing.

My theory is that PCSX2 does not simply render the information given to it (as would a PC game) but instead emulates the PS2 hardware's rendering process, and renders the result of that. (Which seems obvious when written). 

Each PS2 game has its own unique render process, which would account for why some games work better than others, even if they don't work well. 

With many games it seems that rather than rendering a 3D scene in proportion and using a camera matrix to give it depth, the camera transformation is applied directly to the geometry before it is rendered, thus creating a scene which is visually correct, but spatially incorrect. 

This may mean some games will never be rip-able at runtime.

These issues are, by and large, the same issues that every other 3D ripper has when dealing with PS2 emulation; Few rips, incomplete rips, heavily distorted rips.

I have only tested these two game at this point, I will be testing others shortly, and if the results differ drastically with any game, I will make note of it here, in hopes that it may assist tosyk in maximizing compatibility, if he so chooses.

EDIT: Correction, it requires HARDWARE mode, not software.

EDIT: 
Tested Ookami. Similar issues. This game yields many many more objects on rip, but is still terribly distorted, and has the added bonus of being post-backface culling, leaving only half a model. Still no UVs, still no rigging of any kind. Still only works with GSDX11 Hardware mode.
## Post #206
- Username: DaWhirlpool
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 30, 2013 1:43 pm
- Post datetime: 2013-04-30T17:18:18+00:00
- Post Title: Re: Ninja Ripper

> Reply from TehDave
>
> I have the same issue with Dark Souls. If running with the default method (intruder) neither key is functional. (no textures, no rips)

If running with DX9 method, it works, but only textures are able to be captured, trying to rip meshes results in a slight pause, but no rip is produced.

It guess it seems that some games don't work with it.

I managed to capture a number of assets from Dark Souls (Queelag, Queelan, Solaire, Silver Knights, etc). I was running in DX9 and to bypass the hotkey issue I would alt-tab out and then alt-tab back in, and immediately hold the hotkey.   

To bring those models into max you might want to use the UV scale option in the ripper tool and set it to: 0.0009756 (the UVs for some reason are 1000 times to big and there's a padding of 2.5%). So 0.001 * (1/1.025) = 0.00097561

The Dark Souls community is in for a shock. I found a number of closed doors and hidden corridors (like at the Lord Vessel room and the Demon Ruins passage). I wonder if we'll ever figure out how to get there.
## Post #207
- Username: DaWhirlpool
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 30, 2013 1:43 pm
- Post datetime: 2013-04-30T18:06:03+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> chrrox wrote:i see no options for anything besides verts normals and uv's.
where are the weighting / bone import options.there is no options to do that, because our (blackninja and my) knowledges in max scripting is poor

I'd be than more happy to help as well.

I modified the max script to read the "BlendIndices" and "BlendWeights" from the .rip file (glad to see it was stored in there). Applying the weights is not much trouble, however there must be a skeleton/bone-structure that I can assign it to. The skeleton won't be found in the mesh .rip files. Would it be possible to have another file exported that contains the bones at capture time (like the textures and meshes)?
## Post #208
- Username: DaWhirlpool
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 30, 2013 1:43 pm
- Post datetime: 2013-04-30T20:51:37+00:00
- Post Title: Re: Ninja Ripper

> Reply from dragbody
>
> Hi!

I tried this tool with the Sleeping Dogs demo. F9 works and puts out a textures file, but F10 doesn't cause anything to happen. No models are saved. Any suggestions?

Have you tried the "alt-tab, alt-tab back, press the hotkey while it switches" trick?
## Post #209
- Username: DaWhirlpool
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 30, 2013 1:43 pm
- Post datetime: 2013-04-30T21:17:20+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> WRS wrote:but bones are just an abstract concept for animation - you can't get any bone information from directx as it only knows about the vertex data - transformed way before the rendering stageyes, you right.
And in case of 3d tool bone it's nothing, just a "word". Vertices of the model could be binded with "anything" (a dot/helper), and it's good to get coordinates of this "something" to bind with.
i'm not sure we can do this, but what we can do is messing with 3ds max, just need to think what we can do

p.s.: btw, plugin for Noesis will be very usefull too
p.p.s: also will be cool to have an option to load all pairs of uv into 3ds max one by one in uv channels in one time

If I'm not mistaken, a bone is most definitely an object in directX (albeit, an invisible one): 
[http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb322705%28v=vs.85%29.aspx)

If we could get a dump of that data on capture, we'd be set.
## Post #210
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2013-05-01T19:44:47+00:00
- Post Title: Re: Ninja Ripper

When I wanna rip in  The Darkness 2 (press F10) then there are no files. Nothing happen.

The ripper have a problem with the Telltale Engine (The Walking Dead, Back To The Future etc.)
Some Polygons of the models are missing.

When I wanna start Max Payne 3 with the ripper, then the game crashes.


Can someone help me?^^
## Post #211
- Username: AceVentura
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Jul 15, 2012 11:22 am
- Post datetime: 2013-05-04T10:58:40+00:00
- Post Title: Re: Ninja Ripper

Im trying to rip some meshes from Dead Island, but i got blue texture in 3d max.
I have tried to change the vertex layout from u:3 v:4 up to u:22 v:23 but no success.
can u give me a hint, whats the correct config to import to 3ds max?
[Capture.JPG](https://xentaxbackup.github.io/file/6382_Capture.JPG)
## Post #212
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-05-22T18:44:42+00:00
- Post Title: Re: Ninja Ripper

Does ninja ripper works on dreamcast emulator?i read above post that ripping result from pcsx2 has a lot of problem using this tools,i wonder if its happen to other emulator (epsxe,project64,dolphin,or even nullDC)?does anyone has tried to rip from other emulator using this tools?how the result?
## Post #213
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-05-22T22:48:30+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper doesnt work on NullDC/EPSXE, however did work on Dolphin and for Project64 if recall there is an option to dump the current
scene on obj there is also more emulators from PSX/XBOX that i didnt test yet so you will need to take a look at those.
## Post #214
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-27T00:17:48+00:00
- Post Title: Re: Ninja Ripper

I have 3d stuido max 9 x86
I downloaded the max script and it tells me every time I try maxscript>run 

" Maxscript autoload error

 ---unknown "processaffinity" in #struct:sysinfo("

 it goes on to say a whole bunch <fn> and <systemglobal> listings which I can list if needed.

 someone once posted a screenshot  of this very error and never got an answer. what am I doing wrong?
## Post #215
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2013-05-27T17:38:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from octaviousrex
>
> I have 3d stuido max 9 x86...
The readme says use 3ds Max 2009 or above.

> Reply from help_en.txt
>
> IMPORTER FEATURES
to import models used 3ds max version 2009 and above...
## Post #216
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-05-28T18:34:59+00:00
- Post Title: Re: Ninja Ripper

I recall the ninja ripper saying it was tested on max 9 x86 and working. but if it needs 2009 version then I'll see what that will set me back. thanks for the information.
## Post #217
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2013-06-02T13:09:52+00:00
- Post Title: Re: Ninja Ripper

> Reply from The Chief
>
> Ninja Ripper doesnt work on NullDC/EPSXE, however did work on Dolphin and for Project64 if recall there is an option to dump the current
scene on obj there is also more emulators from PSX/XBOX that i didnt test yet so you will need to take a look at those.

Well too bad if that so    i plan to rip shenmue 2 model on nulldc using this tools,but since you say its not working in that emulator,guess i need to figure other way to rip the models
## Post #218
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-06-02T16:35:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from aagems
>
> The Chief wrote:Ninja Ripper doesnt work on NullDC/EPSXE, however did work on Dolphin and for Project64 if recall there is an option to dump the current
scene on obj there is also more emulators from PSX/XBOX that i didnt test yet so you will need to take a look at those.

Well too bad if that so    i plan to rip shenmue 2 model on nulldc using this tools,but since you say its not working in that emulator,guess i need to figure other way to rip the models

well for Shenmue in this forum i recall some models and tools avaible for those games if you wish you can take a look at here:

[http://www.shenmuedojo.net/forum/](http://www.shenmuedojo.net/forum/)
## Post #219
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2013-07-05T04:26:51+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi. Im author of NinjaRipper

Here beta version 1.1.2 with fixed "purple" textures in Dx11 and gamma in Dx9

http://blackninja2000.narod.ru/files/ninjaripper112.7z

can you please post the updated ninjaripper 1.1.4, can't seem to download from your website
thanks...
## Post #220
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-07-06T08:04:45+00:00
- Post Title: Re: Ninja Ripper

Does someone know how to make ninja ripper work with MK:KE??
## Post #221
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-07-12T06:29:32+00:00
- Post Title: Re: Ninja Ripper

> Reply from Darko
>
> Does someone know how to make ninja ripper work with MK:KE??
For UE3 use [Umodel](http://gildor.org/down/35/umodel/umodel_win32.zip)
## Post #222
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2013-07-12T13:57:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from Ekey
>
> Darko wrote:Does someone know how to make ninja ripper work with MK:KE??
For UE3 use Umodel

Yeah, but the little inconvenient that umodel doesn't support the second uv layer for hair.
## Post #223
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2013-07-13T01:34:19+00:00
- Post Title: Re: Ninja Ripper

So it rips nicely, but some games got a weird stretch/skew thing going on. Easily fixable manually, and i know it has something to do with the ingame camera/fov(dxripper had the same problem). Dxripper fixed it with the .3dr importer script.

Anyway to fix it with the ninja ripper importer script?
from this:pic.twitter.com/6xc4LiXm9i
to this:pic.twitter.com/kdBpE5zJIR

 Also, mega props to the guy who made this, I'm talking to you, blackninja(also tosyk) 

EDIT: Forgot to add, look up a tool called "game assassin", it's Chinese, but it seems very similar(weights etc). It can do animations as well(apparently).

Also, after it captures a frame, the screen goes black, but the game resumes playing like normal. Any reason? I can still capture another frame while the screen is black. Directx9, spiderman:web of shadows
## Post #224
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2013-07-13T02:06:44+00:00
- Post Title: Re: Ninja Ripper

Am I using wrong version of max or something? I just dled latest version of ninja ripper, using dx 11 for the options in the gui.

I spent the whole day trying to ninjarip hitman absolution and then in 3dsmax, the textures are ripped, but all the models are a thin piece of square that just slaps the whole texture on it -_-

So it doesn't work....
## Post #225
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-07-13T02:09:09+00:00
- Post Title: Re: Ninja Ripper

can ninjaripper support x64 apps in the future?
## Post #226
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2013-07-13T02:18:54+00:00
- Post Title: Re: Ninja Ripper

OH wait I get boxes if I import more than 6 objects.



Well, at least I got a good script from page 9 i think. Hitman Absolution or I don't even know.

Well, gonna try it on and old version, I hope max 2009 works.
## Post #227
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2013-07-13T05:51:38+00:00
- Post Title: Re: Ninja Ripper

soulslayerzx: I can clearly see a head's polygons in there. Just because you import a model, doesn't necessarily mean it will be the main character. Try importing all models in the folder, the delete them one by one.
## Post #228
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2013-08-08T19:47:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Utility to extract / ripping 3d models (mesh), textures, shaders directly from the running game.
(It's new version of dx ripper)

Author: blackninja

Features:
Extracting all available vertex information of the models (position, all the texture coordinates, normals, weights, BLENDWEIGHT, BLENDINDICES, BINORMAL, TANGENT), indices, textures, shaders. Theoretically all extracted information could be import in the 3D editor!
Support for D3D11, D3D9, D3D8 (processed, however not all methods/techniques, but should work for 95% of all games).

Ripper page  |  English Instructions  |  Official author's website  |  Official support page

Hitman: Absolution  |  Agent 47:
The other day I used Ninja ripper to rip models from Code Lyoko Quest for Infinity, but The characters were not in T-pose. Can you make them rip in T-pose?
## Post #229
- Username: magarcan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 4:06 am
- Post datetime: 2013-08-19T08:57:15+00:00
- Post Title: Re: Ninja Ripper

I've a little problem... When I import my frame into 3D Max (2012) that's what I get:


All my the objects are centered instead of being placed in their position.

Here you can find the link to that files: [https://docs.google.com/file/d/0BzMqUV6 ... sp=sharing](https://docs.google.com/file/d/0BzMqUV6hsx6VcmhqYmo1Zjk4c1U/edit?usp=sharing)

Any idea about how can I fix it?
## Post #230
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2013-08-30T03:31:55+00:00
- Post Title: Re: Ninja Ripper

> Reply from magarcan
>
> I've a little problem... When I import my frame into 3D Max (2012) that's what I get:
All my the objects are centered instead of being placed in their position.
Any idea about how can I fix it?

I think that's how it's supposed to work. If you want to rip a scene with all models in place use dxripper or something similar. Every game i have tried with this works well but yes, moves all models to the centre.
## Post #231
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2013-09-08T14:02:58+00:00
- Post Title: Re: Ninja Ripper

Is there a solution of steam games?
When I start the game "Ghost Master" with Ninjaripper (installed via steam) an error pops up and says "Failed to find Steam".
But Steam is running :/
## Post #232
- Username: fedeita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 22, 2009 12:49 am
- Post datetime: 2013-10-19T17:58:53+00:00
- Post Title: Re: Ninja Ripper

when i rip models from rome2 the uv's are broken, any way to solve this?
## Post #233
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2014-02-08T17:10:32+00:00
- Post Title: Re: Ninja Ripper

Can u add support for Panzar-Forged by chaos? [http://www.panzar.com/](http://www.panzar.com/)
## Post #234
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-03-04T17:08:55+00:00
- Post Title: Re: Ninja Ripper

Hey, I've been trying to rip from Dolphin emulator, and it looks like all the keys you can use to rip with Ninja ripper are already hardcoded as load state keys in Dolphin... so every time I try to rip a model from dolphin, it says "missing state"

This happens with F1-F12, so how the heck am I supposed to rip models? I was trying to rip from a game called Custom Robo.

I even tried using the old 3d Ripper DX program, but it wouldn't even load Dolphin, AND even if it did, it still uses the F buttons, which are already mapped in Dolphin.
## Post #235
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2014-03-06T08:00:26+00:00
- Post Title: Re: Ninja Ripper

> Reply from kingfisher13
>
> it looks like all the keys you can use to rip with Ninja ripper are already hardcoded as load state keys in Dolphin
You can reassign keys in Dolphin. I change save state key from F8 to 8, and assign NR rip-key to F8 - works fine.
## Post #236
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-03-07T01:27:18+00:00
- Post Title: Re: Ninja Ripper

Ok, so I changed the key config, and ran NR with Dolphin... I pressed F8, checked my rip folder, and there was nothing there. I tried both intruder and DX11 inserts... DX9 won't work with this game since the game is glitchy with the DX9 plugin... is there a way around this? How do I fix it?

Thanks for all your help so far, it was a stupid mistake on my part, lol...


EDIT: Not sure if this matters, but Dolphin is 64-bit, version 3.5...
## Post #237
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2014-03-08T03:07:21+00:00
- Post Title: Re: Ninja Ripper

> Reply from kingfisher13
>
> Not sure if this matters, but Dolphin is 64-bit, version 3.5...
I tried ripper with this version - all as you said - nothing seems to rips or even injects.
Ripping works fine with old version of Dolphin 3.0-872 (32-bit i think), i can't test with more recent versions, maybe only 32-bit matters.

Btw, how can you change DX version in Dolphin? I have only OpenGL, Direct3D and Software Rendering in video output submenu.
## Post #238
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-03-08T03:17:36+00:00
- Post Title: Re: Ninja Ripper

Hmmm... that must be it then. 

I think the newest version of Dolphin included a plugin selector, and plugins for both DirectX 9 and 11... its really nice for working around glitches and compatibility issues.

I assume older versions only run DirectX 9, which could be a problem... I'll have to try switching to 32 bit first.
## Post #239
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2014-03-08T15:15:15+00:00
- Post Title: Re: Ninja Ripper

Ok, so I tried the 32 bit version of Dolphin 3.0, and it worked just fine... at least, for that particular game. For some reason, Mario Kart Double Dash won't rip... I really wanted to rip Petey Piranha, because face it, he is AWESOME, but I got nothing in the rip folder :/

Does anyone have an idea as to the ideal settings, dolphin version, etc etc, for ripping from Mario Kart Double Dash?


ALSO, now that I'm all excited about this cool new ripper, does anyone have the best settings for ripping from PCSX2? I attempted to rip models from PCSX2 0.9.8, a game called Shinkon Gattai Godannar- which has some freaking cool mecha models, and got nothing in the rip folder either. 

Any help would be greatly appreciated... when ripping PS2 models, the current standard method is extremely difficult, and ends up with a model that is NOT T-posed, and has mucked up UV mapping.

If I could get Ninja Ripper to work with PCSX2, and utilize its T-posing ability, it would make rigging and texturing PS2 models much MUCH easier.
## Post #240
- Username: luigimario
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 29, 2010 8:50 pm
- Post datetime: 2014-03-09T23:29:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from kingfisher13
>
> Ok, so I tried the 32 bit version of Dolphin 3.0, and it worked just fine... at least, for that particular game. For some reason, Mario Kart Double Dash won't rip... I really wanted to rip Petey Piranha, because face it, he is AWESOME, but I got nothing in the rip folder :/

Does anyone have an idea as to the ideal settings, dolphin version, etc etc, for ripping from Mario Kart Double Dash?


ALSO, now that I'm all excited about this cool new ripper, does anyone have the best settings for ripping from PCSX2? I attempted to rip models from PCSX2 0.9.8, a game called Shinkon Gattai Godannar- which has some freaking cool mecha models, and got nothing in the rip folder either. 

Any help would be greatly appreciated... when ripping PS2 models, the current standard method is extremely difficult, and ends up with a model that is NOT T-posed, and has mucked up UV mapping.

If I could get Ninja Ripper to work with PCSX2, and utilize its T-posing ability, it would make rigging and texturing PS2 models much MUCH easier.
why not use bmdview, or the max script to get the double dash models?
## Post #241
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-04-07T19:25:44+00:00
- Post Title: Re: Ninja Ripper

what is the last version of this tool?
## Post #242
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-04-12T07:30:06+00:00
- Post Title: Re: Ninja Ripper

> Reply from Devilot
>
> what is the last version of this tool?1.1.4 is latest.
## Post #243
- Username: XLAX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Oct 04, 2011 8:18 am
- Post datetime: 2014-04-20T04:55:12+00:00
- Post Title: Re: Ninja Ripper

> Reply from octaviousrex
>
> I have 3d stuido max 9 x86
I downloaded the max script and it tells me every time I try maxscript>run 
" Maxscript autoload error 
 ---unknown "processaffinity" in #struct:sysinfo("
 it goes on to say a whole bunch <fn> and <systemglobal> listings which I can list if needed.
someone once posted a screenshot  of this very error and never got an answer. what am I doing wrong?
if you get this error in max9 x86 or 64 try this:
hit f11(maxscript)
then file>open
select the ninja ripper script
then file>evaluate all

i read on tosyk's site that this software has been abandoned?

[http://cgig.ru/en/2012/10/ho-to-use-nin ... /#comments](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/comment-page-6/#comments)
## Post #244
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-05T13:48:39+00:00
- Post Title: Re: Ninja Ripper

> Reply from CriticalError
>
> Devilot wrote:what is the last version of this tool?1.1.4 is latest.

Development has stopped the previous year then?
## Post #245
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-05-08T03:36:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from Devilot
>
> Development has stopped the previous year then?
Apparently so. 


Also, is there a version of this that does NOT reset bone positions? It would be incredibly useful for ripping buildings and vehicles and such.
## Post #246
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-05-20T18:12:24+00:00
- Post Title: Re: Ninja Ripper

this utility crashes ME2... and I believe it will crash ME3 too. any idea why?
## Post #247
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-05-27T04:30:45+00:00
- Post Title: Re: Ninja Ripper

Hello,

I loved this tool when I was able too use it, but after reinstalling windows recently I can no longer rip anything at all.
For the life of me I can't understand what happened but I've tried many different things to resolve this without any luck.

I'm using Windows 7 64-bit with a Nvidia GTX 460 Graphics Card and a Quad Core Duo processor.
This is the Same Computer Setup with which I have previously ripped many different models, so it can't be the Hardware.

I have tried both a fresh install of Win 7 100% complete windows updates, and a fresh install of Win 7 before adding any updates.
I have tried both the latest Driver for my Graphics Card and a older driver that worked last year.
I have Tried Games i never tried ripping from and games I ripped from before.
Folders are created within the game directories but when the game starts there's no text displaying "Ready to Capture" as before.

Nothing has worked.

does anyone have any ideas on this?
## Post #248
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-05-27T12:45:19+00:00
- Post Title: Re: Ninja Ripper

Would anyone be able to share the most recent 3ds max plugin for the .rip files at all?

The link on the website is broken, I'm assuming the dropbox folder it was linked to has since been deleted.

Thanks
## Post #249
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-05-27T12:59:33+00:00
- Post Title: Re: Ninja Ripper

Here's the one I have.
[ninja_ripper_3dsmax_importer.zip](https://xentaxbackup.github.io/file/7385_ninja_ripper_3dsmax_importer.zip)
## Post #250
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-05-27T13:51:05+00:00
- Post Title: Re: Ninja Ripper

Here is the log file that is generated from the Test Folder TestDx9, used on the file textures which should rip no problem but does not.

Ninja Ripper v1.1.4
(c)2004-2013 black_ninja

Tue May 27 9:44:29 2014

LOG START

D3D9 Ripper Init
D3D9.Direct3DCreate9() hooked
D3D9.Direct3DCreate9(32) ret: 0x002307E0
IDirect3D9_CreateDevice(0x002307E0, 0x00000000, 0x00000001, 0x002A0260, 0x00000020, 0x0018FD70, 0x0042EA50) ret: 0x00000000
IDirect3DDevice9_SetTexture hooked Address: 0x6DC6EDE4
IDirect3DDevice9_DrawPrimitiveUP hooked Address: 0x6DCA5473
IDirect3DDevice9_DrawIndexedPrimitive hooked Address: 0x6DC87651
IDirect3DDevice9_CreateVertexBuffer hooked Address: 0x6DC7D40D
IDirect3DDevice9_CreateIndexBuffer hooked Address: 0x6DC8ED61
IDirect3DDevice9_Present hooked Address: 0x6DCA10C3
IDirect3DDevice9_GetSwapChain hooked Address: 0x6DC7B46C
IDirect3DDevice9_DrawIndexedPrimitiveUP hooked Address: 0x6DD5C4C6
IDirect3DDevice9_DrawPrimitive hooked Address: 0x6DC83660
IDirect3DDevice9_SetPixelShader hooked Address: 0x6DCC260C
IDirect3DDevice9_SetDepthStencilSurface hooked Address: 0x6DCA6E97
IDirect3DDevice9_SetGammaRamp hooked Address: 0x6DD1BA0F
D3D9 Ripper Uninit


Loaded Modules List
0x00400000 C:\Users\\Desktop\ninjaripper114\ninjaripper\TestDx9\Textures.exe
0x77130000 C:\Windows\SysWOW64\ntdll.dll
0x759D0000 C:\Windows\syswow64\kernel32.dll
0x76530000 C:\Windows\syswow64\KERNELBASE.dll
0x6C170000 C:\Users\\Desktop\ninjaripper114\ninjaripper\TestDx9\d3dx9d_32.dll
0x767C0000 C:\Windows\syswow64\msvcrt.dll
0x749A0000 C:\Windows\syswow64\USER32.dll
0x76580000 C:\Windows\syswow64\GDI32.dll
0x76100000 C:\Windows\syswow64\LPK.dll
0x75EC0000 C:\Windows\syswow64\USP10.dll
0x75B60000 C:\Windows\syswow64\ADVAPI32.dll
0x76510000 C:\Windows\SysWOW64\sechost.dll
0x76300000 C:\Windows\syswow64\RPCRT4.dll
0x74820000 C:\Windows\syswow64\SspiCli.dll
0x74810000 C:\Windows\syswow64\CRYPTBASE.dll
0x6DC60000 C:\Windows\system32\d3d9.dll
0x73A80000 C:\Windows\system32\VERSION.dll
0x70D00000 C:\Windows\system32\d3d8thk.dll
0x70980000 C:\Windows\system32\dwmapi.dll
0x70C60000 C:\Windows\system32\WINMM.dll
0x748E0000 C:\Windows\system32\IMM32.DLL
0x758C0000 C:\Windows\syswow64\MSCTF.dll
0x71000000 C:\Users\\Desktop\ninjaripper114\ninjaripper\intruder.dll
0x709A0000 C:\Windows\system32\uxtheme.dll
0x671C0000 C:\Users\\Desktop\ninjaripper114\ninjaripper\d3dx9_36.dll
0x67570000 C:\Windows\system32\nvd3dum.dll
0x74C60000 C:\Windows\syswow64\PSAPI.DLL
0x74C70000 C:\Windows\system32\Shell32.dll
0x74880000 C:\Windows\syswow64\SHLWAPI.dll
0x76610000 C:\Windows\syswow64\ole32.dll
0x70BD0000 C:\Windows\system32\powrprof.dll
0x75F60000 C:\Windows\syswow64\SETUPAPI.dll
0x75990000 C:\Windows\syswow64\CFGMGR32.dll
0x74AA0000 C:\Windows\syswow64\OLEAUT32.dll
0x767A0000 C:\Windows\syswow64\DEVOBJ.dll


LOG END

Tue May 27 9:44:46 2014

Can Anyone Tell if there is something wrong just from This information?
## Post #251
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2014-06-02T08:19:52+00:00
- Post Title: Re: Ninja Ripper

Log looks ok, except this:

> Reply from Modman69
>
> 0x00400000 C:\Users\\Desktop\ninjaripper114\ninjaripper\TestDx9\Textures.exe
If you didn't remove your profile name manually, I assume it's contains wrong symbols (i.e. russian or chinese), so you need to move "ninjaripper114" folder to another path, without wrong symbols.
Like D:\Programs\ninjaripper114 or C:\ninjaripper114 for example.
## Post #252
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2014-06-03T06:03:45+00:00
- Post Title: Re: Ninja Ripper

Thank You Andrakann for examining the log file, I finally managed to figured out the problem.

I'm actually embarassed to say but I needed to actually swap keyboards because for some crazy reason the function keys were not working properly.

what a pain in the neck that was for something so stupid.

Thanks again for responding.
## Post #253
- Username: Viremaster
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 10, 2010 5:09 am
- Post datetime: 2014-06-21T10:23:21+00:00
- Post Title: Re: Ninja Ripper

I was looking for a DX11 equivalent to 3d ripper dx and found Ninja Ripper. I wanted such a tool to get models from Dolphin, as its devs are abandoning 32-bit and DX9 support. I ran the emulator from ninja ripper, hit the capture key and nothing happened. Thinking there was a fluke with the ripper, I opened Freelancer with it. Ripped fine. And while I can get it to dump textures, that both isn't what I want and is redundant due to the emulator's native capability. And while I could just use BRRESviewer for a lot of the games, there are several i wish to rip from that don't support that format. So my question is if anyone else has been having a similar problem and/or have a solution to mine.
## Post #254
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-10T07:44:41+00:00
- Post Title: Re: Ninja Ripper

isn't Ninja ripper supposed to rip also DX11?
## Post #255
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-08-10T15:42:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from Devilot
>
> isn't Ninja ripper supposed to rip also DX11?yes.
## Post #256
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-10T16:07:49+00:00
- Post Title: Re: Ninja Ripper

then I have not understood Viremaster's question..
## Post #257
- Username: mdtarmimi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 15, 2014 3:42 pm
- Post datetime: 2014-08-18T17:17:13+00:00
- Post Title: Re: Ninja Ripper

Yes i'm using this tools and it can extract stuff well
## Post #258
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-08-22T06:15:07+00:00
- Post Title: Re: Ninja Ripper

Not really. It seems to have a lot of trouble ripping UVs, especially from modern games like COD Black Ops.

The only games I've had it rip UVs successfully from are Battlefield Bad Company 2 and Dolphin Gamecube emulator.
## Post #259
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-08-22T06:28:47+00:00
- Post Title: Re: Ninja Ripper

> Reply from SergeantJoe
>
> Not really. It seems to have a lot of trouble ripping UVs, especially from modern games like COD Black Ops.

The only games I've had it rip UVs successfully from are Battlefield Bad Company 2 and Dolphin Gamecube emulator.ripping models implies you to get patience and some trick before you can rip off something. ninja ripper is a great tool and it gives you opportunity to get some model out the game. I do believe that for some people it's better to not rip game models at all than use this tool, but if you really want it NJ do the work.
## Post #260
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-08-22T07:29:23+00:00
- Post Title: Re: Ninja Ripper

I didn't quite understand what you said, but I agree, it's a great tool. However sometimes it doesn't get the job done properly. Maybe I'm missing something? 

If we want to get into specific examples I tried every single possible combination of the numbers 0-20 in the importer script, still nothing.
## Post #261
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-08-22T09:02:06+00:00
- Post Title: Re: Ninja Ripper

> Reply from SergeantJoe
>
> If we want to get into specific examples I tried every single possible combination of the numbers 0-20 in the importer script, still nothing.there are a lot of techniques of a render of different objects which can be used through the one particular game, but ninja ripper doesn't support all of existing render techniques. More on that — new techniques are creating for new games. That's why sometimes you are not able to rip some of the objects/UVs.
## Post #262
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-08-22T20:58:56+00:00
- Post Title: Re: Ninja Ripper

Fair enough. 

However, my question still stands, is there perhaps an older build available that does not rip in t-pose? It would be very useful for things like buildings, vehicles and weapons.
## Post #263
- Username: mdtarmimi
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 15, 2014 3:42 pm
- Post datetime: 2014-08-25T20:38:35+00:00
- Post Title: Re: Ninja Ripper

yes actually same with me.. But some how this tools still doing a great job...   Perhaps someday it will be a superb tools that can extract all kind thing model through PS2..
## Post #264
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-27T14:57:20+00:00
- Post Title: Re: Ninja Ripper

are you sure this works with Dolphin?
## Post #265
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-08-31T00:08:52+00:00
- Post Title: Re: Ninja Ripper

Yup. You just need to set Dolphin to DX9 mode. DX11 stuff comes out flat.
## Post #266
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2014-08-31T07:05:47+00:00
- Post Title: Re: Ninja Ripper

to me it does not come at all... it does not rip anything!
## Post #267
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2014-09-03T04:40:18+00:00
- Post Title: Re: Ninja Ripper

I was able to use Ninja Ripper for Jade Dynasty, now i am unable to. Know that it is required to open then game though arc. Also not able to use it, for Diablo 3 anymore. Is there a way to use Ninja ripper for these games? also was seeing for Pwi Neverwinter.
## Post #268
- Username: Abyssinian
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 19, 2013 9:10 am
- Post datetime: 2014-09-10T16:37:03+00:00
- Post Title: Re: Ninja Ripper

I've just used Ninja ripper with Lego: Marvel Super heroes to extract the Helicarrier. While that did work, it's a whole lot of different parts. On importing them into 3ds max, they're all imported at point 0,0,0. Is there any way to not have that? So that the model stays intact.
## Post #269
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2014-09-11T16:46:27+00:00
- Post Title: Re: Ninja Ripper

Is there any way to use this with Cryengine type games?  You start off a launcher, which Ninja Ripper can't connect to.  The launcher starts the game which uses the graphics, and you can't start that .exe without running it through the launcher.
## Post #270
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2014-09-21T07:15:22+00:00
- Post Title: Re: Ninja Ripper

Seems not able to work with wow or diablo anymore
## Post #271
- Username: saso
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 10, 2014 7:42 pm
- Post datetime: 2014-10-10T11:59:10+00:00
- Post Title: Re: Ninja Ripper

Hello everyone, 
My name is Saso and I'm from a small town in Italy, 
I work with a group of work that deals with a mod for Rfactor on hillclimbs, 
I have a problemam, 
I used ninja ripper to copy a Grid Autosport car on the game and when I imported with 3DStudio Max model of the machine I get so, it seems a puzzle, 
does anyone know how to solve this problem is solvable if and can 'help me please? 
Hello and thanks



saso_001.jpg (112.83 KiB) Viewed 389 times
## Post #272
- Username: SergeantJoe
- Rank: mega-veteran
- Number of posts: 242
- Joined date: Fri Aug 30, 2013 12:39 pm
- Post datetime: 2014-10-14T10:26:36+00:00
- Post Title: Re: Ninja Ripper

There's no problem here, that's just how it works. You have the put the pieces back together yourself.
## Post #273
- Username: saso
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 10, 2014 7:42 pm
- Post datetime: 2014-10-14T10:50:42+00:00
- Post Title: Re: Ninja Ripper

thanks for the reply, however I have already solved, thanks to a tool for simulators Sim named 3dsimed, with a bit of calm and patience I repositioned all components
[CatturaA4.JPG](https://xentaxbackup.github.io/file/7936_CatturaA4.JPG)
## Post #274
- Username: XiNAVRO
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 1:39 am
- Post datetime: 2014-10-17T20:28:46+00:00
- Post Title: Re: Ninja Ripper

Question regarding mesh, and orphaned edges:

Currently I'm trying to extract some resources from Dark Souls II (Steam version) to convert them for Skyrim.
Seems like the ripper has no problem acquiring the meshes, but I do have an issue where the result mesh is having odd edges connecting vertices that are not supposed to be connected to begin with.

Here's what I'm talking about:


Cleaning these up is taking more time than the actual porting process.

I have tried 3DSMax and the RIP import script, also tried using Noesis to convert the RIP files into OBJ, and port them to Blender.
Same issue pertains. I'm not really sure if anyone else is also having this problem. Any insights?
## Post #275
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-10-17T23:19:34+00:00
- Post Title: Re: Ninja Ripper

Someone had a similar problem a while ago and MrAdults says use the -killdupfaces command in Noesis to clean it up.

[viewtopic.php?p=80770#p80770](http://forum.xentax.com/viewtopic.php?p=80770#p80770)
[viewtopic.php?p=80782#p80782](http://forum.xentax.com/viewtopic.php?p=80782#p80782)

[viewtopic.php?p=80826#p80826](http://forum.xentax.com/viewtopic.php?p=80826#p80826)

before


after
## Post #276
- Username: XiNAVRO
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Mar 23, 2010 1:39 am
- Post datetime: 2014-10-20T00:08:55+00:00
- Post Title: Re: Ninja Ripper

> Reply from AceWell
>
> Someone had a similar problem a while ago and MrAdults says use the -killdupfaces command in Noesis to clean it up.

Thanks for the link; although the cleanup did work, this time it destroyed the UV mapping instead.
Any similar command or tool I could use in 3DSMax for cleaning?
## Post #277
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2014-10-20T16:02:23+00:00
- Post Title: Re: Ninja Ripper

I'm not familiar with 3dsMax, but I think most major 3d applications have tools to transfer or copy UVs from one object to another. If messed up UVs is your only issue now, you could copy the UVs from the uncleaned model to the cleaned-up one.
## Post #278
- Username: Pork Chops and Beans
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 26, 2014 8:03 pm
- Post datetime: 2014-10-26T12:12:58+00:00
- Post Title: Re: Ninja Ripper

Hello guys, I'm new in 3D ripping and especially this tool! I've been trying to use Ninja Ripper to rip the L.A. Noire's police stations map, I used this wonderful tool before with Kane & Lynch: Dead Men and it worked splendidly, I used D3D9 wraper for Kane & Lynch. But I tried L.A. Noire with same wrapper and it didn't work, every time I tried to launched it, it crashed saying something about intruder error. I triedo use Intruder in the configuration and D3D11 wrapper, both allowed me to be in game, but when I pressed F10 or F9, it didn't do anything. I'm wondering what I did wrong here? Thanks!
## Post #279
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-11-05T14:50:36+00:00
- Post Title: Re: Ninja Ripper

Is there any way to get ahold of the Source for this at all?

Or perhaps for the original creator to compile ninjaripper for 64 bit too, many games are turning to 64bit, and Ninja Ripper can't use 64bit applications.

What would be really cool though, is a way to rip via a launcher, far too many games have launchers, especially steam games, and even if the point NR at the games .exe it still launches the launcher anyway.
## Post #280
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2014-11-16T12:59:05+00:00
- Post Title: Re: Ninja Ripper

I'm not sure what causes this, I use Ninja per [http://souls.darknode.org/](http://souls.darknode.org/) and it works just fine. 

> Reply from XiNAVRO
>
> Question regarding mesh, and orphaned edges:

Currently I'm trying to extract some resources from Dark Souls II (Steam version) to convert them for Skyrim.
Seems like the ripper has no problem acquiring the meshes, but I do have an issue where the result mesh is having odd edges connecting vertices that are not supposed to be connected to begin with.

Here's what I'm talking about:
[snip]

Cleaning these up is taking more time than the actual porting process.

I have tried 3DSMax and the RIP import script, also tried using Noesis to convert the RIP files into OBJ, and port them to Blender.
Same issue pertains. I'm not really sure if anyone else is also having this problem. Any insights?
## Post #281
- Username: zookone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 29, 2013 6:14 am
- Post datetime: 2014-12-13T20:25:20+00:00
- Post Title: Re: Ninja Ripper

My Ninja is getting smacked down...

Win7 64bit machine, using Ninja Ripper in dx11 wrapper mode. I think I have to use wrapper mode because game launcher blocks the ability to use intruder mode.

F9 texture capture is working for textures but unable to F10 capture models. Does anyone have a tip on what might be wrong? Maybe just doesn't work?

Sorry for the long log post below... Thanks

```
Ninja Ripper v1.1.4
(c)2004-2013 black_ninja

Sat Dec 13 12:18:15 2014

LOG START

D3D11.DLL loaded
D3D11 Ripper Init
D3D11.D3D11CreateDeviceAndSwapChain() hooked
D3D11.D3D11CreateDevice() hooked
DXGI.CreateDXGIFactory() hooked
DXGI.CreateDXGIFactory1() hooked
D3D11.D3D11CreateDeviceAndSwapChain() ret: 0x00000001
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

D3D11.D3D11CreateDevice() ret: 0x00000001
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

D3D11.D3D11CreateDeviceAndSwapChain() ret: 0x00000000
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

ID3D11DeviceContext_DrawIndexed hooked Address: 0x67C14BB0
ID3D11DeviceContext_Draw hooked Address: 0x67C22780
ID3D11DeviceContext_DrawAuto hooked Address: 0x67C00EA0
ID3D11DeviceContext_DrawIndexedInstanced hooked Address: 0x67BFF220
ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked Address: 0x67C00EC0
ID3D11DeviceContext_DrawInstanced hooked Address: 0x67BFF250
ID3D11DeviceContext_PSSetShaderResources hooked Address: 0x67BFEA80
ID3D11Device_CreateInputLayout hooked Address: 0x67B89BA6
D3D11.D3D11CreateDevice() ret: 0x00000000
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

D3D11.D3D11CreateDeviceAndSwapChain() ret: 0x00000000
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

D3D11.D3D11CreateDevice() ret: 0x00000000
DriverType  : D3D_DRIVER_TYPE_UNKNOWN
FeatureLevel: D3D_FEATURE_LEVEL_11_0

D3D11 Ripper Uninit

Loaded Modules List
0x00230000 C:\Program Files (x86)\Frontier\EDLaunch\Products\FORC-FDEV-D-1002\EliteDangerous32.exe
0x777F0000 C:\Windows\SysWOW64\ntdll.dll
0x76300000 C:\Windows\syswow64\kernel32.dll
0x75E70000 C:\Windows\syswow64\KERNELBASE.dll
0x75B70000 C:\Windows\syswow64\GDI32.dll
0x758E0000 C:\Windows\syswow64\USER32.dll
0x757A0000 C:\Windows\syswow64\ADVAPI32.dll
0x75AA0000 C:\Windows\syswow64\msvcrt.dll
0x75720000 C:\Windows\SysWOW64\sechost.dll
0x766A0000 C:\Windows\syswow64\RPCRT4.dll
0x75190000 C:\Windows\syswow64\SspiCli.dll
0x75180000 C:\Windows\syswow64\CRYPTBASE.dll
0x75A90000 C:\Windows\syswow64\LPK.dll
0x759E0000 C:\Windows\syswow64\USP10.dll
0x767A0000 C:\Windows\syswow64\SHELL32.dll
0x75D50000 C:\Windows\syswow64\SHLWAPI.dll
0x76150000 C:\Windows\syswow64\ole32.dll
0x75CC0000 C:\Windows\syswow64\OLEAUT32.dll
0x72DF0000 C:\Program Files (x86)\Frontier\EDLaunch\Products\FORC-FDEV-D-1002\d3d11.dll
0x67CF0000 C:\Windows\system32\dxgi.dll
0x750B0000 C:\Windows\system32\VERSION.dll
0x6AF70000 C:\Windows\system32\dwmapi.dll
0x74F00000 C:\Windows\system32\dbghelp.dll
0x725D0000 C:\Windows\system32\WINMM.dll
0x00070000 C:\Windows\system32\XINPUT1_3.dll
0x75420000 C:\Windows\syswow64\SETUPAPI.dll
0x75E30000 C:\Windows\syswow64\CFGMGR32.dll
0x752E0000 C:\Windows\syswow64\DEVOBJ.dll
0x72DC0000 C:\Windows\system32\DINPUT8.dll
0x758A0000 C:\Windows\syswow64\WS2_32.dll
0x75E60000 C:\Windows\syswow64\NSI.dll
0x70CA0000 C:\Windows\system32\IPHLPAPI.DLL
0x70C90000 C:\Windows\system32\WINNSI.DLL
0x67EC0000 C:\Windows\system32\OPENGL32.dll
0x67E90000 C:\Windows\system32\GLU32.dll
0x67DA0000 C:\Windows\system32\DDRAW.dll
0x69B60000 C:\Windows\system32\DCIMAN32.dll
0x70F20000 C:\Windows\system32\WINHTTP.dll
0x70ED0000 C:\Windows\system32\webio.dll
0x72DA0000 C:\Windows\system32\VCOMP110.DLL
0x75840000 C:\Windows\system32\IMM32.DLL
0x75210000 C:\Windows\syswow64\MSCTF.dll
0x72C10000 C:\Ninja\intruder.dll
0x71070000 C:\Windows\system32\mswsock.dll
0x6B7D0000 C:\Windows\System32\wship6.dll
0x76140000 C:\Windows\syswow64\profapi.dll
0x67A90000 C:\Windows\system32\credssp.dll
0x6FC80000 C:\Windows\system32\DNSAPI.dll
0x6B7A0000 C:\Program Files (x86)\Bonjour\mdnsNSP.dll
0x6B750000 C:\Windows\System32\fwpuclnt.dll
0x6B790000 C:\Windows\system32\rasadhlp.dll
0x71060000 C:\Windows\System32\wshtcpip.dll
0x69C90000 C:\Windows\system32\dhcpcsvc6.DLL
0x6A010000 C:\Windows\system32\dhcpcsvc.DLL
0x67A10000 C:\Windows\system32\NLAapi.dll
0x67A00000 C:\Windows\system32\napinsp.dll
0x679E0000 C:\Windows\system32\pnrpnsp.dll
0x679C0000 C:\Windows\System32\winrnr.dll
0x75C00000 C:\Windows\syswow64\WINTRUST.dll
0x75300000 C:\Windows\syswow64\CRYPT32.dll
0x751F0000 C:\Windows\syswow64\MSASN1.dll
0x67B70000 C:\Windows\system32\d3d11.dll
0x72D60000 C:\Ninja\d3dx11_43.dll
0x46B20000 C:\Windows\system32\nvspcap.dll
0x6AF90000 C:\Windows\system32\uxtheme.dll
0x75C30000 C:\Windows\syswow64\CLBCatQ.DLL
0x60D80000 C:\Windows\system32\nvwgf2um.dll
0x75B60000 C:\Windows\syswow64\PSAPI.DLL
0x70A20000 C:\Windows\system32\bcrypt.dll
0x709E0000 C:\Windows\SysWOW64\bcryptprimitives.dll
0x73B10000 C:\Windows\system32\HID.DLL
0x74EC0000 C:\Windows\system32\CRYPTSP.dll
0x74E80000 C:\Windows\system32\rsaenh.dll
0x74E70000 C:\Windows\system32\RpcRtRemote.dll
0x73E60000 C:\Windows\System32\MMDevApi.dll
0x67F90000 C:\Windows\System32\PROPSYS.dll
0x73E20000 C:\Windows\system32\AUDIOSES.DLL
0x72D30000 C:\Windows\system32\avrt.dll
0x6AE60000 C:\Windows\system32\wdmaud.drv
0x72D50000 C:\Windows\system32\ksuser.dll
0x72D20000 C:\Windows\system32\msacm32.drv
0x72BF0000 C:\Windows\system32\MSACM32.dll
0x72D10000 C:\Windows\system32\midimap.dll
0x73EC0000 C:\Windows\SysWOW64\schannel.dll
0x69B70000 C:\Windows\system32\secur32.dll
0x70A40000 C:\Windows\system32\ncrypt.dll
0x76650000 C:\Windows\syswow64\USERENV.dll
0x70840000 C:\Windows\system32\GPAPI.dll
0x45450000 C:\Program Files (x86)\Frontier\EDLaunch\Products\FORC-FDEV-D-1002\dsfVorbisDecoder.dll
0x66CA0000 C:\Windows\WinSxS\x86_microsoft.vc80.crt_1fc8b3b9a1e18e3b_8.0.50727.6195_none_d09154e044272b9a\MSVCP80.dll
0x66ED0000 C:\Windows\WinSxS\x86_microsoft.vc80.crt_1fc8b3b9a1e18e3b_8.0.50727.6195_none_d09154e044272b9a\MSVCR80.dll
0x755C0000 C:\Windows\syswow64\urlmon.dll
0x75A80000 C:\Windows\syswow64\api-ms-win-downlevel-ole32-l1-1-0.dll
0x75F50000 C:\Windows\syswow64\api-ms-win-downlevel-shlwapi-l1-1-0.dll
0x75710000 C:\Windows\syswow64\api-ms-win-downlevel-advapi32-l1-1-0.dll
0x75B50000 C:\Windows\syswow64\api-ms-win-downlevel-user32-l1-1-0.dll
0x76790000 C:\Windows\syswow64\api-ms-win-downlevel-version-l1-1-0.dll
0x75200000 C:\Windows\syswow64\api-ms-win-downlevel-normaliz-l1-1-0.dll
0x777C0000 C:\Windows\syswow64\normaliz.DLL
0x76410000 C:\Windows\syswow64\iertutil.dll
0x75F60000 C:\Windows\syswow64\WININET.dll
0x6B1A0000 C:\Windows\system32\api-ms-win-downlevel-shlwapi-l2-1-0.dll
0x454D0000 C:\Program Files (x86)\Frontier\EDLaunch\Products\FORC-FDEV-D-1002\vp8decoder.dll
0x45F70000 C:\Program Files (x86)\Frontier\EDLaunch\Products\FORC-FDEV-D-1002\webmsplit.dll
0x66A90000 C:\Windows\system32\d3dcompiler_43.dll


LOG END

Sat Dec 13 12:19:23 2014


```
## Post #282
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-12-14T11:26:38+00:00
- Post Title: Re: Ninja Ripper

[quote="zookone"] My Ninja is getting smacked down...

Win7 64bit machine, using Ninja Ripper in dx11 wrapper mode. I think I have to use wrapper mode because game launcher blocks the ability to use intruder mode.

F9 texture capture is working for textures but unable to F10 capture models. Does anyone have a tip on what might be wrong? Maybe just doesn't work?

Sorry for the long log post below... Thanks

Are you trying to access a game thats 64bit, Ninja Ripper is 32bit and only works with 32bit applications.

However I was sent the source a few days back by the original creator as he's no longer working on it. I've taken a good look but changing everything from 32bit to 64bit functions and calls is a bit beyond my level, I understand a little of it, so if anyone thinks they're upto that challenge, I'll sent it on over.

I intended to upload it to github but I've not had the time so far.
## Post #283
- Username: zookone
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 29, 2013 6:14 am
- Post datetime: 2014-12-14T20:47:52+00:00
- Post Title: Re: Ninja Ripper

No the game is 32bit.
## Post #284
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2014-12-24T12:26:51+00:00
- Post Title: Re: Ninja Ripper

NinjaRipper is open source now. Merry Christmas

[https://github.com/blackninja2/ninjaripper](https://github.com/blackninja2/ninjaripper)
## Post #285
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-12-30T20:26:09+00:00
- Post Title: Re: Ninja Ripper

Excellent, thanks for letting us know!
## Post #286
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-03T15:21:50+00:00
- Post Title: Re: Ninja Ripper

Hey there!
Can someone explain the group-import function? I don't know how to use it   
I want to import ALL ripped meshes without importing every single one.

@BlackNinja BTW it would be awesome if you could make an option to rip all meshes into a single .rip.
## Post #287
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-03-03T17:50:03+00:00
- Post Title: Re: Ninja Ripper

> Reply from Slandey
>
> Hey there!
Can someone explain the group-import function? I don't know how to use it   
I want to import ALL ripped meshes without importing every single one.just type 0-N where N is the number for latest mesh of your folder rip.
## Post #288
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-07T09:56:36+00:00
- Post Title: Re: Ninja Ripper

Thanks!!

But now I have the problem that my PC will freeze because it has not enough RAM (3DS Max uses more than 3GB, WTF??) when I try to import all 2122 meshes.
(Game: Slender - The Arrival) I'll try to import them step-by-step, I mean the first 1-100, then 101-200, and so on.
## Post #289
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-03-07T11:43:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from Slandey
>
> But now I have the problem that my PC will freeze because it has not enough RAM (3DS Max uses more than 3GB, WTF??) when I try to import all 2122 meshes.you shouldn't put your 3ds max into some sort of a unaffordable task. Even though your pc rig has 8gb of ram and you'll be able to load all of 2122 meshes into 3ds max scene at once (or either step by step) I'm perfectly sure that you can not do anything with these meshes.

I would suggest to move textures out of the rip folder somwhere else and turn wireframe mode of your current 3ds max scene on. Then you can import rip files group by group.
## Post #290
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-07T14:37:14+00:00
- Post Title: Re: Ninja Ripper

Ok. BTW i have only 4 GB RAM 

The problem is that I cant set the render distance in Slender: The Arrival (and most other games) so I rip a lot more than I need, and I have no idea what I import cause there is no preview function etc.

Why is no 3D ripper perfect??   

3D Ripper DX: Warped meshes (FOV)
Ninja Ripper: Only 3DS Max support & this importing stuff
DX Ripper: Milkshape3D license needed
GameAssassin: Complicated & chinese

I don't want to complain, but this bothers me a bit.
NinjaRipper would be perfect if it rips to OBJ or FBX.
## Post #291
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-03-07T15:16:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from Slandey
>
> Why is no 3D ripper perfect??we always faced with limitations of possibilities, knowledge, interest. You have to be patient to get a perfect result. The Magic button simply can not exist
## Post #292
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2015-03-10T16:31:42+00:00
- Post Title: Re: Ninja Ripper

> Reply from Slandey
>
> Ok. BTW i have only 4 GB RAM 

Why is no 3D ripper perfect??   

3D Ripper DX: Warped meshes (FOV)
Ninja Ripper: Only 3DS Max support & this importing stuff
DX Ripper: Milkshape3D license needed
GameAssassin: Complicated & chinese

I don't want to complain, but this bothers me a bit.
NinjaRipper would be perfect if it rips to OBJ or FBX.

I really don't get the point about dx-ripper and ninja ripper which have an almost perfect noesis plug-in with preview, totally free.
Then with noesis tool u can can convert your rips in what format you want.
## Post #293
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-10T18:15:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from Ares722
>
> Slandey wrote:Ok. BTW i have only 4 GB RAM 

Why is no 3D ripper perfect??   

3D Ripper DX: Warped meshes (FOV)
Ninja Ripper: Only 3DS Max support & this importing stuff
DX Ripper: Milkshape3D license needed
GameAssassin: Complicated & chinese

I don't want to complain, but this bothers me a bit.
NinjaRipper would be perfect if it rips to OBJ or FBX.

I really don't get the point about dx-ripper and ninja ripper which have an almost perfect noesis plug-in with preview, totally free.
Then with noesis tool u can can convert your rips in what format you want.

You're right, but my knowledge changed A LOT since this post   

I didn't know that importing to 3DS Max fixes warped meshes.

EDIT: When I view a .rip model in Noesis it works & I have textures, but when I export it I have no textures?
I didn't tick "No texture" and tried to change the texture setting or the format.
## Post #294
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2015-03-21T17:51:11+00:00
- Post Title: Re: Ninja Ripper

> Reply from deadca7
>
> fil1969 wrote:Sorry, i have problems with Hitman Absolution... and also problems with the textures uv's ..
also the textures are a kind of blue...  please help! and sorry for my english

To fix the blue textures you need to swap the red channel with the blue channel.
Here's my quick and dirty Photoshop script that does the job for you http://filebeam.com/349161abf2095301b9f2c1cf1002c0d6
Almost every DX11 game I have ripped with NinjaRipper has this channel bug.

Ah! Thanks; I wanna try that script -- I was using XnView's RGB -> BGR option and boy was it tedious. 

==========================================================
Also, I have a general question about importing ripped .obj files into 3Ds Max:

Why do my models come out looking so...blocky and triangular? 




I rescaled and rotated the mesh in 3DS Max 2010, rearranged the UV Map and textures in UV Mapper, and in Milkshape I aligned the Normals and added backfaces (cuz 3DS Max confuses me on a good day). But the mesh just doesn't look any better.



This is the screen snap I ripped 

 

And yet in 3DS Max/Milkshape it was just a fugly mess. It wasn't even low poly, either -- there were like 4000 vertices alone, before I added the backfaces and it doubled the size.

So is there an important step I missed? 

Or a setting in Ninjas Ripper I overlooked? 

Or maybe my computer graphics, I dunno. Cuz it's just not sexy.
## Post #295
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2015-03-25T00:10:23+00:00
- Post Title: Re: Ninja Ripper

Rippers like Ninja Ripper, work by looking at what polygons are in the RAM or GPU memory, as it is being rendered, and trying to interpret that back into a file.

Some programs, games, emulators, etc., alter this data as it is rendered.
Many games transform the on screen geometry, by shrinking the models themselves as they get farther away from the camera object. This is how these games create the effect of perspective.

More than that, many games shrink models in the along the visual X and Y (according to the camera) while increasing the Z direction (camera 'depth').

More still, the game is always rendering as long as it is able. It's not uncommon for a game to store the next frame in RAM while the current one is being drawn, so that it can be immediately processed when the screen is filled. This could cause multiple copies of almost identical polygons to be ripped.

When you merge two vertices front to back, (such as a plane being merged to a plane just behind it) the normals are recalculated to try and find an appropriate light angle by taking the average of all the vertex normals connected to it, which on a single surface results in a nice smooth effect over an entire model. However, with the surfaces (which the computer sees as only having one side) are connected front to back, in the center somewhere, the average cannot be properly calculated, and ends up being some inverted angle or something of the like, which is why they tend to appear black (their surface normal is facing at an angle which never receives light).

All PS2 games transform the actual vertex positions before rendering.
Many PC games do as well, but not all. 

Some games do store nice T pose models in memory, and those are the games that get ripped nicely... others do not.

This is the reason for your issues.

There is no current tool for accurately fixing the camera frustum matrix transform that I am aware of. That is why it is always best to look for a more direct way of importing models, before relying on 3D Printscreen ripping, if you care about the accuracy.


Keeping that in mind, most 3D printscreen tools are not designed for the purpose of ripping game scenes, and this one is. And Ninja Ripper is far more reliable at it because of this.
## Post #296
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-26T15:38:25+00:00
- Post Title: Re: Ninja Ripper

I have a new problem that appears only in some games, not in every game.

(Test model: Camera from Portal 1)
In 3DS Max the model looks normal:

IMG

But when I export it and view it in other programs like Unity3D or Noesis, it looks like I can look through it and the outside is inside...

IMG

How can I fix this? I happens only in Portal (maybe all Source games, I haven't tried other)

EDIT 3/27/15: Images removed
## Post #297
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-03-26T17:44:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from Slandey
>
> But when I export it and view it in other programs like Unity3D or Noesis, it looks like I can look through it and the outside is inside...don't you think this is beside this thread?

flip polygons and remove map from alpha channel.
## Post #298
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-03-27T12:05:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Slandey wrote:But when I export it and view it in other programs like Unity3D or Noesis, it looks like I can look through it and the outside is inside...don't you think this is beside this thread?

flip polygons and remove map from alpha channel.

Thanks ^^
## Post #299
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-03-28T17:09:47+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Slandey wrote:But when I export it and view it in other programs like Unity3D or Noesis, it looks like I can look through it and the outside is inside...don't you think this is beside this thread?

flip polygons and remove map from alpha channel.

Its like just about every other 3D issue people have on the forum so often.

Its always simply because people just don't really know how to use 3D software properly, Nobody expects people do be able to rig, weightpaint, or anything advanced of course, but flipping a normal or actually 'applying' a texture to a material, these are the most basic of things (ok flipping normals might not be taught so early on I guess).

I think the forum could actually do with a 3D Software section so people could post all their 3D issues and people can simply reply with the tutorials they found when googling another users problem.

It might sound a bit dickish but the 3D issues are getting more and more basic and wasting several posts on fixing an issue a user could just google most of the time (the above post not withstanding as it was fixed in 2 posts)
## Post #300
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-04-01T07:41:49+00:00
- Post Title: Re: Ninja Ripper

I can't rip from newer Unity games (Games that have the "Select monitor" option in the launcher, probably Unity5)



Do you know why or have a solution?
## Post #301
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-04-07T08:10:19+00:00
- Post Title: Re: Ninja Ripper

someone is able to recode it in 64 bits, to rip 64 bits software, as the new Dolphin emulator in 64 bits ?
## Post #302
- Username: Slandey
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 10, 2014 11:20 am
- Post datetime: 2015-04-08T14:48:20+00:00
- Post Title: Re: Ninja Ripper

> Reply from CZW
>
> someone is able to recode it in 64 bits, to rip 64 bits software, as the new Dolphin emulator in 64 bits ?

Yes, that'd be gr8.
## Post #303
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2015-04-09T20:02:39+00:00
- Post Title: Re: Ninja Ripper

I have a question for using Ninja Ripper (D3D9 and D3D11 Wrapper) on PCSX2 0.9.8:

I'm trying to rip models from Magna Carta: Tears of Blood, and I got the .obj meshes out just fine ( [Shift] + [F8] ), but when I click [F9] to get the .dds textures, all it gives me in the _Ripper folder are just the useless on-screen captures.   




I have the model with no textures. It has a proper UV Map though.   



Is this maybe just a game-specific problem? Is there something about Magna Carta T.o.B that it refuses to give me the model's textures? I've been able to easily get .dds textures from other PS2 games with the [F9] button just fine. 

And TexMod only gives me 6 textures, while in other games it gives me 100+.   

So, I was just wondering.
## Post #304
- Username: falconcool
- Rank: veteran
- Number of posts: 105
- Joined date: Tue Jun 16, 2009 11:41 am
- Post datetime: 2015-05-25T12:12:52+00:00
- Post Title: Re: Ninja Ripper

A suggestion for Ninja Ripper coders.
The model captured by this tool currently is not what we saw on screen.It's the raw data from the model file.
Recent MMO games have amazing character customization.Some people may want to capture the model that you created by your own customization.
Hope you can add a function that can capture the screen model we see like Game Assassin and other old capture tool did.
## Post #305
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-05-25T18:06:32+00:00
- Post Title: Re: Ninja Ripper

> Reply from falconcool
>
> A suggestion for Ninja Ripper coders.
The model captured by this tool currently is not what we saw on screen.It's the raw data from the model file.
Recent MMO games have amazing character customization.Some people may want to capture the model that you created by your own customization.
Hope you can add a function that can capture the screen model we see like Game Assassin and other old capture tool did.

Its been stated a good 10 times in this thread, even on the front page.

Its now abandonware, free for anyone else to pickup if they so wanted.
## Post #306
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-06-29T15:12:06+00:00
- Post Title: Re: Ninja Ripper

My favorite ripper seems to be not working on Yebis3 engine games (Ride and MotoGP15 by Milestone in my case). It worked well on MotoGP14 which was running Yebis2.

When attempting to run the 32bit version, I got the "Function already hooked and have ANOTHER handler" message, and the rip button does nothing on 64 bits version for both mesh and textures 

While looking at the available code on Github, this error is coming from the Hook Manager, but I'm not good enough at coding (and doesn't have the "afxres.h" file due to my Visual Studio version) to resolve it by myself.

I'm fear nobody can help since I can see this in the code 

```
//Need additional research
```

which probably means even the great BlackNinja is thinking it will ask more work on code.

If anybody has an idea, I'll take it. I'm a bit hopeless
## Post #307
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-06-30T09:14:01+00:00
- Post Title: Re: Ninja Ripper

RiccoChicco 
Try VisualStudio 2010 for compiling ripper. Or correctly upgrade project for another IDE.

Ripper not will work on 64bit games. Ripper need porting  to 64bit. Sources are available.
## Post #308
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-06-30T10:53:46+00:00
- Post Title: Re: Ninja Ripper

Thanks, I'm gonna give it a try 

I'll let you know if I find anything.
## Post #309
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-07-13T09:40:40+00:00
- Post Title: Re: Ninja Ripper

Hi
Bug fixes beta release. If "Rip" button not work, try this version

NinjaRipper 1.1.5
[http://rghost.ru/7Hghc4Sf5](http://rghost.ru/7Hghc4Sf5)
## Post #310
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-07-15T14:35:57+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi
Bug fixes beta release. If "Rip" button not work, try this version

NinjaRipper 1.1.5
http://rghost.ru/7Hghc4Sf5

thks alot 
i hope, you can work on a version able to rip 64 bits programs ...
## Post #311
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-07-16T13:53:51+00:00
- Post Title: Re: Ninja Ripper

Thank you very much
## Post #312
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-07-19T09:49:16+00:00
- Post Title: Re: Ninja Ripper

I have checked last ripper version and updated the link on the main page:
[http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)

new version is 1.1.5:
- bug fix: D3D11 swaps the functions therefor set hooks doesn't worked.
## Post #313
- Username: kawayide
- Rank: beginner
- Number of posts: 37
- Joined date: Wed Nov 09, 2011 9:03 am
- Post datetime: 2015-07-23T03:49:21+00:00
- Post Title: Re: Ninja Ripper

Hi, I imported models to 3dsmax, everything is good except for textures are missing. I tried resident evil 5 and cod8, both no texture. How can I fix it?
## Post #314
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-07-27T07:48:57+00:00
- Post Title: Re: Ninja Ripper

Hi. Ninja Ripper updated. Now support x64.
Beta version. On any bugs attach log here.


[http://rghost.ru/7xRgSszzn](http://rghost.ru/7xRgSszzn)
## Post #315
- Username: sandmangecko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 29, 2015 12:01 am
- Post datetime: 2015-07-27T21:22:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi. Ninja Ripper updated. Now support x64.
Beta version. On any bugs attach log here.


http://rghost.ru/7xRgSszzn

Download link doesn't work, only one that does through this link is to a free game zone download.
## Post #316
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-07-28T07:42:53+00:00
- Post Title: Re: Ninja Ripper

Hmm. Strange

Try this
[https://yadi.sk/d/wNSS76PNi8Mv8](https://yadi.sk/d/wNSS76PNi8Mv8)
## Post #317
- Username: RiccoChicco
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Apr 06, 2015 12:45 am
- Post datetime: 2015-07-28T17:25:01+00:00
- Post Title: Re: Ninja Ripper

Amazing! Thank you Black Ninja!
## Post #318
- Username: sandmangecko
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 29, 2015 12:01 am
- Post datetime: 2015-07-29T11:41:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hmm. Strange

Try this
https://yadi.sk/d/wNSS76PNi8Mv8
Yup that link works, ill try the ripper later.
Thanks.
## Post #319
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-04T14:31:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi. Ninja Ripper updated. Now support x64.
Beta version. On any bugs attach log here.


http://rghost.ru/7xRgSszzn

it don't work with Dolphin Emulator 64 bits .. sadly ...
[https://dolphin-emu.org/download/?nocr=true](https://dolphin-emu.org/download/?nocr=true)

and trojan detected into the x86 version ( ESET V8.0 )
## Post #320
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-08-07T15:37:06+00:00
- Post Title: Re: Ninja Ripper

> Reply from ellegirl01
>
> I have a question for using Ninja Ripper (D3D9 and D3D11 Wrapper) on PCSX2 0.9.8:

I'm trying to rip models from Magna Carta: Tears of Blood, and I got the .obj meshes out just fine ( [Shift] + [F8] ), but when I click [F9] to get the .dds textures, all it gives me in the _Ripper folder are just the useless on-screen captures.   




I have the model with no textures. It has a proper UV Map though.   



Is this maybe just a game-specific problem? Is there something about Magna Carta T.o.B that it refuses to give me the model's textures? I've been able to easily get .dds textures from other PS2 games with the [F9] button just fine. 

And TexMod only gives me 6 textures, while in other games it gives me 100+.   

So, I was just wondering.

How do you rip the mesh with correct uv-mapping? Is it the result of Ninja Ripper? I tried using Ninja Ripper with Enthusia Professional Racing, i got the same kind of mesh that you got from doing SHIFT+F8, but when i scaled it, it always turn out weird. Something like FOV problem. I'm wondering how you get that character model just fine without the flipped faces and correct scaling. Can you please share how you rip the mesh?

EDIT : I know the mesh came up flat, but what i mean, is that when i re-scaled it so it looks like a car, the scaling seems kind of weird. Here's a picture of the model after being scaled in 3DSMax and imported into ZModeler 2 :
## Post #321
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-08-07T20:57:47+00:00
- Post Title: Re: Ninja Ripper

New version  1.2.5

+New games support
+Bug fixes

Download here:
http://cgig.ru/ninjaripper/
## Post #322
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-08-25T16:22:27+00:00
- Post Title: Re: Ninja Ripper

i have test the 1.2.7B with Dolphin emulator 64 bits

it look working !!! 
have you update your import script for 3Dmax ?? on which version it work today ?? V2015 , V2016 ??
do you have a script for Noesis ?
## Post #323
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2015-08-26T13:10:08+00:00
- Post Title: Re: Ninja Ripper

> Reply from REDZOEU
>
> ellegirl01 wrote:I have a question for using Ninja Ripper (D3D9 and D3D11 Wrapper) on PCSX2 0.9.8:

I'm trying to rip models from Magna Carta: Tears of Blood, and I got the .obj meshes out just fine ( [Shift] + [F8] ), but when I click [F9] to get the .dds textures, all it gives me in the _Ripper folder are just the useless on-screen captures.   




I have the model with no textures. It has a proper UV Map though.   



Is this maybe just a game-specific problem? Is there something about Magna Carta T.o.B that it refuses to give me the model's textures? I've been able to easily get .dds textures from other PS2 games with the [F9] button just fine. 

And TexMod only gives me 6 textures, while in other games it gives me 100+.   

So, I was just wondering. 

How do you rip the mesh with correct uv-mapping? Is it the result of Ninja Ripper? I tried using Ninja Ripper with Enthusia Professional Racing, i got the same kind of mesh that you got from doing SHIFT+F8, but when i scaled it, it always turn out weird. Something like FOV problem. I'm wondering how you get that character model just fine without the flipped faces and correct scaling. Can you please share how you rip the mesh?

EDIT : I know the mesh came up flat, but what i mean, is that when i re-scaled it so it looks like a car, the scaling seems kind of weird. Here's a picture of the model after being scaled in 3DSMax and imported into ZModeler 2 :

Ohhhhh trust me: the faces were ALL screwed up. Every time. It's TERRIBLE trying to fix them. I got lucky with this Calintz model, but did you see my other post? [viewtopic.php?p=104528#p104528](http://forum.xentax.com/viewtopic.php?p=104528#p104528)
TRAGIC.   

The scaling is weird, yes. You have to rescale it so it's not stretched to hell. 
The flipped faces are evil, yes. You have to reverse the vertex order, align the normals, smooth, wash, rinse, and repeat. 

It doesn't work for me all the time. I fiddle around A LOT; and move the mesh around between 3DS Max and Milkshape.
I can't tell you exactly how I got it, since I just click and click and click till the mesh looks right. Shots in the dark, honestly.

Also, with those gaps I'm seeing in your picture: can you turn on Backface Culling with the 3d Program you're using? I find that that helped me a great deal with those gaps you're seeing all over the mesh. 
3DS Max has the Backface Culling option under Object Properties when you right-click your mesh.  

I am still getting the odd F9 problem though. Sometimes I can press F9 and get all the textures I need. then a few days later I'll load up the same game with the same settings, and get only the screencapture. I have zero idea why it does this sometimes; I can't get ahead.
## Post #324
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2015-09-06T20:16:22+00:00
- Post Title: Re: Ninja Ripper

I figured it out -- somehow the renderer in GSdx9 got set to Software instead of Hardware, which is why I kept getting screencaptures instead of textures when pressing F9.   I'm back in business now; hurrah!
## Post #325
- Username: jetpack3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 10, 2015 1:00 am
- Post datetime: 2015-09-09T17:13:40+00:00
- Post Title: Re: Ninja Ripper

Can i get a direct download link to Ninja Ripper v1.1.5 Please?
When i try to download it, It says The page isn’t redirecting properly.
Here is the link i am using [http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)
## Post #326
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-09-10T05:09:15+00:00
- Post Title: Re: Ninja Ripper

Hi
New version 1.3.1

-Bug fixes
-New games support (nba2015, evil within etc)


[http://cgig.ru/ninjaripper](http://cgig.ru/ninjaripper)
## Post #327
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-09-10T05:16:58+00:00
- Post Title: Re: Ninja Ripper

still the 1.2.7b on your link ...
## Post #328
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-09-10T05:35:49+00:00
- Post Title: Re: Ninja Ripper

Clear browser cache
## Post #329
- Username: jetpack3
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 10, 2015 1:00 am
- Post datetime: 2015-09-10T05:49:50+00:00
- Post Title: Re: Ninja Ripper

Thank you Everyone I was able to download the v1.2.7b
## Post #330
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-09-10T07:26:46+00:00
- Post Title: Re: Ninja Ripper

It work thanks
## Post #331
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-09-12T08:25:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi
New version 1.3.1

-Bug fixes
-New games support (nba2015, evil within etc)


http://cgig.ru/ninjaripper

i have do a couple of tests with your last version ...
it's fantastic !!!
it work fine on Dolphin 64 bits .. to rip meshes without wrong faces orientation

except , we cannot rip twice .. the second request crash .. and we cannot rip textures
but i have an other way to rip textures ...
## Post #332
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-09-12T09:25:00+00:00
- Post Title: Re: Ninja Ripper

Hi
Ripper not tested on emulators

Is f9 textures rip button work?

Attach dolphin log here, pls
## Post #333
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2015-09-12T17:14:32+00:00
- Post Title: Re: Ninja Ripper

I'm trying to get character models and textures from Undying editor's (UndEd and UndEd2) model browser, but ninja catches nothing.
I have read the tutorial, but alas it doesn't have a troubleshooting section.
Running both, ninja and editor, as administrator.
Log shows 4 "hook set arg"s and loaded modules list, no errors.
Am I doing something wrong?

Thanks in advance.
## Post #334
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-09-13T12:44:22+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi
Ripper not tested on emulators

Is f9 textures rip button work?

Attach dolphin log here, pls

the button look working, but the folder is always empty

[http://www.filedropper.com/dolphinexelogtxt](http://www.filedropper.com/dolphinexelogtxt)
## Post #335
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-09-13T20:21:52+00:00
- Post Title: Re: Ninja Ripper

Tested on dolphin 4.0.1. Game ikaruga.

In dx9 video mode textures are saved.
In dx11 mode only meshes.
## Post #336
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2015-09-13T22:12:42+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Tested on dolphin 4.0.1. Game ikaruga.

In dx9 video mode textures are saved.
In dx11 mode only meshes.

Dolphin 4.0.1 is 1 year old
try the version 5.0
[https://dolphin-emu.org/download/](https://dolphin-emu.org/download/)

i use intruder setting
## Post #337
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-09-14T13:03:28+00:00
- Post Title: Re: Ninja Ripper

After log viewing, In dolphin 5
texture2d arrays used.
They not supported by ripper.
## Post #338
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2015-10-04T16:25:45+00:00
- Post Title: Re: Ninja Ripper

hey, i tested ninja ripper 1.3.1 beta for 64 bits. it is really good, but i have to you a request. I want to rip rooms (as models) and i cannot rip floor and ceiling (the highest and lowest meshes of room). Please fix that
## Post #339
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-04T19:40:42+00:00
- Post Title: Re: Ninja Ripper

May be floor is rendered as quad with four vertexes and it skipped by ripper

Open regedit
Hcu/software/blackninja/ninjaripper

Change minprimitive,minvertexes,minindexes to 0

May be this help
## Post #340
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2015-10-04T20:34:07+00:00
- Post Title: Re: Ninja Ripper

floor does appear!! but still i haven't ceiling  how this fix?


EDIT: now i can ceiling, just i must chnage for direct9D. THANK YOU!!!!!! )
## Post #341
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2015-10-06T07:21:15+00:00
- Post Title: Re: Ninja Ripper

Sorry for double post, but i have new problem.

first 5 meshes look that:



this is my regedit:



Can i fix that somehow?
## Post #342
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-06T08:15:42+00:00
- Post Title: Re: Ninja Ripper

Mkbewe, if you want your problems will be resolved and not be ignored you should provide more information such as game you ripping, log file. additionally you can post your pc specs.
## Post #343
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2015-10-07T09:34:48+00:00
- Post Title: Re: Ninja Ripper

How can i fix double ripping the same mesh? (too much triangles so i want one rip every one different mesh)
## Post #344
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-07T10:03:43+00:00
- Post Title: Re: Ninja Ripper

> Reply from Mkbewe
>
> How can i fix double ripping the same mesh? (too much triangles so i want one rip every one different mesh)ripper rips every mesh which is renders by game engine. newest game -> more shaders/more possibilities -> more "same" meshes. Frequently meshes are not the same — they can hold different useful information such as another UV layout. just import meshes you want.
## Post #345
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-10T05:41:51+00:00
- Post Title: Re: Ninja Ripper

New ripper version released.

cgig.ru/ninjaripper/
## Post #346
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-10-10T21:40:01+00:00
- Post Title: Re: Ninja Ripper

Is there any possibility/chance to make this work through a browser for 3d web content?
## Post #347
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-11T06:43:05+00:00
- Post Title: Re: Ninja Ripper

Yes, If browser render through directx

Set "inject to child process" checkbox in settings.
And browser as target exe
## Post #348
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-10-11T16:25:50+00:00
- Post Title: Re: Ninja Ripper

Thanks for the info, I guess the real problem is finding good content that renders through directX, I suppose all the model viewing websites use webgl or something like that?
## Post #349
- Username: Pavikjan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 11, 2015 2:45 am
- Post datetime: 2015-10-11T19:16:12+00:00
- Post Title: Re: Ninja Ripper

Hey guys!
It's my second post on this wonderful site! 
I am using Ninja Ripper for a while now and i have only come across one game i can't rip!
That cursed game is "Shadow Of Mordor".I need that Celebrimbor as same as i need to Eat and Sleep and Drink every day.
I put F9 to be my Ripping Button,i picked WRAPPER11 and Ran the game.
I go to "Change Skins"
I select Bright Lord one,and click F9,but nothing happens
I tried the Intruder but it says that i have d3d11.dll in x64.
I cut it from there and put it to the desktop and Run the game again (with Intruder) but still nothing happens.
Please HELP!!!
## Post #350
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-10-11T19:23:29+00:00
- Post Title: Re: Ninja Ripper

I would have questions to the creator of Ninja ripper. first of all thank you because thanks to you we were able to ottonere models such as dark souls, but unfortunately not always go as planned. I tried to use it on bioshock 2 to retrieve some texture but unfortunately I can not get anything! same thing happens to another game called Warhammer 40,000 team kill. you can do something?
## Post #351
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-11T21:00:16+00:00
- Post Title: Re: Ninja Ripper

Attach log here.
## Post #352
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2015-10-12T04:42:38+00:00
- Post Title: Re: Ninja Ripper

Is Ninja Ripper 1.3.4 beta avaible to download?
## Post #353
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-12T07:58:02+00:00
- Post Title: Re: Ninja Ripper

> Reply from Mkbewe
>
> Is Ninja Ripper 1.3.4 beta avaible to download?no, it's in progress.
## Post #354
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-10-12T10:12:01+00:00
- Post Title: Re: Ninja Ripper

have you ever thought of making a list of games in which it works ninja ripper?
## Post #355
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-12T11:00:12+00:00
- Post Title: Re: Ninja Ripper

> Reply from dibe91
>
> have you ever thought of making a list of games in which it works ninja ripper?actually recently I started working on it, but the list is still too short to make it public. so any help would be appreciated.
layout the following:

Year.....Title..........................Win.............DirectX....Bit....Mesh.....UV.....Textures
2015.....Battlefield Hardline........W7Prox64......11..........64....YES.......YES....YES
## Post #356
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-10-12T18:14:13+00:00
- Post Title: Re: Ninja Ripper

I can confirm that on dark souls one and two runs. we both mesh textures. The common problem is that the mapping is magnified around getting high! Nothing serious though. It can easily solve. while in dark souls 2 there is the problem that concerns the characters with capes. It lacks the mesh in between the shoulders and the rest of the coat. other games where it does not work is the series warhmmer 40000 Dawn of War 2 while another game that you call of the Orcs and Men are unable to have the mesh but the textures are white. I hope you can help!
## Post #357
- Username: Pavikjan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 11, 2015 2:45 am
- Post datetime: 2015-10-12T19:16:07+00:00
- Post Title: Re: Ninja Ripper

Is there a fix for F9 not doing anything.
I tested it with other games it works perfectly,but with soM it doesn't.
## Post #358
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-12T19:33:09+00:00
- Post Title: Re: Ninja Ripper

Attach log.
## Post #359
- Username: Pavikjan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 11, 2015 2:45 am
- Post datetime: 2015-10-12T20:48:02+00:00
- Post Title: Re: Ninja Ripper

I will attach it tomorrow.
## Post #360
- Username: bobbobbob
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 22, 2015 5:48 pm
- Post datetime: 2015-10-22T09:53:38+00:00
- Post Title: Re: Ninja Ripper

Ripped, worked wonders, but I'm having a few issues I was hoping someone could help me with. While the .rip files convert to OBJ just fine and work in most anything, I seem to be entirely unable to apply the textures to these models, and when I attempt to do so in 3ds using the plugin, it looks like a bad acid trip.

I tried watching a few youtube videos and they mention using the group function, however I'm only going for one model.

And oddly, the model is numbered 0044 but the corresponding texture file is 1950. 

Could someone help a newbie out? I'm at a point i'd even pay to get this done.
## Post #361
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-22T11:15:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from bobbobbob
>
> I seem to be entirely unable to apply the textures to these modelsapplying textures in 3ds max it's something outside this thread. watch youtube tutorials for this.

p.s.: sometimes there's no way to automatically apply texture on imported .rip mesh. there nothing we can do yet.
## Post #362
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-23T02:08:17+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper (lastest version) doesn't even work with google chrome or firefox just keeps telling me please check if (forgot this part) is writable, Is there anyways to fix this or no there is something i wanna rip from a website but can't.
## Post #363
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-23T04:18:22+00:00
- Post Title: Re: Ninja Ripper

Which web site url?
## Post #364
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-10-23T07:19:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Which web site url?

Um trying to rip halo 5 armor from halowaypoint [https://www.halowaypoint.com/en-us#customize-h5](https://www.halowaypoint.com/en-us#customize-h5) it uses Webgl as far as i know if that makes a difference but i can't get ninjaripper to even open chrome or firefox to even try it.
## Post #365
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-10-23T16:06:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from JakeGreen
>
> blackninja wrote:Which web site url?

Um trying to rip halo 5 armor from halowaypoint https://www.halowaypoint.com/en-us#customize-h5 it uses Webgl as far as i know if that makes a difference but i can't get ninjaripper to even open chrome or firefox to even try it.

NinjaRipper runs via DirectX applications, it won't work on WebGL stuff because WebGL isn't DirectX its more or less (from my understanding) a web version of OpenGL.

Almost nothing on websites runs using Direct X, it all runs WebGL.
## Post #366
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-24T07:18:29+00:00
- Post Title: Re: Ninja Ripper

No. Browsers emulate webgl through directx

Rip will aviable after some fixes in next version
## Post #367
- Username: patopeixe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 25, 2015 3:19 am
- Post datetime: 2015-10-24T19:22:22+00:00
- Post Title: Re: Ninja Ripper

So, I've tried using this on Street Fighter V (which is DirectX11, Unreal Engine 4) and all textures come out purple/pink. Is this working as intended? Also when I import the models corresponding to the proper textures to 3ds max 2016 they form a sphere instead of the proper model   

I'm sure I'm probably doing something wrong though
## Post #368
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-10-31T14:31:55+00:00
- Post Title: Re: Ninja Ripper

> Reply from patopeixe
>
> So, I've tried using this on Street Fighter V (which is DirectX11, Unreal Engine 4) and all textures come out purple/pink. Is this working as intended? Also when I import the models corresponding to the proper textures to 3ds max 2016 they form a sphere instead of the proper model   

I'm sure I'm probably doing something wrong though

Use umodel instead.

I already extracted models from SFV:

[https://www.youtube.com/watch?v=VvskRVewq9I](https://www.youtube.com/watch?v=VvskRVewq9I)
## Post #369
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-10-31T14:48:22+00:00
- Post Title: Re: Ninja Ripper

Where can I download sfv?
## Post #370
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2015-11-01T17:28:26+00:00
- Post Title: Re: Ninja Ripper

anyone managed to rip models from the new Tales of Zestiria ?

tried all ripping otions and got only a log file every time, maybe a windows 10 problem ?

edit : nevermind it uses opengl
## Post #371
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-11-02T05:03:55+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Where can I download sfv?

> PC users can get access to the online beta by pre-ordering Street Fighter V on Steam.
## Post #372
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-11-02T10:44:18+00:00
- Post Title: Re: Ninja Ripper

> Reply from shadowmoy
>
> edit : nevermind it uses opengl

Wow... A new game that uses opengl... I played it, and my graphics card could stop responding and recover randomly. That was reduced by setting the LOD detail to High/Medium. But to think that the game uses OpenGL... What a suprise.

And still no luck for RIDE. I was able to rip textures witj F8, but when i press F10 to get models, nothing happens. Tried intruder, DX11, and DXGI mode. Still no luck. I'm using the stable 1.3.3 version of Ninja Ripper (cmiiw).
## Post #373
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2015-11-02T16:07:38+00:00
- Post Title: Re: Ninja Ripper

hum strange, some guy posted models of tales of zestiria ripped using ninja ripper but not tposed, maybe this game is dx9 after all
here is my log :

```
[1CC8] © 2004 - 2015 black_ninja

[1CC8] LOG START
[1CC8] Date/Time: 2015/11/01 18:33:03

[1CC8] Inject mode: "intruder"

[1CC8] Texture downscale max width : 4096
[1CC8] Texture downscale max height: 4096
[1CC8] Texture downscale value: 2

[1CC8] Loaded Modules List
[1CC8] 0x00930000 C:\Program Files (x86)\Steam\steam.exe
[1CC8] 0x76EE0000 C:\WINDOWS\SYSTEM32\ntdll.dll
[1CC8] 0x74070000 C:\WINDOWS\SYSTEM32\KERNEL32.DLL
[1CC8] 0x766F0000 C:\WINDOWS\SYSTEM32\KERNELBASE.dll
[1CC8] 0x76B00000 C:\WINDOWS\SYSTEM32\WS2_32.dll
[1CC8] 0x76930000 C:\WINDOWS\SYSTEM32\sechost.dll
[1CC8] 0x76590000 C:\WINDOWS\SYSTEM32\RPCRT4.dll
[1CC8] 0x73FF0000 C:\WINDOWS\SYSTEM32\SspiCli.dll
[1CC8] 0x73FE0000 C:\WINDOWS\SYSTEM32\CRYPTBASE.dll
[1CC8] 0x73F80000 C:\WINDOWS\SYSTEM32\bcryptPrimitives.dll
[1CC8] 0x74340000 C:\WINDOWS\SYSTEM32\NSI.dll
[1CC8] 0x761C0000 C:\WINDOWS\SYSTEM32\USER32.dll
[1CC8] 0x74AD0000 C:\WINDOWS\SYSTEM32\GDI32.dll
[1CC8] 0x76C50000 C:\WINDOWS\SYSTEM32\ADVAPI32.dll
[1CC8] 0x76870000 C:\WINDOWS\SYSTEM32\msvcrt.dll
[1CC8] 0x71A20000 C:\WINDOWS\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_6.0.10240.16384_none_3bccb1ff6bcd1849\COMCTL32.dll
[1CC8] 0x74CE0000 C:\WINDOWS\SYSTEM32\SHELL32.dll
[1CC8] 0x745F0000 C:\WINDOWS\SYSTEM32\windows.storage.dll
[1CC8] 0x74170000 C:\WINDOWS\SYSTEM32\combase.dll
[1CC8] 0x74500000 C:\WINDOWS\SYSTEM32\shlwapi.dll
[1CC8] 0x74330000 C:\WINDOWS\SYSTEM32\kernel.appcore.dll
[1CC8] 0x76BC0000 C:\WINDOWS\SYSTEM32\shcore.dll
[1CC8] 0x763F0000 C:\WINDOWS\SYSTEM32\powrprof.dll
[1CC8] 0x76440000 C:\WINDOWS\SYSTEM32\profapi.dll
[1CC8] 0x74550000 C:\WINDOWS\SYSTEM32\OLEAUT32.dll
[1CC8] 0x74040000 C:\WINDOWS\SYSTEM32\IMM32.DLL
[1CC8] 0x760A0000 C:\WINDOWS\SYSTEM32\MSCTF.dll
[1CC8] 0x64AF0000 F:\Ninjaripper\x86\intruder.dll
[1CC8] 0x76450000 C:\WINDOWS\SYSTEM32\psapi.dll
[1CC8] LOG END

```


seems the injection work but the game don't show up and just stay in the process list without doing anything grrr.

edit : tested on a copy found on the net and the ripping work but the models are not tposed !
## Post #374
- Username: Pavikjan
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Oct 11, 2015 2:45 am
- Post datetime: 2015-11-08T10:13:32+00:00
- Post Title: Re: Ninja Ripper

Hey guys!
How do i rip models from Warhammer Online:Age Of Reckoning-Return Of reckoning
Help please!!I need those models!!
## Post #375
- Username: Lopunny
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 10, 2015 11:53 pm
- Post datetime: 2015-11-10T16:09:35+00:00
- Post Title: Re: Ninja Ripper

Not to sure if this is right place to post this, but is it possible to make Ninja Ripper to be able to rip from Burnout Paradise? Because currently the only way to rip from Burnout Paradise is by using 3D Ripper DX which didn't work for me. Even if it did worked, it required that I needed 3DS Max 2011 or older because the Max plugin only supports up to 3DS Max 2011. The .OBJ rip wouldn't work either because it will end up giving unusable UVs. Unless if there is another method to rip from Burnout Paradise that I didn't know, then basically ripping from Burnout Paradise is impossible.
## Post #376
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-11-14T22:00:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> No. Browsers emulate webgl through directx

Rip will aviable after some fixes in next version

this is great!
## Post #377
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-11-15T00:17:10+00:00
- Post Title: Re: Ninja Ripper

I've been trying to rip from Alien Isolation recently... back before Windows 10  hit, it used to rip textures fine, but now it's ripping everything with an odd green/blue tint... Here's a couple of examples: 

Does anyone know what might be going on and how I can possibly fix this? The ones on the right are how they USED to and should come out. The ones on the left being what happens now.
## Post #378
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-11-15T01:12:07+00:00
- Post Title: Re: Ninja Ripper

> Reply from trexjones
>
> I've been trying to rip from Alien Isolation recently... back before Windows 10  hit, it used to rip textures fine, but now it's ripping everything with an odd green/blue tint... Here's a couple of examples: 

Does anyone know what might be going on and how I can possibly fix this? The ones on the right are how they USED to and should come out. The ones on the left being what happens now.

R&B channels are swapped, open your texture in photophop and just correct it.
## Post #379
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-11-15T07:51:35+00:00
- Post Title: Re: Ninja Ripper

I need some help
When open noesis I get "ImportError: NO module named fmt_ninjaripper_rip_1.18"
I put "fmt_ninjaripper_rip_1.18.py"  in \noesis\plugins\python\
versions:python-3.5.0 & noesisv417
## Post #380
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2015-11-15T09:44:58+00:00
- Post Title: Re: Ninja Ripper

> Reply from trexjones
>
> how I can possibly fix this?
Fastest way is using XnView (or XnViewMP) batch converter with BGR>RGB parameter active.
## Post #381
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2015-11-15T10:43:28+00:00
- Post Title: Re: Ninja Ripper

> Reply from Darko
>
> 

R&B channels are swapped, open your texture in photophop and just correct it.

Thanks Darko!

I do have one more puzzle -- I tried ripping some of the Villain characters from Amazing Spider-man, but for some reason, it ripped everything BUT those characters. Does anyone know why it might skip some models like that?
## Post #382
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-28T07:35:47+00:00
- Post Title: Re: Ninja Ripper

Would this ever work with Assassin's Creed Syndicate?
## Post #383
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-11-28T09:30:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from pewposterous
>
> Would this ever work with Assassin's Creed Syndicate?hardly, Assassin's Creed engine uses way too complex techniques.
## Post #384
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-11-28T10:13:03+00:00
- Post Title: Re: Ninja Ripper

No mesh ripping available from AC. Non standart renderer used

Read this
[http://advances.realtimerendering.com/s ... 220dpi.pdf](http://advances.realtimerendering.com/s2015/aaltonenhaar_siggraph2015_combined_final_footer_220dpi.pdf)
## Post #385
- Username: pewposterous
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 30, 2015 12:05 pm
- Post datetime: 2015-11-28T10:29:59+00:00
- Post Title: Re: Ninja Ripper

Thanks for the info. Guess i'll have to wait for Archive_next~
## Post #386
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-03T07:13:50+00:00
- Post Title: Re: Ninja Ripper

New version released.

1.5.0 (03.12.2015)
+ Support Direct3D 6 (DirectX 6);
+ Autolegend USSR is now ripping properly with glass;

+ Support Direct3D 7 (DirectX 7);
+ Support DirectDraw;
+ Bug fixes in D3D9 ripper - now more meshes should rip properly;
+ Browser (Firefox only tested) ripping now working (Forced Hotkey, see Settings window);
+ Support of a rip of al the D3D7/D3D8/D3D9/D3D11 functions;

[http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)

p.s.: Tutorial is updating. Will inform when it's done.
Suggestions/questions are always usefull.
## Post #387
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-12-03T16:13:00+00:00
- Post Title: Re: Ninja Ripper

Finally! DirectX7 support! Will test it out tomorrow after my exam 
Big thanks Tosyk
## Post #388
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-03T16:36:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from REDZOEU
>
> Finally! DirectX7 support! Will test it out tomorrow after my exam 
Big thanks Tosykgood luck with exam and all thanks to blackninja.
## Post #389
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-12-04T05:08:28+00:00
- Post Title: Re: Ninja Ripper

Is it possible to add a function to enable ripping in place.

For some environments for example, having all objects recenter to 0 can get quite messy, is it possible to enable not reset to 0 positions at all?
## Post #390
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-04T06:23:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from lionheartuk
>
> Is it possible to add a function to enable ripping in place.
For some environments for example, having all objects recenter to 0 can get quite messy, is it possible to enable not reset to 0 positions at all?more NO than YES. It's completely different type of ripper.
## Post #391
- Username: Doronetty
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Jun 03, 2010 6:05 pm
- Post datetime: 2015-12-04T14:08:38+00:00
- Post Title: Re: Ninja Ripper

> Reply from REDZOEU
>
> Finally! DirectX7 support! Will test it out tomorrow after my exam 
Big thanks Tosyk
Yeah, it's a really GREAT NEWS about DX7 for me too!
## Post #392
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-12-06T08:41:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> lionheartuk wrote:Is it possible to add a function to enable ripping in place.
For some environments for example, having all objects recenter to 0 can get quite messy, is it possible to enable not reset to 0 positions at all?more NO than YES. It's completely different type of ripper.

Hmm interesting.

I tried the DX7 Ripper on A Final Fantasy IX World Map viewer, it ripped the models and textures, however the application splits the map into tiles, so it means Ninja Ripper turns all these tiles into tiles at the 0axis, so the end result is millions of individual tiles.

Perhaps some sort of option to merge vertices in memory before completing the rip? I'm not entirely sure how it works under the hood, but my thought is if the mesh is combined/merged then it will be ripped as 1 single large mesh, instead of lots of individual pieces, if that makes sense.

But its likely not possible as you say.
## Post #393
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-12-06T09:57:32+00:00
- Post Title: Re: Ninja Ripper

Try import mesh groups not single mesh
## Post #394
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-12-06T15:12:57+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Try import mesh groups not single mesh

Ah tried it, same situation unfortunately, just overlaps hundreds of map tiles ontop of eachother.
Damn.
## Post #395
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-12-11T23:41:09+00:00
- Post Title: Re: Ninja Ripper

Has anyone tried to ninja rip the game Panzar forged by chaos? its russian and i love the models but i cant seem to make ninja ripper work with it
## Post #396
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-13T19:51:00+00:00
- Post Title: Re: Ninja Ripper

New version released.

1.5.1 (09.12.2015)
+ Bug fixes in D3D11 ripper - minor issues with uv solved;
+ New importer added;

Tutorial is updated:
[http://cgig.ru/en/2012/10/how-to-use-ninja-ripper-en/](http://cgig.ru/en/2012/10/how-to-use-ninja-ripper-en/)

[http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)

Suggestions/questions are always usefull.
## Post #397
- Username: borisquezadaa
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 07, 2015 10:54 am
- Post datetime: 2015-12-22T14:49:45+00:00
- Post Title: Re: Ninja Ripper

I tried to rip the head from tutorial with no luck. Using firefox in windows 7 x64, both x32 and x64 executables and all modes intruder and wrapper. Only intruder creates a folder with some text in it but no rip at all.
## Post #398
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-22T19:20:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from borisquezadaa
>
> I tried to rip the head from tutorial with no luck. Using firefox in windows 7 x64, both x32 and x64 executables and all modes intruder and wrapper. Only intruder creates a folder with some text in it but no rip at all.it's a problem we can't reproduce on devs end. so I'll be appreciate for any details on how you ripping it, logs etc
## Post #399
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-12-22T23:22:34+00:00
- Post Title: Re: Ninja Ripper

How can i use this to rip from webGL viewers on browser?
## Post #400
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-23T06:39:09+00:00
- Post Title: Re: Ninja Ripper

> Reply from freakshow
>
> How can i use this to rip from webGL viewers on browser?why don't you like the tutorial on how to do it?
## Post #401
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-12-25T18:50:38+00:00
- Post Title: Re: Ninja Ripper

This Tool is Freaking Awesome!

Just wanted say that.

Is there any possible way to add vertex color support in the Rip process? such as in the formats like .ply, and I believe .wrl

I'm really curious to know if it's possible.

And... Thank you for the Great tool!
## Post #402
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-25T20:12:21+00:00
- Post Title: Re: Ninja Ripper

> Reply from Modman69
>
> Is there any possible way to add vertex color support in the Rip process?vertex coloring rips and can be loaded for some games with new 3ds max importer.
## Post #403
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-12-26T02:31:20+00:00
- Post Title: Re: Ninja Ripper

OOOHH! I can't wait, I'm gonna try this now:)))

Hmm...I couldn't get it to work, however I was using web browser rips maybe that's my problem.

Thanks for this great tool anyhow:)
## Post #404
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-12-26T07:41:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from Modman69
>
> Hmm...I couldn't get it to work, however I was using web browser rips maybe that's my problem.are you ripping from web browser? if so why do you think those models have vertex color?
## Post #405
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2015-12-26T10:30:59+00:00
- Post Title: Re: Ninja Ripper

Vertex color attribute presentation can be determined from rip file dump or vertex shader analyze(for experts)
## Post #406
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2015-12-26T16:57:58+00:00
- Post Title: Re: Ninja Ripper

Hi
Yes Firefox rip, and I assume they're vertex colors, because it looks like the original files uploaded were in a format that supports color on the model without UV maps like .ply
and they have no texture maps I'll send you a link to see for a sample yourself if you would like.
## Post #407
- Username: Snoopy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 12, 2015 9:50 pm
- Post datetime: 2016-01-07T12:12:07+00:00
- Post Title: Re: Ninja Ripper

Hello guys, has anyone had any luck with ripping google earth models? I need some of the legacy models but the tool won't rip in any mode. It just creates empty folders.
I've attached the log.
[googleearth.exe.log.txt.zip](https://xentaxbackup.github.io/file/10274_googleearth.exe.log.txt.zip)
## Post #408
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-01-07T17:07:54+00:00
- Post Title: Re: Ninja Ripper

Switch to d3d renderer in settings. Restart app
## Post #409
- Username: Snoopy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Jan 12, 2015 9:50 pm
- Post datetime: 2016-01-08T07:26:50+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Switch to d3d renderer in settings. Restart app
I was actually able to rip some models (apparently it doesnt work in win 10 or something), but I can't get the UVs to import properly in max. They are stretched and misplaced at best. For some objects there are no UVs.
## Post #410
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-01-17T07:52:57+00:00
- Post Title: Re: Ninja Ripper

I downloaded the last version of google earth but on settings I don't see any d3d mode only open gl or directx but direct x does not export anything do I need to use a different version ? Or where do I get d3d option i have also use all the different wrapper modes in ninjaripper 151 please help
## Post #411
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-01-23T21:54:53+00:00
- Post Title: Re: Ninja Ripper

Can anyone help me with this i wanted to rip some models from the new version of google earth to use it as base specially for proportions please if anyone knows how let me know i sent a pm to blackninja and snoopy because i think they know how but i have not receive any answer here or pm please i would really appreciated
## Post #412
- Username: Scaveng3r
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 05, 2016 10:09 pm
- Post datetime: 2016-02-05T15:31:06+00:00
- Post Title: Re: Ninja Ripper

Wow. It's been so long I even forgot my nickname. Very glad to see that 64bit version arrived. You're doing an amazing job. It has a huge potential for a whole plethora of uses. Starting from newbies having a way to learn how content for modern games is done, to reviving the modding community, which was in a steep decline for years. 

But the tool is not there yet. I wanna ask: will there be a way to rip 3D scenes without having all the props zeroed in the center? I remember 3DripperDX working in such way (but the scene got warped and deformed because the capture was based off of camera FOV).

I have a bunch of ideas for modding, but the way NinjaRipper is currently working you have to place all the props by hand. It's fine if you only need a single model, but completely inefficient for ripping landscapes and game world objects. If there was a way to rip scenes with everything in its place we could get the map modding really going. There's a lot of old/dead games with game worlds that could be given a new life. People still try to convert old GTA game worlds into the latest version. Unfortunately, for other games there's simply no way to get the content out. But NinjaRipper is universal. You don't need to disassemble the whole engine for each game. That's a BIG difference. If you can make it keep the object coordinates during capture, this will open the floodgate for really cool mods. 

I'm a 3d artist, not a programmer, but I imagine the easiest and cheapest way to do this would be to reset all the prop pivot points to zero while ripping. That way everything will stay in place. I personally can handle reassigning pivots for a bunch of props, that's not as bad as figuring where they should be. 

Anyway, enough of me rambling. Here's some feedback: I did a little test drive of NinjaRipper on NFS World. All works fine, except one issue with the car model. Its scale is way off and UV's are affected by it too. Could be fixed if exact scaling ratio is provided (but ideally would be great to know why this happens). Here's some screens:
## Post #413
- Username: Atreides Fighter
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 10, 2015 11:47 am
- Post datetime: 2016-02-05T19:51:15+00:00
- Post Title: Re: Ninja Ripper

Tosyk's level of programming - godlike
## Post #414
- Username: alex4x
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2016 2:35 am
- Post datetime: 2016-02-07T19:51:21+00:00
- Post Title: Re: Ninja Ripper

Very Interesting tool!  
Can i'm extract textures from METRO 2033 REDUX with this tool?
And what about shaders ? this tool can save HLSL shader files from running application?
## Post #415
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-02-12T01:26:22+00:00
- Post Title: Re: Ninja Ripper

I haven't been able to get this to work with a browser. Trying to rip: [nsfw](https://www.artstation.com/embed/1687119). I don't get a mesh using the marmo extractor, tried this instead, didn't work.

Is there a chance for a global monitoring setting? Or, would someone be willing to rip the above model for me?
## Post #416
- Username: Jimbo13
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 13, 2016 5:47 am
- Post datetime: 2016-02-12T22:01:59+00:00
- Post Title: Re: Ninja Ripper

Can anyone point me towards some tutorials most of the official website is down. I'm trying to get ninja.rips to a usable format, ideally I'd like to get them to Gmod or any common format I can find a exporter for.  I'm not much of a modeler I just goof around with videos and screen shots mainly, I have access to C4D & 3DS at school.

Any help or a pointer would be very much appreciated.
## Post #417
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-02-13T04:04:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from Jimbo13
>
> Can anyone point me towards some tutorials most of the official website is down. I'm trying to get ninja.rips to a usable format, ideally I'd like to get them to Gmod or any common format I can find a exporter for.  I'm not much of a modeler I just goof around with videos and screen shots mainly, I have access to C4D & 3DS at school.

Any help or a pointer would be very much appreciated.

There's a Blender 3D importer for ninja rip files (somewhere on this site, use search), then from Blender you can export to many other formats.
## Post #418
- Username: Scaveng3r
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 05, 2016 10:09 pm
- Post datetime: 2016-02-15T08:26:29+00:00
- Post Title: Re: Ninja Ripper

This thread sure seems quiet. Is it always like this or Tosyk is just taking a break?
## Post #419
- Username: segabit
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 21, 2016 3:05 am
- Post datetime: 2016-02-17T18:22:54+00:00
- Post Title: Re: Ninja Ripper

I followed the official walkthrough, and seemed to run everything ok. It copies a d3d9.dll file into the game folder and launches the game just fine. The problem is that it seems to ONLY write the log files, and never actually does any ripping when I press the correct F-keys. There's no pause in the game or anything. Is it supposed to copy the intruder.dll into the game directory? It seems to copy a different dll into that folder as it's much smaller in size.

Here are my settings:


Here's my log:

```
0217/131551 [3538] © 2004-2015 black_ninja

0217/131551 [3538] LOG START
0217/131551 [3538] Inject mode: "intruder"

0217/131551 [3538] Texture downscale max width : 4096
0217/131551 [3538] Texture downscale max height: 4096
0217/131551 [3538] Texture downscale value: 2

0217/131551 [3538] LdrLoadDll hooked. Target: 0x772AF33B
0217/131551 [3538] LdrUnloadDll hooked. Target: 0x772B3B8C
0217/131551 [3538] CreateProcessA hooked. Target: 0x76B41072
0217/131551 [3538] CreateProcessW hooked. Target: 0x76B4103D
0217/131551 [3538] CreateProcessAsUserW hooked. Target: 0x7662C53A
0217/131551 [3538] CreateProcessWithLogonW hooked. Target: 0x76665609
0217/131551 [3538] CreateProcessWithTokenW hooked. Target: 0x7666563F
0217/131551 [3538] D3D9 ripper init
0217/131551 [3538] Direct3DCreate9 hooked. Target: 0x5F580A62
0217/131553 [3538] CreateProcessW("C:\Program Files (x86)\Steam\steam.exe") return: 1
0217/131553 [3538] Injecting to child process. Status: OK
0217/131554 [3538] D3D9 ripper uninit

0217/131554 [3538] Loaded Modules List
0217/131554 [3538] --------------------------------
0217/131554 [3538] BaseAddr    Size         Module
0217/131554 [3538] --------------------------------
0217/131554 [3538] 0x00400000 (0x01F25000)  C:\Program Files (x86)\Steam\steamapps\common\Ghostbusters\ghost_w32.exe
0217/131554 [3538] 0x77270000 (0x00180000)  C:\Windows\SysWOW64\ntdll.dll
0217/131554 [3538] 0x76B30000 (0x00110000)  C:\Windows\syswow64\kernel32.dll
0217/131554 [3538] 0x753C0000 (0x00047000)  C:\Windows\syswow64\KERNELBASE.dll
0217/131554 [3538] 0x76CE0000 (0x00100000)  C:\Windows\syswow64\USER32.dll
0217/131554 [3538] 0x76DE0000 (0x00090000)  C:\Windows\syswow64\GDI32.dll
0217/131554 [3538] 0x76C40000 (0x0000A000)  C:\Windows\syswow64\LPK.dll
0217/131554 [3538] 0x75080000 (0x0009D000)  C:\Windows\syswow64\USP10.dll
0217/131554 [3538] 0x757C0000 (0x000AC000)  C:\Windows\syswow64\msvcrt.dll
0217/131554 [3538] 0x76620000 (0x000A1000)  C:\Windows\syswow64\ADVAPI32.dll
0217/131554 [3538] 0x76940000 (0x00019000)  C:\Windows\SysWOW64\sechost.dll
0217/131554 [3538] 0x76A30000 (0x000F0000)  C:\Windows\syswow64\RPCRT4.dll
0217/131554 [3538] 0x74BD0000 (0x00060000)  C:\Windows\syswow64\SspiCli.dll
0217/131554 [3538] 0x74BC0000 (0x0000C000)  C:\Windows\syswow64\CRYPTBASE.dll
0217/131554 [3538] 0x76830000 (0x0007B000)  C:\Windows\syswow64\comdlg32.dll
0217/131554 [3538] 0x76990000 (0x00057000)  C:\Windows\syswow64\SHLWAPI.dll
0217/131554 [3538] 0x65BE0000 (0x00084000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_5.82.7601.18837_none_ec86b8d6858ec0bc\COMCTL32.dll
0217/131554 [3538] 0x759D0000 (0x00C4B000)  C:\Windows\syswow64\SHELL32.dll
0217/131554 [3538] 0x75870000 (0x0015C000)  C:\Windows\syswow64\ole32.dll
0217/131554 [3538] 0x76C50000 (0x0008F000)  C:\Windows\syswow64\OLEAUT32.dll
0217/131554 [3538] 0x5F520000 (0x001C3000)  C:\Windows\system32\d3d9.dll
0217/131554 [3538] 0x745E0000 (0x00009000)  C:\Windows\system32\VERSION.dll
0217/131554 [3538] 0x65FC0000 (0x00006000)  C:\Windows\system32\d3d8thk.dll
0217/131554 [3538] 0x716A0000 (0x00013000)  C:\Windows\system32\dwmapi.dll
0217/131554 [3538] 0x00020000 (0x00016000)  C:\Program Files (x86)\Steam\steamapps\common\Ghostbusters\XINPUT1_3.dll
0217/131554 [3538] 0x75210000 (0x0019D000)  C:\Windows\syswow64\SETUPAPI.dll
0217/131554 [3538] 0x76960000 (0x00027000)  C:\Windows\syswow64\CFGMGR32.dll
0217/131554 [3538] 0x751F0000 (0x00012000)  C:\Windows\syswow64\DEVOBJ.dll
0217/131554 [3538] 0x41790000 (0x00025000)  C:\Windows\system32\DINPUT.dll
0217/131554 [3538] 0x74900000 (0x00032000)  C:\Windows\system32\WINMM.dll
0217/131554 [3538] 0x73530000 (0x00011000)  C:\Windows\system32\NETAPI32.dll
0217/131554 [3538] 0x73860000 (0x00009000)  C:\Windows\system32\netutils.dll
0217/131554 [3538] 0x73510000 (0x00019000)  C:\Windows\system32\srvcli.dll
0217/131554 [3538] 0x73500000 (0x0000F000)  C:\Windows\system32\wkscli.dll
0217/131554 [3538] 0x75120000 (0x00005000)  C:\Windows\syswow64\PSAPI.DLL
0217/131554 [3538] 0x510E0000 (0x00007000)  C:\Windows\system32\X3DAudio1_3.dll
0217/131554 [3538] 0x767A0000 (0x00035000)  C:\Windows\syswow64\WS2_32.dll
0217/131554 [3538] 0x75410000 (0x00006000)  C:\Windows\syswow64\NSI.dll
0217/131554 [3538] 0x755C0000 (0x00060000)  C:\Windows\system32\IMM32.DLL
0217/131554 [3538] 0x766D0000 (0x000CC000)  C:\Windows\syswow64\MSCTF.dll
0217/131554 [3538] 0x0FBB0000 (0x000C1000)  C:\ninjaripper\intruder.dll
0217/131554 [3538] 0x506F0000 (0x000EB000)  C:\Windows\system32\dbghelp.dll
0217/131554 [3538] 0x74360000 (0x00017000)  C:\Windows\system32\CRYPTSP.dll
0217/131554 [3538] 0x74320000 (0x0003B000)  C:\Windows\system32\rsaenh.dll
0217/131554 [3538] 0x71B30000 (0x00080000)  C:\Windows\system32\uxtheme.dll
0217/131554 [3538] 0x747D0000 (0x00058000)  C:\Program Files (x86)\Common Files\microsoft shared\ink\tiptsf.dll
0217/131554 [3538] 0x64BF0000 (0x000F5000)  C:\Windows\system32\PROPSYS.dll
0217/131554 [3538] 0x745F0000 (0x0019E000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_6.0.7601.18837_none_41e855142bd5705d\comctl32.dll
0217/131554 [3538] 0x768B0000 (0x00083000)  C:\Windows\syswow64\CLBCatQ.DLL
0217/131554 [3538] 0x743A0000 (0x00021000)  C:\Windows\system32\ntmarta.dll
0217/131554 [3538] 0x767E0000 (0x00045000)  C:\Windows\syswow64\WLDAP32.dll
0217/131554 [3538] 0x753B0000 (0x0000B000)  C:\Windows\syswow64\profapi.dll
0217/131554 [3538] 0x769F0000 (0x00004000)  C:\Windows\syswow64\api-ms-win-downlevel-shlwapi-l1-1-0.dll
0217/131554 [3538] 0x74E30000 (0x00005000)  C:\Windows\syswow64\api-ms-win-downlevel-advapi32-l1-1-0.dll
0217/131554 [3538] 0x745D0000 (0x00008000)  C:\Windows\system32\Secur32.dll
0217/131554 [3538] 0x745C0000 (0x00004000)  C:\Windows\system32\api-ms-win-downlevel-advapi32-l2-1-0.dll
0217/131554 [3538] 0x6FAC0000 (0x0004C000)  C:\Windows\system32\apphelp.dll
0217/131554 [3538] LOG END

```


No .rip files appear or anything. I would assume the log file would show an error if it didn't hook in correctly, but I don't see anything. I'm using Windows 7 64-bit. Ghostbusters is a 32-bit application, and I've seen that plenty of other people have used it successfully. Does anyone see something wrong? I'd appreciate any help I could get. Thank you in advance!
## Post #420
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-02-17T23:12:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from segabit
>
> I followed the official walkthrough, and seemed to run everything ok. It copies a d3d9.dll file into the game folder and launches the game just fine. The problem is that it seems to ONLY write the log files, and never actually does any ripping when I press the correct F-keys. There's no pause in the game or anything. Is it supposed to copy the intruder.dll into the game directory? It seems to copy a different dll into that folder as it's much smaller in size.

Here are my settings:


Here's my log:
Code: Select all0217/131551 [3538] Ninja Ripper 1.5.1 x86
0217/131551 [3538] © 2004-2015 black_ninja

0217/131551 [3538] LOG START
0217/131551 [3538] Inject mode: "intruder"

0217/131551 [3538] Texture downscale max width : 4096
0217/131551 [3538] Texture downscale max height: 4096
0217/131551 [3538] Texture downscale value: 2

0217/131551 [3538] LdrLoadDll hooked. Target: 0x772AF33B
0217/131551 [3538] LdrUnloadDll hooked. Target: 0x772B3B8C
0217/131551 [3538] CreateProcessA hooked. Target: 0x76B41072
0217/131551 [3538] CreateProcessW hooked. Target: 0x76B4103D
0217/131551 [3538] CreateProcessAsUserW hooked. Target: 0x7662C53A
0217/131551 [3538] CreateProcessWithLogonW hooked. Target: 0x76665609
0217/131551 [3538] CreateProcessWithTokenW hooked. Target: 0x7666563F
0217/131551 [3538] D3D9 ripper init
0217/131551 [3538] Direct3DCreate9 hooked. Target: 0x5F580A62
0217/131553 [3538] CreateProcessW("C:\Program Files (x86)\Steam\steam.exe") return: 1
0217/131553 [3538] Injecting to child process. Status: OK
0217/131554 [3538] D3D9 ripper uninit

0217/131554 [3538] Loaded Modules List
0217/131554 [3538] --------------------------------
0217/131554 [3538] BaseAddr    Size         Module
0217/131554 [3538] --------------------------------
0217/131554 [3538] 0x00400000 (0x01F25000)  C:\Program Files (x86)\Steam\steamapps\common\Ghostbusters\ghost_w32.exe
0217/131554 [3538] 0x77270000 (0x00180000)  C:\Windows\SysWOW64\ntdll.dll
0217/131554 [3538] 0x76B30000 (0x00110000)  C:\Windows\syswow64\kernel32.dll
0217/131554 [3538] 0x753C0000 (0x00047000)  C:\Windows\syswow64\KERNELBASE.dll
0217/131554 [3538] 0x76CE0000 (0x00100000)  C:\Windows\syswow64\USER32.dll
0217/131554 [3538] 0x76DE0000 (0x00090000)  C:\Windows\syswow64\GDI32.dll
0217/131554 [3538] 0x76C40000 (0x0000A000)  C:\Windows\syswow64\LPK.dll
0217/131554 [3538] 0x75080000 (0x0009D000)  C:\Windows\syswow64\USP10.dll
0217/131554 [3538] 0x757C0000 (0x000AC000)  C:\Windows\syswow64\msvcrt.dll
0217/131554 [3538] 0x76620000 (0x000A1000)  C:\Windows\syswow64\ADVAPI32.dll
0217/131554 [3538] 0x76940000 (0x00019000)  C:\Windows\SysWOW64\sechost.dll
0217/131554 [3538] 0x76A30000 (0x000F0000)  C:\Windows\syswow64\RPCRT4.dll
0217/131554 [3538] 0x74BD0000 (0x00060000)  C:\Windows\syswow64\SspiCli.dll
0217/131554 [3538] 0x74BC0000 (0x0000C000)  C:\Windows\syswow64\CRYPTBASE.dll
0217/131554 [3538] 0x76830000 (0x0007B000)  C:\Windows\syswow64\comdlg32.dll
0217/131554 [3538] 0x76990000 (0x00057000)  C:\Windows\syswow64\SHLWAPI.dll
0217/131554 [3538] 0x65BE0000 (0x00084000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_5.82.7601.18837_none_ec86b8d6858ec0bc\COMCTL32.dll
0217/131554 [3538] 0x759D0000 (0x00C4B000)  C:\Windows\syswow64\SHELL32.dll
0217/131554 [3538] 0x75870000 (0x0015C000)  C:\Windows\syswow64\ole32.dll
0217/131554 [3538] 0x76C50000 (0x0008F000)  C:\Windows\syswow64\OLEAUT32.dll
0217/131554 [3538] 0x5F520000 (0x001C3000)  C:\Windows\system32\d3d9.dll
0217/131554 [3538] 0x745E0000 (0x00009000)  C:\Windows\system32\VERSION.dll
0217/131554 [3538] 0x65FC0000 (0x00006000)  C:\Windows\system32\d3d8thk.dll
0217/131554 [3538] 0x716A0000 (0x00013000)  C:\Windows\system32\dwmapi.dll
0217/131554 [3538] 0x00020000 (0x00016000)  C:\Program Files (x86)\Steam\steamapps\common\Ghostbusters\XINPUT1_3.dll
0217/131554 [3538] 0x75210000 (0x0019D000)  C:\Windows\syswow64\SETUPAPI.dll
0217/131554 [3538] 0x76960000 (0x00027000)  C:\Windows\syswow64\CFGMGR32.dll
0217/131554 [3538] 0x751F0000 (0x00012000)  C:\Windows\syswow64\DEVOBJ.dll
0217/131554 [3538] 0x41790000 (0x00025000)  C:\Windows\system32\DINPUT.dll
0217/131554 [3538] 0x74900000 (0x00032000)  C:\Windows\system32\WINMM.dll
0217/131554 [3538] 0x73530000 (0x00011000)  C:\Windows\system32\NETAPI32.dll
0217/131554 [3538] 0x73860000 (0x00009000)  C:\Windows\system32\netutils.dll
0217/131554 [3538] 0x73510000 (0x00019000)  C:\Windows\system32\srvcli.dll
0217/131554 [3538] 0x73500000 (0x0000F000)  C:\Windows\system32\wkscli.dll
0217/131554 [3538] 0x75120000 (0x00005000)  C:\Windows\syswow64\PSAPI.DLL
0217/131554 [3538] 0x510E0000 (0x00007000)  C:\Windows\system32\X3DAudio1_3.dll
0217/131554 [3538] 0x767A0000 (0x00035000)  C:\Windows\syswow64\WS2_32.dll
0217/131554 [3538] 0x75410000 (0x00006000)  C:\Windows\syswow64\NSI.dll
0217/131554 [3538] 0x755C0000 (0x00060000)  C:\Windows\system32\IMM32.DLL
0217/131554 [3538] 0x766D0000 (0x000CC000)  C:\Windows\syswow64\MSCTF.dll
0217/131554 [3538] 0x0FBB0000 (0x000C1000)  C:\ninjaripper\intruder.dll
0217/131554 [3538] 0x506F0000 (0x000EB000)  C:\Windows\system32\dbghelp.dll
0217/131554 [3538] 0x74360000 (0x00017000)  C:\Windows\system32\CRYPTSP.dll
0217/131554 [3538] 0x74320000 (0x0003B000)  C:\Windows\system32\rsaenh.dll
0217/131554 [3538] 0x71B30000 (0x00080000)  C:\Windows\system32\uxtheme.dll
0217/131554 [3538] 0x747D0000 (0x00058000)  C:\Program Files (x86)\Common Files\microsoft shared\ink\tiptsf.dll
0217/131554 [3538] 0x64BF0000 (0x000F5000)  C:\Windows\system32\PROPSYS.dll
0217/131554 [3538] 0x745F0000 (0x0019E000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_6.0.7601.18837_none_41e855142bd5705d\comctl32.dll
0217/131554 [3538] 0x768B0000 (0x00083000)  C:\Windows\syswow64\CLBCatQ.DLL
0217/131554 [3538] 0x743A0000 (0x00021000)  C:\Windows\system32\ntmarta.dll
0217/131554 [3538] 0x767E0000 (0x00045000)  C:\Windows\syswow64\WLDAP32.dll
0217/131554 [3538] 0x753B0000 (0x0000B000)  C:\Windows\syswow64\profapi.dll
0217/131554 [3538] 0x769F0000 (0x00004000)  C:\Windows\syswow64\api-ms-win-downlevel-shlwapi-l1-1-0.dll
0217/131554 [3538] 0x74E30000 (0x00005000)  C:\Windows\syswow64\api-ms-win-downlevel-advapi32-l1-1-0.dll
0217/131554 [3538] 0x745D0000 (0x00008000)  C:\Windows\system32\Secur32.dll
0217/131554 [3538] 0x745C0000 (0x00004000)  C:\Windows\system32\api-ms-win-downlevel-advapi32-l2-1-0.dll
0217/131554 [3538] 0x6FAC0000 (0x0004C000)  C:\Windows\system32\apphelp.dll
0217/131554 [3538] LOG END


No .rip files appear or anything. I would assume the log file would show an error if it didn't hook in correctly, but I don't see anything. I'm using Windows 7 64-bit. Ghostbusters is a 32-bit application, and I've seen that plenty of other people have used it successfully. Does anyone see something wrong? I'd appreciate any help I could get. Thank you in advance!

I'm having the exact same issue as ^; only a log file, no rip files.

I really hope this project hasn't died, it was so close to perfect.
## Post #421
- Username: Scaveng3r
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 05, 2016 10:09 pm
- Post datetime: 2016-02-18T01:25:44+00:00
- Post Title: Re: Ninja Ripper

That happened to me once, but then I realized I accidentally pressed the "Fmode" key on my keyboard    Not that I think you guys had done the same, but just worth to mention.
## Post #422
- Username: HBOSS81
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 22, 2015 9:48 am
- Post datetime: 2016-02-18T07:26:42+00:00
- Post Title: Re: Ninja Ripper

Hey guys,
Great application! Love tinkering with this thing. Everything works great so far, (I can rip textures in .dds format & view them/extract them) and models just fine. Haven't sorted out how to get them to load into ninja ripper's importer plugin with the textures on them though, I have to manually place them. I managed to run the importer script via the shelf menu button in MAX to run the script and I was also able to set up GIM's version (troubleshooting this setup resulted in the extracted files being "blocked" after extract, so I changed that status via properties option, then reloaded 3DS Max and it worked instantly).

Honestly, the only issue I'm having at this point is within Noesis itself. I installed the plugins as instructed per the website source, yet when I run Noesis, at launch, I get this message, "ImportError: No module named fmt_ninjaripper_rip_1.18". So I click "ok", it goes away and nothing seems to malfunction otherwise. Any help with this error message would be great and much appreciated. I have double/triple checked that the needed files are in the correct directories as per the install instructions (the fmt_ninjaripper_rip_1.18.py is in the "~./plugins/python" folder dir for Noesis v 4.177 & I even included the "fmt_ninjaripper_rip_1.18.ms" file, but to no avail. I also have a small question about this..is it necessary to have Noesis, Ninja Ripper, & 3DS Max runing simultaneously in order for Noesis to somehow detect the "fmt_ninjaripper_rip_1.18.py" file? I didn't think it would be necessary once the rips are done.

PS: Later on, I'll be posting up an in-depth, step-by-step PICTURE tutorial on how to quickly, rip models/textures, fix UV coordinate's manually (as I don't the the exact 3DS MAX ninja importer by GIM to further automate this process for me.) Feedback welcome once I post it up. You won't need to edit any file's at all (granted you can get the F10 function to work for you in the default settings on Ninja Ripper; as well as Noesis v.4177, already having your .dds game cache extracts done/ready to view after extracting them with the most current Quick BMS>>Darkness2.bms script available online in the forums/internet), aside from that you only have to adjust 3 minor settings at most on any ripped model in order to get the textures to be placed correctly in the baked-in UV set's (if they don't match then you changed a setting in the ninja ripper importer tool or you got a bad rip, it happens). It is possible to apply all the required files within 3DS max, but I personally found way faster to do all the texture applications in TennoGen Workshop because of the different terminology seen/used in the Tennogen tool versus the Autodesk softwares, then I could zip it complete for steam if I/you like or you can save it to your own assets collection. I'll gladly help anyone who asks, I won't do it for you though..simply, I'll demystify any issues you're having. Hope this much info helps all you out there breaking your heads over this stuff.
## Post #423
- Username: segabit
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 21, 2016 3:05 am
- Post datetime: 2016-02-18T15:57:43+00:00
- Post Title: Re: Ninja Ripper

> Reply from Scaveng3r
>
> That happened to me once, but then I realized I accidentally pressed the "Fmode" key on my keyboard    Not that I think you guys had done the same, but just worth to mention.
Thanks! It's not that for me anyway. The function keys do the normal functions, and my keyboard doesn't have different modes for the F-keys. I take screenshots in steam for instance when I hit F12. I thought maybe Steam's actions were getting in the way, and changed to different F-keys in ninjaripper, but that doesn't work either. Has anyone had it work with Steam specifically? Do I need a non-steam version of the game?

And is it bad that it says "D3D9 ripper uninit"?
## Post #424
- Username: HBOSS81
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 22, 2015 9:48 am
- Post datetime: 2016-02-19T05:42:55+00:00
- Post Title: Re: Ninja Ripper

> Reply from segabit
>
> Scaveng3r wrote:That happened to me once, but then I realized I accidentally pressed the "Fmode" key on my keyboard    Not that I think you guys had done the same, but just worth to mention.
Thanks! It's not that for me anyway. The function keys do the normal functions, and my keyboard doesn't have different modes for the F-keys. I take screenshots in steam for instance when I hit F12. I thought maybe Steam's actions were getting in the way, and changed to different F-keys in ninjaripper, but that doesn't work either. Has anyone had it work with Steam specifically? Do I need a non-steam version of the game?

And is it bad that it says "D3D9 ripper uninit"?

Yes, it does work with steam version games, i've tested this out on several which have non steam version as well and i get the same results. As to whether it'll possibly affect your account status and end you in the BANNED list..i don't know. From what I've noticed everything ninja ripper does is outside the game so you're not really hacking it in any way, simply "hooking" DX9/11 functions in a duplicate window, rather than the default window made by the game. All I've accessed is game caches which most games make too that arent on steam. just depends on the title. so far i've had this work on Warframe, Arma, and a few other games.
## Post #425
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-02-20T13:45:28+00:00
- Post Title: Re: Ninja Ripper

Has anyone figured out the browser problem yet? I'm itching to get started on a project that requires a specific model.
## Post #426
- Username: lurchi5000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 25, 2013 3:32 pm
- Post datetime: 2016-02-24T12:07:16+00:00
- Post Title: Re: Ninja Ripper

Hey guys,

if GTA 5 is ripped with Ninja Ripper are not shown the parts transparent
(windshield for example)
what setting is required to represent all meshes
## Post #427
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2016-02-24T16:54:11+00:00
- Post Title: Re: Ninja Ripper

Hello buddies,
Last time i downloaded ninja ripper 1.5.1. It ripped very well, but i have problem in 3ds max. When i import more than 20 .rip files, 3ds max crashes (disappair all 4 windows and models). In previous version of Ninja Ripper i haven't that problem, even i can import over 600 models in one time. Can you fix that in this version?
I have 3ds max 2011.
## Post #428
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-02-25T07:24:04+00:00
- Post Title: Re: Ninja Ripper

> Reply from alex4x
>
> Can i'm extract textures from METRO 2033 REDUX with this tool?
And what about shaders ? this tool can save HLSL shader files from running application?you can extract textures and shaders with the latest version of NR.

> Reply from Karric
>
> I haven't been able to get this to work with a browser. Trying to rip: nsfw. I don't get a mesh using the marmo extractor, tried this instead, didn't work.
Is there a chance for a global monitoring setting? Or, would someone be willing to rip the above model for me?what browser do did you use? what your specific actions for ripping nfsw? Global monitoring will never happen.

> Reply from Jimbo13
>
> Can anyone point me towards some tutorials most of the official website is down.website is up now.

> Reply from segabit
>
> I followed the official walkthrough, and seemed to run everything ok. It copies a d3d9.dll file into the game folder and launches the game just fine. The problem is that it seems to ONLY write the log files, and never actually does any ripping when I press the correct F-keys. There's no pause in the game or anything. Is it supposed to copy the intruder.dll into the game directory? It seems to copy a different dll into that folder as it's much smaller in size.try to use both "intruder" and "wrapper" mode.

> Reply from Karric
>
> Has anyone figured out the browser problem yet? I'm itching to get started on a project that requires a specific model.what issue do you have?

> Reply from lurchi5000
>
> if GTA 5 is ripped with Ninja Ripper are not shown the parts transparent
(windshield for example)
what setting is required to represent all meshesthat kind of objects for most of the times in the end of the mesh list. So you should load ALL the meshes from a folder and delete redundant ones.

> Reply from Mkbewe
>
> Last time i downloaded ninja ripper 1.5.1. It ripped very well, but i have problem in 3ds max. When i import more than 20 .rip files, 3ds max crashes (disappair all 4 windows and models). In previous version of Ninja Ripper i haven't that problem, even i can import over 600 models in one time. Can you fix that in this version?
I have 3ds max 2011.it happens when 3ds max can't handle a huge amount of textures because of a video memory lack. Turn wireframe mode on in you 3d max and try to load meshes again.
## Post #429
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-02-25T10:58:06+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Karric wrote:I haven't been able to get this to work with a browser. Trying to rip: nsfw. I don't get a mesh using the marmo extractor, tried this instead, didn't work.
Is there a chance for a global monitoring setting? Or, would someone be willing to rip the above model for me?what browser do did you use? what your specific actions for ripping nfsw? Global monitoring will never happen.
segabit wrote:I followed the official walkthrough, and seemed to run everything ok. It copies a d3d9.dll file into the game folder and launches the game just fine. The problem is that it seems to ONLY write the log files, and never actually does any ripping when I press the correct F-keys. There's no pause in the game or anything. Is it supposed to copy the intruder.dll into the game directory? It seems to copy a different dll into that folder as it's much smaller in size.try to use both "intruder" and "wrapper" mode.

I have the same problem as Segabit, only a log file is created. I've tried every mode, changed the capture keys, nothing works. There is no pause or any sign of a capturing process. I've tried several browser models from different sites, no go.

I'm using Windows 7 64-bit w/ Firefox (newest version). Could it be something about my Direct X? Does hardware type have an impact?

Also, when you launch the .exe using NR, is it possible to have some kind of notification or visual that NR is ready/not ready to extract?
## Post #430
- Username: Scaveng3r
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 05, 2016 10:09 pm
- Post datetime: 2016-02-25T12:36:08+00:00
- Post Title: Re: Ninja Ripper

I guess this means no object placement support...
## Post #431
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-02-25T13:20:24+00:00
- Post Title: Re: Ninja Ripper

> Reply from Karric
>
> I have the same problem as Segabit, only a log file is created. I've tried every mode, changed the capture keys, nothing works. There is no pause or any sign of a capturing process. I've tried several browser models from different sites, no go.

I'm using Windows 7 64-bit w/ Firefox (newest version). Could it be something about my Direct X? Does hardware type have an impact?

Also, when you launch the .exe using NR, is it possible to have some kind of notification or visual that NR is ready/not ready to extract?send me links to websites with models you want to rip. Also, several users report that newest firefox version is not working.

about notification - it's not possible.
## Post #432
- Username: segabit
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 21, 2016 3:05 am
- Post datetime: 2016-02-25T16:44:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> Karric wrote:I have the same problem as Segabit, only a log file is created. I've tried every mode, changed the capture keys, nothing works. There is no pause or any sign of a capturing process. I've tried several browser models from different sites, no go.

I'm using Windows 7 64-bit w/ Firefox (newest version). Could it be something about my Direct X? Does hardware type have an impact?

Also, when you launch the .exe using NR, is it possible to have some kind of notification or visual that NR is ready/not ready to extract?send me links to websites with models you want to rip. Also, several users report that newest firefox version is not working.

about notification - it's not possible.

Karric's issue is with websites, but we both have the same results and I focus on games. We only get log files, and nothing else. I've tried several Steam games that others have confirmed as working, like Ghostbusters The Video Game or Sonic & SEGA All-Stars Racing. I've personally stuck with 32-bit games as I've heard there are problems with 64-bit. Tried intruder and wrapper modes. It uses DirectX 9, but I've tried them all.

I posted a log for Ghostbusters above, but here's another for Sonic All Stars Racing in case that has any new information. I can't find anything in the log that would show an error with trying to rip when the rip key is pressed. I've tried every single F-key just in case it didn't take my F-key settings.

```
0225/112619 [18A8] © 2004-2015 black_ninja

0225/112619 [18A8] LOG START
0225/112619 [18A8] Inject mode: "intruder"

0225/112619 [18A8] Texture downscale max width : 4096
0225/112619 [18A8] Texture downscale max height: 4096
0225/112619 [18A8] Texture downscale value: 2

0225/112619 [18A8] LdrLoadDll hooked. Target: 0x778EF33B
0225/112619 [18A8] LdrUnloadDll hooked. Target: 0x778F3B8C
0225/112619 [18A8] CreateProcessA hooked. Target: 0x75811072
0225/112619 [18A8] CreateProcessW hooked. Target: 0x7581103D
0225/112619 [18A8] CreateProcessAsUserW hooked. Target: 0x7591C53A
0225/112619 [18A8] CreateProcessWithLogonW hooked. Target: 0x75955609
0225/112619 [18A8] CreateProcessWithTokenW hooked. Target: 0x7595563F
0225/112619 [18A8] D3D9 ripper init
0225/112619 [18A8] Direct3DCreate9 hooked. Target: 0x624B0A62
0225/112621 [18A8] CreateProcessW("C:\Program Files (x86)\Steam\steam.exe") return: 1
0225/112621 [18A8] Injecting to child process. Status: OK
0225/112622 [18A8] D3D9 ripper uninit

0225/112622 [18A8] Loaded Modules List
0225/112622 [18A8] --------------------------------
0225/112622 [18A8] BaseAddr    Size         Module
0225/112622 [18A8] --------------------------------
0225/112622 [18A8] 0x00400000 (0x00B4E000)  C:\Program Files (x86)\Steam\steamapps\common\Sonic and SEGA All Stars Racing\Sonic & SEGA All-Stars Racing.exe
0225/112622 [18A8] 0x778B0000 (0x00180000)  C:\Windows\SysWOW64\ntdll.dll
0225/112622 [18A8] 0x75800000 (0x00110000)  C:\Windows\syswow64\kernel32.dll
0225/112622 [18A8] 0x773C0000 (0x00047000)  C:\Windows\syswow64\KERNELBASE.dll
0225/112622 [18A8] 0x74F40000 (0x00032000)  C:\Windows\system32\WINMM.dll
0225/112622 [18A8] 0x75520000 (0x000AC000)  C:\Windows\syswow64\msvcrt.dll
0225/112622 [18A8] 0x772C0000 (0x00100000)  C:\Windows\syswow64\USER32.dll
0225/112622 [18A8] 0x75CA0000 (0x00090000)  C:\Windows\syswow64\GDI32.dll
0225/112622 [18A8] 0x75680000 (0x0000A000)  C:\Windows\syswow64\LPK.dll
0225/112622 [18A8] 0x77090000 (0x0009D000)  C:\Windows\syswow64\USP10.dll
0225/112622 [18A8] 0x75910000 (0x000A1000)  C:\Windows\syswow64\ADVAPI32.dll
0225/112622 [18A8] 0x76D10000 (0x00019000)  C:\Windows\SysWOW64\sechost.dll
0225/112622 [18A8] 0x759E0000 (0x000F0000)  C:\Windows\syswow64\RPCRT4.dll
0225/112622 [18A8] 0x75210000 (0x00060000)  C:\Windows\syswow64\SspiCli.dll
0225/112622 [18A8] 0x75200000 (0x0000C000)  C:\Windows\syswow64\CRYPTBASE.dll
0225/112622 [18A8] 0x62450000 (0x001C3000)  C:\Windows\system32\d3d9.dll
0225/112622 [18A8] 0x74C20000 (0x00009000)  C:\Windows\system32\VERSION.dll
0225/112622 [18A8] 0x6EA50000 (0x00006000)  C:\Windows\system32\d3d8thk.dll
0225/112622 [18A8] 0x72430000 (0x00013000)  C:\Windows\system32\dwmapi.dll
0225/112622 [18A8] 0x0FD70000 (0x001E5000)  C:\Windows\system32\d3dx9_42.dll
0225/112622 [18A8] 0x59560000 (0x00030000)  C:\Windows\system32\DINPUT8.dll
0225/112622 [18A8] 0x00020000 (0x00016000)  C:\Windows\system32\XINPUT1_3.dll
0225/112622 [18A8] 0x75AF0000 (0x0019D000)  C:\Windows\syswow64\SETUPAPI.dll
0225/112622 [18A8] 0x75EB0000 (0x00027000)  C:\Windows\syswow64\CFGMGR32.dll
0225/112622 [18A8] 0x75D40000 (0x0008F000)  C:\Windows\syswow64\OLEAUT32.dll
0225/112622 [18A8] 0x77130000 (0x0015C000)  C:\Windows\syswow64\ole32.dll
0225/112622 [18A8] 0x759C0000 (0x00012000)  C:\Windows\syswow64\DEVOBJ.dll
0225/112622 [18A8] 0x59610000 (0x000EB000)  C:\Windows\system32\dbghelp.dll
0225/112622 [18A8] 0x760C0000 (0x00C4B000)  C:\Windows\syswow64\SHELL32.dll
0225/112622 [18A8] 0x76D90000 (0x00057000)  C:\Windows\syswow64\SHLWAPI.dll
0225/112622 [18A8] 0x003B0000 (0x00007000)  C:\Windows\system32\X3DAudio1_6.dll
0225/112622 [18A8] 0x77430000 (0x0007B000)  C:\Windows\syswow64\comdlg32.dll
0225/112622 [18A8] 0x6D830000 (0x00084000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_5.82.7601.18837_none_ec86b8d6858ec0bc\COMCTL32.dll
0225/112622 [18A8] 0x76D30000 (0x00060000)  C:\Windows\system32\IMM32.DLL
0225/112622 [18A8] 0x75DD0000 (0x000CC000)  C:\Windows\syswow64\MSCTF.dll
0225/112622 [18A8] 0x0F580000 (0x000C1000)  C:\Users\username\Documents\_Projects\Rip\ninjaripper\intruder.dll
0225/112622 [18A8] 0x75EA0000 (0x00005000)  C:\Windows\syswow64\psapi.dll
0225/112622 [18A8] 0x747A0000 (0x00017000)  C:\Windows\system32\CRYPTSP.dll
0225/112622 [18A8] 0x74760000 (0x0003B000)  C:\Windows\system32\rsaenh.dll
0225/112622 [18A8] 0x72450000 (0x00080000)  C:\Windows\system32\uxtheme.dll
0225/112622 [18A8] 0x74DD0000 (0x000F5000)  C:\Windows\system32\PROPSYS.dll
0225/112622 [18A8] 0x74C30000 (0x0019E000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_6.0.7601.18837_none_41e855142bd5705d\comctl32.dll
0225/112622 [18A8] 0x75EE0000 (0x00083000)  C:\Windows\syswow64\CLBCatQ.DLL
0225/112622 [18A8] 0x749C0000 (0x00021000)  C:\Windows\system32\ntmarta.dll
0225/112622 [18A8] 0x75630000 (0x00045000)  C:\Windows\syswow64\WLDAP32.dll
0225/112622 [18A8] 0x75AD0000 (0x0000B000)  C:\Windows\syswow64\profapi.dll
0225/112622 [18A8] 0x75310000 (0x00004000)  C:\Windows\syswow64\api-ms-win-downlevel-shlwapi-l1-1-0.dll
0225/112622 [18A8] 0x757F0000 (0x00005000)  C:\Windows\syswow64\api-ms-win-downlevel-advapi32-l1-1-0.dll
0225/112622 [18A8] 0x74C10000 (0x00008000)  C:\Windows\system32\Secur32.dll
0225/112622 [18A8] 0x74C00000 (0x00004000)  C:\Windows\system32\api-ms-win-downlevel-advapi32-l2-1-0.dll
0225/112622 [18A8] 0x75180000 (0x0004C000)  C:\Windows\system32\apphelp.dll
0225/112622 [18A8] LOG END
```


Could we have something in the log to show a failed rip? I can't figure out what in these logs means that it might not work. I run this on the same games on another machine and it rips, so I know I'm setting it up/using it correctly, but I can't get it to rip on my own machine. Thanks so much for your help.
## Post #433
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-02-26T09:59:38+00:00
- Post Title: Re: Ninja Ripper

segabit
From log:
Child process steam.exe created (CreateProcess function).
Another log from child processes must present in logs dir.

May be try another version of game, without steam.
## Post #434
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-03-03T23:28:38+00:00
- Post Title: Re: Ninja Ripper

I have a question. for so long I'm trying to retrieve textures from bioshock 2 and would like to use ripper ninja. it is feasible or not?
## Post #435
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-03-04T07:10:04+00:00
- Post Title: Re: Ninja Ripper

dibe91
[http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/)
## Post #436
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-04T07:38:36+00:00
- Post Title: Re: Ninja Ripper

> Reply from dibe91
>
> I have a question. for so long I'm trying to retrieve textures from bioshock 2 and would like to use ripper ninja. it is feasible or not?why don't you use goldor's umodel instead? Use google to search.
## Post #437
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-03-05T00:37:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> dibe91 wrote:I have a question. for so long I'm trying to retrieve textures from bioshock 2 and would like to use ripper ninja. it is feasible or not?why don't you use goldor's umodel instead? Use google to search.

I know him very well UModel but can not upload some texture such as the drill. for this I want to use ninjaripper or something similar
## Post #438
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-05T00:51:42+00:00
- Post Title: Re: Ninja Ripper

> Reply from dibe91
>
> Tosyk wrote:dibe91 wrote:I have a question. for so long I'm trying to retrieve textures from bioshock 2 and would like to use ripper ninja. it is feasible or not?why don't you use goldor's umodel instead? Use google to search.I know him very well UModel but can not upload some texture such as the drill. for this I want to use ninjaripper or something similarwell in this case ninja ripper fits you perfectly.
## Post #439
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-07T01:13:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> NinjaRipper is open source now. Merry Christmas

https://github.com/blackninja2/ninjaripper
Source is gone
## Post #440
- Username: nicociri
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 08, 2016 1:44 am
- Post datetime: 2016-03-07T17:56:45+00:00
- Post Title: Re: Ninja Ripper

So ninjaripper does: "Extracting all available vertex information of the models (position"

I'm trying to rip some models from Transformers:Devastation and the ripper works, no problems with it.

But it rips the transformer model in its "zero" position (standing straight, arms to the sides). the scenery is also misplaced: it rips every model, but not in the right places.

I want to rip the model in a particular action, much like dxripper used to do: I make the character do something and capture just the right moment.

I am doing something wrong or it is just the way ninjaripper works?

Win7 64bits (info FYI, not sure if it matters)

Thanks!
## Post #441
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-03-07T19:00:48+00:00
- Post Title: Re: Ninja Ripper

AceWell
After version 1.2 ripper only free, not open source.
## Post #442
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2016-03-08T18:53:33+00:00
- Post Title: Re: Ninja Ripper

I've been experimenting with Dark Souls and Ninja Ripper and found that it crashes when run on Linux under Wine. This happens because of [this call](https://github.com/jacky14/ninjaripper/blob/master/intruder/dx9/SaveTexture9.cpp#L331), which is still there in the current version. I could not find any documentation that suggests that it is OK to pass NULL to SetGammaRamp as the ramp parameter, so I hesitate to call this a bug in Wine. Replacing this call with NOPs makes it work just fine.

Also, it seems that the ripper checks only 8 texture slots, when actually there are 16 or so. Judging by the shader code, Dark Souls actually puts a texture in slot 15 of some objects for some reason. It's probably just a light map or something similar though.

On the positive side, since I couldn't find a good blender importer for .rip files, I made a new [script](https://github.com/angavrilov/blender-scripts/blob/master/import-ninja.py), and with the right parameters it seems to handle Dark Souls data correctly.

Edit: Here are the [script settings](https://i.imgur.com/YUb9DRG.png) for Dark Souls in case somebody is interested. For 'filter by shader inputs' to work you need to enable ripping "Shaders (for experts)" and import the files from the _NinjaRipper folder.
## Post #443
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-03-09T12:08:55+00:00
- Post Title: Re: Ninja Ripper

AlexNG 
Good job
## Post #444
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2016-03-09T14:25:58+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> well in this case ninja ripper fits you perfectly.

Sir i have a problem with Ninja Ripper.
Two days ago, i've started ripping stuff from MGS V and MGO, some of it have been ripped and cleaned relatevly successfully, but today i've stumbled with problem, that game will not launch with ripper involved. I think today's steam update involved. Ripper haven't worked for many people but because of some odds, it worked for me until today.
Please help me out with this, many people need this to be working.

edit:
here's a link on facepunch with some details of problem

[https://facepunch.com/showthread.php?t= ... st49898295](https://facepunch.com/showthread.php?t=1443449&p=49898295&viewfull=1#post49898295)
## Post #445
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-03-11T01:30:41+00:00
- Post Title: Re: Ninja Ripper

My friend, I use the NinjaRipper interception model in MAX, but its UV is wrong, do you have the solution?
Bad English. I'm sorry
## Post #446
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-11T06:03:20+00:00
- Post Title: Re: Ninja Ripper

> Reply from wjh12338093
>
> 


My friend, I use the NinjaRipper interception model in MAX, but its UV is wrong, do you have the solution?
Bad English. I'm sorryinstead of tell obvious things you should provide more details.
## Post #447
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-03-11T09:41:41+00:00
- Post Title: Re: Ninja Ripper

I uploaded the NinjaRipper file, take a look at.

[http://www.filedropper.com/frame0001](http://www.filedropper.com/frame0001)
## Post #448
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-03-11T09:49:19+00:00
- Post Title: Re: Ninja Ripper

> Reply from wjh12338093
>
> I uploaded the NinjaRipper file, take a look at.

http://www.filedropper.com/frame0001where did you ripped this file?
## Post #449
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-03-11T11:40:36+00:00
- Post Title: Re: Ninja Ripper

Can't download? I sent up。


 Frame0001.zip
(68.43 KiB) Downloaded 21 times
## Post #450
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-03-11T18:03:13+00:00
- Post Title: Re: Ninja Ripper

I think what Tosyk means is Mesh_0009.rip isn't the same thing from the image you posted before



Mesh_0009.png (23.06 KiB) Viewed 386 times
## Post #451
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-03-12T00:34:09+00:00
- Post Title: Re: Ninja Ripper

I'm sorry, I forgot to material.

You can see, UV, it's not open, but a ball.
## Post #452
- Username: Snowmeow
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Nov 17, 2010 5:07 am
- Post datetime: 2016-03-12T06:29:11+00:00
- Post Title: Re: Ninja Ripper

Seems interesting.
May it rip from 3d games running under MAME?
## Post #453
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2016-03-12T10:09:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from wjh12338093
>
> I uploaded the NinjaRipper file, take a look at.

For some reason that game appears to declare all vertex attributes as UV coordinates. In reality they seem to be:

 4 component position
 2 component UV
 4 components, likely normal but I don't understand the encoding
 4 component blend indices
 4 component blend weights
## Post #454
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2016-03-12T18:24:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from wjh12338093
>
> I'm sorry, I forgot to material.

You can see, UV, it's not open, but a ball.

Just curious, what game is it?
## Post #455
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-03-13T02:42:19+00:00
- Post Title: Re: Ninja Ripper

the game is Sky forge.
## Post #456
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2016-03-13T16:16:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from wjh12338093
>
> Can't download? I sent up。
Frame0001.zip
I took a fast look at the ripped frame and i noticed that the UV seams were intact, so the uv maps where present, u simply need to change the UV parameters in the import script  manually from ( U=6;V=7) to (U=4;V=5) and u get the correct UV maps:



Unfortunately the UV maps are too small, and don't fit correctly the texture so u have to manually scale them. The correct UVmap scale is 400% of the original size. I use the old import script, so i don't know if the new one can automatically scale the UV. If u use the old one, one way is to use this Blue monster script to scale them:
[http://polycount.com/discussion/124526/ ... ly-3ds-max](http://polycount.com/discussion/124526/scale-uvs-numerically-3ds-max) .

That is the result, i hope this help:
## Post #457
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-03-15T01:49:24+00:00
- Post Title: Re: Ninja Ripper

Can anyone help me extract some models from the new Google earth 
i have tried all the settings  in version 1.5.1 but non of them rip anything please any help would be appreciated
## Post #458
- Username: BOTLANNER
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 17, 2016 12:22 am
- Post datetime: 2016-03-16T16:26:49+00:00
- Post Title: Re: Ninja Ripper

Is it possible to implement some way of importing the modified models or at least textures back into the game from which we ripped it a la Texmod? If it were open source I would have tried myself but I see it is not.
## Post #459
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-03-21T23:18:28+00:00
- Post Title: Re: Ninja Ripper

Tosyk,  blackninja, can you give us an update on your interest/plans regarding this thread and NJ?
## Post #460
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-03-22T06:04:40+00:00
- Post Title: Re: Ninja Ripper

Karric
Ripper development/updates stopped due no donations.
## Post #461
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2016-03-22T10:03:51+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> it happens when 3ds max can't handle a huge amount of textures because of a video memory lack. Turn wireframe mode on in you 3d max and try to load meshes again.

Well, i can't do that, because boxes in wireframes dissapair too. For the luck i have Ninja Ripper 1.3.3 and works perfectly
## Post #462
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-01T09:40:38+00:00
- Post Title: Re: Ninja Ripper

Hi. 
Tiny update v1.5.2

[http://rghost.ru/7t9CbjYb7](http://rghost.ru/7t9CbjYb7)
## Post #463
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-03T19:44:43+00:00
- Post Title: Re: Ninja Ripper

Thanks for the update 
I will be happy to donate but can u please tell me how to use your tool to rip 3d from google earth new version
please contact me i tried contacting you before but you didnt answer pm or email let me know please
## Post #464
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-04T18:02:03+00:00
- Post Title: Re: Ninja Ripper

Joserod1980
Attach ripper log on google earth
## Post #465
- Username: JinzoAdvance
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2016 4:28 am
- Post datetime: 2016-04-04T21:40:14+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> chrrox wrote:i see no options for anything besides verts normals and uv's.
where are the weighting / bone import options.there is no options to do that, because our (blackninja and my) knowledges in max scripting is poorFirst off, I'd like to say thanks to you and Mr. Ninja. Anyway, if Max Scripting is still a pain, I'd suggest going for Blender 2.77 if you think working with Python 3.5 would be easier. 

I'm not sure if this link will be useful to you or not, but I'll offer it just in case it is helpful in some way.
[http://richardssoftware.net/Home/Post/34](http://richardssoftware.net/Home/Post/34)

I'll also mention this. I've tried using the ripdump exe file with a few files and noticed that it did have "blendindices" and "blendweight" variables.
## Post #466
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2016-04-05T08:12:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from JinzoAdvance
>
> Anyway, if Max Scripting is still a pain, I'd suggest going for Blender 2.77 if you think working with Python 3.5 would be easier.

My recently made [blender importer add-on](https://github.com/angavrilov/blender-import-ninjaripper) already supports weights, vertex colors and multiple UV maps, although it's only tested on Dark Souls 1 data. Also, obviously there's no skeleton or meaningful bone names, since there's no available data for that.
## Post #467
- Username: JinzoAdvance
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Apr 05, 2016 4:28 am
- Post datetime: 2016-04-06T02:01:16+00:00
- Post Title: Re: Ninja Ripper

> Reply from AlexNG
>
> JinzoAdvance wrote:Anyway, if Max Scripting is still a pain, I'd suggest going for Blender 2.77 if you think working with Python 3.5 would be easier.

My recently made blender importer add-on already supports weights, vertex colors and multiple UV maps, although it's only tested on Dark Souls 1 data. Also, obviously there's no skeleton or meaningful bone names, since there's no available data for that.It seems to import vertex groups. Nice! You might want to consider seeing if you can use them to produce bones. They might have generic names, but the bones can be renamed after they are imported if it works.
## Post #468
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-06T05:45:54+00:00
- Post Title: Re: Ninja Ripper

i tried with the new version of your tool and now is able to rip 3d and textures but when loads on 3d software its a complete mess no way to tell what is  what its pretty much useless
maybe this problem has nothing to do with your tools but with the way google earth loads 3d  but i dont really know anyway here is the log of the last rip i did
perhaps you might see something wrong 
Thanks
[googleearth.exe.log.rar](https://xentaxbackup.github.io/file/10739_googleearth.exe.log.rar)
## Post #469
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2016-04-06T06:35:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from Joserod1980
>
> i tried with the new version of your tool and now is able to rip 3d and textures but when loads on 3d software its a complete mess no way to tell what is  what its pretty much useless
maybe this problem has nothing to do with your tools but with the way google earth loads 3d  but i dont really know anyway here is the log of the last rip i did
perhaps you might see something wrong 
Thanks

Dude, look on the date of new update - it was April Fools!
## Post #470
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-06T09:29:06+00:00
- Post Title: Re: Ninja Ripper

Joserod1980
From log, new ripper works correctly. 
Correct import is not ripper problem. 
Read ripper manual, attach rip file etc
## Post #471
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-07T02:25:06+00:00
- Post Title: Re: Ninja Ripper

This is what i wanted to rip and thats what i got  its really hard to find any usable parts its more than 400 all mix together
 here is the rip if you want to take a look




 File
[http://www.mediafire.com/download/lwfwq ... th.exe.rar](http://www.mediafire.com/download/lwfwq3cz62rc5w3/2016.04.05_22.11.29_googleearth.exe.rar)

Thanks
## Post #472
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2016-04-07T09:37:33+00:00
- Post Title: Re: Ninja Ripper

> Reply from Joserod1980
>
> This is what i wanted to rip and thats what i got  its really hard to find any usable parts its more than 400 all mix together
 here is the rip if you want to take a look

Yet another program that declares all attributes as UV coordinates. The real types seem to be:

 3 component position
 4 component blendindices
 2 component UV

Applying that it's obvious that the program splits the scenery into cubical fragments. Arranging those unfortunately is up to you.

As an aside, I wonder if it's technically possible for the ripper to export the values of uniform shader parameters (as raw data if nothing else), if exporting shaders is enabled. I think it might enable making import scripts that recover e.g. object positions in specific simple cases.
## Post #473
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-07T11:46:05+00:00
- Post Title: Re: Ninja Ripper

AlexNG
Yes, it  possible to dump shader params with shaders
But as I sayed before, tool development stopped.
## Post #474
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-07T16:09:14+00:00
- Post Title: Re: Ninja Ripper

Hey please contact me if you can help me with this problem like i said i can help you with a donation if its something that you can do thats not too much work as i cannot donate too much but please contact me maybe we can reach an agreement. Google eqrth is free so you can do the testing and see what to fix thanks for the help 
[joserod1980@hotmail.com](mailto:joserod1980@hotmail.com)
## Post #475
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-07T16:37:03+00:00
- Post Title: Re: Ninja Ripper

Joserod1980
No time for that now.
Try another tool.
## Post #476
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-07T21:41:57+00:00
- Post Title: Re: Ninja Ripper

There is no tool that can do that and since all the others stopped updating years ago thats why i was asking you you were the only one still updating anyway thanks
## Post #477
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-15T16:33:38+00:00
- Post Title: Re: Ninja Ripper

Blackninja,
First thanks for a great program 

I'm having some problems ripping many 64-bit games, what happens is that the maps like occlusion, etc. are ripped in display-size textures and 1x1x1 planes, but none of the actual geometry. This does not happen in 32-bit versions (tested on games like Tomb Raider that can be started in either 32- or 64-bit), not sure whether it's a DX9 vs. DX11 problem or something different.

Will you be able to assist? I can donate a few $$$ either way as I've had good use of Ninja Ripper but would definitely consider funding development of working 64-bit ripping if you believe it can be done.
## Post #478
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-16T04:41:32+00:00
- Post Title: Re: Ninja Ripper

Zoetropes
32 and 64 versions uses same code.

Ripper trys to save ALL meshs/textures/shaders in both modes.
Dx9 and dx11 games uses different render techniques.
Try to find better mode for rip 32/64/dx9/dx11 game.
## Post #479
- Username: ravage
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 13, 2014 1:39 am
- Post datetime: 2016-04-17T16:52:35+00:00
- Post Title: Re: Ninja Ripper

Hi, ninja ripper is not working with Just Cause 2, when i press the rip keys like F12 there is no response?
## Post #480
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-17T21:16:21+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Zoetropes
32 and 64 versions uses same code.

Ripper trys to save ALL meshs/textures/shaders in both modes.
Dx9 and dx11 games uses different render techniques.
Try to find better mode for rip 32/64/dx9/dx11 game.

Hi, thanks for your response!

I've tried every option and using intruder, force rip and forced interval set to 90-120 seconds, I get more meshes but not at all as many as expected (by a few hundred less) and mostly 1x1 planes holding composed maps for the entire screen (specular, occlusion, and so on). The logfile states "ID3D11DeviceContext_DrawIndexed target hook not found" if that is any help?
## Post #481
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-18T07:18:41+00:00
- Post Title: Re: Ninja Ripper

Zoetropes
Attach full log
## Post #482
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-18T22:53:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Zoetropes
Attach full log

I tried attaching it but it's too large for the forum, which parts of the log are you interested in?
## Post #483
- Username: phailhaus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 30, 2014 1:47 pm
- Post datetime: 2016-04-20T15:59:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from Zoetropes
>
> blackninja wrote:Zoetropes
Attach full log

I tried attaching it but it's too large for the forum, which parts of the log are you interested in?

Upload it to [WHFF](https://frogbox.es/whff/). It should easily fit on there.
## Post #484
- Username: Zoetropes
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jun 11, 2014 12:37 am
- Post datetime: 2016-04-21T16:50:45+00:00
- Post Title: Re: Ninja Ripper

> Reply from phailhaus
>
> Zoetropes wrote:blackninja wrote:Zoetropes
Attach full log

I tried attaching it but it's too large for the forum, which parts of the log are you interested in?

Upload it to WHFF. It should easily fit on there.

Hi, it seems the max filesize is 768 MB on WHHF, my log file is over 2 GB. If I set the forced interval to lower so not as much gets ripped, the logfile shrinks in size, but then I get a lot more missing geometry and textures.

I uploaded a much smaller file:[https://i.frogbox.es/gdz](https://i.frogbox.es/gdz) (Couldn't upload here as the forum didn't take .log or .txt, didn't want to keep retrying).

Hopefully this can shed some light on things!
## Post #485
- Username: Joserod1980
- Rank: beginner
- Number of posts: 23
- Joined date: Thu Apr 30, 2015 6:16 am
- Post datetime: 2016-04-28T02:42:20+00:00
- Post Title: Re: Ninja Ripper

Hey blackninja im doing a little better at my work i was wondering if you can help me get good rips from google earth let me know how much would i need to donate so you can help me fix that  thanks
## Post #486
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-04-29T09:56:08+00:00
- Post Title: Re: Ninja Ripper

Joserod1980
Project closed due no donations. 
No time for that now.
## Post #487
- Username: mrschinken123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 16, 2016 8:11 pm
- Post datetime: 2016-05-16T12:15:02+00:00
- Post Title: Re: Ninja Ripper

ohai,

I am having a problem with v1.5.1 and Guild Wars 2 - injecting seems to work fine - but ninja ripper also tries to inject into child processes, which in this case kills the entire programm since the child is "CoherentUI" which is no dx9 app.
Is there any way to disable the child injecting?

Log attached & Thank you.

> 0516/134334 [15D0] Ninja Ripper 1.5.1 x64
>
> 0516/134334 [15D0] © 2004-2015 black_ninja
>
> 
>
> 0516/134334 [15D0] LOG START
>
> 0516/134334 [15D0] Inject mode: "intruder"
>
> 
>
> 0516/134334 [15D0] Texture downscale max width : 4096
>
> 0516/134334 [15D0] Texture downscale max height: 4096
>
> 0516/134334 [15D0] Texture downscale value: 2
>
> 
>
> 0516/134334 [15D0] LdrLoadDll hooked. Target: 0x00000000772F7A90
>
> 0516/134334 [15D0] LdrUnloadDll hooked. Target: 0x00000000772F3AE0
>
> 0516/134334 [15D0] CreateProcessA hooked. Target: 0x0000000077148840
>
> 0516/134334 [15D0] CreateProcessW hooked. Target: 0x00000000770D1BB0
>
> 0516/134334 [15D0] CreateProcessAsUserW hooked. Target: 0x000007FEFD97AFE8
>
> 0516/134334 [15D0] CreateProcessWithLogonW hooked. Target: 0x000007FEFD9DFA50
>
> 0516/134334 [15D0] CreateProcessWithTokenW hooked. Target: 0x000007FEFD9DF9E0
>
> 0516/134334 [15D0] D3D9.DLL loaded
>
> 0516/134334 [15D0] D3D9 ripper init
>
> 0516/134334 [15D0] Direct3DCreate9 hooked. Target: 0x000007FEEDCC96B0
>
> 0516/134334 [15D0] Direct3DCreate9(32) return: 0x00000000004F1300
>
> 0516/134334 [15D0] IDirect3D9_CreateDevice hooked. Target: 0x000007FEEDCA0390
>
> 0516/134334 [15D0] D3D9.DLL unloaded
>
> 0516/134334 [15D0] D3D9 ripper uninit
>
> 
>
> 0516/134334 [15D0] DDRAW.DLL loaded
>
> 0516/134334 [15D0] DDRAW init
>
> 0516/134334 [15D0] DirectDrawCreateEx hooked. Target: 0x000007FEF3788968
>
> 0516/134334 [15D0] DirectDrawCreate hooked. Target: 0x000007FEF378815C
>
> 0516/134334 [15D0] DirectDrawCreate() ret: 0x00000000
>
> 0516/134334 [15D0] IDirectDraw_QueryInterface hooked. Target: 0x000007FEF3788498
>
> 0516/134334 [15D0] IDirectDraw_CreateSurface hooked. Target: 0x000007FEF3785FE0
>
> 0516/134334 [15D0] IUnknown_QueryInterface(IID_IDirectDraw7) HRESULT: 0x00000000
>
> 0516/134334 [15D0] IDirectDraw_CreateSurface hooked. Target: 0x000007FEF37AC64C
>
> 0516/134334 [15D0] DDRAW.DLL unloaded
>
> 0516/134334 [15D0] DDRAW uninit
>
> 
>
> 0516/134336 [15E0] D3D9.DLL loaded
>
> 0516/134336 [15E0] D3D9 ripper init
>
> 0516/134336 [15E0] Direct3DCreate9 hooked. Target: 0x000007FEED2896B0
>
> 0516/134336 [15E0] Direct3DCreate9(32) return: 0x0000000004AA1300
>
> 0516/134336 [15E0] IDirect3D9_CreateDevice hooked. Target: 0x000007FEED260390
>
> 0516/134336 [15E0] D3D11.DLL loaded
>
> 0516/134336 [15E0] D3D11 ripper init
>
> 0516/134336 [15E0] D3D11CreateDeviceAndSwapChain hooked. Target: 0x000007FEEDC955C4
>
> 0516/134336 [15E0] D3D11CreateDevice hooked. Target: 0x000007FEEDC9555C
>
> 0516/134336 [15E0] DXGI init
>
> 0516/134336 [15E0] CreateDXGIFactory hooked. Target: 0x000007FEF7EE4DA4
>
> 0516/134336 [15E0] CreateDXGIFactory1 hooked. Target: 0x000007FEF7F09AF4
>
> 0516/134338 [15E0] CreateDXGIFactory()
>
> 0516/134338 [15E0] IDXGIFactory_QueryInterface hooked. Target: 0x000007FEF7EE4CA8
>
> 0516/134338 [15E0] IDXGIFactory_CreateSwapChain hooked. Target: 0x000007FEF7F09E20
>
> 0516/134338 [15E0] D3D11CreateDeviceAndSwapChain() return: 0x00000000
>
> 0516/134338 [15E0] ID3D11Device_CreateInputLayout hooked. Target: 0x000007FEEDCA031C
>
> 0516/134338 [15E0] ID3D11Device_CreateVertexShader hooked. Target: 0x000007FEEDC9F544
>
> 0516/134338 [15E0] ID3D11Device_CreatePixelShader hooked. Target: 0x000007FEEDC9FF40
>
> 0516/134338 [15E0] ID3D11Device_CreateGeometryShader hooked. Target: 0x000007FEEDC9FA90
>
> 0516/134338 [15E0] ID3D11Device_CreateGeometryShaderWithStreamOutput hooked. Target: 0x000007FEEDC9FC7C
>
> 0516/134338 [15E0] D3D11CreateDevice() return: 0x00000000
>
> 0516/134338 [15E0] Direct3DCreate9(32) return: 0x0000000004758640
>
> 0516/134338 [15E0] DDRAW.DLL loaded
>
> 0516/134338 [15E0] DDRAW init
>
> 0516/134338 [15E0] DirectDrawCreateEx hooked. Target: 0x000007FEF3788968
>
> 0516/134338 [15E0] DirectDrawCreate hooked. Target: 0x000007FEF378815C
>
> 0516/134338 [15E0] DirectDrawCreate() ret: 0x00000000
>
> 0516/134338 [15E0] IDirectDraw_QueryInterface hooked. Target: 0x000007FEF3788498
>
> 0516/134338 [15E0] IDirectDraw_CreateSurface hooked. Target: 0x000007FEF3785FE0
>
> 0516/134338 [15E0] IUnknown_QueryInterface(IID_IDirectDraw7) HRESULT: 0x00000000
>
> 0516/134338 [15E0] IDirectDraw_CreateSurface hooked. Target: 0x000007FEF37AC64C
>
> 0516/134338 [15E0] IUnknown_QueryInterface({ACA12120-3356-11D1-8F-CF-00-C0-4F-C2-9B-4E}) HRESULT: 0x00000000
>
> 0516/134338 [15E0] DDRAW.DLL unloaded
>
> 0516/134338 [15E0] DDRAW uninit
>
> 
>
> 0516/134338 [15E0] D3D11.DLL unloaded
>
> 0516/134338 [15E0] D3D11 ripper uninit
>
> 
>
> 0516/134338 [15E0] DXGI.DLL unloaded
>
> 0516/134338 [15E0] DXGI uninit
>
> 
>
> 0516/134338 [15E0] IDirect3D9_CreateDevice(0x0000000004AA1300, ...) return: 0x00000000
>
> 0516/134338 [15E0] IDirect3DDevice9_SetTexture hooked. Target: 0x000007FEED289748
>
> 0516/134338 [15E0] IDirect3DDevice9_DrawPrimitiveUP hooked. Target: 0x000007FEED287394
>
> 0516/134338 [15E0] IDirect3DDevice9_DrawIndexedPrimitive hooked. Target: 0x000007FEED291BD0
>
> 0516/134338 [15E0] IDirect3DDevice9_DrawIndexedPrimitiveUP hooked. Target: 0x000007FEED326A98
>
> 0516/134338 [15E0] IDirect3DDevice9_DrawPrimitive hooked. Target: 0x000007FEED262B24
>
> 0516/134338 [15E0] IDirect3DDevice9_CreateVertexBuffer hooked. Target: 0x000007FEED25751C
>
> 0516/134338 [15E0] IDirect3DDevice9_CreateIndexBuffer hooked. Target: 0x000007FEED28AC90
>
> 0516/134338 [15E0] IDirect3DDevice9_Present hooked. Target: 0x000007FEED284378
>
> 0516/134338 [15E0] IDirect3DDevice9_GetSwapChain hooked. Target: 0x000007FEED292D8C
>
> 0516/134338 [15E0] IDirect3DDevice9_CreateAdditionalSwapChain hooked. Target: 0x000007FEED2EC990
>
> 0516/134338 [15E0] IDirect3DDevice9_SetPixelShader hooked. Target: 0x000007FEED284E14
>
> 0516/134338 [15E0] IDirect3DDevice9_SetDepthStencilSurface hooked. Target: 0x000007FEED277BA0
>
> 0516/134339 [15E0] IDirect3DDevice9_SetGammaRamp hooked. Target: 0x000007FEED2ED3F8
>
> 0516/134339 [15E0] IDirect3DDevice9_SetStreamSource hooked. Target: 0x000007FEED2877C0
>
> 0516/134339 [15E0] IDirect3DDevice9_CreateVertexShader hooked. Target: 0x000007FEED272DA0
>
> 0516/134339 [15E0] IDirect3DDevice9_CreatePixelShader hooked. Target: 0x000007FEED26F560
>
> 0516/134400 [15E0] CreateProcessW("D:\Program Files (x86)\GuildWars2\bin64\CoherentUI_Host.exe" --coherent-options=host-46f31bc0-8cde-4b5b-983c-3b73600e9962") return: 1
>
> 0516/134400 [15E0] Injecting to child process. Status: OK
## Post #488
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-16T22:39:51+00:00
- Post Title: Re: Ninja Ripper

I try to rip maps from BeamNG but when I load the files to 3dmax it looks like that:
[](http://postimg.org/image/yjewlbi4x/)

I use this ripper for the first time. What I do wrong?
## Post #489
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-05-17T06:41:23+00:00
- Post Title: Re: Ninja Ripper

> Reply from TomWin
>
> I try to rip maps from BeamNG but when I load the files to 3dmax it looks like that:


I use this ripper for the first time. What I do wrong?basically ther is nothing wrong. ninja ripper rips models in their original position/transformation (so called t-pose) which is 0,0,0.
## Post #490
- Username: Mkbewe
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Oct 04, 2015 11:53 pm
- Post datetime: 2016-05-17T08:13:03+00:00
- Post Title: Re: Ninja Ripper

> Reply from TomWin
>
> I try to rip maps from BeamNG but when I load the files to 3dmax it looks like that:


I use this ripper for the first time. What I do wrong?

Here you have all meshes (of map and of models). Idk how is in your game, but in my ripped i have first 100-150 meshes of maps, next are models and another (f.e. skybox, some 2d models).
## Post #491
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2016-05-17T12:28:55+00:00
- Post Title: Re: Ninja Ripper

And how can I make it load a map like it was in game?
I remember 3d ripper DX was ripping all the scene just like it was.

BTW. Any idea how to rip models from WindowsApps games eg. Asphalt 8?
I tried to do shortcut lnk and some bat file converted to exe because it's not possible to run ripper in WindowsApps dir, but it didnt work anyway.
## Post #492
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-05-17T12:54:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from TomWin
>
> And how can I make it load a map like it was in game?
I remember 3d ripper DX was ripping all the scene just like it was.not possible with ninja ripper;

> Reply from TomWin
>
> BTW. Any idea how to rip models from WindowsApps games eg. Asphalt 8?
I tried to do shortcut lnk and some bat file converted to exe because it's not possible to run ripper in WindowsApps dir, but it didnt work anyway.not sure what you doing but this ripper only for windows desktop.
## Post #493
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2016-05-22T02:36:10+00:00
- Post Title: Re: Ninja Ripper

Is Ninja Ripper dead for anyone else's Star trek online?
## Post #494
- Username: imarceldoe
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jan 28, 2016 9:55 pm
- Post datetime: 2016-06-15T11:03:13+00:00
- Post Title: Re: Ninja Ripper

Hello,

It appears Ninja Ripper has stopped working with MGS TPP. Is there anyway I could donate $200 USD or something along those lines to getting it fixed again for it? I really am desperate and the tool was working last I used it, so I'm sad to see it's not working anymore.
I'll send the money first and everything, no problems. 

I would really appreciate it if I could do something like that for it.
I would also be happy to buy the game for you.

Here are two links -
Here is a .rip folder example: [https://a.pomf.cat/suphyj.zip](https://a.pomf.cat/suphyj.zip)
and the log file: [https://a.pomf.cat/stzzyd.txt](https://a.pomf.cat/stzzyd.txt)

Also, I would be more than happy to donate to a Patreon monthly.

Thanks.
## Post #495
- Username: Karric
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Aug 28, 2015 7:20 am
- Post datetime: 2016-07-20T22:28:48+00:00
- Post Title: Re: Ninja Ripper

I'm unable to use Ninja Ripper (I'm on a mac), would anyone be willing to rip a model for me? PM if possible, thanks.
## Post #496
- Username: KillerSpring
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 20, 2015 1:47 am
- Post datetime: 2016-07-25T20:39:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from AlexNG
>
> I've been experimenting with Dark Souls and Ninja Ripper and found that it crashes when run on Linux under Wine. This happens because of this call, which is still there in the current version. I could not find any documentation that suggests that it is OK to pass NULL to SetGammaRamp as the ramp parameter, so I hesitate to call this a bug in Wine. Replacing this call with NOPs makes it work just fine.

Also, it seems that the ripper checks only 8 texture slots, when actually there are 16 or so. Judging by the shader code, Dark Souls actually puts a texture in slot 15 of some objects for some reason. It's probably just a light map or something similar though.

On the positive side, since I couldn't find a good blender importer for .rip files, I made a new script, and with the right parameters it seems to handle Dark Souls data correctly.

Edit: Here are the script settings for Dark Souls in case somebody is interested. For 'filter by shader inputs' to work you need to enable ripping "Shaders (for experts)" and import the files from the _NinjaRipper folder.

I installed the script but I can't find the settings, where is it?
## Post #497
- Username: AlexNG
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Mar 08, 2016 3:45 pm
- Post datetime: 2016-07-29T06:20:23+00:00
- Post Title: Re: Ninja Ripper

> Reply from KillerSpring
>
> I installed the script but I can't find the settings, where is it?
Same as with any other blender importer obviously: [https://i.imgur.com/ynARv2r.png](https://i.imgur.com/ynARv2r.png)
## Post #498
- Username: ruadhs
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 04, 2016 12:05 am
- Post datetime: 2016-08-04T09:12:39+00:00
- Post Title: Re: Ninja Ripper

I sent message to you 

Check out message 

Thanks you !
## Post #499
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2016-08-26T18:07:37+00:00
- Post Title: Re: Ninja Ripper

I don't know if goes by the topic, but thanks to NinjaRipper I was able to extract models from the Saint Seiya Soldier Soul on PC (on T-Pose and with texture but no bones)

I did even try with PCSX2 emu, both 0,09,8 and 1,4,0 and in both extract the same like with extract in .obj way with 9,8. But, with a better texture easy to resize and with the actual accurate Texture name for each mesh

The only problem, its the size proportion, its not like if were of Z and resize (which happen actually), but more in other way... like if it were resize from the middle of Z & X, that maybe the only problem, but its quiet useful, at least for PC that use Directx11.

I kind hope they made a plugging for the PCSX2 that its more friendly with NinjaRipper like what they did on Dolphin emulator
## Post #500
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-09-02T07:42:35+00:00
- Post Title: Re: Ninja Ripper

Version 1.5.2 available 
[http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)
## Post #501
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2016-09-02T16:52:06+00:00
- Post Title: Re: Ninja Ripper

What was the bug that was fixed?
## Post #502
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-09-05T08:14:15+00:00
- Post Title: Re: Ninja Ripper

D3D11  internals patch VTBL on some cards/drivers  and so mesh rip don't work.
## Post #503
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2016-09-09T22:02:48+00:00
- Post Title: Re: Ninja Ripper

Hey guys.

Has any of you encountered any issues running last v1.2 NFS World offline version, because I have tried every possible combination, and the NFS World wont load Ninja Ripper, I tried putting the offline server executable or the NFSW_Launcher.exe, all with various possible combinations, and still no result, depending on the combination, it either exports a log and no game data or not even the log, I'm stuck.

Any of you have more info as to why wont work?

cheers
## Post #504
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2016-10-05T23:45:22+00:00
- Post Title: Re: Ninja Ripper

Does anyone have any idea why some games result in T-pose ragdolls when being ripped? Also the textures seem to get messed up.
I used 1.5.1 for those rips.
## Post #505
- Username: wjh12338093
- Rank: beginner
- Number of posts: 20
- Joined date: Thu May 01, 2014 9:12 pm
- Post datetime: 2016-10-07T05:46:15+00:00
- Post Title: Re: Ninja Ripper

Interception of CE engine game model, Special is very black, is there a way to recover?
Bad English, I'm sorry
## Post #506
- Username: EGGO
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 10, 2011 11:17 am
- Post datetime: 2016-12-04T05:51:56+00:00
- Post Title: Re: Ninja Ripper

Maybe somebody can help with ripping android games from emulators like BlueStack or NOX? Any help appreciated)
## Post #507
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2016-12-08T02:03:08+00:00
- Post Title: Re: Ninja Ripper

Can someone please consider making a Blender .rip model Importer?
A blender Importer would be so awesome!
## Post #508
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-08T04:38:54+00:00
- Post Title: Re: Ninja Ripper

you mean like the one released here
[viewtopic.php?p=117531#p117531](http://forum.xentax.com/viewtopic.php?p=117531#p117531)
and another here
[viewtopic.php?f=33&t=15302](http://forum.xentax.com/viewtopic.php?f=33&t=15302)



[https://github.com/angavrilov/blender-i ... injaripper](https://github.com/angavrilov/blender-import-ninjaripper)
[https://github.com/Dummiesman/RipImport](https://github.com/Dummiesman/RipImport)
## Post #509
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2016-12-08T14:23:43+00:00
- Post Title: Re: Ninja Ripper

Wow! I totally missed both of those, I can't wait to try them out after work tonight.

Thanks for the links:)))))))))))))

I did try them both and this one ([https://github.com/Dummiesman/RipImport](https://github.com/Dummiesman/RipImport)) seems to have worked better for me as far as getting textures to work, but I couldn't figure out how to import more than 1 file at a time, is that possible?
## Post #510
- Username: NAVAZA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 13, 2016 12:21 pm
- Post datetime: 2016-12-13T04:27:19+00:00
- Post Title: Re: Ninja Ripper

What could be the reason why it doesn't on web browsers for me?
I'm trying to rip this model, but it's not working. Could someone give it a try, please?
[http://es.wowhead.com/dressing-room#mV0 ... D808jLA87c](http://es.wowhead.com/dressing-room#mV0z0zH8cbkz9V8MXn808deT808ryI808bCS808qXb87Vqgh808jen87cVeD808jLA87c)

Thank you.
## Post #511
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2016-12-26T07:40:27+00:00
- Post Title: Re: Ninja Ripper

NAVAZA
Flash used for rendering. Crashed on rip. It seems ripper bug.
## Post #512
- Username: Gopher86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 24, 2015 9:45 pm
- Post datetime: 2016-12-31T09:40:56+00:00
- Post Title: Re: Ninja Ripper

Hello everyone!

First of all, thank you for Ninja ripper - it's a great tool!   

@blackninja: if I want to use the tool on The Darkness 2, I don't get any rip files. Unless I use NinjaRipper version 1.1.2 or 1.1.4 with the dx9-wrapper, but then only textures if I force it via the default shortcut F2.
Whenever I use a newer version I only get a log file (text), but nothing else happens.
Somewhere I saw a guy who got it to work with ripping the main character, but I don't know how. What am I missing or doing wrong?

It's the steam version of Darkness 2 and I'm on Windows 10.

Any help would be greatly appreciated!!

Thank you very much.
## Post #513
- Username: Gopher86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 24, 2015 9:45 pm
- Post datetime: 2017-01-02T19:42:03+00:00
- Post Title: Re: Ninja Ripper

Never mind. Apparently the problem was Windows 10. Now that I switched to Windows 7 it works like a charm!
## Post #514
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2017-01-20T23:36:46+00:00
- Post Title: Re: Ninja Ripper

I'm trying to rip a level from Dead Space 3 because the script that can be used to extract the meshes directly from the game files is broken and gives broken UVs, so I have to rip any levels I want from the game. However, the problem is that there are 7252 rip files and probably half are just duplicates. A one mesh has maybe 3-4 copies of itself stacked on top of each other which lag out 3D max if I import everything at once. So far I have imported everything in parts.

Is there a way to disable the duplication? Oh and another problem is that I really have no clue where each texture is supposed to go as there were over 300 texture maps ripped. Ninjaripper did apply automatically some textures but everything is wrong with most of them being normal maps and some are being screenshots of the scene I ripped. None are actually correct textures.
## Post #515
- Username: fenasi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 22, 2017 12:06 am
- Post datetime: 2017-01-21T16:33:24+00:00
- Post Title: Re: Ninja Ripper

Hi blackninja. This tool is very useful. Thank you so much to create it. I ve ripped a few models but now i have a problem. There is a game named "Racer". I want use Ninja Ripper with this game but it doesnt rip any models. Can you have a look for that game? Game is not soo big to download. It is nearly 90 mb. 

Homepage;
[http://www.racer.nl](http://www.racer.nl)

Fan page and all versions in this site;
[http://www.tracciontrasera.es/downloads ... s?start=60](http://www.tracciontrasera.es/downloads/category/73-betas?start=60)

I hope this awesome tool works with this game. I really need that
## Post #516
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-01-23T07:22:11+00:00
- Post Title: Re: Ninja Ripper

fenasi
OpenGL used for rendering. Ripper support DirectX only
## Post #517
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2017-01-24T04:27:24+00:00
- Post Title: Re: Ninja Ripper

What about Tales of Berseria? Ninja Ripper 1.5.1 doesn't seem to rip anything from the demo version. Tried both 32 and 64bit versions of Ninja Ripper.
## Post #518
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-01-24T09:33:16+00:00
- Post Title: Re: Ninja Ripper

demonslayerx8
Attach log
## Post #519
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2017-01-25T00:38:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> demonslayerx8
Attach log
here's the log. Log only came with the 64bit version of Ninja Ripper, while 32bit gives no log

[http://pastebin.com/6zDGYyk1](http://pastebin.com/6zDGYyk1)
## Post #520
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-01-25T07:17:23+00:00
- Post Title: Re: Ninja Ripper

May be anticheat or steam blocks ripper
## Post #521
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2017-01-25T13:46:02+00:00
- Post Title: Re: Ninja Ripper

I see.. I'll try again when the full game is out via steam, and another copy elsewhere.
## Post #522
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-01-31T13:04:19+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper update 1.6.0

Direct9Ex bugfix
FireFox browser > 51 rip available
Google Chrome browser rip available (tested on last version 56)

[http://dropmefiles.com/xA0pt](http://dropmefiles.com/xA0pt)
## Post #523
- Username: Norkkom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 31, 2017 10:20 pm
- Post datetime: 2017-01-31T18:49:34+00:00
- Post Title: Re: Ninja Ripper

I'm trying to rip from Titanfall 2, but without any luck. The dx11/9 wrappers seem to have no success (hotkeys do not work, doesn't even generate a log).
Using the injector does generate a log, which is a good sign, but causes interference with Origin's authentication methods (the Authentication UI crashes, which in turn means the game can never actually start).
Here is the log, hopefully there is a solution..
[http://pastebin.com/raw/xyb1DxF8](http://pastebin.com/raw/xyb1DxF8)
## Post #524
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-02-01T07:12:28+00:00
- Post Title: Re: Ninja Ripper

Norkkom
If injection failed (no log etc), anticheat system may block ripper.

From log child process spawned, C:\PROGRA~2\ORIGIN~1\TITANF~1\\Core\ActivationUI.exe
another log must present
## Post #525
- Username: Norkkom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 31, 2017 10:20 pm
- Post datetime: 2017-02-01T13:16:35+00:00
- Post Title: Re: Ninja Ripper

No other log was present in the rip output folder, but there is a crash .dmp for the ActivationUI.exe
I'm not sure if this is what you're referring to by a log, but I'll upload it just in case. There's also a report.wer that was generated by it crashing, but I don't think that's important/relevant to this.
Either way, that's all that was generated from the attempt.
[https://a.pomf.cat/qtgypu.dmp](https://a.pomf.cat/qtgypu.dmp)
## Post #526
- Username: Norkkom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 31, 2017 10:20 pm
- Post datetime: 2017-02-02T19:57:09+00:00
- Post Title: Re: Ninja Ripper

A followup to my previous post:
Because injection seemed to be blocked when the game was  being launched, I tried using a separate injector, which injected the intruder.dll after the game was already running. This seemed to work - it injected without error and began generating a log. However, from here I was unable to actually rip anything. I'm aware this is not a "recommended" method of running the ripper, and it clearly didn't work properly as a result, however it does bypass the issue of the ActivationUI.exe throwing errors and grinding the game to a halt.

I've uploaded the log generated from this manual injection - it looks to me like it successfully hooked into everything and was running, but then idled waiting for commands it wasn't able to receive (considering it never actually closes the log, but merely gets forcibly shut down when I closed the game). Of course, there's plenty chance I'm wrong about that, so I'll let you decide.
Is there anything I can do involving this method of injection to bypass the ActivationUI.exe, or is this just a bad idea?

Log:
[http://pastebin.com/raw/YdDjSf11](http://pastebin.com/raw/YdDjSf11)
## Post #527
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-02-03T07:06:01+00:00
- Post Title: Re: Ninja Ripper

Injecting after game start totally wrong. Ripper must  start with game.

1. Try copy wrapper dll /x64/d3dwrap.dll to C:\Program Files (x86)\Origin Games\Titanfall2\Core\
2. Rename this dll to d3d11.dll
3. start game exe (not from injector)

Or try another game version wo origin.
## Post #528
- Username: Norkkom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 31, 2017 10:20 pm
- Post datetime: 2017-02-03T07:16:01+00:00
- Post Title: Re: Ninja Ripper

Unfortunately, Titanfall 2 is released exclusively through Origin, so there's no way for me to get a copy without it.

I tried putting the .dll in the core folder and renaming it, but no luck; not even a log created.

EDIT: I tried putting the renamed .dll file into C:\Program Files (x86)\Origin Games\Titanfall2\bin\x64_retail\ instead (it was the only other game folder with .dll files in it) and it worked perfectly!
Thank you so much for helping me out with this, I would never have thought to do this on my own.
## Post #529
- Username: Lethro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 22, 2016 5:31 pm
- Post datetime: 2017-02-04T17:09:54+00:00
- Post Title: Re: Ninja Ripper

Before the last update, for me NinjaRipper wasn't doing anything when pressing the keybind in Revelation Online (whereas it was working fine in other games). Now the capture is triggered successfully.


However, the game crashes before the end of the ripping process, and many textures are missing !

(It seems all the meshes are ripped though, only the textures seem to be the problem !)
## Post #530
- Username: Lethro
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 22, 2016 5:31 pm
- Post datetime: 2017-02-05T14:24:57+00:00
- Post Title: Re: Ninja Ripper

In addition to my previous post :

I tried a "texture only" rip, and in the folder were only 2 textures (Tex_0000.dds and Tex_0405.dds).
The game crashed after only a few seconds.
 I attached the log file to this post.


 tianyu.exe.log.txt.7z
(1.83 KiB) Downloaded 16 times
## Post #531
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-02-06T15:05:30+00:00
- Post Title: Re: Ninja Ripper

Help with model transparent and texture issue, when ever i import ripp files always have this issue anyway to fix it 


Capture.PNG (202.54 KiB) Viewed 628 times
## Post #532
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-02-07T08:24:13+00:00
- Post Title: Re: Ninja Ripper

Looks like incorrect Texture U/V
Unwrap UV in 3Dmax
## Post #533
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-02-07T11:27:21+00:00
- Post Title: Re: Ninja Ripper

anyway to fix it while im importing them. see theres tex number 0 and uv x 1. for options 

> Reply from blackninja
>
> Looks like incorrect Texture U/V
Unwrap UV in 3Dmax
## Post #534
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2017-02-07T12:23:49+00:00
- Post Title: Re: Ninja Ripper

Im not good with unwrapping in max or maya.  

i converted dds to jpeg, tried png and tiff and neither one imports textures. seems the issue is with the dds textures.
## Post #535
- Username: tetTris11
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 25, 2015 4:54 pm
- Post datetime: 2017-02-24T12:56:06+00:00
- Post Title: Re: Ninja Ripper

Anyone know how to get into Elite: Dangerous? if i try running it as is it complains that i'm not logged in and if i run it with the server token (what the game's launcher sends to the game to tell it to log into this account) Ninja Ripper crashes. Any ideas?
## Post #536
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-03-10T06:03:49+00:00
- Post Title: Re: Ninja Ripper

anticheat may be
## Post #537
- Username: fenasi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 22, 2017 12:06 am
- Post datetime: 2017-03-12T08:44:06+00:00
- Post Title: Re: Ninja Ripper

Hi blackninja. Nowadays im trying ripping locked gta v models via openIV. Problem is your tool doesnt work with the latest openIV. When i try to view model in openIV without ninjaripper, i see the model, but when i start openIV with ninjaripper, openIV doesnt view the model.  But otherwise your tool works very well with openIV v1.0.7 but this old version doesnt support gta v. So i have to use latest openIV. Can you have a check whats the problem with the latest openIV?
## Post #538
- Username: Tanagashi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jan 09, 2017 4:22 am
- Post datetime: 2017-03-13T03:09:04+00:00
- Post Title: Re: Ninja Ripper

> Reply from Norkkom
>
> 
EDIT: I tried putting the renamed .dll file into C:\Program Files (x86)\Origin Games\Titanfall2\bin\x64_retail\ instead (it was the only other game folder with .dll files in it) and it worked perfectly!

Could you walk me through what you did, because it doesn't seem to work for me?

Edit: Nevermind, got it to work as well. I just renamed the dll incorrectly.
Textures seem to be ripping correctly, but model geometry is fucked up. Maybe I'm missing something.
## Post #539
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-07T15:15:51+00:00
- Post Title: Re: Ninja Ripper

it is possible to rip with ninjaripper on windows 10? i tried several games but when i press the rip keys nothing happen.... it works on win10?
thanks
## Post #540
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-04-08T07:57:23+00:00
- Post Title: Re: Ninja Ripper

> Reply from Marvey
>
> it is possible to rip with ninjaripper on windows 10? i tried several games but when i press the rip keys nothing happen.... it works on win10?
thanks
Hi. ripper must work on Win10
I tested on chrome and firefox browsers (real system and virtualbox)

Try run as adminstrator
Log created? Attach log here
## Post #541
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-09T18:44:50+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Marvey wrote:it is possible to rip with ninjaripper on windows 10? i tried several games but when i press the rip keys nothing happen.... it works on win10?
thanks
Hi. ripper must work on Win10
I tested on chrome and firefox browsers (real system and virtualbox)

Try run as adminstrator
Log created? Attach log here

Hi there Ninja

Finnaly i got it working, dont ask me what was the problema because i have no idea... from nothing the ripper start to work... i tried everything, even installed a virtual box and something was blocking it... but i no idea where was the problema,  i disabled antivírus, everything... anyway like i said now is working! thank you for this amazing tool you have created!
## Post #542
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-10T00:18:48+00:00
- Post Title: Re: Ninja Ripper

btw Ninja,

it is possible in future ninjaripper be able to rip larger texture files? right now only rips max 4096x4096... would be great if possible!
## Post #543
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2017-04-10T16:22:31+00:00
- Post Title: Re: Ninja Ripper

hello people

I am tryng to use Ninja Ripper for Tales of Zestiria Steam edition

I want extract the Forge Spear of Alisha Diphda

I run the ripper.exe and run the game

I hit the hotkeys to grab texture and model ingame but generated log files only

I ask help
## Post #544
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-04-11T06:25:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from YUKI
>
> hello people

I am tryng to use Ninja Ripper for Tales of Zestiria Steam edition

I want extract the Forge Spear of Alisha Diphda

I run the ripper.exe and run the game

I hit the hotkeys to grab texture and model ingame but generated log files only

I ask help

Log?
## Post #545
- Username: audreyisme
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 13, 2014 12:03 pm
- Post datetime: 2017-04-11T08:39:49+00:00
- Post Title: Re: Ninja Ripper

A most marvellous day to the good people of Xentqx and of course the gifted creator of Ninja Ripper,

With pardon to my ignorance has anyone managed to use Ninja Ripper 1.6 or prior on Windows 10 apps from the App Store?

From my naive perspective I understand that Ninja Ripper can be run either via an exe on the application one wishes to rip or the exe of a chosen web browser in the case of webgl media. However, despite my best efforts I cannot seem to devise a current way to use it with Apps from the Win 10 marketplace.

Indeed it seems difficult to even locate the exe for the indivise Apps from the marketplace on my local drive.

Any assistance you might provide would be immensely appreciated.

Also does anyone know of a similar capable Ninja Ripper application for mac pax?

With best regards and thanks
## Post #546
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2017-04-11T09:09:37+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> YUKI wrote:hello people

I am tryng to use Ninja Ripper for Tales of Zestiria Steam edition

I want extract the Forge Spear of Alisha Diphda

I run the ripper.exe and run the game

I hit the hotkeys to grab texture and model ingame but generated log files only

I ask help 

Log?

yes when I run ninja ripper and I hit ripkeys, there is the folder _NinjaRipper in game folder but there are folders named 2017.04.11_00.11.05_Tales of Zestiria.exe_488. Inside folders there are logs like this:

```
0411/001105 [1F80] © 2004-2017 black_ninja

0411/001105 [1F80] LOG START

0411/001105 [1F80] Output directory: C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\_NinjaRipper\2017.04.11_00.11.05_Tales of Zestiria.exe_488\
0411/001105 [1F80] Win ver: 6.1 x64 Service Pack 1

0411/001105 [1F80] Inject mode: "d3d9.dll wrapper"
0411/001105 [1F80] Texture downscale max width : 4096
0411/001105 [1F80] Texture downscale max height: 4096
0411/001105 [1F80] Texture downscale value: 2
0411/001105 [1F80] LdrLoadDll hooked. Target: 0x7772EB2A
0411/001105 [1F80] LdrUnloadDll hooked. Target: 0x7772D2F6
0411/001105 [1F80] CreateProcessA hooked. Target: 0x75A11072
0411/001105 [1F80] CreateProcessW hooked. Target: 0x75A1103D
0411/001105 [1F80] CreateProcessAsUserW hooked. Target: 0x75DCC512
0411/001105 [1F80] CreateProcessWithLogonW hooked. Target: 0x75E055E1
0411/001105 [1F80] CreateProcessWithTokenW hooked. Target: 0x75E05617
0411/001105 [1F80] SetTokenInformation hooked. Target: 0x75DC9A12
0411/001107 [1F80] CreateProcessW("C:\Program Files (x86)\Steam\steam.exe") return: 1
0411/001107 [1F80] Injecting to child process. Status: OK
0411/001107 [1F80] Loaded Modules List
0411/001107 [1F80] --------------------------------
0411/001107 [1F80] BaseAddr    Size         Module
0411/001107 [1F80] --------------------------------
0411/001107 [1F80] 0x00400000 (0x02FF7000)  C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\Tales of Zestiria.exe
0411/001107 [1F80] 0x776F0000 (0x00180000)  C:\Windows\SysWOW64\ntdll.dll
0411/001107 [1F80] 0x75A00000 (0x00110000)  C:\Windows\syswow64\kernel32.dll
0411/001107 [1F80] 0x67C90000 (0x0002F000)  C:\Program Files\AVAST Software\Avast\aswhookx.dll
0411/001107 [1F80] 0x75290000 (0x00047000)  C:\Windows\syswow64\KERNELBASE.dll
0411/001107 [1F80] 0x67860000 (0x0006A000)  C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\bink2w32.dll
0411/001107 [1F80] 0x764B0000 (0x00100000)  C:\Windows\syswow64\USER32.dll
0411/001107 [1F80] 0x76060000 (0x00090000)  C:\Windows\syswow64\GDI32.dll
0411/001107 [1F80] 0x75D20000 (0x0000A000)  C:\Windows\syswow64\LPK.dll
0411/001107 [1F80] 0x75330000 (0x0009D000)  C:\Windows\syswow64\USP10.dll
0411/001107 [1F80] 0x75E80000 (0x000AC000)  C:\Windows\syswow64\msvcrt.dll
0411/001107 [1F80] 0x75DC0000 (0x000A1000)  C:\Windows\syswow64\ADVAPI32.dll
0411/001107 [1F80] 0x75DA0000 (0x00019000)  C:\Windows\SysWOW64\sechost.dll
0411/001107 [1F80] 0x763C0000 (0x000F0000)  C:\Windows\syswow64\RPCRT4.dll
0411/001107 [1F80] 0x74F90000 (0x00060000)  C:\Windows\syswow64\SspiCli.dll
0411/001107 [1F80] 0x74F80000 (0x0000C000)  C:\Windows\syswow64\CRYPTBASE.dll
0411/001107 [1F80] 0x71330000 (0x00032000)  C:\Windows\system32\WINMM.dll
0411/001107 [1F80] 0x75100000 (0x0015D000)  C:\Windows\syswow64\ole32.dll
0411/001107 [1F80] 0x765C0000 (0x00C4C000)  C:\Windows\syswow64\shell32.dll
0411/001107 [1F80] 0x75580000 (0x00057000)  C:\Windows\syswow64\SHLWAPI.dll
0411/001107 [1F80] 0x6C740000 (0x000FF000)  C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\sdl2.dll
0411/001107 [1F80] 0x76360000 (0x00060000)  C:\Windows\syswow64\IMM32.DLL
0411/001107 [1F80] 0x74FF0000 (0x000CD000)  C:\Windows\syswow64\MSCTF.dll
0411/001107 [1F80] 0x75FC0000 (0x00091000)  C:\Windows\syswow64\OLEAUT32.dll
0411/001107 [1F80] 0x72EA0000 (0x00009000)  C:\Windows\system32\VERSION.dll
0411/001107 [1F80] 0x750C0000 (0x00035000)  C:\Windows\syswow64\ws2_32.dll
0411/001107 [1F80] 0x765B0000 (0x00006000)  C:\Windows\syswow64\NSI.dll
0411/001107 [1F80] 0x71A50000 (0x00021000)  C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\d3d9.dll
0411/001107 [1F80] 0x0FF20000 (0x001FF000)  C:\Windows\system32\d3dx9_43.dll
0411/001107 [1F80] 0x002C0000 (0x00016000)  C:\Windows\system32\xinput1_3.dll
0411/001107 [1F80] 0x753E0000 (0x0019D000)  C:\Windows\syswow64\SETUPAPI.dll
0411/001107 [1F80] 0x75B40000 (0x00027000)  C:\Windows\syswow64\CFGMGR32.dll
0411/001107 [1F80] 0x75B20000 (0x00012000)  C:\Windows\syswow64\DEVOBJ.dll
0411/001107 [1F80] 0x678D0000 (0x00069000)  C:\Windows\system32\msvcp100.dll
0411/001107 [1F80] 0x66A00000 (0x000BF000)  C:\Windows\system32\MSVCR100.dll
0411/001107 [1F80] 0x67820000 (0x00031000)  C:\Program Files (x86)\Steam\SteamApps\common\Tales of Zestiria\steam_api.dll
0411/001107 [1F80] 0x75B70000 (0x0007B000)  C:\Windows\syswow64\comdlg32.dll
0411/001107 [1F80] 0x6FD90000 (0x0019E000)  C:\Windows\WinSxS\x86_microsoft.windows.common-controls_6595b64144ccf1df_6.0.7601.18837_none_41e855142bd5705d\COMCTL32.dll
0411/001107 [1F80] 0x0F2B0000 (0x000C2000)  C:\Program Files (x86)\Steam\steamapps\common\Tales of Zestiria\ninjaripper1.6.0\x86\intruder.dll
0411/001107 [1F80] 0x69250000 (0x00080000)  C:\Windows\system32\uxtheme.dll
0411/001107 [1F80] 0x6A780000 (0x000F5000)  C:\Windows\system32\PROPSYS.dll
0411/001107 [1F80] 0x75F30000 (0x00083000)  C:\Windows\syswow64\CLBCatQ.DLL
0411/001107 [1F80] 0x6D6E0000 (0x00021000)  C:\Windows\system32\ntmarta.dll
0411/001107 [1F80] 0x752E0000 (0x00045000)  C:\Windows\syswow64\WLDAP32.dll
0411/001107 [1F80] 0x75E70000 (0x0000B000)  C:\Windows\syswow64\profapi.dll
0411/001107 [1F80] 0x753D0000 (0x00004000)  C:\Windows\syswow64\api-ms-win-downlevel-shlwapi-l1-1-0.dll
0411/001107 [1F80] 0x77210000 (0x00005000)  C:\Windows\syswow64\api-ms-win-downlevel-advapi32-l1-1-0.dll
0411/001107 [1F80] 0x71C50000 (0x00008000)  C:\Windows\system32\Secur32.dll
0411/001107 [1F80] 0x71C40000 (0x00004000)  C:\Windows\system32\api-ms-win-downlevel-advapi32-l2-1-0.dll
0411/001107 [1F80] 0x69680000 (0x0004C000)  C:\Windows\system32\apphelp.dll
0411/001107 [1F80] 0x75B10000 (0x00005000)  C:\Windows\syswow64\psapi.dll
0411/001107 [1F80] LOG END

```
## Post #547
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-04-11T11:32:52+00:00
- Post Title: Re: Ninja Ripper

> Reply from Marvey
>
> btw Ninja,

it is possible in future ninjaripper be able to rip larger texture files? right now only rips max 4096x4096... would be great if possible!

Registry key HCU\Software\black_ninja\NinjaRipper\     DownscaleHeight\DownscaleWidth



> Reply from YUKI
>
> blackninja wrote:YUKI wrote:hello people

I am tryng to use Ninja Ripper for Tales of Zestiria Steam edition

I want extract the Forge Spear of Alisha Diphda

I run the ripper.exe and run the game 

I hit the hotkeys to grab texture and model ingame but generated log files only

I ask help 

Log?

yes when I run ninja ripper and I hit ripkeys, there is the folder _NinjaRipper in game folder but there are folders named 2017.04.11_00.11.05_Tales of Zestiria.exe_488. Inside folders there are logs like this:
From log: game exe starts steam and exit
Anticheat may be
## Post #548
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2017-04-11T11:56:41+00:00
- Post Title: Re: Ninja Ripper

I tryed to run the game with Ninja Ripper without Steam background ( task manager ) but the menu start screen is black.

There is a way with same rip software ? I want extract weapons only, especially the spear of Alisha Diphda.
## Post #549
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2017-04-11T16:16:48+00:00
- Post Title: Re: Ninja Ripper

It'd be nice to see an option to rip a game as you see it (like 3D Ripper DX does, instead of it being at the 0,0,0 position have the original co-ords stay intact). It'd be most useful for ripping scenes!
## Post #550
- Username: YUKI
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Nov 27, 2014 7:17 am
- Post datetime: 2017-04-11T17:16:03+00:00
- Post Title: Re: Ninja Ripper

in Tales of Zestiria there are single files on weapons ? or a way to rip them ? I am tryng with ni nja ripper everytime but ninjaripper not works
## Post #551
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2017-04-11T20:48:07+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> 
Registry key HCU\Software\black_ninja\NinjaRipper\     DownscaleHeight\DownscaleWidth

Thanks Ninja
## Post #552
- Username: keku645
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 18, 2017 6:25 pm
- Post datetime: 2017-04-12T15:40:57+00:00
- Post Title: Re: Ninja Ripper

So I'm currently working on import Mirror's Edge Catalyst models into the first game, but everytime i rip the models their UV maps seems that were ripped bad.



```
0412/171202 [27E4] © 2004-2017 black_ninja

0412/171202 [27E4] LOG START

0412/171202 [27E4] Output directory: D:\Desktop\Mirror's Edge\MEC\Mirror's Edge Catalyst Extracted\Ninja Ripper\_NinjaRipper\2017.04.12_17.12.02_MirrorsEdgeCatalyst.exe_305\
0412/171202 [27E4] Win ver: 6.2 x64 

0412/171202 [27E4] Inject mode: "d3d11.dll wrapper"
0412/171202 [27E4] Texture downscale max width : 4096
0412/171202 [27E4] Texture downscale max height: 4096
0412/171202 [27E4] Texture downscale value: 2
0412/171202 [27E4] LdrLoadDll hooked. Target: 0x00007FFFE8CE9E70
0412/171202 [27E4] LdrUnloadDll hooked. Target: 0x00007FFFE8D2ED90
0412/171202 [27E4] CreateProcessA hooked. Target: 0x00007FFFE8A4B970
0412/171202 [27E4] CreateProcessW hooked. Target: 0x00007FFFE8A4BEC0
0412/171202 [27E4] CreateProcessAsUserW hooked. Target: 0x00007FFFE7A682B0
0412/171202 [27E4] CreateProcessWithLogonW hooked. Target: 0x00007FFFE7A95C10
0412/171202 [27E4] CreateProcessWithTokenW hooked. Target: 0x00007FFFE7A52790
0412/171202 [27E4] SetTokenInformation hooked. Target: 0x00007FFFE7A6C2E0
0412/171202 [27E4] DXGI.DLL loaded
0412/171202 [27E4] DXGI init
0412/171202 [27E4] CreateDXGIFactory hooked. Target: 0x00007FFFE40C6490
0412/171202 [27E4] CreateDXGIFactory1 hooked. Target: 0x00007FFFE40C7030
0412/171203 [125C] CreateDXGIFactory1()
0412/171203 [125C] IDXGIFactory_QueryInterface hooked. Target: 0x00007FFFE40C7C50
0412/171203 [125C] IDXGIFactory1_CreateSwapChain hooked. Target: 0x00007FFFE4109590
0412/171203 [125C] D3D11.DLL loaded
0412/171203 [125C] D3D11 ripper init
0412/171203 [125C] D3D11CreateDeviceAndSwapChain hooked. Target: 0x00007FFFE0425170
0412/171203 [125C] D3D11CreateDevice hooked. Target: 0x00007FFFE0425080
0412/171203 [125C] D3D11CreateDeviceAndSwapChain() return: 0x00000000
0412/171203 [125C] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFFE050F6E0
0412/171204 [125C] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFFE0562ED0
0412/171204 [125C] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFFE051B270
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFFE0511470
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFFE05631C0
0412/171204 [125C] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFFE05643B0
0412/171204 [125C] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFFE051F8D0
0412/171204 [125C] ID3D11DeviceContext_PSSetShaderResources hooked. Target: 0x00007FFFE0515910
0412/171204 [125C] ID3D11Device_CreateInputLayout hooked. Target: 0x00007FFFE03EEA60
0412/171204 [125C] ID3D11Device_CreateVertexShader hooked. Target: 0x00007FFFE03EEAA0
0412/171204 [125C] ID3D11Device_CreatePixelShader hooked. Target: 0x00007FFFE03EEAE0
0412/171204 [125C] ID3D11Device_CreateGeometryShader hooked. Target: 0x00007FFFE04978E0
0412/171204 [125C] ID3D11Device_CreateGeometryShaderWithStreamOutput hooked. Target: 0x00007FFFE0497920
0412/171204 [125C] D3D11CreateDevice() return: 0x00000000
0412/171204 [125C] IDXGIFactory_CreateSwapChain()
0412/171204 [125C] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0412/171204 [125C] IDXGISwapChain_Present hooked. Target: 0x00007FFFE40C2140
0412/171204 [125C] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFFE0503A90
0412/171204 [125C] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFFE05A87E0
0412/171204 [125C] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFFE051AD90
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFFE0510980
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFFE05A8950
0412/171204 [125C] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFFE05A8DA0
0412/171204 [125C] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFFE0507C20
```
## Post #553
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-04-13T05:51:32+00:00
- Post Title: Re: Ninja Ripper

> Reply from keku645
>
> So I'm currently working on import Mirror's Edge Catalyst models into the first game, but everytime i rip the models their UV maps seems that were ripped bad.


Code: Select all0412/171202 [27E4] Ninja Ripper 1.6.0 x64
0412/171202 [27E4] © 2004-2017 black_ninja

0412/171202 [27E4] LOG START

0412/171202 [27E4] Output directory: D:\Desktop\Mirror's Edge\MEC\Mirror's Edge Catalyst Extracted\Ninja Ripper\_NinjaRipper\2017.04.12_17.12.02_MirrorsEdgeCatalyst.exe_305\
0412/171202 [27E4] Win ver: 6.2 x64 

0412/171202 [27E4] Inject mode: "d3d11.dll wrapper"
0412/171202 [27E4] Texture downscale max width : 4096
0412/171202 [27E4] Texture downscale max height: 4096
0412/171202 [27E4] Texture downscale value: 2
0412/171202 [27E4] LdrLoadDll hooked. Target: 0x00007FFFE8CE9E70
0412/171202 [27E4] LdrUnloadDll hooked. Target: 0x00007FFFE8D2ED90
0412/171202 [27E4] CreateProcessA hooked. Target: 0x00007FFFE8A4B970
0412/171202 [27E4] CreateProcessW hooked. Target: 0x00007FFFE8A4BEC0
0412/171202 [27E4] CreateProcessAsUserW hooked. Target: 0x00007FFFE7A682B0
0412/171202 [27E4] CreateProcessWithLogonW hooked. Target: 0x00007FFFE7A95C10
0412/171202 [27E4] CreateProcessWithTokenW hooked. Target: 0x00007FFFE7A52790
0412/171202 [27E4] SetTokenInformation hooked. Target: 0x00007FFFE7A6C2E0
0412/171202 [27E4] DXGI.DLL loaded
0412/171202 [27E4] DXGI init
0412/171202 [27E4] CreateDXGIFactory hooked. Target: 0x00007FFFE40C6490
0412/171202 [27E4] CreateDXGIFactory1 hooked. Target: 0x00007FFFE40C7030
0412/171203 [125C] CreateDXGIFactory1()
0412/171203 [125C] IDXGIFactory_QueryInterface hooked. Target: 0x00007FFFE40C7C50
0412/171203 [125C] IDXGIFactory1_CreateSwapChain hooked. Target: 0x00007FFFE4109590
0412/171203 [125C] D3D11.DLL loaded
0412/171203 [125C] D3D11 ripper init
0412/171203 [125C] D3D11CreateDeviceAndSwapChain hooked. Target: 0x00007FFFE0425170
0412/171203 [125C] D3D11CreateDevice hooked. Target: 0x00007FFFE0425080
0412/171203 [125C] D3D11CreateDeviceAndSwapChain() return: 0x00000000
0412/171203 [125C] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFFE050F6E0
0412/171204 [125C] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFFE0562ED0
0412/171204 [125C] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFFE051B270
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFFE0511470
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFFE05631C0
0412/171204 [125C] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFFE05643B0
0412/171204 [125C] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFFE051F8D0
0412/171204 [125C] ID3D11DeviceContext_PSSetShaderResources hooked. Target: 0x00007FFFE0515910
0412/171204 [125C] ID3D11Device_CreateInputLayout hooked. Target: 0x00007FFFE03EEA60
0412/171204 [125C] ID3D11Device_CreateVertexShader hooked. Target: 0x00007FFFE03EEAA0
0412/171204 [125C] ID3D11Device_CreatePixelShader hooked. Target: 0x00007FFFE03EEAE0
0412/171204 [125C] ID3D11Device_CreateGeometryShader hooked. Target: 0x00007FFFE04978E0
0412/171204 [125C] ID3D11Device_CreateGeometryShaderWithStreamOutput hooked. Target: 0x00007FFFE0497920
0412/171204 [125C] D3D11CreateDevice() return: 0x00000000
0412/171204 [125C] IDXGIFactory_CreateSwapChain()
0412/171204 [125C] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0412/171204 [125C] IDXGISwapChain_Present hooked. Target: 0x00007FFFE40C2140
0412/171204 [125C] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFFE0503A90
0412/171204 [125C] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFFE05A87E0
0412/171204 [125C] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFFE051AD90
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFFE0510980
0412/171204 [125C] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFFE05A8950
0412/171204 [125C] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFFE05A8DA0
0412/171204 [125C] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFFE0507C20

Ripper works correctly. Read manual how find correct UV  [http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/)
## Post #554
- Username: wardialer6000
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jun 09, 2016 2:05 am
- Post datetime: 2017-04-16T04:24:29+00:00
- Post Title: Re: Ninja Ripper

i know it says it shouldn't rip posed models.  but sometimes it does... and that's great... 'cause that's exactly what i want for 3D printing.  i'm just piecing together verveto from tales of berseria.  i haven't tried the ninja ripper 3DS MAX script, but i might later.

off the top of my head, other games that rip posed models... naruto 4 (for sure), CM3D2 and a few other unity games (i think).

anyways couldn't get anything out of bayonetta (posed or unposed) w/ ninja ripper or 3D ripper DX despite the game being DX9.  i think the splash screen disables it, but that's w/ 1.5.2... i'll try the latest version tomorrow.

glad you're still around, updating this tool.  thanks.

just tried out the MAX import script.  works great except it didn't attach velvet's blade to her arm (my fault... didn't include the first 2 rips in the group and i'm guessing they were important).  also the normals are flipped, but again that's my fault because i didn't really pay attention to the check boxes.
## Post #555
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-04-17T08:16:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from wardialer6000
>
> 

i know it says it shouldn't rip posed models.  but sometimes it does... and that's great... 'cause that's exactly what i want for 3D printing.  i'm just piecing together verveto from tales of berseria.  i haven't tried the ninja ripper 3DS MAX script, but i might later.

off the top of my head, other games that rip posed models... naruto 4 (for sure), CM3D2 and a few other unity games (i think).

anyways couldn't get anything out of bayonetta (posed or unposed) w/ ninja ripper or 3D ripper DX despite the game being DX9.  i think the splash screen disables it, but that's w/ 1.5.2... i'll try the latest version tomorrow.

glad you're still around, updating this tool.  thanks.

just tried out the MAX import script.  works great except it didn't attach velvet's blade to her arm (my fault... didn't include the first 2 rips in the group and i'm guessing they were important).  also the normals are flipped, but again that's my fault because i didn't really pay attention to the check boxes.

"Thank you" words is good. Donation is better
## Post #556
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-05-01T03:10:12+00:00
- Post Title: Re: Ninja Ripper

so im trying to use ninja ripper with mass effect Andromeda but when i use the x64 version it wont start the game and its like that for every game that uses x64. the x86 starts the game but it dosnt allow me to rip how do i fix this
## Post #557
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-02T07:26:44+00:00
- Post Title: Re: Ninja Ripper

Attach log
## Post #558
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-05-02T20:16:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Attach log

```
0424/143210 [03A8] © 2004-2017 black_ninja

0424/143210 [03A8] LOG START

0424/143210 [03A8] Executable: F:\EA GAMES\Mass Effect Andromeda\MassEffectAndromeda.exe
0424/143210 [03A8] Output directory: F:\EA GAMES\Mass Effect Andromeda\_NinjaRipper\2017.04.24_14.32.10_MassEffectAndromeda.exe_15428\
0424/143210 [03A8] Win ver: 6.2 x64 

0424/143210 [03A8] Inject mode: "intruder"
0424/143210 [03A8] Texture downscale max width : 4096
0424/143210 [03A8] Texture downscale max height: 4096
0424/143210 [03A8] Texture downscale value: 2
0424/143210 [03A8] LdrLoadDll hooked. Target: 0x00007FF8BA889E70
0424/143210 [03A8] LdrUnloadDll hooked. Target: 0x00007FF8BA8CED90
0424/143210 [03A8] CreateProcessA hooked. Target: 0x00007FF8BA67B970
0424/143210 [03A8] CreateProcessW hooked. Target: 0x00007FF8BA67BEC0
0424/143210 [03A8] CreateProcessAsUserW hooked. Target: 0x00007FF8B8B082B0
0424/143210 [03A8] CreateProcessWithLogonW hooked. Target: 0x00007FF8B8B35C10
0424/143210 [03A8] CreateProcessWithTokenW hooked. Target: 0x00007FF8B8AF2790
0424/143210 [03A8] SetTokenInformation hooked. Target: 0x00007FF8B8B0C2E0
0424/143212 [03A8] CreateProcessW("F:\EAGAME~1\MASSEF~1\\Core\ActivationUI.exe" /SMOID=372") return: 1
0424/143212 [03A8] Injecting to child process. Status: OK
0424/143214 [03A8] Loaded Modules List
0424/143214 [03A8] ----------------------------------------
0424/143214 [03A8] BaseAddr            Size         Module
0424/143214 [03A8] ----------------------------------------
0424/143214 [03A8] 0x0000000140000000 (0x0874B000)  F:\EA GAMES\Mass Effect Andromeda\MassEffectAndromeda.exe
0424/143214 [03A8] 0x00007FF8BA880000 (0x001D1000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0424/143214 [03A8] 0x00007FF8BA660000 (0x000AB000)  C:\WINDOWS\System32\KERNEL32.DLL
0424/143214 [03A8] 0x00007FF8B76F0000 (0x0021D000)  C:\WINDOWS\System32\KERNELBASE.dll
0424/143214 [03A8] 0x00007FF88AE80000 (0x000F5000)  F:\EA GAMES\Mass Effect Andromeda\Core\Activation64.dll
0424/143214 [03A8] 0x00007FF8B7470000 (0x001C9000)  C:\WINDOWS\System32\CRYPT32.dll
0424/143214 [03A8] 0x00007FF8B7980000 (0x000F5000)  C:\WINDOWS\System32\ucrtbase.dll
0424/143214 [03A8] 0x00007FF8B6D10000 (0x00010000)  C:\WINDOWS\System32\MSASN1.dll
0424/143214 [03A8] 0x00007FF8B7A80000 (0x00055000)  C:\WINDOWS\System32\WINTRUST.dll
0424/143214 [03A8] 0x00007FF8B8980000 (0x0009E000)  C:\WINDOWS\System32\msvcrt.dll
0424/143214 [03A8] 0x00007FF8B7E20000 (0x00121000)  C:\WINDOWS\System32\RPCRT4.dll
0424/143214 [03A8] 0x00007FF8BA710000 (0x00165000)  C:\WINDOWS\System32\USER32.dll
0424/143214 [03A8] 0x00007FF8B6D70000 (0x0001E000)  C:\WINDOWS\System32\win32u.dll
0424/143214 [03A8] 0x00007FF8B87B0000 (0x00034000)  C:\WINDOWS\System32\GDI32.dll
0424/143214 [03A8] 0x00007FF8AA1D0000 (0x000EF000)  C:\WINDOWS\SYSTEM32\MSVCR120.dll
0424/143214 [03A8] 0x00007FF8AA0F0000 (0x000A6000)  C:\WINDOWS\SYSTEM32\MSVCP120.dll
0424/143214 [03A8] 0x00007FF8B7BD0000 (0x00182000)  C:\WINDOWS\System32\gdi32full.dll
0424/143214 [03A8] 0x00007FF8B8AF0000 (0x000A2000)  C:\WINDOWS\System32\ADVAPI32.dll
0424/143214 [03A8] 0x00007FF8B80B0000 (0x00059000)  C:\WINDOWS\System32\sechost.dll
0424/143214 [03A8] 0x00007FF8B8BA0000 (0x01508000)  C:\WINDOWS\System32\SHELL32.dll
0424/143214 [03A8] 0x00007FF8B7B80000 (0x00042000)  C:\WINDOWS\System32\cfgmgr32.dll
0424/143214 [03A8] 0x00007FF8B6D90000 (0x006DA000)  C:\WINDOWS\System32\windows.storage.dll
0424/143214 [03A8] 0x00007FF8BA0B0000 (0x002C8000)  C:\WINDOWS\System32\combase.dll
0424/143214 [03A8] 0x00007FF8B7910000 (0x0006A000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0424/143214 [03A8] 0x00007FF8B6D20000 (0x0004C000)  C:\WINDOWS\System32\powrprof.dll
0424/143214 [03A8] 0x00007FF8BA4B0000 (0x00052000)  C:\WINDOWS\System32\shlwapi.dll
0424/143214 [03A8] 0x00007FF8B6D00000 (0x0000F000)  C:\WINDOWS\System32\kernel.appcore.dll
0424/143214 [03A8] 0x00007FF8B7D60000 (0x000A9000)  C:\WINDOWS\System32\shcore.dll
0424/143214 [03A8] 0x00007FF8B6CE0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0424/143214 [03A8] 0x00007FF8BA380000 (0x0002E000)  C:\WINDOWS\System32\IMM32.DLL
0424/143214 [03A8] 0x00007FF889390000 (0x00105000)  C:\Users\david\Desktop\ninjaripper1.6.1\x64\intruder.dll
0424/143214 [03A8] 0x00007FF8B05A0000 (0x00192000)  C:\WINDOWS\SYSTEM32\dbghelp.dll
0424/143214 [03A8] 0x00007FF8B0240000 (0x00029000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0424/143214 [03A8] 0x00007FF8BA650000 (0x00008000)  C:\WINDOWS\System32\psapi.dll
0424/143214 [03A8] LOG END

```
## Post #559
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-03T07:36:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from savinpvtmike
>
> blackninja wrote:Attach log
Code: Select all0424/143210 [03A8] Ninja Ripper 1.6.1 x64
0424/143210 [03A8] © 2004-2017 black_ninja

0424/143210 [03A8] LOG START

0424/143210 [03A8] Executable: F:\EA GAMES\Mass Effect Andromeda\MassEffectAndromeda.exe
0424/143210 [03A8] Output directory: F:\EA GAMES\Mass Effect Andromeda\_NinjaRipper\2017.04.24_14.32.10_MassEffectAndromeda.exe_15428\
0424/143210 [03A8] Win ver: 6.2 x64 

0424/143210 [03A8] Inject mode: "intruder"
0424/143210 [03A8] Texture downscale max width : 4096
0424/143210 [03A8] Texture downscale max height: 4096
0424/143210 [03A8] Texture downscale value: 2
0424/143210 [03A8] LdrLoadDll hooked. Target: 0x00007FF8BA889E70
0424/143210 [03A8] LdrUnloadDll hooked. Target: 0x00007FF8BA8CED90
0424/143210 [03A8] CreateProcessA hooked. Target: 0x00007FF8BA67B970
0424/143210 [03A8] CreateProcessW hooked. Target: 0x00007FF8BA67BEC0
0424/143210 [03A8] CreateProcessAsUserW hooked. Target: 0x00007FF8B8B082B0
0424/143210 [03A8] CreateProcessWithLogonW hooked. Target: 0x00007FF8B8B35C10
0424/143210 [03A8] CreateProcessWithTokenW hooked. Target: 0x00007FF8B8AF2790
0424/143210 [03A8] SetTokenInformation hooked. Target: 0x00007FF8B8B0C2E0
0424/143212 [03A8] CreateProcessW("F:\EAGAME~1\MASSEF~1\\Core\ActivationUI.exe" /SMOID=372") return: 1
0424/143212 [03A8] Injecting to child process. Status: OK
0424/143214 [03A8] Loaded Modules List
0424/143214 [03A8] ----------------------------------------
0424/143214 [03A8] BaseAddr            Size         Module
0424/143214 [03A8] ----------------------------------------
0424/143214 [03A8] 0x0000000140000000 (0x0874B000)  F:\EA GAMES\Mass Effect Andromeda\MassEffectAndromeda.exe
0424/143214 [03A8] 0x00007FF8BA880000 (0x001D1000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0424/143214 [03A8] 0x00007FF8BA660000 (0x000AB000)  C:\WINDOWS\System32\KERNEL32.DLL
0424/143214 [03A8] 0x00007FF8B76F0000 (0x0021D000)  C:\WINDOWS\System32\KERNELBASE.dll
0424/143214 [03A8] 0x00007FF88AE80000 (0x000F5000)  F:\EA GAMES\Mass Effect Andromeda\Core\Activation64.dll
0424/143214 [03A8] 0x00007FF8B7470000 (0x001C9000)  C:\WINDOWS\System32\CRYPT32.dll
0424/143214 [03A8] 0x00007FF8B7980000 (0x000F5000)  C:\WINDOWS\System32\ucrtbase.dll
0424/143214 [03A8] 0x00007FF8B6D10000 (0x00010000)  C:\WINDOWS\System32\MSASN1.dll
0424/143214 [03A8] 0x00007FF8B7A80000 (0x00055000)  C:\WINDOWS\System32\WINTRUST.dll
0424/143214 [03A8] 0x00007FF8B8980000 (0x0009E000)  C:\WINDOWS\System32\msvcrt.dll
0424/143214 [03A8] 0x00007FF8B7E20000 (0x00121000)  C:\WINDOWS\System32\RPCRT4.dll
0424/143214 [03A8] 0x00007FF8BA710000 (0x00165000)  C:\WINDOWS\System32\USER32.dll
0424/143214 [03A8] 0x00007FF8B6D70000 (0x0001E000)  C:\WINDOWS\System32\win32u.dll
0424/143214 [03A8] 0x00007FF8B87B0000 (0x00034000)  C:\WINDOWS\System32\GDI32.dll
0424/143214 [03A8] 0x00007FF8AA1D0000 (0x000EF000)  C:\WINDOWS\SYSTEM32\MSVCR120.dll
0424/143214 [03A8] 0x00007FF8AA0F0000 (0x000A6000)  C:\WINDOWS\SYSTEM32\MSVCP120.dll
0424/143214 [03A8] 0x00007FF8B7BD0000 (0x00182000)  C:\WINDOWS\System32\gdi32full.dll
0424/143214 [03A8] 0x00007FF8B8AF0000 (0x000A2000)  C:\WINDOWS\System32\ADVAPI32.dll
0424/143214 [03A8] 0x00007FF8B80B0000 (0x00059000)  C:\WINDOWS\System32\sechost.dll
0424/143214 [03A8] 0x00007FF8B8BA0000 (0x01508000)  C:\WINDOWS\System32\SHELL32.dll
0424/143214 [03A8] 0x00007FF8B7B80000 (0x00042000)  C:\WINDOWS\System32\cfgmgr32.dll
0424/143214 [03A8] 0x00007FF8B6D90000 (0x006DA000)  C:\WINDOWS\System32\windows.storage.dll
0424/143214 [03A8] 0x00007FF8BA0B0000 (0x002C8000)  C:\WINDOWS\System32\combase.dll
0424/143214 [03A8] 0x00007FF8B7910000 (0x0006A000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0424/143214 [03A8] 0x00007FF8B6D20000 (0x0004C000)  C:\WINDOWS\System32\powrprof.dll
0424/143214 [03A8] 0x00007FF8BA4B0000 (0x00052000)  C:\WINDOWS\System32\shlwapi.dll
0424/143214 [03A8] 0x00007FF8B6D00000 (0x0000F000)  C:\WINDOWS\System32\kernel.appcore.dll
0424/143214 [03A8] 0x00007FF8B7D60000 (0x000A9000)  C:\WINDOWS\System32\shcore.dll
0424/143214 [03A8] 0x00007FF8B6CE0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0424/143214 [03A8] 0x00007FF8BA380000 (0x0002E000)  C:\WINDOWS\System32\IMM32.DLL
0424/143214 [03A8] 0x00007FF889390000 (0x00105000)  C:\Users\david\Desktop\ninjaripper1.6.1\x64\intruder.dll
0424/143214 [03A8] 0x00007FF8B05A0000 (0x00192000)  C:\WINDOWS\SYSTEM32\dbghelp.dll
0424/143214 [03A8] 0x00007FF8B0240000 (0x00029000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0424/143214 [03A8] 0x00007FF8BA650000 (0x00008000)  C:\WINDOWS\System32\psapi.dll
0424/143214 [03A8] LOG END

From log analyze child process created and ripper injected
Second log for F:\EAGAME~1\MASSEF~1\\Core\ActivationUI.exe exist?

Added: Looks like ActivationUI.exe 32bit process and injection from x64 process failed. If so its a ripper bug.
## Post #560
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-05-06T19:52:43+00:00
- Post Title: Re: Ninja Ripper

Grats for your tool which is amazing and the script works too with 3DSMax 2015, unfortunatly looks like it have some problems with Google Earth, see the screenshot.
[http://i.imgur.com/YOKvFo7.jpg](http://i.imgur.com/YOKvFo7.jpg)

Any advice?
## Post #561
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-07T08:51:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> Grats for your tool which is amazing and the script works too with 3DSMax 2015, unfortunatly looks like it have some problems with Google Earth, see the screenshot.
http://i.imgur.com/YOKvFo7.jpg

Any advice?

Too many objects in import. Try import by single meshs
## Post #562
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-05-07T09:04:43+00:00
- Post Title: Re: Ninja Ripper

Nope... it import squashed mesh but also do a mess with textures too  

texture
[http://i.imgur.com/Onv83t2.jpg](http://i.imgur.com/Onv83t2.jpg)

3d model
[http://i.imgur.com/hSSRG6I.jpg](http://i.imgur.com/hSSRG6I.jpg)
## Post #563
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-07T11:23:01+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> Nope... it import squashed mesh but also do a mess with textures too  

texture
http://i.imgur.com/Onv83t2.jpg

3d model
http://i.imgur.com/hSSRG6I.jpg

On old GE version objects are not transformed.
May be google update format
## Post #564
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2017-05-09T13:25:36+00:00
- Post Title: Re: Ninja Ripper

Thank you for this tool. I want to quickly mention the steps for the game launcher in DCUO, in case someone out there is still confused.

How to rip your custom character model from DC Universe Online:
How to run Ninja Ripper with DCUO Game Launcher:
Step 1: Run the x86 version of NinjaRipper as administrator.
Step 2: In the Exe path, input the location of the launcher's executable file: LaunchPad.exe
Step 3: Set wrapper to D3D9 wrapper.
Step 4: Set the output directory to the folder where you want the ripped meshes/textures.
Step 5: Click 'Run'. The game launcher will start, but don't click 'Play'.
- Ninja Ripper created a d3d9.dll file in the same folder as the LaunchPad.exe.
Step 6: Open the steamapps\common\DC Universe Online folder and copy the d3d9.dll file.
Step 7: Open the folder that contains the game's executable: DCGAME.EXE
- steamapps\common\DC Universe Online\UNREAL3\BINARIES\WIN32 folder
Step 8: Paste the d3d9.dll file into the folder.
Step 9: Now click 'Play' button on the game's launcher.
Step 10: In the character login menu, select the character you want, and press F10 to rip.
- Your game will freeze for a few seconds or up to a minute.
- The meshes and textures will be located in your output folder.

Troubleshoot: 
- If nothing happens, check if  both LaunchPad.exe and DCGAME.EXE are set to 'Run as Administrator'.
- Try Fullscreen or Windowed mode.
- Check Antivirus

If you plan to use Blender to import the rip meshes, you can install this Blender addon:

```
https://github.com/angavrilov/blender-import-ninjaripper
```
 (install import-ninja.py)
- In the import option, you may need to enable 'Flip Vertical'.

Search Engine Keywords: Ninja Ripper Game Launcher Launchpad DCUO DC Universe Online Custom Character Creation
## Post #565
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-16T07:39:26+00:00
- Post Title: Re: Ninja Ripper

Version 1.6.2

Fixed injection from x32 to x64 and x64 to x32

[http://dropmefiles.com/QLALq](http://dropmefiles.com/QLALq)
## Post #566
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-05-16T09:20:54+00:00
- Post Title: Re: Ninja Ripper

Have you fixed Google Earth too ?   
Thank's for updating it btw
## Post #567
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-16T10:22:24+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> Have you fixed Google Earth too ?   
Thank's for updating it btw
No
## Post #568
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2017-05-18T03:34:19+00:00
- Post Title: Re: Ninja Ripper

Is there a way for ninjaripper to attach to an already running application?
## Post #569
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-18T07:04:21+00:00
- Post Title: Re: Ninja Ripper

> Reply from majidemo
>
> Is there a way for ninjaripper to attach to an already running application?
No. This feature not realized.
## Post #570
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-05-18T08:01:43+00:00
- Post Title: Re: Ninja Ripper

> Reply from majidemo
>
> Is there a way for ninjaripper to attach to an already running application?
No, you have to tell to ninjaripper which application you want to capture, 'cause it need to monitor what the program will load in memory.
## Post #571
- Username: pleup
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat May 20, 2017 10:56 pm
- Post datetime: 2017-05-20T15:07:31+00:00
- Post Title: Re: Ninja Ripper

Hi

I tried to run ninjaripper (1.6.2) on GhostRecon Wildland

After running the exe from ninjaripper, the game won't launch, and thousands of  injhelper.exe instances have spawn.
Then if i launch the game normaly from UPlay launcher, the same thing happen and the game won't launch.

How can't i just fix the mess ninjaripper made in the game so i can just launch it normally?

Here the logs:

```
0519/231259 [035C] Ninja Ripper 1.6.2 x64
0519/231259 [035C] © 2004-2017 black_ninja

0519/231259 [035C] LOG START

0519/231259 [035C] Executable: D:\Programs\Tom Clancy's Ghost Recon Wildlands\GRW.exe
0519/231259 [035C] Output directory: D:\tmp\GRW\_NinjaRipper\2017.05.19_23.12.59_GRW.exe_928\
0519/231259 [035C] Win ver: 6.2 x64 

0519/231259 [035C] Inject mode: "d3d11.dll wrapper"
0519/231259 [035C] Texture downscale max width : 4096
0519/231259 [035C] Texture downscale max height: 4096
0519/231259 [035C] Texture downscale value: 2
0519/231259 [035C] LdrLoadDll hooked. Target: 0x00007FFA18B60B30
0519/231259 [035C] LdrUnloadDll hooked. Target: 0x00007FFA18B58CA0
0519/231259 [035C] CreateProcessA hooked. Target: 0x00007FFA18343600
0519/231259 [035C] CreateProcessW hooked. Target: 0x00007FFA18343B00
0519/231259 [035C] CreateProcessAsUserW hooked. Target: 0x00007FFA161A7F10
0519/231259 [035C] CreateProcessWithLogonW hooked. Target: 0x00007FFA161C3CB0
0519/231259 [035C] CreateProcessWithTokenW hooked. Target: 0x00007FFA16192810
0519/231259 [035C] SetTokenInformation hooked. Target: 0x00007FFA161ABFC0
0519/231259 [035C] D3D9 ripper init
0519/231259 [035C] Direct3DCreate9 hooked. Target: 0x00007FF9F4096C30
0519/231259 [035C] Direct3DCreate9Ex hooked. Target: 0x00007FF9F4095DE0
0519/231259 [035C] DXGI init
0519/231259 [035C] CreateDXGIFactory hooked. Target: 0x00007FFA127E6270
0519/231259 [035C] CreateDXGIFactory1 hooked. Target: 0x00007FFA127E63D0
0519/231259 [035C] DDRAW init
0519/231259 [035C] DirectDrawCreateEx hooked. Target: 0x00007FF9F5FDA570
0519/231259 [035C] DirectDrawCreate hooked. Target: 0x00007FF9F5FA56E0
0519/231305 [035C] CreateProcessW("C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\UbisoftGameLauncher.exe") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7692 4076") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  3388 3320") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8108 8012") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8112 5480") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8020 5484") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  5496 7276") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7716 7272") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  6484 7332") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7832 7864") return: 1

... like this for 600 lines 


```


Thanks
## Post #572
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-20T20:25:28+00:00
- Post Title: Re: Ninja Ripper

Why my textures that i get using the  NinjaRipper are Discolored ?



Tex_0001.bmp (25.7 KiB) Viewed 218 times


[http://imgur.com/3HD0X6o](http://imgur.com/3HD0X6o)
[http://imgur.com/HDgFyHF](http://imgur.com/HDgFyHF)
## Post #573
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-21T06:53:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from pleup
>
> Hi

I tried to run ninjaripper (1.6.2) on GhostRecon Wildland

After running the exe from ninjaripper, the game won't launch, and thousands of  injhelper.exe instances have spawn.
Then if i launch the game normaly from UPlay launcher, the same thing happen and the game won't launch.

How can't i just fix the mess ninjaripper made in the game so i can just launch it normally?

Here the logs:
Code: Select all
0519/231259 [035C] Ninja Ripper 1.6.2 x64
0519/231259 [035C] © 2004-2017 black_ninja

0519/231259 [035C] LOG START

0519/231259 [035C] Executable: D:\Programs\Tom Clancy's Ghost Recon Wildlands\GRW.exe
0519/231259 [035C] Output directory: D:\tmp\GRW\_NinjaRipper\2017.05.19_23.12.59_GRW.exe_928\
0519/231259 [035C] Win ver: 6.2 x64 

0519/231259 [035C] Inject mode: "d3d11.dll wrapper"
0519/231259 [035C] Texture downscale max width : 4096
0519/231259 [035C] Texture downscale max height: 4096
0519/231259 [035C] Texture downscale value: 2
0519/231259 [035C] LdrLoadDll hooked. Target: 0x00007FFA18B60B30
0519/231259 [035C] LdrUnloadDll hooked. Target: 0x00007FFA18B58CA0
0519/231259 [035C] CreateProcessA hooked. Target: 0x00007FFA18343600
0519/231259 [035C] CreateProcessW hooked. Target: 0x00007FFA18343B00
0519/231259 [035C] CreateProcessAsUserW hooked. Target: 0x00007FFA161A7F10
0519/231259 [035C] CreateProcessWithLogonW hooked. Target: 0x00007FFA161C3CB0
0519/231259 [035C] CreateProcessWithTokenW hooked. Target: 0x00007FFA16192810
0519/231259 [035C] SetTokenInformation hooked. Target: 0x00007FFA161ABFC0
0519/231259 [035C] D3D9 ripper init
0519/231259 [035C] Direct3DCreate9 hooked. Target: 0x00007FF9F4096C30
0519/231259 [035C] Direct3DCreate9Ex hooked. Target: 0x00007FF9F4095DE0
0519/231259 [035C] DXGI init
0519/231259 [035C] CreateDXGIFactory hooked. Target: 0x00007FFA127E6270
0519/231259 [035C] CreateDXGIFactory1 hooked. Target: 0x00007FFA127E63D0
0519/231259 [035C] DDRAW init
0519/231259 [035C] DirectDrawCreateEx hooked. Target: 0x00007FF9F5FDA570
0519/231259 [035C] DirectDrawCreate hooked. Target: 0x00007FF9F5FA56E0
0519/231305 [035C] CreateProcessW("C:\Program Files (x86)\Ubisoft\Ubisoft Game Launcher\UbisoftGameLauncher.exe") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7692 4076") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  3388 3320") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8108 8012") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8112 5480") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  8020 5484") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  5496 7276") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7716 7272") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  6484 7332") return: 1
0519/231305 [035C] CreateProcessW("C:\Users\pierre\Desktop\ninjaripper1.6.2\x86\injhelper.exe  7832 7864") return: 1

... like this for 600 lines 



Thanks

Looks like ripper hooks confilct.
Try this
1.6.3
[http://dropmefiles.com/cSkcN](http://dropmefiles.com/cSkcN)
## Post #574
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-21T08:06:29+00:00
- Post Title: Re: Ninja Ripper

> Reply from BL4CK0UT
>
> Why my textures that i get using the  NinjaRipper are Discolored ?
Tex_0001.bmp
http://imgur.com/3HD0X6o
http://imgur.com/HDgFyHF

Game name?
May be image processed by pixel shader before render, may be ripper bug
## Post #575
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-21T16:03:57+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> BL4CK0UT wrote:Why my textures that i get using the  NinjaRipper are Discolored ?
Tex_0001.bmp
http://imgur.com/3HD0X6o
http://imgur.com/HDgFyHF

Game name?
May be image processed by pixel shader before render, may be ripper bug

It's a PS2 game that i play on PCSX2 : NARUTO UZUMAKI CHRONICLES
## Post #576
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-05-22T00:05:24+00:00
- Post Title: Re: Ninja Ripper

> Reply from BL4CK0UT
>
> Why my textures that i get using the  NinjaRipper are Discolored ?
Textures are in BGR format, you can use [XnViewMP](http://www.xnview.com/en/xnviewmp/#downloads) to batch convert them to RGB:
[](http://fastpic.ru/view/94/2017/0522/01efcc047d1be2a6e69a19487461bbfe.png.html)
## Post #577
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-23T07:30:02+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 1.6.4
[http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)
## Post #578
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-23T19:23:35+00:00
- Post Title: Re: Ninja Ripper

> Reply from Andrakann
>
> BL4CK0UT wrote:Why my textures that i get using the  NinjaRipper are Discolored ?
Textures are in BGR format, you can use XnViewMP to batch convert them to RGB:
Thank You Very Much
## Post #579
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-05-24T09:37:42+00:00
- Post Title: Re: Ninja Ripper

> Reply from BL4CK0UT
>
> Andrakann wrote:BL4CK0UT wrote:Why my textures that i get using the  NinjaRipper are Discolored ?
Textures are in BGR format, you can use XnViewMP to batch convert them to RGB:

Thank You Very Much

Emulator version?
## Post #580
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-24T19:30:09+00:00
- Post Title: Re: Ninja Ripper

Textures are in BGR format, you can use [XnViewMP](http://www.xnview.com/en/xnviewmp/#downloads) to batch convert them to RGB:
[](http://fastpic.ru/view/94/2017/0522/01efcc047d1be2a6e69a19487461bbfe.png.html)[/quote]
Thank You Very Much [/quote]

Emulator version?[/quote]
Yep, i'm trying to mod this game.. but it's being impossible , i don't know how i can open the .RAW "data" files inside the CFC.DIG
## Post #581
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-05-29T14:19:14+00:00
- Post Title: Re: Ninja Ripper

> Reply from BL4CK0UT
>
> blackninja wrote:Emulator version?
Yep, i'm trying to mod this game.. but it's being impossible , i don't know how i can open the .RAW "data" files inside the CFC.DIG
He asked about version (and name) of emulator you are using for ripping and got those BGR-colored textures.
## Post #582
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2017-05-29T22:07:24+00:00
- Post Title: Re: Ninja Ripper

> Reply from Andrakann
>
> BL4CK0UT wrote:blackninja wrote:Emulator version?
Yep, i'm trying to mod this game.. but it's being impossible , i don't know how i can open the .RAW "data" files inside the CFC.DIG
He asked about version (and name) of emulator you are using for ripping and got those BGR-colored textures.

i see now lol , my bad , it's pcsx2 version 1.4.0
## Post #583
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-05-31T22:24:51+00:00
- Post Title: Re: Ninja Ripper

Is it possible to edit the intruder.dll to force the game models from Tales of Zestiria and Tales of Berseria in T-Pose?
## Post #584
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-05-31T23:02:54+00:00
- Post Title: Re: Ninja Ripper

> Reply from Escope12
>
> Is it possible to edit the intruder.dll to force the game models from Tales of Zestiria and Tales of Berseria in T-Pose?
If their animation files is available (not packed to big archive or within model file), you can try to replace them to zeroed files or copy and replace with smallest animation files from another models - if you lucky and game doesn't crash, you can get models staying in t-pose in game. Then rip it.
## Post #585
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2017-06-01T00:49:14+00:00
- Post Title: Re: Ninja Ripper

> Reply from Andrakann
>
> Escope12 wrote:Is it possible to edit the intruder.dll to force the game models from Tales of Zestiria and Tales of Berseria in T-Pose?
If their animation files is available (not packed to big archive or within model file), you can try to replace them to zeroed files or copy and replace with smallest animation files from another models - if you lucky and game doesn't crash, you can get models staying in t-pose in game. Then rip it.
I may have trouble doing that.
## Post #586
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-06-07T14:54:11+00:00
- Post Title: Re: Ninja Ripper

Incredible, Ninja fail with Settlers 7   
this damned game still unbeatable
## Post #587
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-06-07T17:09:38+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> Incredible, Ninja fail with Settlers 7   
this damned game still unbeatable
Attach log
## Post #588
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-06-07T18:39:10+00:00
- Post Title: Re: Ninja Ripper

Nevemind D3D9 wrapper do his jobs!  
But find what I'm looking for is a mess between  1209 files  

... but sometime still fail: 
F12 didn't caputre anything and F10 did the same "cube" with useless meshes just like with GoogleEarth, so I've left the log in attach.


[edit]
Ok, i've removed the d3d dll from the game folder, now it import correctly   
[/edit]
[Settlers7R.exe.log.7z](https://xentaxbackup.github.io/file/12972_Settlers7R.exe.log.7z)
## Post #589
- Username: redmoone
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 15, 2017 7:30 pm
- Post datetime: 2017-06-15T11:39:36+00:00
- Post Title: Re: Ninja Ripper

Hey Guys, so I've been trying to rip Heroforge.com , which works very well. Now the have some very nice poses there but when i rip it i get char in T-Pose,
Is there a way to get the pose displayed? I know i can rig the character which works but takes a lot of time, i would love to just capture the pose!
## Post #590
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-06-17T13:02:55+00:00
- Post Title: Re: Ninja Ripper

Any chance to import the objects (group of objects) displaced, instead having it all at 0,0,0 ?
## Post #591
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-17T15:55:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> Any chance to import the objects (group of objects) displaced, instead having it all at 0,0,0 ?as the red line claims here: [http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/) So basically NO.
## Post #592
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-06-21T11:52:40+00:00
- Post Title: Re: Ninja Ripper

NinjaRipper 1.7
[http://dropmefiles.com/7Vk6S](http://dropmefiles.com/7Vk6S)

+ Bug fixes in x64
+ Better browsers rip support
## Post #593
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-21T16:01:14+00:00
- Post Title: Re: Ninja Ripper

also here's updated: [http://cgig.ru/ninjaripper/](http://cgig.ru/ninjaripper/)
## Post #594
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-06-22T08:14:06+00:00
- Post Title: Re: Ninja Ripper

just as idea:
what if you calculate the [bounding box](http://docs.autodesk.com/3DSMAX/16/ENU/MAXScript-Help/index.html?url=files/GUID-B94A1094-002C-4A7D-B5DD-AF5AB3435041.htm,topicNumber=d30e91939) (volume) for each object and place all object in a 2D array on an X - Y grid?
On this way we could avoid the problem of 3700 overlapped object... just an idea.
## Post #595
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-22T08:19:57+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> just as idea:
what if you calculate the bounding box (volume) for each object and place all object in a 2D array on an X - Y grid?
On this way we could avoid the problem of 3700 overlapped object... just an idea.good field for thoughts and researches which devs have no time for  these days
## Post #596
- Username: JohnRWMarchant
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 13, 2016 10:07 pm
- Post datetime: 2017-06-24T14:01:18+00:00
- Post Title: Re: Ninja Ripper

Hi everyone, ive got my models ripped with texures no problem. The problem i have is the model is all dumped at 0,0,0, coordinates in Max and Blender. Has anyone found a way to get the whole model imported to the right positions. At the moment its a mess of 1000 objects all at the center.
## Post #597
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-24T14:11:42+00:00
- Post Title: Re: Ninja Ripper

> Reply from JohnRWMarchant
>
> Hi everyone, ive got my models ripped with texures no problem. The problem i have is the model is all dumped at 0,0,0, coordinates in Max and Blender. Has anyone found a way to get the whole model imported to the right positions. At the moment its a mess of 1000 objects all at the center.
you kidding, right?

> Reply from Tosyk
>
> MaximilianPs wrote:Any chance to import the objects (group of objects) displaced, instead having it all at 0,0,0 ?  as the red line claims here: http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/ So basically NO.
## Post #598
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2017-06-24T15:53:38+00:00
- Post Title: Re: Ninja Ripper

Dante was used to say "Don't care about the other but watch and pass by"   
Which mean "keep calm and don't kill who didn't read the early post"
## Post #599
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2017-07-05T18:07:29+00:00
- Post Title: Re: Ninja Ripper

In all technicality: Could PCSX2 support be added? It appears to rip at least SOME geometry when using D3D11 (Hardware) mode, but the models are a bit skewed.
## Post #600
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-05T22:49:10+00:00
- Post Title: Re: Ninja Ripper

Two questions. 
Nvm. Answered the first question on my own. Derp.

Also, I tried to use it on Danganronpa Despair Girls, and the models come out completely distorted. Any way to fix that?
## Post #601
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-06T09:38:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from frogz2007
>
> In all technicality: Could PCSX2 support be added? It appears to rip at least SOME geometry when using D3D11 (Hardware) mode, but the models are a bit skewed.this is more about emulator specific render method than ripper itself — in other words ripper just rips what PCSX2 renders and its render engine making that skewed models. If you ask why PCSX2 renders that way - my answer will be: I don't know, maybe it's easiest way or cheaper.

> Reply from anime663
>
> Two questions. 
Nvm. Answered the first question on my own. Derp.
Also, I tried to use it on Danganronpa Despair Girls, and the models come out completely distorted. Any way to fix that?all the "distortions" are unique, how do you think developers can help you without any samples, logs or images?
## Post #602
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-06T20:22:04+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> all the "distortions" are unique, how do you think developers can help you without any samples, logs or images?

Image:


Log:
[https://mega.nz/#!Wk1hQIzL!LFvnPzgXrv_Y ... TsAD5ByKSM](https://mega.nz/#!Wk1hQIzL!LFvnPzgXrv_YeiifdLPJTj57UtL90vLcaTsAD5ByKSM)

I've posted samples of the actual model files in another post of mine.
## Post #603
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-06T21:10:00+00:00
- Post Title: Re: Ninja Ripper

> Reply from anime663
>
> Tosyk wrote:all the "distortions" are unique, how do you think developers can help you without any samples, logs or images?

Image:


Log:
https://mega.nz/#!Wk1hQIzL!LFvnPzgXrv_Y ... TsAD5ByKSM

I've posted samples of the actual model files in another post of mine.hm, wierd distortion. this tells me that vertices may be actually compressed so no way to get the models in original shape. Devs might do this compression purposly. Though the NR's author may be more clear on this.
## Post #604
- Username: ElyosOfTheAbyss
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Jan 24, 2016 6:42 pm
- Post datetime: 2017-07-27T11:45:37+00:00
- Post Title: Re: Ninja Ripper

> Reply from Tosyk
>
> anime663 wrote:Tosyk wrote:all the "distortions" are unique, how do you think developers can help you without any samples, logs or images?

Image:


Log:
https://mega.nz/#!Wk1hQIzL!LFvnPzgXrv_Y ... TsAD5ByKSM

I've posted samples of the actual model files in another post of mine.hm, wierd distortion. this tells me that vertices may be actually compressed so no way to get the models in original shape. Devs might do this compression purposly. Though the NR's author may be more clear on this.
Just figured I would put it out there.
the weird distortion only seems to happen to models that have bones (or animations?) assigned to them.
## Post #605
- Username: faizeq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Dec 22, 2010 2:42 am
- Post datetime: 2017-08-16T09:14:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> NinjaRipper is open source now. Merry Christmas

https://github.com/blackninja2/ninjaripper

Hi Blackninja. I've been an admirer of your fine works on Ninja Ripper. Any chance we can have access to the current ninjaripper source code. Based on what I've gathered with the github revision, it is already benched. Would appreciate it if I can get a hold of it. 

Thank you
## Post #606
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-08-20T19:56:44+00:00
- Post Title: Re: Ninja Ripper

> Reply from faizeq
>
> blackninja wrote:NinjaRipper is open source now. Merry Christmas

https://github.com/blackninja2/ninjaripper

Hi Blackninja. I've been an admirer of your fine works on Ninja Ripper. Any chance we can have access to the current ninjaripper source code. Based on what I've gathered with the github revision, it is already benched. Would appreciate it if I can get a hold of it. 

Thank you

Sorry, after refactoring and adding x64 support, tool is not open source
## Post #607
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2017-08-21T02:27:05+00:00
- Post Title: Re: Ninja Ripper

Do you have any plans to add DX12 or Vulkan, or even OpenGL at any point.
A few emulators are slowly switching to using Vulkan instead of DX11.

Though I don't imagine ordinary games are going to do that, just emulators probably.
## Post #608
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2017-08-21T07:24:51+00:00
- Post Title: Re: Ninja Ripper

> Reply from lionheartuk
>
> Do you have any plans to add DX12 or Vulkan, or even OpenGL at any point.
A few emulators are slowly switching to using Vulkan instead of DX11.

Though I don't imagine ordinary games are going to do that, just emulators probably.

there are no plans for support. as there are no donations
## Post #609
- Username: justshopatkmart43
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 06, 2012 2:57 pm
- Post datetime: 2017-10-03T06:15:35+00:00
- Post Title: Re: Ninja Ripper

Any chance you know why I get errors like 'can't create dir' with 32 bit firefox dr9 wrapper on windows 10, I run as admin?
## Post #610
- Username: ExorNor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 11, 2017 9:10 pm
- Post datetime: 2017-11-11T14:22:16+00:00
- Post Title: Re: Ninja Ripper

Hello

Ninja Ripper 1.7.1 partially supports Google Earth Pro (last build)
The problem is that 3D in Earth is now generated via satellite photos and a terrain with chunks is created.
Before Earth displayed 3D buildings made by users.
Ninja Ripper seems to export the chunks but does not place them correctly.
Chunks are one on top of each other, and textures are messed up too.

Ninja Ripper seems to be the closest and only one to google earth export.
## Post #611
- Username: fenasi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 22, 2017 12:06 am
- Post datetime: 2017-11-13T21:22:41+00:00
- Post Title: Re: Ninja Ripper

i want to rip some locked cars from openIV application.but ninjaripper doesnt support it.can you have a look?
## Post #612
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-11-14T10:12:57+00:00
- Post Title: Re: Ninja Ripper

[](https://discord.gg/2PMeU2R)
I've made a Discord channel for quick chatting about ninja ripper. Russian forum is still official help place for feature/problems discussions.
Click on Discord logo to join or [here](https://discord.gg/2PMeU2R).
## Post #613
- Username: MrZasen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 28, 2015 3:48 pm
- Post datetime: 2017-11-29T08:44:11+00:00
- Post Title: Re: Ninja Ripper

I've downloaded Akiba's Trip for pc, and since there's no longer support in here on this game (ps3 version), I just ripped the models with ninja ripper.
But I'm having some trouble, the UV mapping looks incorrect. I can provide you with any model you might need from the game, or any texture, but I just need the map models :C
I tried several UV values and frlipping the UV too...
## Post #614
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2018-01-25T19:01:08+00:00
- Post Title: Re: Ninja Ripper

Can you guys help me out opening a .RAW File?
## Post #615
- Username: brennoarts
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 26, 2018 6:35 am
- Post datetime: 2018-01-31T23:12:24+00:00
- Post Title: Re: Ninja Ripper

guys, when i try open ac origins with Ninja ripper, nothing happen, the game not load, its from steam and uplay, someone can help-me?
## Post #616
- Username: thorh62
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 10, 2018 11:45 am
- Post datetime: 2018-02-22T05:05:40+00:00
- Post Title: Re: Ninja Ripper

Hello, I was wondering if anyone could help me figure out how to rip the 3d models of a racing game called "planet hot wheels"  using Ninja Ripper

I downloaded the latest version of NR, then ran the x86 version of NR as administrator
I followed the steps in the manual and the game launches successfully when I press "run"
but when I press the shortcut for ripping in the car selection menu, nothing happens
these are the logs when I tried the intruder and dx8 wrapper methods

```
0221/222141 [07FC] © black_ninja, 2017

0221/222141 [07FC] LOG START

0221/222141 [07FC] Executable: C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222141 [07FC] Output directory: C:\Users\a_pap\Downloads\highway35_10_17_05\_NinjaRipper\2018.02.21_22.21.41_highway35.exe_11880\
0221/222141 [07FC] Win ver: 6.2 x64 

0221/222141 [07FC] Inject mode: "d3d8.dll wrapper"
0221/222141 [07FC] Texture downscale max width : 4096
0221/222141 [07FC] Texture downscale max height: 4096
0221/222141 [07FC] Texture downscale value: 2
0221/222141 [07FC] LdrLoadDll hooked. Target: 0x772EE860
0221/222141 [07FC] LdrUnloadDll hooked. Target: 0x772EC1E0
0221/222141 [07FC] CreateProcessA hooked. Target: 0x756944B0
0221/222141 [07FC] CreateProcessW hooked. Target: 0x75694510
0221/222141 [07FC] CreateProcessAsUserW hooked. Target: 0x75511210
0221/222141 [07FC] CreateProcessWithLogonW hooked. Target: 0x75536970
0221/222141 [07FC] CreateProcessWithTokenW hooked. Target: 0x75501370
0221/222141 [07FC] SetTokenInformation hooked. Target: 0x75513E50
0221/222141 [07FC] D3D8.DLL loaded
0221/222141 [07FC] D3D8 ripper init
0221/222141 [07FC] Direct3DCreate8 hooked. Target: 0x6DBABFC0
0221/222141 [07FC] Direct3DCreate8(220) return: 0x031FC680
0221/222141 [07FC] IDirect3D8_CreateDevice hooked. Target: 0x6DBE7DB0
0221/222141 [07FC] IDirect3D8_CreateDevice(0x031FC680 ...) return: 0x00000000
0221/222141 [07FC] IDirect3DDevice8_SetTexture hooked. Target: 0x6DBEC540
0221/222141 [07FC] IDirect3DDevice8_Present hooked. Target: 0x6DBC92F0
0221/222141 [07FC] IDirect3DDevice8_DrawPrimitive hooked. Target: 0x6DBEEEE0
0221/222141 [07FC] IDirect3DDevice8_DrawIndexedPrimitive hooked. Target: 0x6DBEEFF0
0221/222141 [07FC] IDirect3DDevice8_DrawPrimitiveUP hooked. Target: 0x6DBEF3B0
0221/222141 [07FC] IDirect3DDevice8_DrawIndexedPrimitiveUP hooked. Target: 0x6DBEF610
0221/222141 [07FC] IDirect3DDevice8_CreateVertexBuffer hooked. Target: 0x6DBCB4E0
0221/222141 [07FC] IDirect3DDevice8_CreateIndexBuffer hooked. Target: 0x6DBCB550
0221/222141 [07FC] IDirect3DDevice8_CreateVertexShader hooked. Target: 0x6DBED910
0221/222141 [07FC] IDirect3DDevice8_CreatePixelShader hooked. Target: 0x6DBEE470
0221/222141 [07FC] IDirect3DDevice8_SetVertexShader hooked. Target: 0x6DBF2640
0221/222142 [07FC] IDirect3DDevice8_CreateAdditionalSwapChain hooked. Target: 0x6DBC8760
0221/222142 [07FC] Direct3DCreate8(220) return: 0x0323F400
0221/222142 [07FC] IDirect3D8_CreateDevice(0x0323F400 ...) return: 0x00000000
0221/222150 [07FC] D3D8 ripper uninit

0221/222150 [07FC] Loaded Modules List
0221/222150 [07FC] --------------------------------
0221/222150 [07FC] BaseAddr    Size         Module
0221/222150 [07FC] --------------------------------
0221/222150 [07FC] 0x00400000 (0x00AEA000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222150 [07FC] 0x772A0000 (0x0018D000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0221/222150 [07FC] 0x75680000 (0x000D0000)  C:\WINDOWS\System32\KERNEL32.DLL
0221/222150 [07FC] 0x740C0000 (0x001D7000)  C:\WINDOWS\System32\KERNELBASE.dll
0221/222150 [07FC] 0x73BC0000 (0x0009A000)  C:\WINDOWS\SYSTEM32\apphelp.dll
0221/222150 [07FC] 0x74C40000 (0x00175000)  C:\WINDOWS\System32\USER32.dll
0221/222150 [07FC] 0x77220000 (0x00016000)  C:\WINDOWS\System32\win32u.dll
0221/222150 [07FC] 0x754C0000 (0x00022000)  C:\WINDOWS\System32\GDI32.dll
0221/222150 [07FC] 0x76CA0000 (0x0015E000)  C:\WINDOWS\System32\gdi32full.dll
0221/222150 [07FC] 0x74030000 (0x0007C000)  C:\WINDOWS\System32\msvcp_win.dll
0221/222150 [07FC] 0x77000000 (0x00117000)  C:\WINDOWS\System32\ucrtbase.dll
0221/222150 [07FC] 0x754F0000 (0x00078000)  C:\WINDOWS\System32\ADVAPI32.dll
0221/222150 [07FC] 0x75400000 (0x000BD000)  C:\WINDOWS\System32\msvcrt.dll
0221/222150 [07FC] 0x75570000 (0x00043000)  C:\WINDOWS\System32\sechost.dll
0221/222150 [07FC] 0x743C0000 (0x000BE000)  C:\WINDOWS\System32\RPCRT4.dll
0221/222150 [07FC] 0x73CC0000 (0x00020000)  C:\WINDOWS\System32\SspiCli.dll
0221/222150 [07FC] 0x73CB0000 (0x0000A000)  C:\WINDOWS\System32\CRYPTBASE.dll
0221/222150 [07FC] 0x74BD0000 (0x00057000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0221/222150 [07FC] 0x73F30000 (0x000F7000)  C:\WINDOWS\System32\ole32.dll
0221/222150 [07FC] 0x73CE0000 (0x00246000)  C:\WINDOWS\System32\combase.dll
0221/222150 [07FC] 0x737B0000 (0x00024000)  C:\WINDOWS\SYSTEM32\WINMM.dll
0221/222150 [07FC] 0x722A0000 (0x00008000)  C:\WINDOWS\SYSTEM32\WSOCK32.dll
0221/222150 [07FC] 0x74900000 (0x00066000)  C:\WINDOWS\System32\WS2_32.dll
0221/222150 [07FC] 0x73170000 (0x00023000)  C:\WINDOWS\SYSTEM32\WINMMBASE.dll
0221/222150 [07FC] 0x74970000 (0x00038000)  C:\WINDOWS\System32\cfgmgr32.dll
0221/222150 [07FC] 0x74BA0000 (0x00025000)  C:\WINDOWS\System32\IMM32.DLL
0221/222150 [07FC] 0x72A60000 (0x00079000)  C:\WINDOWS\system32\uxtheme.dll
0221/222150 [07FC] 0x75800000 (0x00144000)  C:\WINDOWS\System32\MSCTF.dll
0221/222150 [07FC] 0x75760000 (0x00093000)  C:\WINDOWS\System32\OLEAUT32.dll
0221/222150 [07FC] 0x740B0000 (0x0000E000)  C:\WINDOWS\System32\kernel.appcore.dll
0221/222150 [07FC] 0x72340000 (0x00077000)  C:\WINDOWS\System32\TextInputFramework.dll
0221/222150 [07FC] 0x72210000 (0x0008C000)  C:\WINDOWS\System32\CoreMessaging.dll
0221/222150 [07FC] 0x6FBF0000 (0x00234000)  C:\WINDOWS\System32\CoreUIComponents.dll
0221/222150 [07FC] 0x76E00000 (0x00088000)  C:\WINDOWS\System32\SHCORE.dll
0221/222150 [07FC] 0x72A30000 (0x00028000)  C:\WINDOWS\SYSTEM32\ntmarta.dll
0221/222150 [07FC] 0x6FF30000 (0x000CB000)  C:\WINDOWS\SYSTEM32\wintypes.dll
0221/222150 [07FC] 0x73600000 (0x00023000)  C:\WINDOWS\system32\dwmapi.dll
0221/222150 [07FC] 0x721A0000 (0x00026000)  C:\WINDOWS\SYSTEM32\DINPUT.dll
0221/222150 [07FC] 0x6F010000 (0x00026000)  C:\WINDOWS\SYSTEM32\inputhost.dll
0221/222150 [07FC] 0x6F000000 (0x0000A000)  C:\WINDOWS\SYSTEM32\HID.DLL
0221/222150 [07FC] 0x74480000 (0x00426000)  C:\WINDOWS\System32\SETUPAPI.DLL
0221/222150 [07FC] 0x72E50000 (0x00022000)  C:\WINDOWS\SYSTEM32\DEVOBJ.dll
0221/222150 [07FC] 0x755D0000 (0x00046000)  C:\WINDOWS\System32\WINTRUST.dll
0221/222150 [07FC] 0x74C30000 (0x0000E000)  C:\WINDOWS\System32\MSASN1.dll
0221/222150 [07FC] 0x74A10000 (0x00182000)  C:\WINDOWS\System32\CRYPT32.dll
0221/222150 [07FC] 0x6EF80000 (0x00080000)  C:\WINDOWS\SYSTEM32\DSOUND.dll
0221/222150 [07FC] 0x748B0000 (0x00045000)  C:\WINDOWS\System32\powrprof.dll
0221/222150 [07FC] 0x74330000 (0x00082000)  C:\WINDOWS\System32\clbcatq.dll
0221/222150 [07FC] 0x6EF20000 (0x0005B000)  C:\WINDOWS\System32\MMDevApi.dll
0221/222150 [07FC] 0x6E780000 (0x0017A000)  C:\WINDOWS\System32\PROPSYS.dll
0221/222150 [07FC] 0x6EE20000 (0x000F4000)  C:\WINDOWS\SYSTEM32\AUDIOSES.DLL
0221/222150 [07FC] 0x6EE10000 (0x00008000)  C:\WINDOWS\SYSTEM32\AVRT.dll
0221/222150 [07FC] 0x6EDE0000 (0x00025000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\d3d8.dll
0221/222150 [07FC] 0x6DC60000 (0x000C4000)  C:\Users\a_pap\Downloads\ninja\x86\intruder.dll
0221/222150 [07FC] 0x75960000 (0x01333000)  C:\WINDOWS\System32\SHELL32.dll
0221/222150 [07FC] 0x74E10000 (0x005C6000)  C:\WINDOWS\System32\windows.storage.dll
0221/222150 [07FC] 0x74DC0000 (0x00045000)  C:\WINDOWS\System32\shlwapi.dll
0221/222150 [07FC] 0x753E0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0221/222150 [07FC] 0x723F0000 (0x00181000)  C:\WINDOWS\system32\dbghelp.dll
0221/222150 [07FC] 0x723C0000 (0x00024000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0221/222150 [07FC] 0x6DBA0000 (0x000B6000)  C:\WINDOWS\system32\d3d8.dll
0221/222150 [07FC] 0x6EDD0000 (0x00007000)  C:\WINDOWS\SYSTEM32\d3d8thk.dll
0221/222150 [07FC] 0x6D810000 (0x00386000)  C:\WINDOWS\SYSTEM32\d3dcompiler_47.dll
0221/222150 [07FC] 0x72CD0000 (0x00013000)  C:\WINDOWS\SYSTEM32\CRYPTSP.dll
0221/222150 [07FC] 0x6D600000 (0x00207000)  C:\WINDOWS\SYSTEM32\d3dcompiler_43.dll
0221/222150 [07FC] 0x066E0000 (0x000AF000)  C:\Users\a_pap\Downloads\ninja\x86\d3dx8d.dll
0221/222150 [07FC] 0x6B520000 (0x00ED9000)  C:\WINDOWS\System32\DriverStore\FileRepository\igdlh64.inf_amd64_82119d956c80af5a\igc32.dll
0221/222150 [07FC] 0x75950000 (0x00006000)  C:\WINDOWS\System32\psapi.dll
0221/222150 [07FC] LOG END

```


and 

```
0221/222128 [0A0C] © black_ninja, 2017

0221/222128 [0A0C] LOG START

0221/222128 [0A0C] Executable: C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222128 [0A0C] Output directory: C:\Users\a_pap\Downloads\highway35_10_17_05\_NinjaRipper\2018.02.21_22.21.28_highway35.exe_860\
0221/222128 [0A0C] Win ver: 6.2 x64 

0221/222128 [0A0C] Inject mode: "intruder"
0221/222128 [0A0C] Texture downscale max width : 4096
0221/222128 [0A0C] Texture downscale max height: 4096
0221/222128 [0A0C] Texture downscale value: 2
0221/222128 [0A0C] LdrLoadDll hooked. Target: 0x772EE860
0221/222128 [0A0C] LdrUnloadDll hooked. Target: 0x772EC1E0
0221/222128 [0A0C] CreateProcessA hooked. Target: 0x756944B0
0221/222128 [0A0C] CreateProcessW hooked. Target: 0x75694510
0221/222128 [0A0C] CreateProcessAsUserW hooked. Target: 0x75511210
0221/222129 [0A0C] CreateProcessWithLogonW hooked. Target: 0x75536970
0221/222129 [0A0C] CreateProcessWithTokenW hooked. Target: 0x75501370
0221/222129 [0A0C] SetTokenInformation hooked. Target: 0x75513E50
0221/222129 [0A0C] D3D8.DLL loaded
0221/222129 [0A0C] D3D8 ripper init
0221/222129 [0A0C] Direct3DCreate8 hooked. Target: 0x6DB7BFC0
0221/222129 [0A0C] Direct3DCreate8(220) return: 0x031427A0
0221/222129 [0A0C] IDirect3D8_CreateDevice hooked. Target: 0x6DBB7DB0
0221/222129 [0A0C] IDirect3D8_CreateDevice(0x031427A0 ...) return: 0x00000000
0221/222129 [0A0C] IDirect3DDevice8_SetTexture hooked. Target: 0x6DBBC540
0221/222129 [0A0C] IDirect3DDevice8_Present hooked. Target: 0x6DB992F0
0221/222129 [0A0C] IDirect3DDevice8_DrawPrimitive hooked. Target: 0x6DBBEEE0
0221/222129 [0A0C] IDirect3DDevice8_DrawIndexedPrimitive hooked. Target: 0x6DBBEFF0
0221/222129 [0A0C] IDirect3DDevice8_DrawPrimitiveUP hooked. Target: 0x6DBBF3B0
0221/222129 [0A0C] IDirect3DDevice8_DrawIndexedPrimitiveUP hooked. Target: 0x6DBBF610
0221/222129 [0A0C] IDirect3DDevice8_CreateVertexBuffer hooked. Target: 0x6DB9B4E0
0221/222129 [0A0C] IDirect3DDevice8_CreateIndexBuffer hooked. Target: 0x6DB9B550
0221/222129 [0A0C] IDirect3DDevice8_CreateVertexShader hooked. Target: 0x6DBBD910
0221/222129 [0A0C] IDirect3DDevice8_CreatePixelShader hooked. Target: 0x6DBBE470
0221/222129 [0A0C] IDirect3DDevice8_SetVertexShader hooked. Target: 0x6DBC2640
0221/222129 [0A0C] IDirect3DDevice8_CreateAdditionalSwapChain hooked. Target: 0x6DB98760
0221/222129 [0A0C] Direct3DCreate8(220) return: 0x031544C0
0221/222129 [0A0C] IDirect3D8_CreateDevice(0x031544C0 ...) return: 0x00000000
0221/222137 [0A0C] D3D8 ripper uninit

0221/222137 [0A0C] Loaded Modules List
0221/222137 [0A0C] --------------------------------
0221/222137 [0A0C] BaseAddr    Size         Module
0221/222137 [0A0C] --------------------------------
0221/222137 [0A0C] 0x00400000 (0x00AEA000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222137 [0A0C] 0x772A0000 (0x0018D000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0221/222137 [0A0C] 0x75680000 (0x000D0000)  C:\WINDOWS\System32\KERNEL32.DLL
0221/222137 [0A0C] 0x740C0000 (0x001D7000)  C:\WINDOWS\System32\KERNELBASE.dll
0221/222137 [0A0C] 0x73BC0000 (0x0009A000)  C:\WINDOWS\SYSTEM32\apphelp.dll
0221/222137 [0A0C] 0x74C40000 (0x00175000)  C:\WINDOWS\System32\USER32.dll
0221/222137 [0A0C] 0x77220000 (0x00016000)  C:\WINDOWS\System32\win32u.dll
0221/222137 [0A0C] 0x754C0000 (0x00022000)  C:\WINDOWS\System32\GDI32.dll
0221/222137 [0A0C] 0x76CA0000 (0x0015E000)  C:\WINDOWS\System32\gdi32full.dll
0221/222137 [0A0C] 0x74030000 (0x0007C000)  C:\WINDOWS\System32\msvcp_win.dll
0221/222137 [0A0C] 0x77000000 (0x00117000)  C:\WINDOWS\System32\ucrtbase.dll
0221/222137 [0A0C] 0x754F0000 (0x00078000)  C:\WINDOWS\System32\ADVAPI32.dll
0221/222137 [0A0C] 0x75400000 (0x000BD000)  C:\WINDOWS\System32\msvcrt.dll
0221/222137 [0A0C] 0x75570000 (0x00043000)  C:\WINDOWS\System32\sechost.dll
0221/222137 [0A0C] 0x743C0000 (0x000BE000)  C:\WINDOWS\System32\RPCRT4.dll
0221/222137 [0A0C] 0x73CC0000 (0x00020000)  C:\WINDOWS\System32\SspiCli.dll
0221/222137 [0A0C] 0x73CB0000 (0x0000A000)  C:\WINDOWS\System32\CRYPTBASE.dll
0221/222137 [0A0C] 0x74BD0000 (0x00057000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0221/222137 [0A0C] 0x73F30000 (0x000F7000)  C:\WINDOWS\System32\ole32.dll
0221/222137 [0A0C] 0x73CE0000 (0x00246000)  C:\WINDOWS\System32\combase.dll
0221/222137 [0A0C] 0x737B0000 (0x00024000)  C:\WINDOWS\SYSTEM32\WINMM.dll
0221/222137 [0A0C] 0x722A0000 (0x00008000)  C:\WINDOWS\SYSTEM32\WSOCK32.dll
0221/222137 [0A0C] 0x74900000 (0x00066000)  C:\WINDOWS\System32\WS2_32.dll
0221/222137 [0A0C] 0x73170000 (0x00023000)  C:\WINDOWS\SYSTEM32\winmmbase.dll
0221/222137 [0A0C] 0x74970000 (0x00038000)  C:\WINDOWS\System32\cfgmgr32.dll
0221/222137 [0A0C] 0x74BA0000 (0x00025000)  C:\WINDOWS\System32\IMM32.DLL
0221/222137 [0A0C] 0x6EF70000 (0x000C4000)  C:\Users\a_pap\Downloads\ninja\x86\intruder.dll
0221/222137 [0A0C] 0x75960000 (0x01333000)  C:\WINDOWS\System32\SHELL32.dll
0221/222137 [0A0C] 0x76E00000 (0x00088000)  C:\WINDOWS\System32\shcore.dll
0221/222137 [0A0C] 0x74E10000 (0x005C6000)  C:\WINDOWS\System32\windows.storage.dll
0221/222137 [0A0C] 0x74DC0000 (0x00045000)  C:\WINDOWS\System32\shlwapi.dll
0221/222137 [0A0C] 0x740B0000 (0x0000E000)  C:\WINDOWS\System32\kernel.appcore.dll
0221/222137 [0A0C] 0x748B0000 (0x00045000)  C:\WINDOWS\System32\powrprof.dll
0221/222137 [0A0C] 0x753E0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0221/222137 [0A0C] 0x723F0000 (0x00181000)  C:\WINDOWS\system32\dbghelp.dll
0221/222137 [0A0C] 0x723C0000 (0x00024000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0221/222137 [0A0C] 0x72A60000 (0x00079000)  C:\WINDOWS\system32\uxtheme.dll
0221/222137 [0A0C] 0x75800000 (0x00144000)  C:\WINDOWS\System32\MSCTF.dll
0221/222137 [0A0C] 0x75760000 (0x00093000)  C:\WINDOWS\System32\OLEAUT32.dll
0221/222137 [0A0C] 0x72340000 (0x00077000)  C:\WINDOWS\System32\TextInputFramework.dll
0221/222137 [0A0C] 0x6FBF0000 (0x00234000)  C:\WINDOWS\System32\CoreUIComponents.dll
0221/222137 [0A0C] 0x72210000 (0x0008C000)  C:\WINDOWS\System32\CoreMessaging.dll
0221/222137 [0A0C] 0x72A30000 (0x00028000)  C:\WINDOWS\SYSTEM32\ntmarta.dll
0221/222137 [0A0C] 0x6FF30000 (0x000CB000)  C:\WINDOWS\SYSTEM32\wintypes.dll
0221/222137 [0A0C] 0x73600000 (0x00023000)  C:\WINDOWS\system32\dwmapi.dll
0221/222137 [0A0C] 0x721A0000 (0x00026000)  C:\WINDOWS\SYSTEM32\DINPUT.dll
0221/222137 [0A0C] 0x6EF40000 (0x00026000)  C:\WINDOWS\SYSTEM32\inputhost.dll
0221/222137 [0A0C] 0x6EF30000 (0x0000A000)  C:\WINDOWS\SYSTEM32\HID.DLL
0221/222137 [0A0C] 0x74480000 (0x00426000)  C:\WINDOWS\System32\SETUPAPI.DLL
0221/222137 [0A0C] 0x72E50000 (0x00022000)  C:\WINDOWS\SYSTEM32\DEVOBJ.dll
0221/222137 [0A0C] 0x755D0000 (0x00046000)  C:\WINDOWS\System32\WINTRUST.dll
0221/222137 [0A0C] 0x74C30000 (0x0000E000)  C:\WINDOWS\System32\MSASN1.dll
0221/222137 [0A0C] 0x74A10000 (0x00182000)  C:\WINDOWS\System32\CRYPT32.dll
0221/222137 [0A0C] 0x6EEB0000 (0x00080000)  C:\WINDOWS\SYSTEM32\DSOUND.dll
0221/222137 [0A0C] 0x74330000 (0x00082000)  C:\WINDOWS\System32\clbcatq.dll
0221/222137 [0A0C] 0x6EE50000 (0x0005B000)  C:\WINDOWS\System32\MMDevApi.dll
0221/222137 [0A0C] 0x6E780000 (0x0017A000)  C:\WINDOWS\System32\PROPSYS.dll
0221/222137 [0A0C] 0x6DC30000 (0x000F4000)  C:\WINDOWS\SYSTEM32\AUDIOSES.DLL
0221/222137 [0A0C] 0x6EE40000 (0x00008000)  C:\WINDOWS\SYSTEM32\AVRT.dll
0221/222137 [0A0C] 0x6DB70000 (0x000B6000)  C:\WINDOWS\SYSTEM32\d3d8.dll
0221/222137 [0A0C] 0x6EE30000 (0x00007000)  C:\WINDOWS\SYSTEM32\d3d8thk.dll
0221/222137 [0A0C] 0x6D7E0000 (0x00386000)  C:\WINDOWS\SYSTEM32\d3dcompiler_47.dll
0221/222137 [0A0C] 0x72CD0000 (0x00013000)  C:\WINDOWS\SYSTEM32\CRYPTSP.dll
0221/222137 [0A0C] 0x6D5D0000 (0x00207000)  C:\WINDOWS\SYSTEM32\d3dcompiler_43.dll
0221/222137 [0A0C] 0x06640000 (0x000AF000)  C:\Users\a_pap\Downloads\ninja\x86\d3dx8d.dll
0221/222137 [0A0C] 0x6B520000 (0x00ED9000)  C:\WINDOWS\System32\DriverStore\FileRepository\igdlh64.inf_amd64_82119d956c80af5a\igc32.dll
0221/222137 [0A0C] 0x75950000 (0x00006000)  C:\WINDOWS\System32\psapi.dll
0221/222137 [0A0C] LOG END

```


My OS is windows 10.
Let me know if you have any ideas. Finally, I know that it is possible to rip the models using NR because somebody has already done that...They told me they used Win Xp though. Could that play a role?
## Post #617
- Username: Gepejantes
- Rank: beginner
- Number of posts: 38
- Joined date: Wed May 31, 2017 11:43 pm
- Post datetime: 2018-03-01T18:22:29+00:00
- Post Title: Re: Ninja Ripper

> Reply from redmoone
>
> Hey Guys, so I've been trying to rip Heroforge.com , which works very well. Now the have some very nice poses there but when i rip it i get char in T-Pose,
Is there a way to get the pose displayed? I know i can rig the character which works but takes a lot of time, i would love to just capture the pose!
 anyone resolve the T-pose problem from heroforge?
## Post #618
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2018-03-20T14:19:08+00:00
- Post Title: Re: Ninja Ripper

Warhammer Vermintide require to be lunched by Steam.... or via Launcher, Any advice?  

> Reply from BL4CK0UT
>
> Can you guys help me out opening a .RAW File?
a RAW file can be a picture, usually it is used to as HeightMap for the terrain, and define the higher and lower area.

You could use Photoshop or IrfanView but you MUST know the exactly size of the picture, which usually it's a square, multiplied by 8 +1 (for example 1024+1 = 1025x1025)
## Post #619
- Username: Gepejantes
- Rank: beginner
- Number of posts: 38
- Joined date: Wed May 31, 2017 11:43 pm
- Post datetime: 2018-03-22T02:34:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> Hi. Im author of NinjaRipper

Here beta version 1.1.2 with fixed "purple" textures in Dx11 and gamma in Dx9

http://blackninja2000.narod.ru/files/ninjaripper112.7z
could you please fix the T-pose problem ripping from heroforge.com?
## Post #620
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2018-03-24T07:37:00+00:00
- Post Title: Re: Ninja Ripper

It happens to me too everytime with Settlers 7.
you have to use the import plugin to displace the meshes around your X and Y coords.
## Post #621
- Username: leadron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 24, 2018 12:37 pm
- Post datetime: 2018-03-24T10:12:06+00:00
- Post Title: Re: Ninja Ripper

> Reply from MaximilianPs
>
> It happens to me too everytime with Settlers 7.
you have to use the import plugin to displace the meshes around your X and Y coords.
I have tried to open those *.rip files on NoeSis, but it looks the same as in 3DSMax,
i think the problem is not on import process, that is on ripping process (?)
or that site has a rip protection system (?) -- i'm not sure, any other idea?
## Post #622
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2018-03-24T13:51:57+00:00
- Post Title: Re: Ninja Ripper

yes it's in the rip, you have to arrange by your self.
## Post #623
- Username: leadron
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 24, 2018 12:37 pm
- Post datetime: 2018-03-24T16:12:41+00:00
- Post Title: Re: Ninja Ripper

its a big deal to rearrange 20k vertices and since the *.rip files are written in binary format.. its hard to interpret
and finally it means the same as making your own model.

I hope @blackninja can add an option to write it in ASCII like obj or maybe waiting for someone to make a converter

but if someone can give me tips & tricks to solve this problem, I would be very grateful
## Post #624
- Username: Angus94
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 14, 2017 10:04 am
- Post datetime: 2018-04-05T14:08:43+00:00
- Post Title: Re: Ninja Ripper

can anyone shed any light as to why this object came out like this yet the remaining parts are fine
[2018-04-05_22-46-13.jpg](https://xentaxbackup.github.io/file/14169_2018-04-05_22-46-13.jpg)
## Post #625
- Username: emadtvk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 10, 2014 4:21 pm
- Post datetime: 2018-04-19T11:35:59+00:00
- Post Title: Re: Ninja Ripper

I wanna rip some textures from a game called "Rules Of Survival"

It's a d3d9 based game, I tried all methods but as I click enter the game, game will crash. help please
## Post #626
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-05-26T17:18:55+00:00
- Post Title: Re: Ninja Ripper

Can anybody please tell me, why the ripped meshes are seems round shaped. Every file is same type sphered mesh.
Seems all the vertex positions are captured incorrectly.
[ninjaripProblem1.JPG](https://xentaxbackup.github.io/file/14398_ninjaripProblem1.JPG)
## Post #627
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-05-30T15:58:38+00:00
- Post Title: Re: Ninja Ripper

> Reply from Angus94
>
> can anyone shed any light as to why this object came out like this yet the remaining parts are fine

Hey buddy, did you found any solution?
## Post #628
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2018-06-01T12:14:44+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackfoxeye
>
> Angus94 wrote:can anyone shed any light as to why this object came out like this yet the remaining parts are fine

Hey buddy, did you found any solution?

the vertices are modified by the shader. The ripper retrieves the data before the shader
## Post #629
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-06-01T15:31:28+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> blackfoxeye wrote:Angus94 wrote:can anyone shed any light as to why this object came out like this yet the remaining parts are fine

Hey buddy, did you found any solution?

the vertices are modified by the shader. The ripper retrieves the data before the shader

Thanks for your reply, which puts light on the problem. And now I can understand what is the problem.

So is there any way to rip the model after the shader modified the vertices?
## Post #630
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2018-06-02T19:47:52+00:00
- Post Title: Re: Ninja Ripper

> So is there any way to rip the model after the shader modified the vertices?

in the current version of the utility can not be done
## Post #631
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-06-03T04:47:48+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> 
So is there any way to rip the model after the shader modified the vertices?

in the current version of the utility can not be done

Thank you very much for your kind reply.
Eagerly waiting for this feature in future release.

You have made an excellent tool, best tool in the world. hats off to you.
## Post #632
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2018-06-04T06:51:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackfoxeye
>
> blackninja wrote:
So is there any way to rip the model after the shader modified the vertices?

in the current version of the utility can not be done

Thank you very much for your kind reply.
Eagerly waiting for this feature in future release.

You have made an excellent tool, best tool in the world. hats off to you.

The new version of the utility is not so soon
## Post #633
- Username: blackfoxeye
- Rank: veteran
- Number of posts: 110
- Joined date: Tue Mar 08, 2011 7:03 pm
- Post datetime: 2018-06-04T07:02:08+00:00
- Post Title: Re: Ninja Ripper

> Reply from blackninja
>
> 
The new version of the utility is not so soon
As you wish God of Ripper. Thank you very much.
Waiting time may be long but that day will be great.
## Post #634
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-14T16:22:30+00:00
- Post Title: Re: Ninja Ripper

HEY GUYS

I recently posted to the CGSociety forums to find a solution to Ninja Ripper's infamous Normals issue.
I'm very happy to say that NOT ONLY did I find a solution, BUT this solution also works for 3D Ripper DX or other models with messed up normals.

1. Export to .OBJ
2. Import from .OBJ
3. Uncheck normals from file on import (use auto)
4. Use Editable Mesh > Element (subobject) > Unify

This is the 3DS Max method, I'm sure there's a comparable method for blender or maya but I'm not familiar enough to know the steps.

CAN WE PLEASE have this knowledge spread around, stickied, put in the OP, whatever it takes? Because up until this point, every Ninja Ripper tutorial on Youtube or otherwise always used the Flip Normals Mode to fix the normals, and that takes hours.
## Post #635
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-15T05:30:57+00:00
- Post Title: Re: Ninja Ripper

I need help with a program that crashes when Ninja Ripper Intruder is used.
It's actually not a game, but a model viewer which unpacks and renders the models from game archives...

Here's the log file.

```
0615/012925 [2F38] © 2004-2016 black_ninja

0615/012925 [2F38] LOG START

0615/012925 [2F38] Inject mode: "intruder"
0615/012925 [2F38] Texture downscale max width : 4096
0615/012925 [2F38] Texture downscale max height: 4096
0615/012925 [2F38] Texture downscale value: 2
0615/012925 [2F38] Forced dll load mode enabled

0615/012925 [2F38] LdrLoadDll hooked. Target: 0x00007FFFCC24A650
0615/012925 [2F38] LdrUnloadDll hooked. Target: 0x00007FFFCC24F800
0615/012925 [2F38] DXGI.DLL loaded
0615/012925 [2F38] DXGI init
0615/012925 [2F38] CreateDXGIFactory hooked. Target: 0x00007FFFC72E9DE0
0615/012925 [2F38] CreateDXGIFactory1 hooked. Target: 0x00007FFFC72EA200
0615/012925 [2F38] D3D11.DLL loaded
0615/012925 [2F38] D3D11 ripper init
0615/012925 [2F38] D3D11CreateDeviceAndSwapChain hooked. Target: 0x00007FFFC57E5950
0615/012925 [2F38] D3D11CreateDevice hooked. Target: 0x00007FFFC57E5800
0615/012925 [2F38] D3D9.DLL loaded
0615/012925 [2F38] D3D9 ripper init
0615/012925 [2F38] Direct3DCreate9 hooked. Target: 0x00007FFF9FD814B0
0615/012925 [2F38] Direct3DCreate9Ex hooked. Target: 0x00007FFF9FD814E0
0615/012925 [2F38] DDRAW.DLL loaded
0615/012925 [2F38] DDRAW init
0615/012925 [2F38] DirectDrawCreateEx hooked. Target: 0x00007FFF9F3E3680
0615/012925 [2F38] DirectDrawCreate hooked. Target: 0x00007FFF9F3B2900
0615/012925 [2F38] CreateProcessA hooked. Target: 0x00007FFFCC0197E0
0615/012925 [2F38] CreateProcessW hooked. Target: 0x00007FFFCC01A0B0
0615/012925 [2F38] CreateProcessAsUserW hooked. Target: 0x00007FFFCBF035C0
0615/012925 [2F38] CreateProcessWithLogonW hooked. Target: 0x00007FFFCBF2DF00
0615/012925 [2F38] CreateProcessWithTokenW hooked. Target: 0x00007FFFCBEF1E80
0615/012925 [1BFC] Direct3DCreate9Ex(32) return: 0x00000000
0615/012925 [1BFC] IDirect3D9Ex_CreateDevice hooked. Target: 0x00007FFF9FD64C10
0615/012925 [1BFC] IDirect3D9Ex_CreateDeviceEx hooked. Target: 0x00007FFF9FD65B50
0615/012925 [1BFC] IDirect3D9Ex_CreateDeviceEx(0x000000001B9EAF40, ...) return: 0x00000000

```


What happens is the program doesn't start successfully. I suspect that Ninja Ripper somehow interferes with the program, and the program performs some checks on startup, and fails because of Ninja Ripper, and then aborts. It doesn't seem to be Ninja Ripper crashing, but Ninja ripper causing the program to crash.

I tried using DDRAW, DX8, 9, and 11.
It seems Ninja Ripper failed to intrude when using DDRAW, 8, and 11. (no folder is created, no rips are taken)
When using DX9, the results were the same as intruder (crash).

It also crashes when started with 3D Ripper DX, which is really annoying...
## Post #636
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-06-15T07:43:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from ItchyDani3l
>
> I need help with a program that crashes when Ninja Ripper Intruder is used.
Code: Select all0615/012925 [2F38] Ninja Ripper 1.5.2 x64
Try the latest version - [1.7.1 x64](http://cgig.ru/ninjaripper/), don't forget to delete old dll's from intruder.
Try without intruder, then with.
Some software have protection, there's nothing you can do.
## Post #637
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-15T14:51:32+00:00
- Post Title: Re: Ninja Ripper

Thanks for the new link. Didn't know it existed.

When I try with Injector 1.7.1, I get this message:

```
ERROR: APC injection failed. Err: 0x%08X. Win32 error: 0x00000006
```


I'm going to give it a shot with the different wrappers...

Right, so I did a comprehensive check of all of the wrappers, here's the results:

```
1.7.1 x32 DX11			No Folder, No rips (No crash)
1.7.1 x32 DX9			No Folder, No rips (No crash)
1.7.1 x32 DX8			No Folder, No rips (No crash)
1.7.1 x32 DDRAW			No Folder, No rips (No crash)

1.7.1 x64 Injector		Error Code (see log)
1.7.1 x64 DX11			No Folder, No rips (No crash)
1.7.1 x64 DX9			No Folder, No rips (No crash)
1.7.1 x64 DX8			No Folder, No rips (No crash)
1.7.1 x64 DDRAW			No Folder, No rips (No crash)
```


So 1.7.1 will not crash the application on launch, but it will not create the Rip folder or create any rip files.
Yes, I delete the .dll files after each wrapper, I've been using Ninja ripper for a while.

Also, something I noticed, version 1.5.2 will tell me that the target application is 64 bit when I try to run it with the x32 Ninja Ripper, but the same is not true for version 1.7.1

Also, I went back to 1.5.2 to confirm the results I got last night, but now it has changed.
Originally, when I ran Ninja Ripper x64 with Directx9 on the application, it would successfully create the .Rip folder on startup, but then crash immediately.
Now, when I try the same thing with 1.5.2 x64 Directx9, it now says "Can't load ddraw.dll" and doesn't create a folder...

Also, I really don't think this software has some kind of protection, because this is a fan-made model viewer which just unpacks models from archives for a specific game.
## Post #638
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-06-15T22:34:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from ItchyDani3l
>
> Also, I really don't think this software has some kind of protection, because this is a fan-made model viewer which just unpacks models from archives for a specific game.
Some of them have protection, OpenIV for example.
And very often OpenGL is used for output, NR can't deal with it.
For OpenGL you can try [3DVIA Printscreen](http://forum.xentax.com/viewtopic.php?f=16&t=9463) and [importer to max](http://forum.xentax.com/viewtopic.php?p=27425) (check the last posts for both topics).
## Post #639
- Username: ItchyDani3l
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 29, 2016 3:20 pm
- Post datetime: 2018-06-21T03:30:53+00:00
- Post Title: Re: Ninja Ripper

3D Via Printscreen doesn't work very well on my Windows10 machine. Not reliable, and results are pathetic.
I'll give it another shot, but it rarely worked for me.

Anyone know correct settings for Windows 10?

I'm wondering if that's really an issue, can they tell me for sure by looking at the log I posted?
## Post #640
- Username: chuckskull
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jul 13, 2018 10:45 am
- Post datetime: 2018-07-13T02:50:06+00:00
- Post Title: Re: Ninja Ripper

Hello every1. Do i Just type my question here or create new topic about extracting etc with Ninjaripper. Need ask many who knows well in 3dsmax and/or unity
## Post #641
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2018-08-18T20:19:50+00:00
- Post Title: Re: Ninja Ripper

> Reply from thorh62
>
> Hello, I was wondering if anyone could help me figure out how to rip the 3d models of a racing game called "planet hot wheels"  using Ninja Ripper

I downloaded the latest version of NR, then ran the x86 version of NR as administrator
I followed the steps in the manual and the game launches successfully when I press "run"
but when I press the shortcut for ripping in the car selection menu, nothing happens
these are the logs when I tried the intruder and dx8 wrapper methods
Code: Select all0221/222141 [07FC] Ninja Ripper 1.7.1 x86
0221/222141 [07FC] © black_ninja, 2017

0221/222141 [07FC] LOG START

0221/222141 [07FC] Executable: C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222141 [07FC] Output directory: C:\Users\a_pap\Downloads\highway35_10_17_05\_NinjaRipper\2018.02.21_22.21.41_highway35.exe_11880\
0221/222141 [07FC] Win ver: 6.2 x64 

0221/222141 [07FC] Inject mode: "d3d8.dll wrapper"
0221/222141 [07FC] Texture downscale max width : 4096
0221/222141 [07FC] Texture downscale max height: 4096
0221/222141 [07FC] Texture downscale value: 2
0221/222141 [07FC] LdrLoadDll hooked. Target: 0x772EE860
0221/222141 [07FC] LdrUnloadDll hooked. Target: 0x772EC1E0
0221/222141 [07FC] CreateProcessA hooked. Target: 0x756944B0
0221/222141 [07FC] CreateProcessW hooked. Target: 0x75694510
0221/222141 [07FC] CreateProcessAsUserW hooked. Target: 0x75511210
0221/222141 [07FC] CreateProcessWithLogonW hooked. Target: 0x75536970
0221/222141 [07FC] CreateProcessWithTokenW hooked. Target: 0x75501370
0221/222141 [07FC] SetTokenInformation hooked. Target: 0x75513E50
0221/222141 [07FC] D3D8.DLL loaded
0221/222141 [07FC] D3D8 ripper init
0221/222141 [07FC] Direct3DCreate8 hooked. Target: 0x6DBABFC0
0221/222141 [07FC] Direct3DCreate8(220) return: 0x031FC680
0221/222141 [07FC] IDirect3D8_CreateDevice hooked. Target: 0x6DBE7DB0
0221/222141 [07FC] IDirect3D8_CreateDevice(0x031FC680 ...) return: 0x00000000
0221/222141 [07FC] IDirect3DDevice8_SetTexture hooked. Target: 0x6DBEC540
0221/222141 [07FC] IDirect3DDevice8_Present hooked. Target: 0x6DBC92F0
0221/222141 [07FC] IDirect3DDevice8_DrawPrimitive hooked. Target: 0x6DBEEEE0
0221/222141 [07FC] IDirect3DDevice8_DrawIndexedPrimitive hooked. Target: 0x6DBEEFF0
0221/222141 [07FC] IDirect3DDevice8_DrawPrimitiveUP hooked. Target: 0x6DBEF3B0
0221/222141 [07FC] IDirect3DDevice8_DrawIndexedPrimitiveUP hooked. Target: 0x6DBEF610
0221/222141 [07FC] IDirect3DDevice8_CreateVertexBuffer hooked. Target: 0x6DBCB4E0
0221/222141 [07FC] IDirect3DDevice8_CreateIndexBuffer hooked. Target: 0x6DBCB550
0221/222141 [07FC] IDirect3DDevice8_CreateVertexShader hooked. Target: 0x6DBED910
0221/222141 [07FC] IDirect3DDevice8_CreatePixelShader hooked. Target: 0x6DBEE470
0221/222141 [07FC] IDirect3DDevice8_SetVertexShader hooked. Target: 0x6DBF2640
0221/222142 [07FC] IDirect3DDevice8_CreateAdditionalSwapChain hooked. Target: 0x6DBC8760
0221/222142 [07FC] Direct3DCreate8(220) return: 0x0323F400
0221/222142 [07FC] IDirect3D8_CreateDevice(0x0323F400 ...) return: 0x00000000
0221/222150 [07FC] D3D8 ripper uninit

0221/222150 [07FC] Loaded Modules List
0221/222150 [07FC] --------------------------------
0221/222150 [07FC] BaseAddr    Size         Module
0221/222150 [07FC] --------------------------------
0221/222150 [07FC] 0x00400000 (0x00AEA000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222150 [07FC] 0x772A0000 (0x0018D000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0221/222150 [07FC] 0x75680000 (0x000D0000)  C:\WINDOWS\System32\KERNEL32.DLL
0221/222150 [07FC] 0x740C0000 (0x001D7000)  C:\WINDOWS\System32\KERNELBASE.dll
0221/222150 [07FC] 0x73BC0000 (0x0009A000)  C:\WINDOWS\SYSTEM32\apphelp.dll
0221/222150 [07FC] 0x74C40000 (0x00175000)  C:\WINDOWS\System32\USER32.dll
0221/222150 [07FC] 0x77220000 (0x00016000)  C:\WINDOWS\System32\win32u.dll
0221/222150 [07FC] 0x754C0000 (0x00022000)  C:\WINDOWS\System32\GDI32.dll
0221/222150 [07FC] 0x76CA0000 (0x0015E000)  C:\WINDOWS\System32\gdi32full.dll
0221/222150 [07FC] 0x74030000 (0x0007C000)  C:\WINDOWS\System32\msvcp_win.dll
0221/222150 [07FC] 0x77000000 (0x00117000)  C:\WINDOWS\System32\ucrtbase.dll
0221/222150 [07FC] 0x754F0000 (0x00078000)  C:\WINDOWS\System32\ADVAPI32.dll
0221/222150 [07FC] 0x75400000 (0x000BD000)  C:\WINDOWS\System32\msvcrt.dll
0221/222150 [07FC] 0x75570000 (0x00043000)  C:\WINDOWS\System32\sechost.dll
0221/222150 [07FC] 0x743C0000 (0x000BE000)  C:\WINDOWS\System32\RPCRT4.dll
0221/222150 [07FC] 0x73CC0000 (0x00020000)  C:\WINDOWS\System32\SspiCli.dll
0221/222150 [07FC] 0x73CB0000 (0x0000A000)  C:\WINDOWS\System32\CRYPTBASE.dll
0221/222150 [07FC] 0x74BD0000 (0x00057000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0221/222150 [07FC] 0x73F30000 (0x000F7000)  C:\WINDOWS\System32\ole32.dll
0221/222150 [07FC] 0x73CE0000 (0x00246000)  C:\WINDOWS\System32\combase.dll
0221/222150 [07FC] 0x737B0000 (0x00024000)  C:\WINDOWS\SYSTEM32\WINMM.dll
0221/222150 [07FC] 0x722A0000 (0x00008000)  C:\WINDOWS\SYSTEM32\WSOCK32.dll
0221/222150 [07FC] 0x74900000 (0x00066000)  C:\WINDOWS\System32\WS2_32.dll
0221/222150 [07FC] 0x73170000 (0x00023000)  C:\WINDOWS\SYSTEM32\WINMMBASE.dll
0221/222150 [07FC] 0x74970000 (0x00038000)  C:\WINDOWS\System32\cfgmgr32.dll
0221/222150 [07FC] 0x74BA0000 (0x00025000)  C:\WINDOWS\System32\IMM32.DLL
0221/222150 [07FC] 0x72A60000 (0x00079000)  C:\WINDOWS\system32\uxtheme.dll
0221/222150 [07FC] 0x75800000 (0x00144000)  C:\WINDOWS\System32\MSCTF.dll
0221/222150 [07FC] 0x75760000 (0x00093000)  C:\WINDOWS\System32\OLEAUT32.dll
0221/222150 [07FC] 0x740B0000 (0x0000E000)  C:\WINDOWS\System32\kernel.appcore.dll
0221/222150 [07FC] 0x72340000 (0x00077000)  C:\WINDOWS\System32\TextInputFramework.dll
0221/222150 [07FC] 0x72210000 (0x0008C000)  C:\WINDOWS\System32\CoreMessaging.dll
0221/222150 [07FC] 0x6FBF0000 (0x00234000)  C:\WINDOWS\System32\CoreUIComponents.dll
0221/222150 [07FC] 0x76E00000 (0x00088000)  C:\WINDOWS\System32\SHCORE.dll
0221/222150 [07FC] 0x72A30000 (0x00028000)  C:\WINDOWS\SYSTEM32\ntmarta.dll
0221/222150 [07FC] 0x6FF30000 (0x000CB000)  C:\WINDOWS\SYSTEM32\wintypes.dll
0221/222150 [07FC] 0x73600000 (0x00023000)  C:\WINDOWS\system32\dwmapi.dll
0221/222150 [07FC] 0x721A0000 (0x00026000)  C:\WINDOWS\SYSTEM32\DINPUT.dll
0221/222150 [07FC] 0x6F010000 (0x00026000)  C:\WINDOWS\SYSTEM32\inputhost.dll
0221/222150 [07FC] 0x6F000000 (0x0000A000)  C:\WINDOWS\SYSTEM32\HID.DLL
0221/222150 [07FC] 0x74480000 (0x00426000)  C:\WINDOWS\System32\SETUPAPI.DLL
0221/222150 [07FC] 0x72E50000 (0x00022000)  C:\WINDOWS\SYSTEM32\DEVOBJ.dll
0221/222150 [07FC] 0x755D0000 (0x00046000)  C:\WINDOWS\System32\WINTRUST.dll
0221/222150 [07FC] 0x74C30000 (0x0000E000)  C:\WINDOWS\System32\MSASN1.dll
0221/222150 [07FC] 0x74A10000 (0x00182000)  C:\WINDOWS\System32\CRYPT32.dll
0221/222150 [07FC] 0x6EF80000 (0x00080000)  C:\WINDOWS\SYSTEM32\DSOUND.dll
0221/222150 [07FC] 0x748B0000 (0x00045000)  C:\WINDOWS\System32\powrprof.dll
0221/222150 [07FC] 0x74330000 (0x00082000)  C:\WINDOWS\System32\clbcatq.dll
0221/222150 [07FC] 0x6EF20000 (0x0005B000)  C:\WINDOWS\System32\MMDevApi.dll
0221/222150 [07FC] 0x6E780000 (0x0017A000)  C:\WINDOWS\System32\PROPSYS.dll
0221/222150 [07FC] 0x6EE20000 (0x000F4000)  C:\WINDOWS\SYSTEM32\AUDIOSES.DLL
0221/222150 [07FC] 0x6EE10000 (0x00008000)  C:\WINDOWS\SYSTEM32\AVRT.dll
0221/222150 [07FC] 0x6EDE0000 (0x00025000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\d3d8.dll
0221/222150 [07FC] 0x6DC60000 (0x000C4000)  C:\Users\a_pap\Downloads\ninja\x86\intruder.dll
0221/222150 [07FC] 0x75960000 (0x01333000)  C:\WINDOWS\System32\SHELL32.dll
0221/222150 [07FC] 0x74E10000 (0x005C6000)  C:\WINDOWS\System32\windows.storage.dll
0221/222150 [07FC] 0x74DC0000 (0x00045000)  C:\WINDOWS\System32\shlwapi.dll
0221/222150 [07FC] 0x753E0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0221/222150 [07FC] 0x723F0000 (0x00181000)  C:\WINDOWS\system32\dbghelp.dll
0221/222150 [07FC] 0x723C0000 (0x00024000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0221/222150 [07FC] 0x6DBA0000 (0x000B6000)  C:\WINDOWS\system32\d3d8.dll
0221/222150 [07FC] 0x6EDD0000 (0x00007000)  C:\WINDOWS\SYSTEM32\d3d8thk.dll
0221/222150 [07FC] 0x6D810000 (0x00386000)  C:\WINDOWS\SYSTEM32\d3dcompiler_47.dll
0221/222150 [07FC] 0x72CD0000 (0x00013000)  C:\WINDOWS\SYSTEM32\CRYPTSP.dll
0221/222150 [07FC] 0x6D600000 (0x00207000)  C:\WINDOWS\SYSTEM32\d3dcompiler_43.dll
0221/222150 [07FC] 0x066E0000 (0x000AF000)  C:\Users\a_pap\Downloads\ninja\x86\d3dx8d.dll
0221/222150 [07FC] 0x6B520000 (0x00ED9000)  C:\WINDOWS\System32\DriverStore\FileRepository\igdlh64.inf_amd64_82119d956c80af5a\igc32.dll
0221/222150 [07FC] 0x75950000 (0x00006000)  C:\WINDOWS\System32\psapi.dll
0221/222150 [07FC] LOG END


and 
Code: Select all0221/222128 [0A0C] Ninja Ripper 1.7.1 x86
0221/222128 [0A0C] © black_ninja, 2017

0221/222128 [0A0C] LOG START

0221/222128 [0A0C] Executable: C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222128 [0A0C] Output directory: C:\Users\a_pap\Downloads\highway35_10_17_05\_NinjaRipper\2018.02.21_22.21.28_highway35.exe_860\
0221/222128 [0A0C] Win ver: 6.2 x64 

0221/222128 [0A0C] Inject mode: "intruder"
0221/222128 [0A0C] Texture downscale max width : 4096
0221/222128 [0A0C] Texture downscale max height: 4096
0221/222128 [0A0C] Texture downscale value: 2
0221/222128 [0A0C] LdrLoadDll hooked. Target: 0x772EE860
0221/222128 [0A0C] LdrUnloadDll hooked. Target: 0x772EC1E0
0221/222128 [0A0C] CreateProcessA hooked. Target: 0x756944B0
0221/222128 [0A0C] CreateProcessW hooked. Target: 0x75694510
0221/222128 [0A0C] CreateProcessAsUserW hooked. Target: 0x75511210
0221/222129 [0A0C] CreateProcessWithLogonW hooked. Target: 0x75536970
0221/222129 [0A0C] CreateProcessWithTokenW hooked. Target: 0x75501370
0221/222129 [0A0C] SetTokenInformation hooked. Target: 0x75513E50
0221/222129 [0A0C] D3D8.DLL loaded
0221/222129 [0A0C] D3D8 ripper init
0221/222129 [0A0C] Direct3DCreate8 hooked. Target: 0x6DB7BFC0
0221/222129 [0A0C] Direct3DCreate8(220) return: 0x031427A0
0221/222129 [0A0C] IDirect3D8_CreateDevice hooked. Target: 0x6DBB7DB0
0221/222129 [0A0C] IDirect3D8_CreateDevice(0x031427A0 ...) return: 0x00000000
0221/222129 [0A0C] IDirect3DDevice8_SetTexture hooked. Target: 0x6DBBC540
0221/222129 [0A0C] IDirect3DDevice8_Present hooked. Target: 0x6DB992F0
0221/222129 [0A0C] IDirect3DDevice8_DrawPrimitive hooked. Target: 0x6DBBEEE0
0221/222129 [0A0C] IDirect3DDevice8_DrawIndexedPrimitive hooked. Target: 0x6DBBEFF0
0221/222129 [0A0C] IDirect3DDevice8_DrawPrimitiveUP hooked. Target: 0x6DBBF3B0
0221/222129 [0A0C] IDirect3DDevice8_DrawIndexedPrimitiveUP hooked. Target: 0x6DBBF610
0221/222129 [0A0C] IDirect3DDevice8_CreateVertexBuffer hooked. Target: 0x6DB9B4E0
0221/222129 [0A0C] IDirect3DDevice8_CreateIndexBuffer hooked. Target: 0x6DB9B550
0221/222129 [0A0C] IDirect3DDevice8_CreateVertexShader hooked. Target: 0x6DBBD910
0221/222129 [0A0C] IDirect3DDevice8_CreatePixelShader hooked. Target: 0x6DBBE470
0221/222129 [0A0C] IDirect3DDevice8_SetVertexShader hooked. Target: 0x6DBC2640
0221/222129 [0A0C] IDirect3DDevice8_CreateAdditionalSwapChain hooked. Target: 0x6DB98760
0221/222129 [0A0C] Direct3DCreate8(220) return: 0x031544C0
0221/222129 [0A0C] IDirect3D8_CreateDevice(0x031544C0 ...) return: 0x00000000
0221/222137 [0A0C] D3D8 ripper uninit

0221/222137 [0A0C] Loaded Modules List
0221/222137 [0A0C] --------------------------------
0221/222137 [0A0C] BaseAddr    Size         Module
0221/222137 [0A0C] --------------------------------
0221/222137 [0A0C] 0x00400000 (0x00AEA000)  C:\Program Files (x86)\highway35_10_17_05\highway35_10_17_05\highway35\highway35.exe
0221/222137 [0A0C] 0x772A0000 (0x0018D000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0221/222137 [0A0C] 0x75680000 (0x000D0000)  C:\WINDOWS\System32\KERNEL32.DLL
0221/222137 [0A0C] 0x740C0000 (0x001D7000)  C:\WINDOWS\System32\KERNELBASE.dll
0221/222137 [0A0C] 0x73BC0000 (0x0009A000)  C:\WINDOWS\SYSTEM32\apphelp.dll
0221/222137 [0A0C] 0x74C40000 (0x00175000)  C:\WINDOWS\System32\USER32.dll
0221/222137 [0A0C] 0x77220000 (0x00016000)  C:\WINDOWS\System32\win32u.dll
0221/222137 [0A0C] 0x754C0000 (0x00022000)  C:\WINDOWS\System32\GDI32.dll
0221/222137 [0A0C] 0x76CA0000 (0x0015E000)  C:\WINDOWS\System32\gdi32full.dll
0221/222137 [0A0C] 0x74030000 (0x0007C000)  C:\WINDOWS\System32\msvcp_win.dll
0221/222137 [0A0C] 0x77000000 (0x00117000)  C:\WINDOWS\System32\ucrtbase.dll
0221/222137 [0A0C] 0x754F0000 (0x00078000)  C:\WINDOWS\System32\ADVAPI32.dll
0221/222137 [0A0C] 0x75400000 (0x000BD000)  C:\WINDOWS\System32\msvcrt.dll
0221/222137 [0A0C] 0x75570000 (0x00043000)  C:\WINDOWS\System32\sechost.dll
0221/222137 [0A0C] 0x743C0000 (0x000BE000)  C:\WINDOWS\System32\RPCRT4.dll
0221/222137 [0A0C] 0x73CC0000 (0x00020000)  C:\WINDOWS\System32\SspiCli.dll
0221/222137 [0A0C] 0x73CB0000 (0x0000A000)  C:\WINDOWS\System32\CRYPTBASE.dll
0221/222137 [0A0C] 0x74BD0000 (0x00057000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0221/222137 [0A0C] 0x73F30000 (0x000F7000)  C:\WINDOWS\System32\ole32.dll
0221/222137 [0A0C] 0x73CE0000 (0x00246000)  C:\WINDOWS\System32\combase.dll
0221/222137 [0A0C] 0x737B0000 (0x00024000)  C:\WINDOWS\SYSTEM32\WINMM.dll
0221/222137 [0A0C] 0x722A0000 (0x00008000)  C:\WINDOWS\SYSTEM32\WSOCK32.dll
0221/222137 [0A0C] 0x74900000 (0x00066000)  C:\WINDOWS\System32\WS2_32.dll
0221/222137 [0A0C] 0x73170000 (0x00023000)  C:\WINDOWS\SYSTEM32\winmmbase.dll
0221/222137 [0A0C] 0x74970000 (0x00038000)  C:\WINDOWS\System32\cfgmgr32.dll
0221/222137 [0A0C] 0x74BA0000 (0x00025000)  C:\WINDOWS\System32\IMM32.DLL
0221/222137 [0A0C] 0x6EF70000 (0x000C4000)  C:\Users\a_pap\Downloads\ninja\x86\intruder.dll
0221/222137 [0A0C] 0x75960000 (0x01333000)  C:\WINDOWS\System32\SHELL32.dll
0221/222137 [0A0C] 0x76E00000 (0x00088000)  C:\WINDOWS\System32\shcore.dll
0221/222137 [0A0C] 0x74E10000 (0x005C6000)  C:\WINDOWS\System32\windows.storage.dll
0221/222137 [0A0C] 0x74DC0000 (0x00045000)  C:\WINDOWS\System32\shlwapi.dll
0221/222137 [0A0C] 0x740B0000 (0x0000E000)  C:\WINDOWS\System32\kernel.appcore.dll
0221/222137 [0A0C] 0x748B0000 (0x00045000)  C:\WINDOWS\System32\powrprof.dll
0221/222137 [0A0C] 0x753E0000 (0x00014000)  C:\WINDOWS\System32\profapi.dll
0221/222137 [0A0C] 0x723F0000 (0x00181000)  C:\WINDOWS\system32\dbghelp.dll
0221/222137 [0A0C] 0x723C0000 (0x00024000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0221/222137 [0A0C] 0x72A60000 (0x00079000)  C:\WINDOWS\system32\uxtheme.dll
0221/222137 [0A0C] 0x75800000 (0x00144000)  C:\WINDOWS\System32\MSCTF.dll
0221/222137 [0A0C] 0x75760000 (0x00093000)  C:\WINDOWS\System32\OLEAUT32.dll
0221/222137 [0A0C] 0x72340000 (0x00077000)  C:\WINDOWS\System32\TextInputFramework.dll
0221/222137 [0A0C] 0x6FBF0000 (0x00234000)  C:\WINDOWS\System32\CoreUIComponents.dll
0221/222137 [0A0C] 0x72210000 (0x0008C000)  C:\WINDOWS\System32\CoreMessaging.dll
0221/222137 [0A0C] 0x72A30000 (0x00028000)  C:\WINDOWS\SYSTEM32\ntmarta.dll
0221/222137 [0A0C] 0x6FF30000 (0x000CB000)  C:\WINDOWS\SYSTEM32\wintypes.dll
0221/222137 [0A0C] 0x73600000 (0x00023000)  C:\WINDOWS\system32\dwmapi.dll
0221/222137 [0A0C] 0x721A0000 (0x00026000)  C:\WINDOWS\SYSTEM32\DINPUT.dll
0221/222137 [0A0C] 0x6EF40000 (0x00026000)  C:\WINDOWS\SYSTEM32\inputhost.dll
0221/222137 [0A0C] 0x6EF30000 (0x0000A000)  C:\WINDOWS\SYSTEM32\HID.DLL
0221/222137 [0A0C] 0x74480000 (0x00426000)  C:\WINDOWS\System32\SETUPAPI.DLL
0221/222137 [0A0C] 0x72E50000 (0x00022000)  C:\WINDOWS\SYSTEM32\DEVOBJ.dll
0221/222137 [0A0C] 0x755D0000 (0x00046000)  C:\WINDOWS\System32\WINTRUST.dll
0221/222137 [0A0C] 0x74C30000 (0x0000E000)  C:\WINDOWS\System32\MSASN1.dll
0221/222137 [0A0C] 0x74A10000 (0x00182000)  C:\WINDOWS\System32\CRYPT32.dll
0221/222137 [0A0C] 0x6EEB0000 (0x00080000)  C:\WINDOWS\SYSTEM32\DSOUND.dll
0221/222137 [0A0C] 0x74330000 (0x00082000)  C:\WINDOWS\System32\clbcatq.dll
0221/222137 [0A0C] 0x6EE50000 (0x0005B000)  C:\WINDOWS\System32\MMDevApi.dll
0221/222137 [0A0C] 0x6E780000 (0x0017A000)  C:\WINDOWS\System32\PROPSYS.dll
0221/222137 [0A0C] 0x6DC30000 (0x000F4000)  C:\WINDOWS\SYSTEM32\AUDIOSES.DLL
0221/222137 [0A0C] 0x6EE40000 (0x00008000)  C:\WINDOWS\SYSTEM32\AVRT.dll
0221/222137 [0A0C] 0x6DB70000 (0x000B6000)  C:\WINDOWS\SYSTEM32\d3d8.dll
0221/222137 [0A0C] 0x6EE30000 (0x00007000)  C:\WINDOWS\SYSTEM32\d3d8thk.dll
0221/222137 [0A0C] 0x6D7E0000 (0x00386000)  C:\WINDOWS\SYSTEM32\d3dcompiler_47.dll
0221/222137 [0A0C] 0x72CD0000 (0x00013000)  C:\WINDOWS\SYSTEM32\CRYPTSP.dll
0221/222137 [0A0C] 0x6D5D0000 (0x00207000)  C:\WINDOWS\SYSTEM32\d3dcompiler_43.dll
0221/222137 [0A0C] 0x06640000 (0x000AF000)  C:\Users\a_pap\Downloads\ninja\x86\d3dx8d.dll
0221/222137 [0A0C] 0x6B520000 (0x00ED9000)  C:\WINDOWS\System32\DriverStore\FileRepository\igdlh64.inf_amd64_82119d956c80af5a\igc32.dll
0221/222137 [0A0C] 0x75950000 (0x00006000)  C:\WINDOWS\System32\psapi.dll
0221/222137 [0A0C] LOG END


My OS is windows 10.
Let me know if you have any ideas. Finally, I know that it is possible to rip the models using NR because somebody has already done that...They told me they used Win Xp though. Could that play a role?

Hello,

I join with what thorh62 said: Is possible to rip the 3d files of the game "Planet Hot Wheels"? And, if is true that NR on Win XP can rip the game, it can have something to do with it?

Because I've tried to rip with NR, as via Win 10 with d3dx8d.dll, as via Win XP (via Virtual Box) with d3dx9d.dll on Win XP, because on Virtual Box supports only directX 9 and 11 ( idk why), I ran it and nothing happens... only the log files NR created.

Someone so kind can help us, please?
## Post #642
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2018-08-23T20:23:49+00:00
- Post Title: Re: Ninja Ripper

Hi blackninja, can the community provide an updated English translation for this page?
- [http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/)

Also, do you mind adding your PayPal button on that page?

This way you will get additional support from English speaking users.
## Post #643
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2018-08-24T07:35:34+00:00
- Post Title: Re: Ninja Ripper

> Reply from Curtain
>
> Hi blackninja, can the community provide an updated English translation for this page?
- http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/

Also, do you mind adding your PayPal button on that page?

This way you will get additional support from English speaking users.

Hi.  I'm only  tool author. 

Ask Tosyk. He owns the site and support forum
## Post #644
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2018-09-09T02:36:16+00:00
- Post Title: Re: Ninja Ripper

I just downloaded the newest NOX version 6.2.3.0 and was so happy to find the new version plays some of the apps it hasn't played in a long time. So I fired up ninja ripper 1.7.1. and it says it's injecting but it doesn't rip anything nothing at all. 6.2.2.0. ripped just fine but for some reason none of the versions of ninja ripper work with it now and none of the versions of injectors seem to do anything at all. And yes, before the forums ask I made sure to set Nox to render in direct x. I can send the authors my log if they need it but all the sudden we went from ripping fine to nothing at all and it's very frustrating.
## Post #645
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2018-09-25T08:38:19+00:00
- Post Title: Re: Ninja Ripper

Valve recently released their new Steam Play service which uses Proton(WINE+DXVK), 
which got me wondering, can Ninja Ripper function properly in Linux with these compatibility tools?
Or is there a Linux version of Ninja Ripper available?

[https://github.com/ValveSoftware/Proton](https://github.com/ValveSoftware/Proton)
[https://steamcommunity.com/games/221410 ... 5739350561](https://steamcommunity.com/games/221410/announcements/detail/1696055855739350561)
## Post #646
- Username: Maybe Magpie
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 10, 2018 1:54 am
- Post datetime: 2018-10-29T04:51:44+00:00
- Post Title: Re: Ninja Ripper

I asked this question in the discord but I'll ask here too just in case: I'm having some difficulty with getting NinjaRipper and Prey to work. I put the .exe and output directories to what I need, but when I click "run" the .exe shows up as running and steam thinks I'm playing, but the actual game itself won't appear as a window so I can't rip anything. I checked the output and there's only a log, would attaching it here be helpful? I tried the inject first, and it didn't work, and I'm not sure I'm doing the wrapper right. Either way the game doesn't actually start, only the exe itself. No window. Should I attach a log to a post, or is there a more direct solution?

e: I already own the game legally, but I acquired a DRM-less version of it and now NR will rip stuff from that instance, but I can't seem to get it to rip what I want it to (the Morgan models). I've gotten a Neuromod prop and some hair models out but no actual people to be found.
## Post #647
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2018-11-06T12:31:59+00:00
- Post Title: Re: Ninja Ripper

Hi everyone,

Newbie here, did some amateur attempts at 3D ripping way back in 2009 / 2010. Interested to get back into it again.

I currently am attempting to grab a few choice models from Dissidia Final Fantasy Opera Omnia. My intention is to use a couple of their chibi style 3D character models (that are not already available from the older Dissidia Games) as a template for modelling and rigging a full sized character version of my own.

After watching [this tut](https://youtu.be/Dp90rbVntb0), I've been stumbling my way around testing with different versions of the Nox emulator and Ninja Ripper and Noesis.

So far where I'm at:

> - DFFOO will run properly ONLY on an Android 5.1.1 emulator created via Nox's Multi Instance Manager
>
> - The tutorial states that the Ninja ripper method will work only SPECIFICALLY for Nox 3.8.1
>
> - When I go ahead and run Ninja Ripper on the Nox Android 5.1.1 anyway - I am successfully able to see the DDS files, and even the mesh files. Unfortunately, for some weird reason, the 3D geometry is being flattened into a plane shape, that follows the UV mapping of its corresponding 2D texture.
>
> - I tested the same steps above with a different game (Marvel Contest of Champions), but instead of a flat plane, the characters are being crushed into a perfect sphere.

I haven't been able to move beyond this point in 2 weeks. Even if the rip wont include the rigging information, I can work with the 3D geometry regardless of whether or not it is in a default T stance or pose. But yeah, getting a flat mesh will not do at all Sad

I've tried using 3D Ripper DX but it wont work with Nox. Does anyone have any suggestion / advice on what I should do next?

Thanks



showing wire frame of flat geometryand Nox emulator version DFFOO.jpg (83.14 KiB) Viewed 620 times
## Post #648
- Username: ARRadiation
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 18, 2018 5:11 am
- Post datetime: 2018-11-17T21:19:11+00:00
- Post Title: Re: Ninja Ripper

Has anyone had an issue with ninja ripper where the UV maps for the head has the face and scalp on top of each other causing the face to appear on the scalp as well? as well as some of the exported textures are black?
## Post #649
- Username: arlonfelipe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 06, 2016 9:54 pm
- Post datetime: 2019-02-11T17:58:14+00:00
- Post Title: Re: Ninja Ripper

Hey guys, been using n ripper for some time and always worked fine. But ive tried ripping the main character from the game battle royale free trainer [https://igg-games.com/battle-royale-tra ... nload.html](https://igg-games.com/battle-royale-trainer-free-923519798-download.html) with 3ds max, and it all goes well when i export it, expect for the UVs. When i use the EvoGims importer, it exports with no UV at all. And when i run the ninja script to import the rip files, it exports later with a strange uv, that doesnt match the meshes [https://imgur.com/a/TWlHz9V](https://imgur.com/a/TWlHz9V) i tried using others version of importers and chaning the export settings, but doesnt seem to fix. Has anyone had this problem too? Apreciate any help i can get
## Post #650
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-02-12T17:21:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from arlonfelipe
>
> Hey guys, been using n ripper for some time and always worked fine. But ive tried ripping the main character from the game battle royale free trainer https://igg-games.com/battle-royale-tra ... nload.html with 3ds max, and it all goes well when i export it, expect for the UVs. When i use the EvoGims importer, it exports with no UV at all. And when i run the ninja script to import the rip files, it exports later with a strange uv, that doesnt match the meshes https://imgur.com/a/TWlHz9V i tried using others version of importers and chaning the export settings, but doesnt seem to fix. Has anyone had this problem too? Apreciate any help i can get

Its a unreal program so try umodel which can export with uvs, mesh, texture, skeleton etc.
## Post #651
- Username: arlonfelipe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Dec 06, 2016 9:54 pm
- Post datetime: 2019-02-12T18:18:57+00:00
- Post Title: Re: Ninja Ripper

Gonna try it, Thanks a lot Will ^^
## Post #652
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2019-03-24T15:51:08+00:00
- Post Title: Re: Ninja Ripper

Whether this tool can be updated, the latest Warframe does not work
## Post #653
- Username: dolem
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 31, 2019 10:08 pm
- Post datetime: 2019-03-31T14:13:44+00:00
- Post Title: Re: Ninja Ripper

I think I am running into a problem. 

A game I am dumping from doesnt seem to be a complete rip. There is no depth buffer extracted by ninjaripper, but in a previous version of the game ninja did dump the depth buffer just fine. That was when the game was dx9 and since then the developers have moved over to dx11. I suspect that there are some other textures not getting dumped as well. 

Is there something obvious I'm missing? Are there any arguments I should be using?
## Post #654
- Username: Farrarie
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Mar 19, 2017 6:00 pm
- Post datetime: 2019-05-20T00:39:06+00:00
- Post Title: Re: Ninja Ripper

Any possiblity for an update for ninja ripper to work with assassin creed odyssey ?
because rn, I can start the game with it
## Post #655
- Username: SciBott
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 18, 2016 3:44 pm
- Post datetime: 2019-05-20T05:05:27+00:00
- Post Title: Re: Ninja Ripper

I'm curious if there's any possibility of adding OpenGL support, or version of NinjaRipper, there are a few things I'd like to rip that only have that option so it is quite difficult to rip assets. If you want specifics, just look at Citra.
## Post #656
- Username: bacarlitos
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 05, 2012 1:59 am
- Post datetime: 2019-05-30T19:11:36+00:00
- Post Title: Re: Ninja Ripper

Hello, I was wondering if there is a way to ripping gta v models via openIV. It seems that Ninja Ripper tool doesnt work with the latest openIV. I can only view the 3d file window ussing the DDRAW wrapper when I press the hotkeys to start ripping the model nothing happens, is that a protection from openIV? and you are planning to solve this problem? The other Toos like intruder iject makes the 3D view window to crash in open iv. Any help with this issue will be apreciate it.
Thanks in advance.
## Post #657
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-07-02T14:40:02+00:00
- Post Title: Re: Ninja Ripper

Hello there!

I use Ninja as 3 years or more - it's amasing!
Before that I use old script in my old 3dsmax.
Then I install 3dsmax 2017 and try to load EvoGIMS script, but whatever I do, it says "Unavailable download" when I start my max. 
Tell me, please, how or where I can get right EvoGims script?
I can make UV and weight by myself, but it's too long for me..
## Post #658
- Username: Ody
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 13, 2019 5:31 am
- Post datetime: 2019-07-12T21:35:20+00:00
- Post Title: Re: Ninja Ripper

Hi guys I m trying to use the Ninja Ripper to rip model from GTA 5, for research purposes. Is it even possible,and what would be the best way to do it?
## Post #659
- Username: XENZEN
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 12, 2019 12:13 pm
- Post datetime: 2019-07-15T09:25:23+00:00
- Post Title: Re: Ninja Ripper

I hope someone here can help. I'm trying to extract a model from the game for honor to try and 3d print for another same name game from apknite. Can someone tell me if this is even possible or if I am doing somthing wrong?
## Post #660
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2019-07-31T19:34:48+00:00
- Post Title: Re: Ninja Ripper

> Reply from Ody ↑Sat Jul 13, 2019 5:35 am at Sat Jul 13, 2019 5:35 am
>
> 
Hi guys I m trying to use the Ninja Ripper to rip model from GTA 5, for research purposes. Is it even possible,and what would be the best way to do it?
Get GTA5 "torrent edition" (without anticheat and risk to get banned).
Get good Trainer (with god mode, teleport and car spawner).
In game enable god mode, then teleport to map corner with deep sea.
Spawn car underwater and rip it (minimal amount of unwanted objects is ripped by this way).



Maybe you can find a trainer or edit config to enable all tuning parts always visible for ripping them with one shot - untested atm.
## Post #661
- Username: aske0874
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 04, 2019 5:45 pm
- Post datetime: 2019-08-04T10:11:53+00:00
- Post Title: Re: Ninja Ripper

Hi ninja experts
I'm trying to rip models from the game Abzü, but haven't had much luck yet. I used UE viewer with some results, but only for the bigger fish. It seems they used some special form of static mesh so UE viewer can not view the majority of fish in the game. I then thought ninja ripper maybe could be the answar, since it treats the 3D models differently than UE viewer does. But for some reason ninja ripper does not work with Abzü at all, it does't even create a ripping folder for the game then I launch it. The game launches but nothing more happens. I tried opening Age Of Mythology in ninja ripper and it does open and create a folder, but then i try to extract something it doesnt do anything other than leaving a log. This is strange since i have succesfully ripped models from Age Of Mythology before, so now I'm thinking I am doing something wrong. I am running ninja ripper as admin and I am running Abzü in the 64 bit version and the directx 11 mode, which I think is what Abzü is made for. Does anyone maybe have a solution to this problem?
Thanks for the help and have a great day
## Post #662
- Username: BeanMachine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 02, 2019 2:21 am
- Post datetime: 2019-09-01T18:42:46+00:00
- Post Title: Re: Ninja Ripper

Hello. I am currently having an issue where I am not able to rip from any game. I am using the x64 version of NinjaRipper and have tested on GTA 5 (Steam version) and WWE 2k17 (Torrent). Using Intruder the log file and the folder for where the rips are supposed to be were created but the folder was empty. Using d3d11 wrapper only the log file was created. This was the same for both games. I have tried to turn off anti-virus and that has not even worked. If anyone could let me know what is wrong it would be greatly appreciated.

OS Name	Microsoft Windows 10 Home
Version	10.0.17134 Build 17134
OS Manufacturer	Microsoft Corporation
System Name	DESKTOP-LJ14A70
System Manufacturer	Micro-Star International Co., Ltd.
System Model	MS-B90111
System Type	x64-based PC
System SKU	Default string
Processor	Intel(R) Core(TM) i5-6400 CPU @ 2.70GHz, 2712 Mhz, 4 Core(s), 4 Logical Processor(s)

Log files for WWE 2k17:

0901/140837 [30F0] LOG START

0901/140837 [30F0] Executable: D:\Games\WWE 2K17\WWE2K17_x64.exe
0901/140837 [30F0] Output directory: D:\NINJARIPPER\_NinjaRipper\2019.09.01_14.08.37_WWE2K17_x64.exe_4224\
0901/140837 [30F0] Win ver: 6.2 x64 

0901/140837 [30F0] Inject mode: "intruder"
0901/140837 [30F0] Texture downscale max width : 4096
0901/140837 [30F0] Texture downscale max height: 4096
0901/140837 [30F0] Texture downscale value: 2
0901/140837 [30F0] LdrLoadDll hooked. Target: 0x00007FFCCFB41BB0
0901/140837 [30F0] LdrUnloadDll hooked. Target: 0x00007FFCCFB46DB0
0901/140837 [30F0] CreateProcessA hooked. Target: 0x00007FFCCDCAB0C0
0901/140837 [30F0] CreateProcessW hooked. Target: 0x00007FFCCDCAB990
0901/140837 [30F0] CreateProcessAsUserW hooked. Target: 0x00007FFCCDF235C0
0901/140837 [30F0] CreateProcessWithLogonW hooked. Target: 0x00007FFCCDF4DF10
0901/140837 [30F0] CreateProcessWithTokenW hooked. Target: 0x00007FFCCDF11E80
0901/140837 [30F0] SetTokenInformation hooked. Target: 0x00007FFCCDF26990
0901/140837 [30F0] D3D11 ripper init
0901/140837 [30F0] D3D11CreateDeviceAndSwapChain hooked. Target: 0x00007FFCC8C15950
0901/140837 [30F0] D3D11CreateDevice hooked. Target: 0x00007FFCC8C15800
0901/140837 [30F0] DXGI init
0901/140837 [30F0] CreateDXGIFactory hooked. Target: 0x00007FFCCACB9DE0
0901/140837 [30F0] CreateDXGIFactory1 hooked. Target: 0x00007FFCCACBA200
0901/140846 [30F0] CreateDXGIFactory()
0901/140848 [30F0] IDXGIFactory_QueryInterface hooked. Target: 0x00007FFCCACBCB30
0901/140848 [30F0] IDXGIFactory_CreateSwapChain hooked. Target: 0x00007FFCCAD04420
0901/140852 [4A58] CreateDXGIFactory()
0901/140853 [4A58] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/140909 [30F0] CreateDXGIFactory()
0901/140909 [30F0] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/140910 [30F0] IDXGIFactory_QueryInterface(IID_IUnknown)
0901/140910 [30F0] WARNING: hookIDXGIFactory() GUID param not recognized: IID_IUnknown
0901/140910 [30F0] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/140913 [30F0] D3D11CreateDeviceAndSwapChain(ppSwapChain: 0x0000000000000000, ppDevice: 0x000000010DB29CA8, ppImmediateContext: 0x000000010DC92AE8) return: 0x00000000
0901/140913 [30F0] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFCC8D878C0
0901/140913 [30F0] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFCC8DCF8D0
0901/140913 [30F0] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFCC8D87D80
0901/140913 [30F0] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFCC8D8A0D0
0901/140913 [30F0] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFCC8DCFA60
0901/140913 [30F0] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFCC8DD2150
0901/140913 [30F0] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFCC8D87530
0901/140913 [30F0] ID3D11DeviceContext_PSSetShaderResources hooked. Target: 0x00007FFCC8D844F0
0901/140913 [30F0] WARNING: KDxgi::hookSwapChain() zero ppSwapChain
0901/140913 [30F0] ID3D11Device_CreateInputLayout hooked. Target: 0x00007FFCC8C4F6C0
0901/140913 [30F0] ID3D11Device_CreateVertexShader hooked. Target: 0x00007FFCC8C4F6F0
0901/140913 [30F0] ID3D11Device_CreatePixelShader hooked. Target: 0x00007FFCC8C4F720
0901/140913 [30F0] ID3D11Device_CreateGeometryShader hooked. Target: 0x00007FFCC8CE3620
0901/140913 [30F0] ID3D11Device_CreateGeometryShaderWithStreamOutput hooked. Target: 0x00007FFCC8CE3650
0901/140914 [30F0] ID3D11Device_GetImmediateContext hooked. Target: 0x00007FFCC8C4F980
0901/140914 [30F0] D3D11CreateDevice(ppDevice: 0x000000010DB29CA8, ppImmediateContext: 0x000000010DC92AE8) return: 0x00000000
0901/140914 [30F0] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/140914 [30F0] IDXGIFactory_CreateSwapChain()
0901/140914 [30F0] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/140914 [30F0] IDXGISwapChain_Present hooked. Target: 0x00007FFCCACB5070
0901/140924 [30F0] ID3D11Device_CreateInputLayout(): 0x000000003C437688
0901/140925 [30F0] ID3D11Device_CreateInputLayout(): 0x000000003C437988
0901/140925 [30F0] ID3D11Device_CreateInputLayout(): 0x000000003C4387C8
0901/140925 [30F0] ID3D11Device_CreateInputLayout(): 0x00000000044EE188
0901/140926 [424C] ID3D11Device_CreateInputLayout(): 0x00000000044EDD48
0901/140926 [424C] ID3D11Device_CreateInputLayout(): 0x00000000044EDBC8
0901/140926 [424C] ID3D11Device_CreateInputLayout(): 0x0000000003924348
0901/140926 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766B048
0901/140926 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766AD88
0901/140927 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766A948
0901/140927 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766AF08
0901/140927 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766B4C8
0901/140927 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766AA88
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAF188
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAEE88
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAED08
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAD908
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAF008
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAF448
0901/140943 [30F0] ID3D11Device_CreateInputLayout(): 0x0000000023AAD608
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7F548
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA810C8
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA80B08
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7EE48
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA827C8
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA81208
0901/140943 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7F6C8
0901/140944 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA803C8
0901/140944 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7F288
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7F408
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA824C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA80988
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA80F48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA817C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA81AC8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA7F108
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA81C48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA82088
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA82208
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA82648
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x0000000023AAD788
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x0000000023AADA88
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x0000000023AADBC8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000004766A208
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292988
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291408
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291E08
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D2919C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291548
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D2923C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292808
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D2916C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291B08
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D2920C8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292B08
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291F88
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292248
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292C48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292548
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D292688
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D290E48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D290F88
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D291288
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14DFC8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150F48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14DE48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14F548
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14E288
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14E588
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14EB48
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150AC8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D151088
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14ECC8
0901/141000 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14EE08
0901/141001 [2724] ID3D11Device_CreateInputLayout(): 0x000000001D14E708
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14F988
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14FE08
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14FB08
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14FF48
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14FC88
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D1500C8
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150248
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150508
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150688
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150988
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D150C48
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D151508
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D151648
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D14DA08
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001BA80688
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D3D2F08
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000001D3D4D08
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000004DF88C48
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000004DF8AA88
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000004DF8AEC8
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000004DF8B608
0901/141003 [424C] ID3D11Device_CreateInputLayout(): 0x000000004DF8BA48
0901/141018 [4A58] Frame Start...#00
0901/141019 [4A58] Frame len: 30144us
0901/141019 [4A58] Frame End...

0901/141054 [2B74] LOG START

0901/141054 [2B74] Executable: D:\Games\WWE 2K17\WWE2K17_x64.exe
0901/141054 [2B74] Output directory: D:\NINJARIPPER\_NinjaRipper\2019.09.01_14.10.54_WWE2K17_x64.exe_14868\
0901/141054 [2B74] Win ver: 6.2 x64 

0901/141054 [2B74] Inject mode: "d3d11.dll wrapper"
0901/141054 [2B74] Texture downscale max width : 4096
0901/141054 [2B74] Texture downscale max height: 4096
0901/141054 [2B74] Texture downscale value: 2
0901/141054 [2B74] LdrLoadDll hooked. Target: 0x00007FFCCFB41BB0
0901/141054 [2B74] LdrUnloadDll hooked. Target: 0x00007FFCCFB46DB0
0901/141054 [2B74] CreateProcessA hooked. Target: 0x00007FFCCDCAB0C0
0901/141054 [2B74] CreateProcessW hooked. Target: 0x00007FFCCDCAB990
0901/141054 [2B74] CreateProcessAsUserW hooked. Target: 0x00007FFCCDF235C0
0901/141054 [2B74] CreateProcessWithLogonW hooked. Target: 0x00007FFCCDF4DF10
0901/141054 [2B74] CreateProcessWithTokenW hooked. Target: 0x00007FFCCDF11E80
0901/141054 [2B74] SetTokenInformation hooked. Target: 0x00007FFCCDF26990
0901/141054 [2B74] DXGI init
0901/141054 [2B74] DXGI.DLL loaded
0901/141054 [2B74] DXGI init
0901/141054 [2B74] CreateDXGIFactory hooked. Target: 0x00007FFCCACB9DE0
0901/141054 [2B74] CreateDXGIFactory1 hooked. Target: 0x00007FFCCACBA200
0901/141054 [2B74] DXGI initialized
0901/141057 [2B74] CreateDXGIFactory()
0901/141057 [2B74] IDXGIFactory_QueryInterface hooked. Target: 0x00007FFCCACBCB30
0901/141057 [2B74] IDXGIFactory_CreateSwapChain hooked. Target: 0x00007FFCCAD04420
0901/141057 [3D28] CreateDXGIFactory()
0901/141057 [3D28] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/141108 [2B74] CreateDXGIFactory()
0901/141108 [2B74] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/141108 [2B74] D3D11.DLL loaded
0901/141108 [2B74] D3D11 ripper init
0901/141108 [2B74] D3D11CreateDeviceAndSwapChain hooked. Target: 0x00007FFCC8C15950
0901/141108 [2B74] D3D11CreateDevice hooked. Target: 0x00007FFCC8C15800
0901/141109 [2B74] IDXGIFactory_QueryInterface(IID_IUnknown)
0901/141109 [2B74] WARNING: hookIDXGIFactory() GUID param not recognized: IID_IUnknown
0901/141109 [2B74] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/141110 [2B74] D3D11CreateDeviceAndSwapChain(ppSwapChain: 0x0000000000000000, ppDevice: 0x000000010DB2ECA8, ppImmediateContext: 0x000000010DC97AE8) return: 0x00000000
0901/141110 [2B74] ID3D11DeviceContext_Draw hooked. Target: 0x00007FFCC8D878C0
0901/141110 [2B74] ID3D11DeviceContext_DrawAuto hooked. Target: 0x00007FFCC8DCF8D0
0901/141110 [2B74] ID3D11DeviceContext_DrawIndexed hooked. Target: 0x00007FFCC8D87D80
0901/141110 [2B74] ID3D11DeviceContext_DrawIndexedInstanced hooked. Target: 0x00007FFCC8D8A0D0
0901/141110 [2B74] ID3D11DeviceContext_DrawIndexedInstancedIndirect hooked. Target: 0x00007FFCC8DCFA60
0901/141110 [2B74] ID3D11DeviceContext_DrawInstanced hooked. Target: 0x00007FFCC8DD2150
0901/141110 [2B74] ID3D11DeviceContext_ClearRenderTargetView hooked. Target: 0x00007FFCC8D87530
0901/141110 [2B74] ID3D11DeviceContext_PSSetShaderResources hooked. Target: 0x00007FFCC8D844F0
0901/141110 [2B74] WARNING: KDxgi::hookSwapChain() zero ppSwapChain
0901/141110 [2B74] ID3D11Device_CreateInputLayout hooked. Target: 0x00007FFCC8C4F6C0
0901/141110 [2B74] ID3D11Device_CreateVertexShader hooked. Target: 0x00007FFCC8C4F6F0
0901/141110 [2B74] ID3D11Device_CreatePixelShader hooked. Target: 0x00007FFCC8C4F720
0901/141110 [2B74] ID3D11Device_CreateGeometryShader hooked. Target: 0x00007FFCC8CE3620
0901/141110 [2B74] ID3D11Device_CreateGeometryShaderWithStreamOutput hooked. Target: 0x00007FFCC8CE3650
0901/141110 [2B74] ID3D11Device_GetImmediateContext hooked. Target: 0x00007FFCC8C4F980
0901/141110 [2B74] D3D11CreateDevice(ppDevice: 0x000000010DB2ECA8, ppImmediateContext: 0x000000010DC97AE8) return: 0x00000000
0901/141110 [2B74] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/141110 [2B74] IDXGIFactory_CreateSwapChain()
0901/141110 [2B74] IDXGIFactory_QueryInterface(IID_IDXGIFactory)
0901/141111 [2B74] IDXGISwapChain_Present hooked. Target: 0x00007FFCCACB5070
0901/141117 [2B74] ID3D11Device_CreateInputLayout(): 0x000000003C4AA3C8
0901/141118 [2B74] ID3D11Device_CreateInputLayout(): 0x000000003C4AA808
0901/141118 [2B74] ID3D11Device_CreateInputLayout(): 0x000000003C4A9288
0901/141118 [2B74] ID3D11Device_CreateInputLayout(): 0x00000000032DC588
0901/141119 [2710] ID3D11Device_CreateInputLayout(): 0x00000000032DCF88
0901/141119 [2710] ID3D11Device_CreateInputLayout(): 0x000000003C4AA548
0901/141119 [2710] ID3D11Device_CreateInputLayout(): 0x000000000578D908
0901/141119 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC4DC8
0901/141119 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC4688
0901/141120 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC5C08
0901/141120 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC4248
0901/141120 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC5208
0901/141120 [2710] ID3D11Device_CreateInputLayout(): 0x0000000047CC4988
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC8108
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC7F88
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC5748
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC6FC8
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC55C8
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC6708
0901/141132 [2B74] ID3D11Device_CreateInputLayout(): 0x000000001DFC5D08
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC5B88
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC7108
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC6888
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC5E88
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC76C8
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC5FC8
0901/141132 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC8248
0901/141133 [48C0] ID3D11Device_CreateInputLayout(): 0x000000001DFC6A08
0901/141133 [48C0] ID3D11Device_CreateInputLayout(): 0x000000001DFC79C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC6E48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC48C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC4D48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC7408
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC7E08
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC4E88
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC5308
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC7B48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC7C88
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC5008
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC83C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001B4FD488
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000001B4FD788
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x000000003C4AAF48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59048
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B148
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59488
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B2C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5AA08
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C408
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5BE48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5BF88
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5AB88
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59608
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5AE48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59D08
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59188
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B408
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C108
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59E88
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5AFC8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59308
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C9C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A448
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A5C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B9C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A888
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C548
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59A48
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B588
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A188
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E59BC8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C6C8
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5CB08
0901/141151 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C848
0901/141151 [0534] ID3D11Device_CreateInputLayout(): 0x0000000038E5B708
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E6DD88
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E6FD48
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E6FEC8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5B888
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5BB48
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A2C8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5A748
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5BCC8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E5C288
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000038E58D48
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC6448
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC4608
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC6CC8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x000000001DFC4A48
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB1B08
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BAF5C8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB1548
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB1848
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB0CC8
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BAF188
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB1F88
0901/141153 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB2248
0901/141226 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB0408
0901/141226 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB2B08
0901/141226 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB0708
0901/141226 [2710] ID3D11Device_CreateInputLayout(): 0x0000000039BB2DC8
0901/141237 [2B74] D3D11 ripper uninit

0901/141237 [2B74] DXGI uninit

0901/141237 [2B74] Loaded Modules List
0901/141237 [2B74] ----------------------------------------
0901/141237 [2B74] BaseAddr            Size         Module
0901/141237 [2B74] ----------------------------------------
0901/141237 [2B74] 0x0000000140000000 (0x034CD000)  D:\Games\WWE 2K17\WWE2K17_x64.exe
0901/141237 [2B74] 0x00007FFCCFB00000 (0x001E1000)  C:\WINDOWS\SYSTEM32\ntdll.dll
0901/141237 [2B74] 0x00007FFCCDC90000 (0x000B1000)  C:\WINDOWS\System32\KERNEL32.DLL
0901/141237 [2B74] 0x00007FFCCBED0000 (0x00273000)  C:\WINDOWS\System32\KERNELBASE.dll
0901/141237 [2B74] 0x00007FFCCA430000 (0x0008B000)  C:\WINDOWS\SYSTEM32\apphelp.dll
0901/141237 [2B74] 0x00007FFC8D000000 (0x0048F000)  C:\WINDOWS\SYSTEM32\AcLayers.DLL
0901/141237 [2B74] 0x00007FFCCFA30000 (0x0009E000)  C:\WINDOWS\System32\msvcrt.dll
0901/141237 [2B74] 0x00007FFCCDD50000 (0x00190000)  C:\WINDOWS\System32\USER32.dll
0901/141237 [2B74] 0x00007FFCCCF70000 (0x00020000)  C:\WINDOWS\System32\win32u.dll
0901/141237 [2B74] 0x00007FFCCD4F0000 (0x00028000)  C:\WINDOWS\System32\GDI32.dll
0901/141237 [2B74] 0x00007FFCCC150000 (0x00191000)  C:\WINDOWS\System32\gdi32full.dll
0901/141237 [2B74] 0x00007FFCCC340000 (0x0009F000)  C:\WINDOWS\System32\msvcp_win.dll
0901/141237 [2B74] 0x00007FFCCC440000 (0x000F8000)  C:\WINDOWS\System32\ucrtbase.dll
0901/141237 [2B74] 0x00007FFCCF620000 (0x00051000)  C:\WINDOWS\System32\SHLWAPI.dll
0901/141237 [2B74] 0x00007FFCCF6E0000 (0x00322000)  C:\WINDOWS\System32\combase.dll
0901/141237 [2B74] 0x00007FFCCD520000 (0x00124000)  C:\WINDOWS\System32\RPCRT4.dll
0901/141237 [2B74] 0x00007FFCCCC50000 (0x00079000)  C:\WINDOWS\System32\bcryptPrimitives.dll
0901/141237 [2B74] 0x0000000180000000 (0x00003000)  C:\WINDOWS\SYSTEM32\sfc.dll
0901/141237 [2B74] 0x00007FFCC77C0000 (0x00085000)  C:\WINDOWS\SYSTEM32\WINSPOOL.DRV
0901/141237 [2B74] 0x00007FFCCBE90000 (0x00011000)  C:\WINDOWS\System32\kernel.appcore.dll
0901/141237 [2B74] 0x00007FFCC89D0000 (0x001B4000)  C:\WINDOWS\SYSTEM32\PROPSYS.dll
0901/141237 [2B74] 0x00007FFCCCFF0000 (0x000C2000)  C:\WINDOWS\System32\OLEAUT32.dll
0901/141237 [2B74] 0x00007FFCCD440000 (0x000A9000)  C:\WINDOWS\System32\shcore.dll
0901/141237 [2B74] 0x00007FFCCD0D0000 (0x0005B000)  C:\WINDOWS\System32\sechost.dll
0901/141237 [2B74] 0x00007FFCCB3C0000 (0x00038000)  C:\WINDOWS\SYSTEM32\IPHLPAPI.DLL
0901/141237 [2B74] 0x00007FFCCB970000 (0x00025000)  C:\WINDOWS\SYSTEM32\bcrypt.dll
0901/141237 [2B74] 0x00007FFCC8470000 (0x00013000)  C:\WINDOWS\SYSTEM32\sfc_os.DLL
0901/141237 [2B74] 0x00007FFCCDEE0000 (0x0002D000)  C:\WINDOWS\System32\IMM32.DLL
0901/141237 [2B74] 0x00007FFCCDFC0000 (0x01440000)  C:\WINDOWS\System32\SHELL32.dll
0901/141237 [2B74] 0x00007FFCCC2F0000 (0x00049000)  C:\WINDOWS\System32\cfgmgr32.dll
0901/141237 [2B74] 0x00007FFCC9DF0000 (0x00013000)  C:\WINDOWS\SYSTEM32\WTSAPI32.dll
0901/141237 [2B74] 0x00007FFCCC540000 (0x0070D000)  C:\WINDOWS\System32\windows.storage.dll
0901/141237 [2B74] 0x00007FFCAD040000 (0x00043000)  C:\WINDOWS\SYSTEM32\DINPUT8.dll
0901/141237 [2B74] 0x00007FFCCDF10000 (0x000A1000)  C:\WINDOWS\System32\ADVAPI32.dll
0901/141237 [2B74] 0x00007FFCBFBF0000 (0x00007000)  C:\WINDOWS\SYSTEM32\XINPUT9_1_0.dll
0901/141237 [2B74] 0x00007FFCCBE70000 (0x0001F000)  C:\WINDOWS\System32\profapi.dll
0901/141237 [2B74] 0x00007FFCAA570000 (0x00063000)  D:\Games\WWE 2K17\bink2w64.dll
0901/141237 [2B74] 0x00007FFCCBE10000 (0x0004C000)  C:\WINDOWS\System32\powrprof.dll
0901/141237 [2B74] 0x00007FFCB9D50000 (0x004BD000)  C:\WINDOWS\SYSTEM32\WININET.dll
0901/141237 [2B74] 0x00007FFCCD130000 (0x00151000)  C:\WINDOWS\System32\ole32.dll
0901/141237 [2B74] 0x00007FFCCBE60000 (0x0000A000)  C:\WINDOWS\System32\FLTLIB.DLL
0901/141237 [2B74] 0x00007FFCCDC20000 (0x0006C000)  C:\WINDOWS\System32\WS2_32.dll
0901/141237 [2B74] 0x00007FFC97A00000 (0x000DC000)  D:\Games\WWE 2K17\steam_api64.dll
0901/141237 [2B74] 0x00007FFCCD430000 (0x00008000)  C:\WINDOWS\System32\PSAPI.DLL
0901/141237 [2B74] 0x00007FFCCA140000 (0x00023000)  C:\WINDOWS\SYSTEM32\WINMM.dll
0901/141237 [2B74] 0x00007FFC9BCE0000 (0x000A7000)  D:\Games\WWE 2K17\MSVCP110.dll
0901/141237 [2B74] 0x00007FFC977A0000 (0x000D4000)  D:\Games\WWE 2K17\MSVCR110.dll
0901/141237 [2B74] 0x00007FFCC3CE0000 (0x000DD000)  C:\WINDOWS\SYSTEM32\WINHTTP.dll
0901/141237 [2B74] 0x00007FFCCACB0000 (0x000BB000)  C:\WINDOWS\SYSTEM32\dxgi.dll
0901/141237 [2B74] 0x00007FFC8B7F0000 (0x003B6000)  D:\Games\WWE 2K17\D3DCOMPILER_46.dll
0901/141237 [2B74] 0x00007FFCC9F70000 (0x0002A000)  C:\WINDOWS\SYSTEM32\WINMMBASE.dll
0901/141237 [2B74] 0x00007FFCAA0C0000 (0x0002C000)  D:\Games\WWE 2K17\d3d11.dll
0901/141237 [2B74] 0x00007FFC97690000 (0x00108000)  D:\ninjaripper1.7.1\x64\intruder.dll
0901/141237 [2B74] 0x00007FFCBADB0000 (0x001C9000)  C:\WINDOWS\system32\dbghelp.dll
0901/141237 [2B74] 0x00007FFCBEC00000 (0x00029000)  C:\WINDOWS\SYSTEM32\dbgcore.DLL
0901/141237 [2B74] 0x00007FFCC00C0000 (0x00079000)  C:\WINDOWS\SYSTEM32\inputhost.dll
0901/141237 [2B74] 0x00007FFCCA230000 (0x000DA000)  C:\WINDOWS\SYSTEM32\CoreMessaging.dll
0901/141237 [2B74] 0x00007FFCC7AD0000 (0x0014D000)  C:\WINDOWS\SYSTEM32\wintypes.dll
0901/141237 [2B74] 0x00007FFCC64D0000 (0x0031E000)  C:\WINDOWS\SYSTEM32\CoreUIComponents.dll
0901/141237 [2B74] 0x00007FFCCAF10000 (0x00031000)  C:\WINDOWS\SYSTEM32\ntmarta.dll
0901/141237 [2B74] 0x00007FFCCF580000 (0x000A0000)  C:\WINDOWS\System32\clbcatq.dll
0901/141237 [2B74] 0x00007FFCCA6B0000 (0x00098000)  C:\WINDOWS\system32\uxtheme.dll
0901/141237 [2B74] 0x00007FFCCD650000 (0x00173000)  C:\WINDOWS\System32\MSCTF.dll
0901/141237 [2B74] 0x00007FFCCA7B0000 (0x00029000)  C:\WINDOWS\system32\dwmapi.dll
0901/141237 [2B74] 0x00007FFCC0020000 (0x00096000)  C:\WINDOWS\System32\TextInputFramework.dll
0901/141237 [2B74] 0x00007FFCCB4E0000 (0x00056000)  C:\WINDOWS\SYSTEM32\WINSTA.dll
0901/141237 [2B74] 0x00007FFC9AEC0000 (0x0008F000)  C:\WINDOWS\SYSTEM32\DSOUND.DLL
0901/141237 [2B74] 0x00007FFCC52C0000 (0x00076000)  C:\WINDOWS\System32\MMDevApi.dll
0901/141237 [2B74] 0x00007FFCCBC40000 (0x00027000)  C:\WINDOWS\System32\DEVOBJ.dll
0901/141237 [2B74] 0x00007FFCBEC30000 (0x0012C000)  C:\WINDOWS\SYSTEM32\AUDIOSES.DLL
0901/141237 [2B74] 0x00007FFCC69B0000 (0x0000A000)  C:\WINDOWS\SYSTEM32\AVRT.dll
0901/141237 [2B74] 0x00007FFCBE920000 (0x00010000)  C:\WINDOWS\SYSTEM32\XInput1_4.dll
0901/141237 [2B74] 0x00007FFCCD0C0000 (0x00008000)  C:\WINDOWS\System32\NSI.dll
0901/141237 [2B74] 0x00007FFCC17C0000 (0x0001A000)  C:\WINDOWS\SYSTEM32\dhcpcsvc.DLL
0901/141237 [2B74] 0x00007FFCC8C00000 (0x0030B000)  C:\WINDOWS\system32\d3d11.dll
0901/141237 [2B74] 0x00007FFCC94E0000 (0x0042F000)  C:\WINDOWS\SYSTEM32\d3dcompiler_47.dll
0901/141237 [2B74] 0x00007FFCCB840000 (0x00017000)  C:\WINDOWS\SYSTEM32\CRYPTSP.dll
0901/141237 [2B74] 0x00007FFC94310000 (0x0026F000)  C:\WINDOWS\SYSTEM32\d3dcompiler_43.dll
0901/141237 [2B74] 0x00007FFCC55E0000 (0x000EA000)  C:\WINDOWS\System32\DriverStore\FileRepository\nv_ref_pubwu.inf_amd64_2e7fa54192fe16d0\nvldumdx.dll
0901/141237 [2B74] 0x00007FFCC7F50000 (0x0000A000)  C:\WINDOWS\SYSTEM32\VERSION.dll
0901/141237 [2B74] 0x00007FFCCCD80000 (0x001E2000)  C:\WINDOWS\System32\crypt32.dll
0901/141237 [2B74] 0x00007FFCCBEB0000 (0x00012000)  C:\WINDOWS\System32\MSASN1.dll
0901/141237 [2B74] 0x00007FFCCC3E0000 (0x00057000)  C:\WINDOWS\System32\WINTRUST.DLL
0901/141237 [2B74] 0x00007FFCCFA10000 (0x0001D000)  C:\WINDOWS\System32\imagehlp.dll
0901/141237 [2B74] 0x00007FFCCB220000 (0x00033000)  C:\WINDOWS\system32\rsaenh.dll
0901/141237 [2B74] 0x00007FFCCB860000 (0x0000B000)  C:\WINDOWS\SYSTEM32\CRYPTBASE.dll
0901/141237 [2B74] 0x00007FFC7B180000 (0x01AEC000)  C:\WINDOWS\System32\DriverStore\FileRepository\nv_ref_pubwu.inf_amd64_2e7fa54192fe16d0\nvwgf2umx.dll
0901/141237 [2B74] 0x00007FFCBD000000 (0x001B7000)  C:\WINDOWS\system32\nvspcap64.dll
0901/141237 [2B74] 0x00007FFCCD7D0000 (0x0044B000)  C:\WINDOWS\System32\SETUPAPI.dll
0901/141237 [2B74] 0x00007FFCC6C20000 (0x00480000)  C:\WINDOWS\system32\nvapi64.dll
0901/141237 [2B74] 0x00007FFCCBD40000 (0x00030000)  C:\WINDOWS\SYSTEM32\SspiCli.dll
0901/141237 [2B74] 0x00007FFCC9FA0000 (0x0019C000)  C:\WINDOWS\SYSTEM32\dcomp.dll
0901/141237 [2B74] 0x00007FFCA5FC0000 (0x0008B000)  C:\WINDOWS\system32\XAudio2_7.dll
0901/141237 [2B74] 0x00007FFCCAB50000 (0x0000C000)  C:\WINDOWS\SYSTEM32\HID.DLL
0901/141237 [2B74] 0x00007FFCBEF10000 (0x002A6000)  C:\WINDOWS\SYSTEM32\iertutil.dll
0901/141237 [2B74] 0x00007FFCC17A0000 (0x00015000)  C:\WINDOWS\SYSTEM32\ondemandconnroutehelper.dll
0901/141237 [2B74] 0x00007FFCCB690000 (0x00066000)  C:\WINDOWS\system32\mswsock.dll
0901/141237 [2B74] 0x00007FFCC18F0000 (0x0000B000)  C:\WINDOWS\SYSTEM32\WINNSI.DLL
0901/141237 [2B74] 0x00007FFCAAF70000 (0x00016000)  C:\WINDOWS\system32\napinsp.dll
0901/141237 [2B74] 0x00007FFCAAF50000 (0x0001A000)  C:\WINDOWS\system32\pnrpnsp.dll
0901/141237 [2B74] 0x00007FFCC8700000 (0x00019000)  C:\WINDOWS\system32\NLAapi.dll
0901/141237 [2B74] 0x00007FFCCB400000 (0x000BE000)  C:\WINDOWS\SYSTEM32\DNSAPI.dll
0901/141237 [2B74] 0x00007FFCAEAD0000 (0x0000E000)  C:\WINDOWS\System32\winrnr.dll
0901/141237 [2B74] 0x00007FFCC4F90000 (0x00015000)  C:\WINDOWS\System32\wshbth.dll
0901/141237 [2B74] 0x00007FFCC0AE0000 (0x00072000)  C:\WINDOWS\System32\fwpuclnt.dll
0901/141237 [2B74] 0x00007FFCC0580000 (0x0000A000)  C:\Windows\System32\rasadhlp.dll
0901/141237 [2B74] LOG END
## Post #663
- Username: haluk444
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 13, 2016 6:49 am
- Post datetime: 2019-09-07T15:47:45+00:00
- Post Title: Re: Ninja Ripper

Hi,
I am trying to use NinjaRipper with Chrome or Firefox for Pinshape.com model ripping. My question is which versions of Ninja ripper (including x32 or 64) works on which version of chrome and firefox? I used to do that but I couldn't make it work now.
Thanks!
## Post #664
- Username: Moonday41
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 08, 2018 10:56 am
- Post datetime: 2019-09-12T16:27:05+00:00
- Post Title: Re: Ninja Ripper

Hello 

I am also trying to rip with Firefox or Chrome. As of right now when rip models it gives me meshes but they are only tangles or squares not the full object am I doing something wrong. if you really need a version of Firefox or Chrome to work with ripping models I would also like to know.
## Post #665
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-10-15T17:32:00+00:00
- Post Title: Re: Ninja Ripper

Hello,

There is a way to rip "damaged" 3d models from NFS Payback? with "damaged" I mean the cars, not the files 

Because if I use Ninjaripper in NFS Payback, it rip the game without damages... 

(I mean damages like this:)
[https://www.dropbox.com/s/09toxly0j9q24fm/0243.jpg?dl=0](https://www.dropbox.com/s/09toxly0j9q24fm/0243.jpg?dl=0)

Someone can help me, please?
## Post #666
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-15T17:36:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from Fiammanera628 ↑Wed Oct 16, 2019 1:32 am at Wed Oct 16, 2019 1:32 am
>
> Because if I use Ninjaripper in NFS Payback, it rip the game without damages...
Have you tried Frosty Tool Suite?: [http://frostytoolsuite.com/](http://frostytoolsuite.com/)
Just load the game in the editor, then navigate to your desired car mesh and see what you can export from it.
Join their discord server I think they know how to if you cant do it on your own.
## Post #667
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-10-15T17:40:52+00:00
- Post Title: Re: Ninja Ripper

> Reply from mono24 ↑Wed Oct 16, 2019 1:36 am at Wed Oct 16, 2019 1:36 am
>
> 
Fiammanera628 wrote: ↑Wed Oct 16, 2019 1:32 amBecause if I use Ninjaripper in NFS Payback, it rip the game without damages... 
Have you tried Frosty Tool Suite?: http://frostytoolsuite.com/
Just load the game in the editor, then navigate to your desired car mesh and see what you can export from it.
Join their discord server I think they know how to if you cant do it on your own.

Yes, I know the existence of Frosty Editor, but it take a looooooong time to process all the pieces... and also is it, it takes the mesh like Ninjaripper: without damages
## Post #668
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-15T17:44:27+00:00
- Post Title: Re: Ninja Ripper

> Reply from Fiammanera628 ↑Wed Oct 16, 2019 1:40 am at Wed Oct 16, 2019 1:40 am
>
> Yes, I know the existence of Frosty Editor, but it take a looooooong time to process all the pieces... and also is it, it takes the mesh like Ninjaripper: without damages
If I remember correctly their Havoc physics and those can NOT be exported I don't even think the format is even reversed.
NR is not good for any of this stuff anymore, you should avoid it.
## Post #669
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-10-15T17:48:37+00:00
- Post Title: Re: Ninja Ripper

> Reply from mono24 ↑Wed Oct 16, 2019 1:44 am at Wed Oct 16, 2019 1:44 am
>
> 
Fiammanera628 wrote: ↑Wed Oct 16, 2019 1:40 amYes, I know the existence of Frosty Editor, but it take a looooooong time to process all the pieces... and also is it, it takes the mesh like Ninjaripper: without damages  

If I remember correctly their Havoc physics and those can NOT be exported I don't even think the format is even reversed.
NR is not good for any of this stuff anymore, you should avoid it.

Mh... if Ninjaripper isn't good no more, what I can use for extract the damaged mesh?
## Post #670
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-15T18:47:26+00:00
- Post Title: Re: Ninja Ripper

> Reply from Fiammanera628 ↑Wed Oct 16, 2019 1:48 am at Wed Oct 16, 2019 1:48 am
>
> Mh... if Ninjaripper isn't good no more, what I can use for extract the damaged mesh?
As I said their NOT supported by any existing tools, unless Frosty might in the future, your out of luck for now.
## Post #671
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2019-10-15T19:33:13+00:00
- Post Title: Re: Ninja Ripper

> Reply from mono24 ↑Wed Oct 16, 2019 2:47 am at Wed Oct 16, 2019 2:47 am
>
> 
Fiammanera628 wrote: ↑Wed Oct 16, 2019 1:48 amMh... if Ninjaripper isn't good no more, what I can use for extract the damaged mesh?  
As I said their NOT supported by any existing tools, unless Frosty might in the future, your out of luck for now.

Oh, ok, thank you
## Post #672
- Username: Roseweave
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 26, 2019 6:43 am
- Post datetime: 2019-11-06T01:28:07+00:00
- Post Title: Re: Ninja Ripper

No matter what I do, I can't get Ninjaripper to work with Bluestacks. An older version(1.1) runs, but doesn't capture anything. I get an error message with 1.7.1 depending on whether or not I use the x64 or x86 version .

"inject helper debug APC inject failed. see injhelper.og" is what I get on x64(no log is actually generated) 

and

QueueUserApc() error. Win32 error code: 0x00000006

with the x86. 

I'm trying to rip models from Future Fight(which currently doesn't work  on NOX).
## Post #673
- Username: felixon555
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 28, 2017 12:14 pm
- Post datetime: 2019-11-23T23:48:22+00:00
- Post Title: Re: Ninja Ripper

Help me fix uv coordinates. Сhange of values does not affect.[https://ibb.co/MZDFqk5](https://ibb.co/MZDFqk5)
## Post #674
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-11-25T01:27:27+00:00
- Post Title: Re: Ninja Ripper

> Reply from Roseweave ↑Wed Nov 06, 2019 9:28 am at Wed Nov 06, 2019 9:28 am
>
> 
No matter what I do, I can't get Ninjaripper to work with Bluestacks. An older version(1.1) runs, but doesn't capture anything. I get an error message with 1.7.1 depending on whether or not I use the x64 or x86 version .

"inject helper debug APC inject failed. see injhelper.og" is what I get on x64(no log is actually generated) 

and

QueueUserApc() error. Win32 error code: 0x00000006

with the x86. 

I'm trying to rip models from Future Fight(which currently doesn't work  on NOX).

i believe BlueStacks and also NOX use OpenGL or Vulcan, neither use DirectX and Ninja Ripper only works with DirectX.
## Post #675
- Username: hesanda
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 03, 2014 12:35 pm
- Post datetime: 2019-11-26T05:18:14+00:00
- Post Title: Re: Ninja Ripper

trying to rip a game, that was brought back by the players. private server. the original came been shut down since 2011. anyway I get an error when I use dx9
1125/225059 [3FF4] Ninja Ripper 1.7.1 x64
1125/225059 [3FF4] © black_ninja, 2017

1125/225059 [3FF4] LOG START

1125/225059 [3FF4] Executable: D:\ninjaripper1.7.1_with_new_script\x64\injhelper.exe
1125/225059 [3FF4] Output directory: D:\XenRebirth\New folder\_NinjaRipper\2019.11.25_22.50.59_injhelper.exe_12360\
1125/225059 [3FF4] Win ver: 6.2 x64 

1125/225059 [3FF4] Inject mode: "intruder"
1125/225059 [3FF4] Texture downscale max width : 4096
1125/225059 [3FF4] Texture downscale max height: 4096
1125/225059 [3FF4] Texture downscale value: 2
1125/225059 [3FF4] LdrLoadDll hooked. Target: 0x00007FF8D6D957D0
1125/225059 [3FF4] LdrUnloadDll hooked. Target: 0x00007FF8D6D87AB0
1125/225059 [3FF4] CreateProcessA hooked. Target: 0x00007FF8D69EC100
1125/225059 [3FF4] CreateProcessW hooked. Target: 0x00007FF8D69EC290
1125/225059 [3FF4] CreateProcessAsUserW hooked. Target: 0x00007FF8D6C8C1B0
1125/225059 [3FF4] CreateProcessWithLogonW hooked. Target: 0x00007FF8D6CB2E20
1125/225059 [3FF4] CreateProcessWithTokenW hooked. Target: 0x00007FF8D6C72C70
1125/225059 [3FF4] SetTokenInformation hooked. Target: 0x00007FF8D6C9C780
1125/225100 [3FF4] Loaded Modules List
1125/225100 [3FF4] ----------------------------------------
1125/225100 [3FF4] BaseAddr            Size         Module
1125/225100 [3FF4] ----------------------------------------
1125/225100 [3FF4] 0x00007FF7364D0000 (0x00027000)  D:\ninjaripper1.7.1_with_new_script\x64\injhelper.exe
1125/225100 [3FF4] 0x00007FF8D6D50000 (0x001ED000)  C:\Windows\SYSTEM32\ntdll.dll
1125/225100 [3FF4] 0x00007FF8D69D0000 (0x000B3000)  C:\Windows\System32\KERNEL32.DLL
1125/225100 [3FF4] 0x00007FF8D3BC0000 (0x00293000)  C:\Windows\System32\KERNELBASE.dll
1125/225100 [3FF4] 0x00007FF8D1080000 (0x0008C000)  C:\Windows\SYSTEM32\apphelp.dll
1125/225100 [3FF4] 0x00007FF8D5640000 (0x00197000)  C:\Windows\System32\USER32.dll
1125/225100 [3FF4] 0x00007FF8D3F50000 (0x00020000)  C:\Windows\System32\win32u.dll
1125/225100 [3FF4] 0x00007FF8D62A0000 (0x00029000)  C:\Windows\System32\GDI32.dll
1125/225100 [3FF4] 0x00007FF8D2E10000 (0x00199000)  C:\Windows\System32\gdi32full.dll
1125/225100 [3FF4] 0x00007FF8D3E80000 (0x000A0000)  C:\Windows\System32\msvcp_win.dll
1125/225100 [3FF4] 0x00007FF8D3AC0000 (0x000FA000)  C:\Windows\System32\ucrtbase.dll
1125/225100 [3FF4] 0x00007FF8D6C70000 (0x000A3000)  C:\Windows\System32\ADVAPI32.dll
1125/225100 [3FF4] 0x00007FF8D4040000 (0x0009E000)  C:\Windows\System32\msvcrt.dll
1125/225100 [3FF4] 0x00007FF8D6680000 (0x0009E000)  C:\Windows\System32\sechost.dll
1125/225100 [3FF4] 0x00007FF8D6B40000 (0x00122000)  C:\Windows\System32\RPCRT4.dll
1125/225100 [3FF4] 0x00007FF8D40E0000 (0x014F4000)  C:\Windows\System32\SHELL32.dll
1125/225100 [3FF4] 0x00007FF8D2FB0000 (0x0004A000)  C:\Windows\System32\cfgmgr32.dll
1125/225100 [3FF4] 0x00007FF8D59C0000 (0x000A8000)  C:\Windows\System32\shcore.dll
1125/225100 [3FF4] 0x00007FF8D5EF0000 (0x0032C000)  C:\Windows\System32\combase.dll
1125/225100 [3FF4] 0x00007FF8D3240000 (0x0007E000)  C:\Windows\System32\bcryptPrimitives.dll
1125/225100 [3FF4] 0x00007FF8D32C0000 (0x0074D000)  C:\Windows\System32\windows.storage.dll
1125/225100 [3FF4] 0x00007FF8D2D60000 (0x00024000)  C:\Windows\System32\profapi.dll
1125/225100 [3FF4] 0x00007FF8D2D90000 (0x0005D000)  C:\Windows\System32\powrprof.dll
1125/225100 [3FF4] 0x00007FF8D67D0000 (0x00052000)  C:\Windows\System32\shlwapi.dll
1125/225100 [3FF4] 0x00007FF8D2DF0000 (0x00011000)  C:\Windows\System32\kernel.appcore.dll
1125/225100 [3FF4] 0x00007FF8D3E60000 (0x00017000)  C:\Windows\System32\cryptsp.dll
1125/225100 [3FF4] 0x00007FF8D6720000 (0x0002E000)  C:\Windows\System32\IMM32.DLL
1125/225100 [3FF4] 0x00007FF8BA9F0000 (0x00108000)  D:\ninjaripper1.7.1_with_new_script\x64\intruder.dll
1125/225100 [3FF4] 0x00007FF8C4C80000 (0x001ED000)  C:\Windows\system32\dbghelp.dll
1125/225100 [3FF4] 0x00007FF8C4880000 (0x0002A000)  C:\Windows\SYSTEM32\dbgcore.DLL
1125/225100 [3FF4] 0x00007FF8D1330000 (0x0009C000)  C:\Windows\system32\uxtheme.dll
1125/225100 [3FF4] 0x00007FF8D6510000 (0x0016C000)  C:\Windows\System32\MSCTF.dll
1125/225100 [3FF4] 0x00007FF8D3F70000 (0x000C4000)  C:\Windows\System32\OLEAUT32.dll
1125/225100 [3FF4] 0x00007FF8D1660000 (0x0002E000)  C:\Windows\system32\dwmapi.dll
1125/225100 [3FF4] 0x00007FF8D3000000 (0x001DB000)  C:\Windows\System32\CRYPT32.dll
1125/225100 [3FF4] 0x00007FF8D2D40000 (0x00012000)  C:\Windows\System32\MSASN1.dll
1125/225100 [3FF4] 0x00007FF8C22D0000 (0x00095000)  C:\Windows\System32\TextInputFramework.dll
1125/225100 [3FF4] 0x00007FF8CEC10000 (0x00322000)  C:\Windows\System32\CoreUIComponents.dll
1125/225100 [3FF4] 0x00007FF8D0CF0000 (0x000E2000)  C:\Windows\System32\CoreMessaging.dll
1125/225100 [3FF4] 0x00007FF8D1DB0000 (0x00031000)  C:\Windows\SYSTEM32\ntmarta.dll
1125/225100 [3FF4] 0x00007FF8CE9D0000 (0x00153000)  C:\Windows\SYSTEM32\wintypes.dll
1125/225100 [3FF4] 0x00007FF8D57E0000 (0x00155000)  C:\Windows\System32\ole32.dll
1125/225100 [3FF4] 0x00007FF8D6280000 (0x00008000)  C:\Windows\System32\psapi.dll
1125/225100 [3FF4] LOG END

if I use intruder inject I get an error 
ERROR: inject helper debug apc inject failed see injhelper.log 

ERROR: APC injection failed. Err: 0x%08X. Win32 error: 0x00000006
## Post #676
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2019-12-05T08:30:21+00:00
- Post Title: Re: Ninja Ripper

Hy there,

just have one question for ninja ripper importer.
How to correctly import mesh NORMALS from model, because they are messed up after importing?

Thanks.
## Post #677
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2019-12-14T17:25:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from an90dy905909 ↑Thu Dec 05, 2019 4:30 pm at Thu Dec 05, 2019 4:30 pm
>
> 
Hy there,

just have one question for ninja ripper importer.
How to correctly import mesh NORMALS from model, because they are messed up after importing?

Thanks.
If you are importing ripped meshes into Blender, you can take a look at the [Using Blender Instead of Noesis] section [HERE](https://open3dlab.com/tutorials/view/16/), or take a look at how to prepare/clean your 3D mesh [HERE](https://open3dlab.com/tutorials/view/15/#prepmesh).
## Post #678
- Username: DHR
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jul 01, 2019 6:10 am
- Post datetime: 2019-12-15T18:13:08+00:00
- Post Title: Re: Ninja Ripper

Can someone help me, is it possible to use Ninjaripper and import the whole scene as if every object's pivot's coords were 0 0 0

It messes up the whole scene, I want to rip a car but when I import it in max, literally every part is misaligned and has different scale
## Post #679
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-12T17:15:03+00:00
- Post Title: Re: Ninja Ripper

Hi,

Is still possible to rip games from Xenia emulator with Ninjaripper? Or other Xbox 360 / Xbox 1 emulator?
## Post #680
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2020-01-19T19:31:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from DHR ↑Mon Dec 16, 2019 2:13 am at Mon Dec 16, 2019 2:13 am
>
> 
Can someone help me, is it possible to use Ninjaripper and import the whole scene as if every object's pivot's coords were 0 0 0

It messes up the whole scene, I want to rip a car but when I import it in max, literally every part is misaligned and has different scale
I believe this behavior happens depending on the type of game or maybe platform/emulator, but I'm not 100% sure. 

> Reply from Fiammanera628 ↑Mon Jan 13, 2020 1:15 am at Mon Jan 13, 2020 1:15 am
>
> 
Hi,

Is still possible to rip games from Xenia emulator with Ninjaripper? Or other Xbox 360 / Xbox 1 emulator?
If these emulators support directX, there maybe a chance, but I can't make any promises since I have very little experience with ripping from emulators.
## Post #681
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-01-19T20:21:02+00:00
- Post Title: Re: Ninja Ripper

> If these emulators support directX, there maybe a chance, but I can't make any promises since I have very little experience with ripping from emulators.

Yes, it does but Xenia support only the D3D12 one!
## Post #682
- Username: gururu18
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 17, 2019 1:41 pm
- Post datetime: 2020-01-22T02:30:53+00:00
- Post Title: Re: Ninja Ripper

Hello. Are the dynamic meshes of long skirts and long hair unable to rip? Many models I extracted from the game lack similar parts. I also checked all the rip files.

The picture is the character I extracted. On the right is the model after rip. The front of the sleeve and the bottom of the skirt are missing.
## Post #683
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2020-02-01T22:57:15+00:00
- Post Title: Re: Ninja Ripper

> Reply from Fiammanera628 ↑Mon Jan 20, 2020 4:21 am at Mon Jan 20, 2020 4:21 am
>
> 
If these emulators support directX, there maybe a chance, but I can't make any promises since I have very little experience with ripping from emulators.

Yes, it does but Xenia support only the D3D12 one!

Any luck ripping with the D3D11 Wrapper method? 
If the game you are ripping from is using a popular game engine, there may already be an extraction tool that can do a better job than Ninja Ripper. 
You may have to look around here on the forums. 

> Reply from gururu18 ↑Wed Jan 22, 2020 10:30 am at Wed Jan 22, 2020 10:30 am
>
> 
Hello. Are the dynamic meshes of long skirts and long hair unable to rip? Many models I extracted from the game lack similar parts. I also checked all the rip files.

The picture is the character I extracted. On the right is the model after rip. The front of the sleeve and the bottom of the skirt are missing. In that screenshot, which 3D program are you using to view that 3D model? 
It's possible that other parts of the 3D model maybe ripped as separate objects.
## Post #684
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-02-02T10:27:03+00:00
- Post Title: Re: Ninja Ripper

> Reply from Curtain ↑Sun Feb 02, 2020 6:57 am at Sun Feb 02, 2020 6:57 am
>
> 
If these emulators support directX, there maybe a chance, but I can't make any promises since I have very little experience with ripping from emulators.

Yes, it does but Xenia support only the D3D12 one!

> Any luck ripping with the D3D11 Wrapper method? 
>
> If the game you are ripping from is using a popular game engine, there may already be an extraction tool that can do a better job than Ninja Ripper. 
>
> You may have to look around here on the forums.

The game is famous yes (is Burnout Revenge) and also the game engine (Renderware), but nothing and nobody helps me about it.
Xenia, instead, as no D3D11 wrapper, nowadays, has got only D3D12 wrapper.
## Post #685
- Username: gururu18
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 17, 2019 1:41 pm
- Post datetime: 2020-02-04T08:09:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from Curtain ↑Sun Feb 02, 2020 6:57 am at Sun Feb 02, 2020 6:57 am
>
> 
Fiammanera628 wrote: ↑Mon Jan 20, 2020 4:21 am
If these emulators support directX, there maybe a chance, but I can't make any promises since I have very little experience with ripping from emulators.

Yes, it does but Xenia support only the D3D12 one!  


Any luck ripping with the D3D11 Wrapper method? 
If the game you are ripping from is using a popular game engine, there may already be an extraction tool that can do a better job than Ninja Ripper. 
You may have to look around here on the forums. 
gururu18 wrote: ↑Wed Jan 22, 2020 10:30 am
Hello. Are the dynamic meshes of long skirts and long hair unable to rip? Many models I extracted from the game lack similar parts. I also checked all the rip files.

The picture is the character I extracted. On the right is the model after rip. The front of the sleeve and the bottom of the skirt are missing.


 In that screenshot, which 3D program are you using to view that 3D model? 
It's possible that other parts of the 3D model maybe ripped as separate objects.

Thank you for your reply. The pictures on the right are viewed with Blender. I also use Noesis. I checked them one by one. But I did not find these missing parts.
## Post #686
- Username: Penningrothmatt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 08, 2020 12:22 am
- Post datetime: 2020-03-07T16:31:12+00:00
- Post Title: Re: Ninja Ripper

I have a few questions. I'm trying to extract a race track from a certain racing title and I need help on how to extract every part of the racing surface, and not just a certain part? My second question when I rip the mesh I'm getting the graphical racing surface in terms of the textures, but how do I know whether or not I'm getting the physical racing surface such as the loft?
## Post #687
- Username: Fiammanera628
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jan 08, 2018 1:51 am
- Post datetime: 2020-03-13T18:29:06+00:00
- Post Title: Re: Ninja Ripper

In 2020 there is still a hope to rip from PCSX2 1.5.x's games using Ninjaripper?  
I mean, without getting flat 3d models, of course
## Post #688
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2020-03-16T08:19:04+00:00
- Post Title: Re: Ninja Ripper

> Reply from Fiammanera628 ↑Sat Mar 14, 2020 2:29 am at Sat Mar 14, 2020 2:29 am
>
> 
In 2020 there is still a hope to rip from PCSX2 1.5.x's games using Ninjaripper?  
I mean, without getting flat 3d models, of course

No hope. Project is closed))
## Post #689
- Username: illyriana
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 26, 2020 1:19 am
- Post datetime: 2020-03-25T17:32:53+00:00
- Post Title: Re: Ninja Ripper

Looking for some advice with Ninja Ripper against a game.

I am currently trying to pull some DLC files from Conan Exiles. The dev team has made it near physically impossible to access and edit game files (even if you own the DLC) and while I love a few of the outfits I'd honestly just love to pull them, examine them and play around with them on my end. I have no intention of "uploading them to conan to bypass buying them" as the devs seem to fear. Personal project.

I've tried every single setting and option I can think of with ninja ripper. Landscapes and environments load perfectly fine. However, anything character/outfit related has its UV and mesh absolutely shredded. After trying everything in the books I can only assume this is some sort of protection built into the game?

Sadly the Dev Kit only works for non-dlc items. And UE Viewer seems to not work due to everything having some special coding to block it? (Or at least every form under the sun states so.) If Anyone has any input on what might be causing this or if there's a fix I'd be appreciative. Thank you!
[ball.PNG](https://xentaxbackup.github.io/file/17806_ball.PNG)
## Post #690
- Username: juanmasilsca
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 24, 2019 12:34 am
- Post datetime: 2020-04-07T15:05:19+00:00
- Post Title: Re: Ninja Ripper

I've tried with a couple of games in NOX and all i get is a bunch of folders with logs txt files. I can't even delete them without restart my PC first. Says some application is using them...
Any idea?

Here the log:

0407/152536 [53B8] Ninja Ripper 1.7.1 x86
0407/152536 [53B8] © black_ninja, 2017

0407/152536 [53B8] LOG START

0407/152536 [53B8] Executable: C:\Program Files (x86)\Nox\bin\Nox.exe
0407/152536 [53B8] Output directory: C:\Users\juanm\Documents\NinjaRipper\_NinjaRipper\2020.04.07_15.25.36_Nox.exe_24592\
0407/152536 [53B8] Win ver: 6.2 x64 

0407/152536 [53B8] Inject mode: "intruder"
0407/152536 [53B8] Texture downscale max width : 4096
0407/152536 [53B8] Texture downscale max height: 4096
0407/152536 [53B8] Texture downscale value: 2
0407/152536 [53B8] LdrLoadDll hooked. Target: 0x77CB4C80
0407/152536 [53B8] LdrUnloadDll hooked. Target: 0x77CB5780
0407/152536 [53B8] CreateProcessA hooked. Target: 0x754E4060
0407/152536 [53B8] CreateProcessW hooked. Target: 0x754C9EF0
0407/152536 [53B8] CreateProcessAsUserW hooked. Target: 0x77BFFD30
0407/152536 [53B8] CreateProcessWithLogonW hooked. Target: 0x77C26C50
0407/152536 [53B8] CreateProcessWithTokenW hooked. Target: 0x77C26C90
0407/152536 [53B8] SetTokenInformation hooked. Target: 0x77C03B90
0407/152537 [53B8] D3D11.DLL loaded
0407/152537 [53B8] D3D11 ripper init
0407/152537 [53B8] D3D11CreateDeviceAndSwapChain hooked. Target: 0x0F2D4060
0407/152537 [53B8] D3D11CreateDevice hooked. Target: 0x0F2D4130
0407/152537 [53B8] DXGI init
0407/152537 [53B8] CreateDXGIFactory hooked. Target: 0x6FFBA3C0
0407/152537 [53B8] CreateDXGIFactory1 hooked. Target: 0x6FFBD5F0
0407/152537 [19BC] CreateProcessW("tasklist  /FI "Imagename eq NoxVMSVC.exe" -nh") return: 1
0407/152537 [19BC] Injecting to child process. Status: OK
0407/152537 [69D8] CreateProcessW("tasklist  /FI "Imagename eq Nox.exe" -nh") return: 1
0407/152537 [69D8] Injecting to child process. Status: OK
0407/152538 [19BC] CreateProcessW("7za.exe  e -p347829 -oC:\Users\juanm\ C:\Users\juanm\d4ac4633ebd6440fa397b84f1bc94a3c.7z") return: 1
0407/152538 [19BC] Injecting to child process. Status: OK
0407/152539 [69D8] CreateProcessW("cmd  /c "netstat -an -p tcp |findstr -i LISTENING") return: 1
0407/152539 [69D8] Injecting to child process. Status: OK
0407/152539 [69D8] CreateProcessW("netstat  -an -p udp") return: 1
0407/152539 [69D8] Injecting to child process. Status: OK
0407/152540 [69D8] CreateProcessW("netstat  -an -p udp") return: 1
0407/152540 [69D8] Injecting to child process. Status: OK
0407/152541 [69D8] CreateProcessW("cmd  /c "netstat -an -p tcp | findstr -i LISTENING") return: 1
0407/152541 [69D8] Injecting to child process. Status: OK
0407/152541 [69D8] CreateProcessW("netstat  -an -p udp") return: 1
0407/152541 [69D8] Injecting to child process. Status: OK
0407/152555 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152555 [725C] Injecting to child process. Status: OK
0407/152556 [4A80] CreateProcessW("systeminfo") return: 1
0407/152556 [4A80] Injecting to child process. Status: OK
0407/152557 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152557 [725C] Injecting to child process. Status: OK
0407/152559 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152559 [725C] Injecting to child process. Status: OK
0407/152601 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152601 [725C] Injecting to child process. Status: OK
0407/152603 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152603 [725C] Injecting to child process. Status: OK
0407/152605 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152605 [725C] Injecting to child process. Status: OK
0407/152606 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152606 [725C] Injecting to child process. Status: OK
0407/152609 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152609 [725C] Injecting to child process. Status: OK
0407/152610 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152610 [725C] Injecting to child process. Status: OK
0407/152612 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152612 [725C] Injecting to child process. Status: OK
0407/152614 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152614 [725C] Injecting to child process. Status: OK
0407/152616 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152616 [725C] Injecting to child process. Status: OK
0407/152617 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152617 [725C] Injecting to child process. Status: OK
0407/152620 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152620 [725C] Injecting to child process. Status: OK
0407/152621 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152621 [725C] Injecting to child process. Status: OK
0407/152623 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152623 [725C] Injecting to child process. Status: OK
0407/152625 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152625 [725C] Injecting to child process. Status: OK
0407/152627 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152627 [725C] Injecting to child process. Status: OK
0407/152629 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152629 [725C] Injecting to child process. Status: OK
0407/152631 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152631 [725C] Injecting to child process. Status: OK
0407/152632 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152632 [725C] Injecting to child process. Status: OK
0407/152634 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152634 [725C] Injecting to child process. Status: OK
0407/152636 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152636 [725C] Injecting to child process. Status: OK
0407/152638 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152638 [725C] Injecting to child process. Status: OK
0407/152640 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152640 [725C] Injecting to child process. Status: OK
0407/152642 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152642 [725C] Injecting to child process. Status: OK
0407/152643 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152643 [725C] Injecting to child process. Status: OK
0407/152646 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152646 [725C] Injecting to child process. Status: OK
0407/152647 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152647 [725C] Injecting to child process. Status: OK
0407/152649 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152649 [725C] Injecting to child process. Status: OK
0407/152651 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152651 [725C] Injecting to child process. Status: OK
0407/152653 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152653 [725C] Injecting to child process. Status: OK
0407/152655 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152655 [725C] Injecting to child process. Status: OK
0407/152657 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152657 [725C] Injecting to child process. Status: OK
0407/152658 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152658 [725C] Injecting to child process. Status: OK
0407/152700 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152700 [725C] Injecting to child process. Status: OK
0407/152702 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152702 [725C] Injecting to child process. Status: OK
0407/152704 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152704 [725C] Injecting to child process. Status: OK
0407/152706 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152706 [725C] Injecting to child process. Status: OK
0407/152708 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152708 [725C] Injecting to child process. Status: OK
0407/152709 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152709 [725C] Injecting to child process. Status: OK
0407/152712 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152712 [725C] Injecting to child process. Status: OK
0407/152713 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152713 [725C] Injecting to child process. Status: OK
0407/152716 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152716 [725C] Injecting to child process. Status: OK
0407/152717 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152717 [725C] Injecting to child process. Status: OK
0407/152719 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152719 [725C] Injecting to child process. Status: OK
0407/152721 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152721 [725C] Injecting to child process. Status: OK
0407/152723 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152723 [725C] Injecting to child process. Status: OK
0407/152724 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152724 [725C] Injecting to child process. Status: OK
0407/152727 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152727 [725C] Injecting to child process. Status: OK
0407/152728 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152728 [725C] Injecting to child process. Status: OK
0407/152730 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152730 [725C] Injecting to child process. Status: OK
0407/152732 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152732 [725C] Injecting to child process. Status: OK
0407/152734 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152734 [725C] Injecting to child process. Status: OK
0407/152736 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152736 [725C] Injecting to child process. Status: OK
0407/152738 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152738 [725C] Injecting to child process. Status: OK
0407/152739 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152739 [725C] Injecting to child process. Status: OK
0407/152741 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152741 [725C] Injecting to child process. Status: OK
0407/152743 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152743 [725C] Injecting to child process. Status: OK
0407/152745 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152745 [725C] Injecting to child process. Status: OK
0407/152747 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152747 [725C] Injecting to child process. Status: OK
0407/152749 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152749 [725C] Injecting to child process. Status: OK
0407/152750 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152750 [725C] Injecting to child process. Status: OK
0407/152753 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152753 [725C] Injecting to child process. Status: OK
0407/152754 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152754 [725C] Injecting to child process. Status: OK
0407/152756 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152756 [725C] Injecting to child process. Status: OK
0407/152758 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152758 [725C] Injecting to child process. Status: OK
0407/152800 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152800 [725C] Injecting to child process. Status: OK
0407/152801 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152801 [725C] Injecting to child process. Status: OK
0407/152804 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152804 [725C] Injecting to child process. Status: OK
0407/152805 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152805 [725C] Injecting to child process. Status: OK
0407/152807 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152807 [725C] Injecting to child process. Status: OK
0407/152809 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152809 [725C] Injecting to child process. Status: OK
0407/152811 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152811 [725C] Injecting to child process. Status: OK
0407/152813 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152813 [725C] Injecting to child process. Status: OK
0407/152814 [6AE0] CreateProcessW("7za.exe  a -p347829 C:\Users\juanm\d4ac4633ebd6440fa397b84f1bc94a3c.7z C:\Users\juanm\rule.xml C:\Users\juanm\state.xml") return: 1
0407/152814 [6AE0] Injecting to child process. Status: OK
0407/152815 [725C] CreateProcessW("taskkill  /F /IM kadb.exe /T") return: 1
0407/152815 [725C] Injecting to child process. Status: OK
0407/152815 [53B8] CreateProcessW("tasklist  /FI "Imagename eq Nox.exe" -nh") return: 1
0407/152815 [53B8] Injecting to child process. Status: OK
0407/152816 [53B8] CreateProcessW("taskkill  /F /IM nox_adb.exe /T") return: 1
0407/152816 [53B8] Injecting to child process. Status: OK
0407/152816 [725C] CreateProcessW("nox_adb  connect 127.0.0.1:62001") return: 1
0407/152816 [725C] Injecting to child process. Status: OK
## Post #691
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2020-04-12T15:27:46+00:00
- Post Title: Re: Ninja Ripper

Sorry if this was the wrong place for it, kind of a vague subject and hard to choose one. Anyways what's anyone's knowhow here when it comes to ripping from Android emulators, like Bluestacks and such? Years ago Ninja Ripper worked well for this, likewise 3D DX could capture just about anything granted many flaws that would have to fixed. Now and I am assuming it has to do with the emulators frequent updates as well in 3D DX's case not being updated for over a decade it seems to be an impossible task. NR doesn't seem to capture anything modern for that matter anymore at least on current Win systems. This is again from my own station so asking as maybe someone has had better luck. I like direct conversion better myself however especially in the case of many Android games they use very rare file types that can't be cracked. TMNT Legends is my specific one right now. Someone ripped it previously using NR and Bluestacks however they were different old versions then. The same ripper before seemingly bowing out had noted on their page problems with newer then now obsolete versions of BS to the point of being unable to rip anymore. Of course the solution would be to use an old version of the emulator but this emulator auto checks for it's own updates instead so it doesn't work like that. Anyways I'm trying to meet a request here so any help is appreciated.
## Post #692
- Username: Curtain
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Apr 18, 2017 2:13 am
- Post datetime: 2020-04-27T08:00:46+00:00
- Post Title: Re: Ninja Ripper

> Reply from SickAlice ↑Sun Apr 12, 2020 11:27 pm at Sun Apr 12, 2020 11:27 pm
>
> 
Sorry if this was the wrong place for it, kind of a vague subject and hard to choose one. Anyways what's anyone's knowhow here when it comes to ripping from Android emulators, like Bluestacks and such? Years ago Ninja Ripper worked well for this, likewise 3D DX could capture just about anything granted many flaws that would have to fixed. Now and I am assuming it has to do with the emulators frequent updates as well in 3D DX's case not being updated for over a decade it seems to be an impossible task. NR doesn't seem to capture anything modern for that matter anymore at least on current Win systems. This is again from my own station so asking as maybe someone has had better luck. I like direct conversion better myself however especially in the case of many Android games they use very rare file types that can't be cracked. TMNT Legends is my specific one right now. Someone ripped it previously using NR and Bluestacks however they were different old versions then. The same ripper before seemingly bowing out had noted on their page problems with newer then now obsolete versions of BS to the point of being unable to rip anymore. Of course the solution would be to use an old version of the emulator but this emulator auto checks for it's own updates instead so it doesn't work like that. Anyways I'm trying to meet a request here so any help is appreciated.
I wish I had an answer for you. 

I don't have any experience with ripping from mobile games, but if Ninja Ripper isn't working with those emulators, I wonder if software like RenderDoc or apitrace can do it? I haven't experimented with those 2 programs yet. 

Any luck with the folks from ZenHax forums? 

I'm sure someone will eventually post here with some type of solution.
## Post #693
- Username: FreakazoidRobot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 26, 2020 12:45 pm
- Post datetime: 2020-05-26T05:10:04+00:00
- Post Title: Re: Ninja Ripper

I'm really struggling to get everything working properly. First of all, if I use any of the scripts to import a Trials of Mana ripped mesh directly into Blender, I get a long line instead of the model. Noesis displays the mesh properly, although I'm not sure why they are a gold color, which I assume is from the normal map. I can then export the mesh, normal map, and diffuse map individually from there to Blender without any problems. The mesh shows up fine in the object view, but the UV Map Layout in the UV Map Editor is just a straight line (yes, with the entire model selected). I can unwrap the model into a new layout if I want, but then it won't fit the diffuse map. Also, I'm completely new at this, but the normal map seems to use right handed coordinates and I think Blender uses left handed. Do I need to invert the channels of the image to get it to work? Also, I wanted to mention a problem that I did discover the solution for, which is that all the normals for the meshes were pointed inward and needed to be pointed outward before they can be painted on.
## Post #694
- Username: ddadd
- Rank: advanced
- Number of posts: 73
- Joined date: Fri Mar 20, 2020 8:58 am
- Post datetime: 2020-05-30T20:25:10+00:00
- Post Title: Re: Ninja Ripper

Hello is it possible you could make a Ninja ripper for mame? Mame writes data to the cpu and the cpu processes it. is their a way to get the model data from the cpu with ninja ripper? please if not make a new version. Thanks
## Post #695
- Username: FreakazoidRobot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue May 26, 2020 12:45 pm
- Post datetime: 2020-06-13T03:06:29+00:00
- Post Title: Re: Ninja Ripper

OK, since this seems like the most active Ninja Ripper forum, I'm going to use this as a space to post problems I've had with Ninja Ripper and how I fixed them. (I'm exclusively using Blender at the moment)

1) The Blender script to import RIP files produces a long straight line instead of the appropriate meshes. Solution: give up on the scripts and use Noesis to export the meshes to a format Blender understands instead.

2) The UV Layout is screwed up. It might be a long thin line or a random jumble of lines that don't even fit on the UV grid. The Ninja Ripper guide suggests that you use "forced mode" in Ninja Ripper to get more duplicates of the mesh you want until one of them has the correct layout. This has not worked for me. All of the meshes have the exact same UV. Solution: you'll have to unwrap it yourself, sucker! Good luck lining up all the islands to your texture.

3) Cannot paint on the meshes. Solution: the normals are screwed up. You'll have to flip them, set them to point outside, and/or set them to faces using "mesh->normals->?" in edit mode. Also, if you're a n00b like me, it's helpful to know that normals and normal maps have nothing to do with each other.

4) Mesh is the right general shape, but surfaces aren't smooth like they're suppose to be. Solution: See #2. Setting normals to faces seems to solve this problem.

5) In the UV editor, I notice that I have a lot of random faces as their own islands, not connected to anything else. Solution: Ninja Ripper seems to detach vertices along the seams of meshes. This is why they'll unwrap into islands that more or less conform to the textures you got with it, even though there are no seams. Unfortunately, Ninja Ripper screws this up and creates random unattached faces in the process. To fix this problem, first use the current unwrap you have to choose seams for the mesh in UV Edit mode. Then, still in edit mode, select all, and use "vertices->merge->merge by distance" to connect all the overlapping vertices with each other. Then, you can unwrap the model again using the seams you just created and the unconnected faces will be gone.

6) Trying to loop select is a pain in the butt. Solution: Ninja Ripper loves using lots of triangles. Try going to edit mode, selecting all, and using Face->Tris to Quads to make more loops. 

7) What are these gold textures that look so similar to the diffuse textures that go with the meshes? Solution: they are normal maps. The reason they are gold instead of the blue you normally see in Blender is because they are "right" instead of "left." I'm honestly not sure what affect that has on using them in Blender, because I'm still trying to decide if it's even worth using these textures. Considering problems #2 and #5, it may be easier to just make my own textures than use those created by Nina Ripper.
## Post #696
- Username: Migs1190
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 24, 2020 5:58 am
- Post datetime: 2020-07-23T22:06:58+00:00
- Post Title: Re: Ninja Ripper

> Reply from FreakazoidRobot ↑Sat Jun 13, 2020 11:06 am at Sat Jun 13, 2020 11:06 am
>
> 
1) The Blender script to import RIP files produces a long straight line instead of the appropriate meshes. Solution: give up on the scripts and use Noesis to export the meshes to a format Blender understands instead.
That didn't work for me 
do you know if that's a ninjaripper problem or if it is from the game itself?
## Post #697
- Username: kuro0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 28, 2020 5:51 pm
- Post datetime: 2020-12-30T09:46:18+00:00
- Post Title: Re: Ninja Ripper

Hello i have problem in ninjaripper when open the app as administrator there's error message showing "only run from ripper" even when open it normally could anyone help me with this ^^
## Post #698
- Username: Evil Ash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 09, 2018 6:21 pm
- Post datetime: 2021-01-10T12:23:18+00:00
- Post Title: Re: Ninja Ripper

Hi i want to rip a scene made with gmod, how can i do that without T-Pose ? Thx
## Post #699
- Username: MarKreationsStudios
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 03, 2020 5:47 am
- Post datetime: 2021-01-10T22:31:50+00:00
- Post Title: Re: Ninja Ripper

Hey guys sorry for reviving an old thread, but I need help. I don't know if this has been resolved on here already, but has anybody figured out a way to properly rip models from PCSX2? I have the latest versions of both programs, so can anybody help out?
## Post #700
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2021-01-15T17:26:38+00:00
- Post Title: Re: Ninja Ripper

anyone else getting these weird rips?
these are models ripped from a game that previously i had ripped successfully before..
using NR 1.7.1 for first time rip, and this time, and game is cracked, so no auto-updates to the game, which again, worked well before with NR
[https://i.imgur.com/9SlULmb.png](https://i.imgur.com/9SlULmb.png)
[https://i.imgur.com/8j2JBWW.png](https://i.imgur.com/8j2JBWW.png)
[https://i.imgur.com/UqwmJMS.png](https://i.imgur.com/UqwmJMS.png)

any idea what i can do to get the rips working again?
## Post #701
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2021-01-17T00:23:56+00:00
- Post Title: Re: Ninja Ripper

> Reply from ricmetal ↑Sat Jan 16, 2021 1:26 am at Sat Jan 16, 2021 1:26 am
>
> 
worked well before with NR
It's a half of the story - threre are a number of .rip importers, you sure you're using the same one?
Game name would help too.
## Post #702
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2021-01-17T01:47:24+00:00
- Post Title: Re: Ninja Ripper

yeah, im using the same .rip importers. i've got a 2.79b blender folder for that belnder's rip plugin, i made a while back, which used to show the meshes correctly. same goes to noesis and 3ds max. all these are old installs. all these ways to see/edit the ripped meshes shows them screwed up in the same way (images above).

the game(s) is dead island definite edition and dying light. i used to be able to rip dying light correctly, dead island im not so sure i tried previsouly, but both get the same gargled results, as shown in the images above. and dying light i def used to rip meshes, with the same setup i have now.

id venture a guess that dying light got update through steam to break NR's functionality (if at all possible) but dead island isent connected to any update service, and they both get the same types of screwed up meshes.
## Post #703
- Username: hatehatehate
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 14, 2021 7:15 am
- Post datetime: 2021-01-18T07:50:15+00:00
- Post Title: Re: Ninja Ripper

Has anyone ripped from Tales of Vesperia: Definitive Edition? None of the wrappers work aside from DX11, which only works when forced to rip. When forced, it'll manage to rip a handful of random (tiny/useless) models before crashing. Hoping someone might have a fix or workaround for this.
## Post #704
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2021-02-10T04:07:02+00:00
- Post Title: Re: Ninja Ripper

Does Ninjaripper work with 3d.nicovidio? 
I'm using Chrome.
## Post #705
- Username: xorterenshe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 22, 2012 4:04 pm
- Post datetime: 2021-02-19T00:21:44+00:00
- Post Title: Re: Ninja Ripper

Probably for a few months now, I can't get Ninja Ripper to work with Star Trek Online anymore. Could anyone suggest a way to fix this? I'm using the Steam version of STO. Haven't checked it with the standalone version yet, though I'm probably going to try that once I get the chance to install it. [EDIT] I've now also checked it with the standalone version. No difference.[END OF EDIT]

The way I used to be able to do it was as follows:
1)Point NR to ***>steamapps>common>Star Trek Online>Star Trek Online.exe
2)Run it as D3D11 wrapper.
3)Once launcher opens, close it down again.
4)Go into ***>steamapps>common>Star Trek Online folder and move the created D3D11.dll from there into the following folder:
***>steamapps>common>Star Trek Online>Star Trek Online>Live>x64
5)Close and relaunch NR, then run in Intruder mode

That's how it worked in the past, up until a few months ago. At least, I'm 99% positive I am remembering how I used to do it correctly.

Now, when I try to run with Intruder inject, it gives me an error:
"The application was unable to start correctly (0xc0000005). Click OK to close the application." 


I've also tried with substituting the D3D11 wrapper with the D3D9 one. No difference.
I also cant get it to work with just using one of the D3D* wrapper modes. The game runs, but I cant extract anything. It just creates a log file in the extract location and that's it. It always used to need Intruder mode, but now none of them seem to work.

Any suggestions?
## Post #706
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2021-02-19T21:30:40+00:00
- Post Title: Re: Ninja Ripper

> Reply from ricmetal ↑Sun Jan 17, 2021 9:47 am at Sun Jan 17, 2021 9:47 am
>
> 
the game(s) is dead island definite edition and dying light. i used to be able to rip dying light correctly, dead island im not so sure i tried previsouly, but both get the same gargled results, as shown in the images above. and dying light i def used to rip meshes, with the same setup i have now.
I checked in dead island DE, and yes, static meshes all garbaged, but character models looks ok.
## Post #707
- Username: ricmetal
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 07, 2018 3:50 am
- Post datetime: 2021-02-19T23:15:37+00:00
- Post Title: Re: Ninja Ripper

> Reply from Andrakann ↑Sat Feb 20, 2021 5:30 am at Sat Feb 20, 2021 5:30 am
>
> 
I checked in dead island DE, and yes, static meshes all garbaged, but character models looks ok.

unfortunately, it's the static meshes i am after   

i'm guessing a windows update messed the ripper up? i can't seen other explanation. i use the same ripper (rip setup as a long time ago).

i mean, dying light could have been updated, breaking the ripper somehow (idk if that could happen, i'm assuming), but my dead island ain't on steam, and both games result in the same effed up meshes, so i'm thinking dying light being updated (which it still is, to this day) had nothing to do with it and it's something else.

what else is there, but a windows update (in very broadly terms)

hm - does this usually happen to other games, and does it get fixed, usually? would it be possible to ask for a fix to whomever is concearned?
## Post #708
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2021-02-20T12:18:59+00:00
- Post Title: Re: Ninja Ripper

> Reply from ricmetal ↑Sat Feb 20, 2021 7:15 am at Sat Feb 20, 2021 7:15 am
>
> 
i'm guessing a windows update messed the ripper up?
...
what else is there, but a windows update (in very broadly terms)
I'm sure it's not win update, because i never update my 7x64 SP1 (maybe 2-3 updates installed manually over time for some software requirements).

Possible reason is videocard upgrade (1060 6Gb for now), videocard drivers also different.

So, my best guess it's caused by new videochip abilities, unknown to ripper, or by addressing more than 4 Gb of video RAM, which can be unsupported by ripper too.

Ripper developing is abandoned, so, it's better to try something different, like this: [viewtopic.php?f=33&t=21379](https://forum.xentax.com/viewtopic.php?f=33&t=21379)
## Post #709
- Username: Carvalho243
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Feb 26, 2021 8:46 pm
- Post datetime: 2021-02-26T12:52:12+00:00
- Post Title: Re: Ninja Ripper

> Reply from xorterenshe ↑Fri Feb 19, 2021 8:21 am at Fri Feb 19, 2021 8:21 am
>
> 
Probably for a few months now, I can't get Ninja Ripper to work with Star Trek Online anymore. Could anyone suggest a way to fix this? I'm using the Steam version of STO. Haven't checked it with the standalone version yet, though I'm probably going to try that once I get the chance to install it. [EDIT] I've now also checked it with the standalone version. No difference.[END OF EDIT]

The way I used to be able to do it was as follows:
1)Point NR to ***>steamapps>common>Star Trek Online>Star Trek Online.exe
2)Run it as D3D11 wrapper.
3)Once launcher opens, close it down again.
4)Go into ***>steamapps>common>Star Trek Online folder and move the created D3D11.dll from there into the following folder:
***>steamapps>common>Star Trek Online>Star Trek Online>Live>x64
5)Close and relaunch NR, then run in Intruder mode

That's how it worked in the past, up until a few months ago. At least, I'm 99% positive I am remembering how I used to do it correctly.

Now, when I try to run with Intruder inject, it gives me an error:
"The application was unable to start correctly (0xc0000005). Click OK to close the application." 


I've also tried with substituting the D3D11 wrapper with the D3D9 one. No difference.
I also cant get it to work with just using one of the D3D* wrapper modes. The game runs, but I cant extract anything. It just creates a log file in the extract location and that's it. It always used to need Intruder mode, but now none of them seem to work.

Any suggestions?

I just solved this problem yesterday. It was my antivirus (Avast). Turned it off for an hour and worked. Maybe it works with you too, but can be many other reasons as well...
## Post #710
- Username: Galveston
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 17, 2021 8:07 am
- Post datetime: 2021-03-17T23:31:25+00:00
- Post Title: Re: Ninja Ripper

anyone know if it would be possible to rip from Division 2? I tried doing both D3D11Wrapper and Intruder inject but division 2 does not use a d3d11 dll, and when trying with Intruder inject the game will not move past the launch process from uplay, saying it cannot sync achievements and will cancel the launch. The game supports both Dx11 and Dx12



divisionripper.JPG (25.14 KiB) Viewed 866 times
## Post #711
- Username: xorterenshe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 22, 2012 4:04 pm
- Post datetime: 2021-03-20T23:19:48+00:00
- Post Title: Re: Ninja Ripper

> Reply from Carvalho243 ↑Fri Feb 26, 2021 8:52 pm at Fri Feb 26, 2021 8:52 pm
>
> 
I just solved this problem yesterday. It was my antivirus (Avast). Turned it off for an hour and worked. Maybe it works with you too, but can be many other reasons as well...

You are a gentleman and a scholar. Yep, it was Avast causing the problem! Thank you very much. Man, Avast is such a pain. 

Let me ask you if you're still around, when you tried to rip models from STO, were their UV maps all mess up? This time 'round, that's how they appear for me.
If any one knows why this is happening, I'd gladly like any advice. It could be just that STO's updates have messed up how NinjaRipper interacts with it.
For example, the models' UVs are supposed to look like this:
Saucer - [https://i.imgur.com/U2gAb1C.jpg](https://i.imgur.com/U2gAb1C.jpg)
Windows/Escape Pods - [https://i.imgur.com/MJcQ1Vk.jpg](https://i.imgur.com/MJcQ1Vk.jpg)
...because the textures are formatted like this (here are two hull textures and three window textures, for example): [https://i.imgur.com/0VoDiq0.jpg](https://i.imgur.com/0VoDiq0.jpg)

That particular ship in my previous images, the Concorde, was update in-game during the time Avast was preventing me from using NinjaRipper, and so here's the newer model I just ripped. As you can see, the UV maps are, for some reason, circular mesh balls. 
Saucer - [https://i.imgur.com/N4CqcUW.jpg](https://i.imgur.com/N4CqcUW.jpg)
Windows/Escape Pods - [https://i.imgur.com/mqpG5xX.jpg](https://i.imgur.com/mqpG5xX.jpg)
The model order in the NinjaRipper rip folders have changed, but I doubt that would have anything to do with it, in my uneducated opinion. When I used to rip models from the game, there were always two copies of the ship, one pure white without textures auto-applied and one with textures auto-applied. Now, there are still two copies of the ship, but both with these messed up UV and textures auto-applied. 
I've tried using both dx11 and dx9 mode and tried using both of NR's 3dsmax importer scripts with no difference noticeable.

Any idea why this happening?
## Post #712
- Username: MarKreationsStudios
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Sep 03, 2020 5:47 am
- Post datetime: 2021-04-08T15:45:40+00:00
- Post Title: Re: Ninja Ripper

Can somebody please help me figure out a way to use Ninja Ripper on the RPCSX3 or the PCSX2 emulators?
## Post #713
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-04-27T19:43:18+00:00
- Post Title: Re: Ninja Ripper

[https://ninjaripper.com/](https://ninjaripper.com/)

Ninja Ripper 2 is in development by blackninja.

> main feature is post vs scene ripping as in 3dripperdx tool. All object positions saved as in game world. Old ripper save only in object space (t-pose). You can "fly" over level  in blender.
Basically what I think he said, Ninja Ripper 2 will be a modern version of 3d ripper dx.

EDIT: It's now available in a beta state.

[https://youtu.be/MMkLdWBn5Ew](https://youtu.be/MMkLdWBn5Ew)
## Post #714
- Username: Rexamon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 01, 2021 8:55 am
- Post datetime: 2021-06-01T01:09:26+00:00
- Post Title: Re: Ninja Ripper

If not is their any alternatives that work

Thanks in advance
## Post #715
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-06-01T13:31:41+00:00
- Post Title: Re: Ninja Ripper

> Reply from MarKreationsStudios ↑Thu Apr 08, 2021 11:45 pm at Thu Apr 08, 2021 11:45 pm
>
> 
Can somebody please help me figure out a way to use Ninja Ripper on the RPCSX3 or the PCSX2 emulators?

RPCSX3 uses Vulkan, and from my understand uses a special type of Zbuffer, there is no way to get that data without changing the way its rendered in the source code.

PCSX2 does not have Z Depth, it means that the scene LOOKS 3D but it all gets turned into an image and you're viewing that 'image' basically, there isn't actually any depth, its just a flat image that gets output in the end. Again you'd have to create a new rendering plugin for it, or edit the source code, it doesn't really matter much about the tool used, there would have to be a tool that interacts with the way the software is running, which would be more complicated than just creating a new 'model dump' branch of the emulator anyway. PS1 emulators have the exact same issue, no zbuffer, so no depth.
## Post #716
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2021-06-11T15:46:38+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 2.0.1 beta is out NOW!
What's new:

- Shader parameters dump (*cbuffer*)
- Projection matrices (get correct FOV directly from game)
- Ripper bug fix
- Better output mesh validation (blender can load more meshes)
- Import script bug fix (you'll need to update import script in blender)

Instructions
[https://www.youtube.com/watch?v=y4s6BmySd_E](https://www.youtube.com/watch?v=y4s6BmySd_E)

Download: (only from Patreon with Early Access) [https://ninjaripper.com/download](https://ninjaripper.com/download)
## Post #717
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2021-06-25T04:40:17+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 2.0.2 beta is out NOW!
What's new:

Better games ripping support.
  -If your game crashed while ripping(eg Genshin Impact, Subnautica) try this version.
Instructions on how to create your own theme
Instructions on how to create your own localization (language)

Instructions
[https://www.youtube.com/watch?v=y4s6BmySd_E](https://www.youtube.com/watch?v=y4s6BmySd_E)

website: [https://ninjaripper.com/](https://ninjaripper.com/)

Download: (only from Patreon with Early Access) [https://ninjaripper.com/download](https://ninjaripper.com/download)
## Post #718
- Username: lilyampykidYTXeNTaX
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Apr 29, 2021 1:32 am
- Post datetime: 2021-06-25T21:12:08+00:00
- Post Title: Re: Ninja Ripper

PSP uses Directx11, when I rip from that rendering backend, I get is broken colors of a texture. And normal models.
## Post #719
- Username: honeybudger
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 12, 2021 3:52 pm
- Post datetime: 2021-07-12T10:39:41+00:00
- Post Title: Re: Ninja Ripper

Is there any instruction how to rip models from game, that using Easy Anti Cheat? Can't rip Hunt Showdown
## Post #720
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2021-07-26T20:07:15+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 2.0.3 beta is out NOW!
What's new:

Improved support for ripping games
 -In previous version some meshs failed to save due incorrect indexes
Keys mapping
Improved import script
    -You can use all texture coordinates. 
New injection method (D3D Wrapper as in NR1.7.1)
    -Copy d3d11.dll from bin/wrapper directory to target exe dir  and normally start target exe
Updates checker
Styles (qss) fixes

Web:     [https://ninjaripper.com](https://ninjaripper.com)
Discord: [https://discord.com/invite/u8kMqNm](https://discord.com/invite/u8kMqNm)
Youtube: [https://www.youtube.com/channel/UCgT-ET ... cECNtW9gyw](https://www.youtube.com/channel/UCgT-ET20KlC4AcECNtW9gyw)
## Post #721
- Username: blackninja
- Rank: veteran
- Number of posts: 87
- Joined date: Wed Nov 28, 2012 6:55 pm
- Post datetime: 2021-08-28T09:33:26+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 2.0.4 beta is out NOW!

What's new:
Added saving meshes in local space (T-pose)
Added new import options
Improved support for ripping games:
  -If your game didn't rip or crash, try this version
Fixed bugs when ripping through dgVoodoo2 (DX 9/8/7/6 games)
Fixed bugs when ripping games from Origin

Web: [https://ninjaripper.com](https://ninjaripper.com)
Discord: [https://discord.com/invite/u8kMqNm](https://discord.com/invite/u8kMqNm)
YouTube: [https://www.youtube.com/channel/UCgT-ET ... cECNtW9gyw](https://www.youtube.com/channel/UCgT-ET20KlC4AcECNtW9gyw)
## Post #722
- Username: ellis3246
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 16, 2019 1:02 pm
- Post datetime: 2021-08-29T01:04:25+00:00
- Post Title: Re: Ninja Ripper

Hey y'all,i've come across a very destructive issue when ripping from the dx9 based game "ZOMBI"


Geometry and overall construction of meshes after ripping is just,distorted extremely
i'm using 1.7.1,the game uses U-PLAY (Now only runs ubisoft-connect when attempting to run in steam which i am using),Must be ran offline due to a suspended certificate that causes it to crash if ran online,if anyone could give any pointers on how to possibly fix this or make these models usable in a way (which even in this state i don't think would be possible)
## Post #723
- Username: Naznarok
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 03, 2020 4:58 pm
- Post datetime: 2021-11-26T11:22:03+00:00
- Post Title: Re: Ninja Ripper

Hello, anyone tryed to rip model from games lauched by EA Orign laucher? Tryed to rip some assets from Anthem but Ripper wont work.

upd: It works in compatibility mode (got reply from "blackninja" in discord).
## Post #724
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-12-05T19:59:15+00:00
- Post Title: Re: Ninja Ripper

Does anyone have a fix how NinjaRipper rips textures in this dark or reddish hue? I'm trying to get textures from Shadow of the Tomb Raider because it's the only way to get some models that can't be found from the game files with the current tools for that game.
## Post #725
- Username: DPress
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 12, 2019 12:43 am
- Post datetime: 2021-12-11T04:30:48+00:00
- Post Title: Re: Ninja Ripper

Anyone can help me use ninja ripper on The PC Version of Super Mecha Champions?
## Post #726
- Username: mnan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Oct 12, 2020 2:06 am
- Post datetime: 2022-01-21T22:52:17+00:00
- Post Title: Re: Ninja Ripper

I'm sorry if this is a stupid question, but how do you find the correct import matrix within the log file in 2.05?
## Post #727
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-01-21T23:54:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from mnan ↑Sat Jan 22, 2022 6:52 am at Sat Jan 22, 2022 6:52 am
>
> ...but how do you find the correct import matrix within the log file in 2.05?
Not ALL games export such projection matrix, if the LOG does not have it, it means you MUST guess the correct FoV_Y value for the import draw call/frame, see here: [https://www.youtube.com/watch?v=y4s6BmySd_E](https://www.youtube.com/watch?v=y4s6BmySd_E)
## Post #728
- Username: yinami
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 05, 2022 11:15 am
- Post datetime: 2022-03-05T03:22:08+00:00
- Post Title: Re: Ninja Ripper

So i am trying to get a model off of Aion_Classic. ive tried all the .dll(s) and the normal i, injection way. and got nothing. ( and just for giggles i tried Machinima Studio too.  could anyone tell me what im doing wrong?
## Post #729
- Username: nizarwldl97ba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 16, 2022 8:21 am
- Post datetime: 2022-06-17T17:49:25+00:00
- Post Title: Re: Ninja Ripper

i need Marrakesh map   thank you so much
## Post #730
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-06-17T17:50:12+00:00
- Post Title: Re: Ninja Ripper

I’m trying to get models from Beyond Good & Evil.
## Post #731
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-07-03T16:21:19+00:00
- Post Title: Re: Ninja Ripper

I've try to use either old & new version in two games: Final Fantasy 8 Remastered (Steam) and Heaven and Earth Tribulation for PC. With FF8R, it just doesn't recognize either version of NinjaRipper, it simple doesn't grab anything. With Heaven and Earth Tribulation it does recognize the game, but it doesn't extract the game in T-Pose and only on the pose they're in the game. The new version of NinjaRipper actually crash the game or simple keep in a eternal loading the News of the game.

I mostly ask for FF8R because for what I read in a modding pages, they're not interesting in get the models because they're worry about the laws about extract stuff from the game.  
With Heaven and Earth Tribulation, [I did made a threat here](https://forum.xentax.com/viewtopic.php?f=10&t=25320) but got absolutely not answer, and NinjaRipper is the only that I've left.
## Post #732
- Username: Franky212
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 29, 2023 4:07 am
- Post datetime: 2023-07-28T20:31:26+00:00
- Post Title: Re: Ninja Ripper

Ninja Ripper 2.0.5 missing mesh fix by Franky212
[https://www.vogons.org/viewtopic.php?p=1179315#p1179315](https://www.vogons.org/viewtopic.php?p=1179315#p1179315)
[NinjaRipper_2.0.5_MissingMeshFix.zip](https://www.vogons.org/download/file.php?id=168902)
[NinjaRipper_2.0.5_MissingMeshFix.zip](https://web.archive.org/web/20230728202845/https://www.vogons.org/download/file.php?id=168902) (Mirror)

Thanks to this fix, Ninja Ripper gets rid of a critical bug. The program calculates the differences between objects using the CRC32 function, and if it finds the same CRC32, it automatically skips the object. The CRC32 function is unable to detect the slightest differences between two objects, so the fix forces Ninja Ripper to save all objects, including duplicates, regardless of CRC32.

Installation: copy the intruder.dll files with replacement to the bin32/bin64 folders where the Ninja Ripper program was installed.

ninja_log.txt
Before: Mesh already saved with crc=158252cd


After: Saving mesh. crc=158252cd
## Post #733
- Username: Drayken
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Dec 26, 2016 10:54 pm
- Post datetime: 2023-09-15T09:46:57+00:00
- Post Title: Re: Ninja Ripper

How would you go about using Ninja Ripper with games which start from a launcher? Even though I set Ninja Ripper to launch Splinter Cell Blacklist directly from its exe file, it goes through Ubisoft Connect (UPlay) and prints out garbage uplay logs on launch, when I press my rip keys it does absolutely nothing.  

It's legitimately baffling that in 2023 there still aren't any flawlessly working solutions for ripping shit out of games.
## Post #734
- Username: Franky212
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 29, 2023 4:07 am
- Post datetime: 2023-09-15T19:40:17+00:00
- Post Title: Re: Ninja Ripper

> Reply from Drayken ↑Fri Sep 15, 2023 5:46 pm at Fri Sep 15, 2023 5:46 pm
>
> 
How would you go about using Ninja Ripper with games which start from a launcher? Even though I set Ninja Ripper to launch Splinter Cell Blacklist directly from its exe file, it goes through Ubisoft Connect (UPlay) and prints out garbage uplay logs on launch, when I press my rip keys it does absolutely nothing.  

It's legitimately baffling that in 2023 there still aren't any flawlessly working solutions for ripping shit out of games.
Info from official site: [https://ninjaripper.com/faq](https://ninjaripper.com/faq)

> What is wrapper-dll method and how to use it?
>
> This method allows you to rip from games with their own launcher.
>
> You need to copy d3dwrapper.dll from the bin64/wrappers or bin32/wrappers folder to the exe folder of the game you want to rip from.
>
> IMPORTANT: Need to rename to d3d11.dll or d3d12.dll depending on the game. The bit depth of the dll should match. If the game is 64 bit, then the wrapper dll should be taken from 64 bit folder.
>
> After that run the game DIRECTLY. You don't need to run it through ripper.
>
> Watch Wrapper-DLL method video
Download Ninja Ripper 2.0.5 latest free version:
[Ninja Ripper 2.0.5 beta.setup.exe](https://c4.kemono.party/data/a8/41/a84128b8a49693cafb45189dbaa9f3c3ab2200280b8532d9556e948959933e4b.bin?f=Ninja%20Ripper%202.0.5%20beta.setup.exe)
[Ninja Ripper 2.0.5 beta.setup.exe Mirror](https://web.archive.org/web/20230915195234/https://c4.kemono.party/data/a8/41/a84128b8a49693cafb45189dbaa9f3c3ab2200280b8532d9556e948959933e4b.bin?f=Ninja%20Ripper%202.0.5%20beta.setup.exe)
[Ninja Ripper 2.0.5 beta.portable.zip](https://c1.kemono.party/data/14/5f/145fcc8cd93c6c238c1529968588cdbe9ec071c272d1f86e2f3972dc27f9d705.zip?f=Ninja%20Ripper%202.0.5%20beta.portable.zip)
[Ninja Ripper 2.0.5 beta.portable.zip Mirror](https://web.archive.org/web/20230915200436/https://c1.kemono.party/data/14/5f/145fcc8cd93c6c238c1529968588cdbe9ec071c272d1f86e2f3972dc27f9d705.zip?f=Ninja%20Ripper%202.0.5%20beta.portable.zip)
## Post #735
- Username: uzi551
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 31, 2023 12:37 am
- Post datetime: 2023-10-03T09:41:36+00:00
- Post Title: Re: Ninja Ripper

I had a problem. After using Ninja, the app logo didn't appear in the game and I didn't respond when I pressed the shortcut keys
Normally, the dgvoodoo logo would appear in the bottom right corner of the screen and the game would run at a slower speed, but that's not happening right now
