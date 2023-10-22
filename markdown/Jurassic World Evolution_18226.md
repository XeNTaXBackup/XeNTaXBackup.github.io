## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2018-06-13T14:17:11+00:00
- Post Title: Jurassic World Evolution

Hey guys! Haven't been here in a while, but figured I'd strike out and see if someone could help! Seeing as it's the 25th Anniversary of Jurassic Park and the new movie is around the corner, would someone be able to take a look at the texture and model files in here and see if they can come up with a script to extract the files inside?

Would really be appreciated!

[https://mega.nz/#!7BIwHKzB!4AoPhu-htb10 ... iKLo94wVbw](https://mega.nz/#!7BIwHKzB!4AoPhu-htb10RXNSsy9AkifrJHLbqHIjoiKLo94wVbw)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-14T07:51:49+00:00
- Post Title: Jurassic World Evolution

Files used zlib compression. But the vertex format is strange. I only managed to get the UVs, the vertex coordinates might be stored somewhere else.



UV.jpg (255.19 KiB) Viewed 1614 times
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-15T14:14:53+00:00
- Post Title: Jurassic World Evolution

yes, really weird coordinate format 

Since there's not much demand for this obscure engine, first version only supports dinosaurs. But technically it must be possible to get anything from any game on this engine, because i already reversed the base of its data formats. I think even this tool MAY work with other games.

Tool usage:

drop .OVL file onto the tool.
ovs.textures_... files must be in the same dir if you want textures exported too.
Exported files will be in new ASCII format that supports bone rotations (as you may know).
Also OBJ file and SMD skeleton will be created.




[JurassicWE.rar](https://xentaxbackup.github.io/file/14909_JurassicWE.rar)
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-24T17:19:36+00:00
- Post Title: Jurassic World Evolution

Tool posted
## Post #5
- Username: Kaem
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 23, 2012 5:28 am
- Post datetime: 2018-09-27T10:28:24+00:00
- Post Title: Jurassic World Evolution

> Reply from daemon1
>
> Tool posted

You will try update the tool for extract characters like the Ranger/Workers? I only extract corrupt .obj's and .ascii's and 1kb .smd  

And about the texture I need do something to open them?, I've tried let only the ".dds" and they're fucked.
## Post #6
- Username: isocloud
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 19, 2018 6:50 am
- Post datetime: 2018-09-28T03:21:30+00:00
- Post Title: Jurassic World Evolution

Thank you. Texture do seem to be fucked for the most part atm.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T04:26:55+00:00
- Post Title: Jurassic World Evolution

textures are all correct DDS, most of them are DX10
## Post #8
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T15:32:09+00:00
- Post Title: Jurassic World Evolution

I try at the Moment to fix the Trex Model... but can't open the Ascii File in Max or C4D xD
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T15:47:59+00:00
- Post Title: Jurassic World Evolution

why do you need to "fix" it?
## Post #10
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T15:50:07+00:00
- Post Title: Jurassic World Evolution

He lost the whole UVW... that's what i have to fix  and bring her bones back in position
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T16:05:11+00:00
- Post Title: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> He lost the whole UVW... that's what i have to fix  and bring her bones back in position
bones are in correct position. use noesis to convert ascii
## Post #12
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T16:10:33+00:00
- Post Title: Jurassic World Evolution

I see.. i'm not a extraction profi.. i'm rather 3d designer 


But i'm a little confused... all i see in Noesis is the SMD and the OBJ File :/
## Post #13
- Username: isocloud
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 19, 2018 6:50 am
- Post datetime: 2018-09-28T16:46:01+00:00
- Post Title: Jurassic World Evolution

Textures work but only in blender  can’t import into Unreal.
Anyways thank you, but will animations be able to be extracted in future updates?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T17:03:00+00:00
- Post Title: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> But i'm a little confused... all i see in Noesis is the SMD and the OBJ File :/
take .PY file from tool archive and put in into noesis "plugin / python" folder
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T17:03:51+00:00
- Post Title: Jurassic World Evolution

> Reply from isocloud
>
> Textures work but only in blender  can’t import into Unreal.
Anyways thank you, but will animations be able to be extracted in future updates?
i dont plan animation support
its not worth the time needed for it
## Post #16
- Username: isocloud
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 19, 2018 6:50 am
- Post datetime: 2018-09-28T17:12:43+00:00
- Post Title: Re: Jurassic World Evolution

What would I have to offer to get animation support? Would like to import into Ark for mods etc. I can make a donation for the time of work required!
## Post #17
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T18:29:29+00:00
- Post Title: Re: Jurassic World Evolution

I'm maybe stupid or just blind... but i didn't found the script 

I understand, it would need time to write a animation supported script.. but it would be really great
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-28T18:47:26+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> I'm maybe stupid or just blind... but i didn't found the script

fmt_xps_ascii.py
## Post #19
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T19:08:32+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> Mcflyhigh1 wrote:I'm maybe stupid or just blind... but i didn't found the script 

fmt_xps_ascii.py

Thanks about the Tips 
Now just have to fix the Texture and all will be perfect .. after i create a accurate Rexy  same like accurate Raptors
## Post #20
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-28T20:59:45+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> isocloud wrote:Textures work but only in blender  can’t import into Unreal.
Anyways thank you, but will animations be able to be extracted in future updates?
i dont plan animation support
its not worth the time needed for it

So thank you so much dear deamon1 

I got a Rex Version rigged and textured "i just have to figure out now how to open the other textures for it"
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T07:36:15+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from isocloud
>
> What would I have to offer to get animation support? Would like to import into Ark for mods etc. I can make a donation for the time of work required!
sorry i'm not accepting donations
there are many other, much more interesting animation engines waiting for me to support them, like Horizon zero dawn, Quantum break and all frostbite games
## Post #22
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T08:51:56+00:00
- Post Title: Re: Jurassic World Evolution

Deamon1 do you know the location of the High Res Textures ? (The Textures in the OVL File are just 1024x1024, so this can't be the high res textures for the Game, and dosn't incluse the other texture variants like albino, tundra, standard etc.)

with a resolution of 1024x1024 miss the figure good like every skin detail




the render miss a lot of details self with 500% normal setting and own created bumb map



And if yes, so how to open this Files ?

I tried this yesterday 6 Hours xD
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T09:51:59+00:00
- Post Title: Re: Jurassic World Evolution

My tool exports all textures correctly, in high res, with names and including all variations. Normal maps are also there, you even showed it on your picture.

1024x1024 is the high res texture.
## Post #24
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T09:57:37+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> My tool exports all textures correctly, in high res, with names and including all variations. Normal maps are also there, you even showed it on your picture.

1024x1024 is the high res texture.

I think so too.. but i'm not sure if they are so "small" at closer ingame shots... if you move your cam close to a dinosaur so you can see the different skin pattern.. and this what the skin texture 1024x1024 miss


Here is the same area of skin..





the game texture is much sharper and more clean... that's why i ask if a higher resolution exist somewhere... maybe in the textures_l1, what i can't open up
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T10:08:44+00:00
- Post Title: Re: Jurassic World Evolution

i haven't seen the game, but you can be sure they are using all textures extracted, including "normal", "packed" and "blendweights". Last one has a lot of masks which probably makes them looking like you see it in the game.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T10:10:28+00:00
- Post Title: Re: Jurassic World Evolution

textures_l1 - is 1024x1024, it IS extracted with my tool from there.
## Post #27
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T10:16:47+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> i haven't seen the game, but you can be sure they are using all textures extracted, including "normal", "packed" and "blendweights". Last one has a lot of masks which probably makes them looking like you see it in the game.

I tried a lot to extract the L1... renamed.. or opened over HEX Editor or something other.. but ehm how to say.. it didn't work
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T10:18:05+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> daemon1 wrote:i haven't seen the game, but you can be sure they are using all textures extracted, including "normal", "packed" and "blendweights". Last one has a lot of masks which probably makes them looking like you see it in the game.

Did you find a way to open the L1 ?

yes, textures_l1 - is 1024x1024, it IS extracted with my tool
## Post #29
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T10:21:41+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> Mcflyhigh1 wrote:daemon1 wrote:i haven't seen the game, but you can be sure they are using all textures extracted, including "normal", "packed" and "blendweights". Last one has a lot of masks which probably makes them looking like you see it in the game.

Did you find a way to open the L1 ?

yes, textures_l1 - is 1024x1024, it IS extracted with my tool

I tried a lot to extract the L1... renamed.. or opened over HEX Editor or something other.. but ehm how to say.. it didn't work
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T10:23:38+00:00
- Post Title: Re: Jurassic World Evolution

ok i will say it for the 3rd time:

you already HAVE all textures extracted from L1, they are 1024x1024

do you understand ?
## Post #31
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T10:32:53+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> ok i will say it for the 3rd time:

you already HAVE all textures extracted from L1, they are 1024x1024

do you understand ?

You don't must freak out deamon1 ... everything is okay and chilled.. i'm not blind (so i can read what others write) or stupid and over 12 years active as 3d artist for a company, so i understand you very good.. just ask me where are the other skin variants then... every dino has various skin variants "4 -8".. so sorry if i'm confused about the facts
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T10:43:53+00:00
- Post Title: Re: Jurassic World Evolution

i dont have all of dino files, but from those i have, variants are extracted. For example:

indominusrex.pbasediffusetexture.dds
indominusrex.pbasepackedtexture.dds
indominusrex.playered_blendweights.dds
indominusrex.playered_warpoffset.dds
indominusrex.pnormaltexture.dds
indominusrex01.pbasediffusetexture.dds
indominusrex01.pbasepackedtexture.dds
indominusrex02.pbasediffusetexture.dds

These 

indominusrex.pbasediffusetexture.dds
indominusrex01.pbasediffusetexture.dds
indominusrex02.pbasediffusetexture.dds

look like 3 diffuse variations. If you say there are more variations, then those must be "generated" using "blendweight" masks and solid colors.
## Post #33
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T10:48:00+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> i dont have all of dino files, but from those i have, variants are extracted. For example:

indominusrex.pbasediffusetexture.dds
indominusrex.pbasepackedtexture.dds
indominusrex.playered_blendweights.dds
indominusrex.playered_warpoffset.dds
indominusrex.pnormaltexture.dds
indominusrex01.pbasediffusetexture.dds
indominusrex01.pbasepackedtexture.dds
indominusrex02.pbasediffusetexture.dds

These 

indominusrex.pbasediffusetexture.dds
indominusrex01.pbasediffusetexture.dds
indominusrex02.pbasediffusetexture.dds

look like 3 diffuse variations. If you say there are more variations, then those must be "generated" using "blendweight" masks and solid colors.


You say, that you never saw the Game.. so i show you as example the different T-Rex Skins "yeah, the JP Trex is my favourite dinosaur of the jurassic park/world franchise)

there you see the details over what i talked about too

[https://www.youtube.com/watch?v=sJdb29M3HVo](https://www.youtube.com/watch?v=sJdb29M3HVo)


All i get out of the OVL if i export it is :

tyrannosaurus.pbasediffusetexture
tyrannosaurus.pbasepackedtexture
tyrannosaurus.playered_blendweights
tyrannosaurus.playered_warpoffset
tyrannosaurus.pnormaltexture
and
tyrannosaurus01.pbasecolourtexture

so less than you
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T11:07:43+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> tyrannosaurus.pbasediffusetexture
tyrannosaurus.pbasepackedtexture
tyrannosaurus.playered_blendweights
tyrannosaurus.playered_warpoffset
tyrannosaurus.pnormaltexture
and
tyrannosaurus01.pbasecolourtexture

ok, i dont have his file, but all those variations must be rendered with textures you have.

They have so many masks in tyrannosaurus.playered_blendweights - it must be for that.
This DDS is in BC7 format, and it contains from 4 to 16 one-channel (greyscale) masks.
They must all be there.
## Post #35
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T11:18:38+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> Mcflyhigh1 wrote:tyrannosaurus.pbasediffusetexture
tyrannosaurus.pbasepackedtexture
tyrannosaurus.playered_blendweights
tyrannosaurus.playered_warpoffset
tyrannosaurus.pnormaltexture
and
tyrannosaurus01.pbasecolourtexture

ok, i dont have his file, but all those variations must be rendered with textures you have.

They have so many masks in tyrannosaurus.playered_blendweights - it must be for that.
This DDS is in BC7 format, and it contains from 4 to 16 one-channel (greyscale) masks.
They must all be there.

Everything is changeable daemon1

maybe you find out more  "you are much better in this than me"

[https://mega.nz/#!P6IwRaKa!yL-83p7x-Sld ... v0Bs-gy_sg](https://mega.nz/#!P6IwRaKa!yL-83p7x-SldEx3AK0yVnasX44Cjt8YJyv0Bs-gy_sg)
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T11:40:03+00:00
- Post Title: Re: Jurassic World Evolution

this is your tyrannosaurus.playered_blendweights:



it has 16 masks. I sized it down 4x times to show this screen.
I'm not a modeller at all, but it seems to me that this is more than enough to make many skin variations

color split:
## Post #37
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T11:47:17+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> this is your tyrannosaurus.playered_blendweights:



it has 16 masks. I sized it down 4x times to show this screen.
I'm not a modeller at all, but it seems to me that this is more than enough to make many skin variations

You find always a way to confuse me more lol 
How did you exract them always.. the only way i found is with noesis.. and this shows me just two green variants



I see i have a lot to learn.. maybe should you start as teacher and give couses to teach others your knowledge 

Ok PS changing Red/Blue/Green Channels
## Post #38
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-29T12:04:51+00:00
- Post Title: Re: Jurassic World Evolution

Microsofts reference.
[https://docs.microsoft.com/en-us/window ... -reference](https://docs.microsoft.com/en-us/windows/desktop/direct3d11/bc7-format-mode-reference)
you need to extract the channel bits like he showed in the image.
figure out the mode your image is then you can see how the bits are packed.
he is showing 4 in each of the rgba channels then he made them greyscale as they are being used as masks.
## Post #39
- Username: REDEYE
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 02, 2017 8:22 pm
- Post datetime: 2018-09-29T12:28:09+00:00
- Post Title: Re: Jurassic World Evolution

Hey daemon1, I'm working on blender addon for importing OVL format models from Jurassic World Evolution git repo: [https://github.com/REDxEYE/OVL_IO](https://github.com/REDxEYE/OVL_IO)
But i need a bit of help, i can't quite understand what is happening in your tool

[](https://ibb.co/h99JDe)
Thouse numXX are driving me nuts.
That might be reflector decompiled variables names wrong or you actually named them numXX?
Anyways, can you DM me source code or just explain what happaning in your tool?
## Post #40
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-09-29T12:30:42+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from REDEYE
>
> Hey daemon1, I'm working on blender addon for importing OVL format models from Jurassic World Evolution git repo: https://github.com/REDxEYE/OVL_IO
But i need a bit of help, i can't quite understand what is happening in your tool


Thouse numXX are driving me nuts.
That might be reflector decompiled variables names wrong or you actually named that numXX?
Anyways, can you DM me source code or just explain what happaning in your tool?

Hey Red, nice to see you here too
## Post #41
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-29T13:19:39+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from REDEYE
>
> what happaning in your tool?
no comments

i can only say that current version of my tool is not properly parsing packages, because i only needed to quickly export dinos, and only dinos
## Post #42
- Username: REDEYE
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 02, 2017 8:22 pm
- Post datetime: 2018-09-29T13:28:39+00:00
- Post Title: Re: Jurassic World Evolution

Can i have original sources at least? Ones that i decompiles looks a bit weird
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-09-30T13:14:12+00:00
- Post Title: Re: Jurassic World Evolution

I'm working on a better version, for Disneyland Adventures

tool will be posted there: [viewtopic.php?f=16&t=18879](http://forum.xentax.com/viewtopic.php?f=16&t=18879)
## Post #44
- Username: therealdeal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 03, 2018 4:44 pm
- Post datetime: 2018-10-03T08:52:23+00:00
- Post Title: Re: Jurassic World Evolution

where is this tool to download i cant seem to find it
## Post #45
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-10-03T11:39:11+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from therealdeal
>
> where is this tool to download i cant seem to find it

daemon01 has removed the tool for the moment whilst he adds some updates to it.

You'll find it here when its done: [viewtopic.php?f=16&t=18879](http://forum.xentax.com/viewtopic.php?f=16&t=18879)

Which is exactly whats been asked, and written in the last 4 posts above yours.
## Post #46
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-10-03T15:39:34+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from lionheartuk
>
> therealdeal wrote:where is this tool to download i cant seem to find it

daemon01 has removed the tool for the moment whilst he adds some updates to it.

You'll find it here when its done: viewtopic.php?f=16&t=18879

Which is exactly whats been asked, and written in the last 4 posts above yours.

Tool can be found on Page 1 of this Thread
## Post #47
- Username: TakTak01
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 08, 2018 8:21 am
- Post datetime: 2018-11-08T00:44:16+00:00
- Post Title: Re: Jurassic World Evolution

Any reason why the tool keeps crashing on me? I open it, black screen for a while then crash. 

You are doing god's work tho!
## Post #48
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-11-08T03:21:22+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from ttakeshi98
>
> Any reason why the tool keeps crashing on me? I open it, black screen for a while then crash.
That's because you do not open it like a regular executable, by double clicking it, you simply follow the instructions given accordingly and it will work, you run it through command prompt.
## Post #49
- Username: cruizeez96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 05, 2018 11:46 pm
- Post datetime: 2018-11-09T01:05:20+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from ttakeshi98
>
> Any reason why the tool keeps crashing on me? I open it, black screen for a while then crash. 

You are doing god's work tho!

Yeah I literally just dragged the .ovl file onto the JurassicWE .exe file and it extracted a bunch of files I can open with Noesis. My problem is that I can't get any results better than this:



I know there is way more to the textures than I'm finding (pretty much just the diffuse and normal map) but I just don't know enough about the blended weights file to use it. I'm used to using diffuse maps with normal, bump, spec, etc.. Thank you for this tool though, Daemon!
## Post #50
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-11-09T02:42:33+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from cruizeez96
>
> ttakeshi98 wrote:

I know there is way more to the textures than I'm finding (pretty much just the diffuse and normal map) but I just don't know enough about the blended weights file to use it. I'm used to using diffuse maps with normal, bump, spec, etc.. Thank you for this tool though, Daemon!

Can you explain the issue a bit more?

The game uses a detail normal that tiles, but its likely to be a shared detail normal across several dinosaurs.
Blended weights and textures are two unrelated things.
Games with normal & bump? Thats weird, are you sure thats correct, no games I can think of use both of those formats, are you sure you aren't mistaking a heightmap or a roughness/metallic map for a bump map?
## Post #51
- Username: cruizeez96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 05, 2018 11:46 pm
- Post datetime: 2018-11-09T02:50:06+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from lionheartuk
>
> cruizeez96 wrote:ttakeshi98 wrote:

I know there is way more to the textures than I'm finding (pretty much just the diffuse and normal map) but I just don't know enough about the blended weights file to use it. I'm used to using diffuse maps with normal, bump, spec, etc.. Thank you for this tool though, Daemon!

Can you explain the issue a bit more?

The game uses a detail normal that tiles, but its likely to be a shared detail normal across several dinosaurs.
Blended weights and textures are two unrelated things.
Games with normal & bump? Thats weird, are you sure thats correct, no games I can think of use both of those formats, are you sure you aren't mistaking a heightmap or a roughness/metallic map for a bump map?

Sorry I’m sure that was a really confusing post. I know very little about the rendering process in videogames (and just rendering in general). I usually render stuff in DAZ Studio (noob software, I know) and many models do use both normal maps and bump maps.

I’m pretty much having the same problem that another user in this thread had. I’m struggling to understand how these textures/maps result in the super detailed skins we see in-game.
## Post #52
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-11-09T14:32:23+00:00
- Post Title: Re: Jurassic World Evolution

Yes it exist a way for better texturing... but it is a long way to bring good results

First of all.. the skin pattern texture, dosn't have uv mapping.. so this must be created manually.. the diffuse color must be changed too "if you wanna have different skin colors".. 
I worked now more or less since release of this tool on it, and self this isn't completely perfect at the moment



Small Update
## Post #53
- Username: cruizeez96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 05, 2018 11:46 pm
- Post datetime: 2018-11-10T14:08:30+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> Yes it exist a way for better texturing... but it is a long way to bring good results

First of all.. the skin pattern texture, dosn't have uv mapping.. so this must be created manually.. the diffuse color must be changed too "if you wanna have different skin colors".. 
I worked now more or less since release of this tool on it, and self this isn't completely perfect at the moment



Small Update

That looks awesome! Just like in-game. I just don’t understand which texture file contained all the details in the skin in your render. Is it the Normal map? Because even when I crank that really high it just enhances the folds/creases in the skin, which is what normal maps are supposed to do I guess. I just can’t get any of the scales and fine details to show up.

Edit: Also, how did you get the Jeep model in your picture? Did you use the same tool posted earlier or is that from another game?
## Post #54
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-11-10T15:11:50+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from cruizeez96
>
> Mcflyhigh1 wrote:Yes it exist a way for better texturing... but it is a long way to bring good results

First of all.. the skin pattern texture, dosn't have uv mapping.. so this must be created manually.. the diffuse color must be changed too "if you wanna have different skin colors".. 
I worked now more or less since release of this tool on it, and self this isn't completely perfect at the moment



Small Update 



That looks awesome! Just like in-game. I just don’t understand which texture file contained all the details in the skin in your render. Is it the Normal map? Because even when I crank that really high it just enhances the folds/creases in the skin, which is what normal maps are supposed to do I guess. I just can’t get any of the scales and fine details to show up.

Edit: Also, how did you get the Jeep model in your picture? Did you use the same tool posted earlier or is that from another game?

The Jeep Wrangler is mine... i build it 2 Years ago for a JP Game Project. "together with the ML 320 and the Fleetwood etc".









The Skin is a good Question, you have to use different versions of the diffuse map "red,green and blue" and combinate this 3 maps in your bump map area...
second step is... find the file : DinosaurCommon (to find in Dinosaurs/Shared)... there will you find every pattern what frontier used.... BUT !!!! thats a imagine of 500 x 35000 pixel with EVERY pattern version what exist... so you have to copy and paste, the pattern what you need and this pattern dosn't have uvw coordinates... so you have to create own uvw mapping for this texture.... after the copy and paste acting, you have to create green, blue and red layers too, and to put them into your bump map thread... so yep it is complicated !!!!!
## Post #55
- Username: cruizeez96
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Nov 05, 2018 11:46 pm
- Post datetime: 2018-11-10T23:43:00+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1
>
> 
The Skin is a good Question, you have to use different versions of the diffuse map "red,green and blue" and combinate this 3 maps in your bump map area...
second step is... find the file : DinosaurCommon (to find in Dinosaurs/Shared)... there will you find every pattern what frontier used.... BUT !!!! thats a imagine of 500 x 35000 pixel with EVERY pattern version what exist... so you have to copy and paste, the pattern what you need and this pattern dosn't have uvw coordinates... so you have to create own uvw mapping for this texture.... after the copy and paste acting, you have to create green, blue and red layers too, and to put them into your bump map thread... so yep it is complicated !!!!!

Thank you!! I knew there was more to rendering these dinos than the textures within each .ovl file. The Shared .ovl file is exactly what I was looking for. 

It looks like there are 64 patterns within the larger texture file and 52 textures in the Normal map file. Did you happen to jot down or have a list of the order of these skins? I'm going to try to separate them to make it a bit more easy to manage them.
## Post #56
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-11-11T00:27:42+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from cruizeez96
>
> Mcflyhigh1 wrote:
The Skin is a good Question, you have to use different versions of the diffuse map "red,green and blue" and combinate this 3 maps in your bump map area...
second step is... find the file : DinosaurCommon (to find in Dinosaurs/Shared)... there will you find every pattern what frontier used.... BUT !!!! thats a imagine of 500 x 35000 pixel with EVERY pattern version what exist... so you have to copy and paste, the pattern what you need and this pattern dosn't have uvw coordinates... so you have to create own uvw mapping for this texture.... after the copy and paste acting, you have to create green, blue and red layers too, and to put them into your bump map thread... so yep it is complicated !!!!!

Thank you!! I knew there was more to rendering these dinos than the textures within each .ovl file. The Shared .ovl file is exactly what I was looking for. 

It looks like there are 64 patterns within the larger texture file and 52 textures in the Normal map file. Did you happen to jot down or have a list of the order of these skins? I'm going to try to separate them to make it a bit more easy to manage them.

Nothing to thank, you're welcome 

No i dosn't wrote a list for the pattern texture, and dosn't use the pattern normal maps or the standard diffuse map... i created a bump map for the trex pattern and created a mixed texture out of the diffuse and the pattern texture to get the skin illusion... i created some displacement maps... own normal maps... own diffuse maps.. own pattern maps
## Post #57
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-12-28T04:49:33+00:00
- Post Title: Re: Jurassic World Evolution

Can someone tell me if it is possible to extract the vehicles? At the moment, I'm only interested in them.
## Post #58
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-12-28T17:57:30+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> yes, really weird coordinate format 

Since there's not much demand for this obscure engine, first version only supports dinosaurs. But technically it must be possible to get anything from any game on this engine, because i already reversed the base of its data formats. I think even this tool MAY work with other games.

Tool usage:

drop .OVL file onto the tool.
ovs.textures_... files must be in the same dir if you want textures exported too.
Exported files will be in new ASCII format that supports bone rotations (as you may know).
Also OBJ file and SMD skeleton will be created.

Ok, I made several attempts and the tool crashes with all models (dinosaurs excluded).

Anyway, a few days ago I saw these posts on Artstation [https://www.artstation.com/search?q=Jur ... ing=recent](https://www.artstation.com/search?q=Jurassic%20World%20Evolution&sorting=recent), and I thought these models deserve to be extracted. I mean, they're very well done, they can be useful for a lot of things. daemon1, are you still sure you're only interested in dinosaur models?

Come on, take a look here
## Post #59
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-12-29T10:45:34+00:00
- Post Title: Re: Jurassic World Evolution

The models in your artstation post are the high poly models, used for the textures 

this are the low poly models "game models"
## Post #60
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2018-12-29T15:18:06+00:00
- Post Title: Re: Jurassic World Evolution

Oh, damn it! In any case, I'm sure that with a little extra work using the various tools that 3ds Max offers, probably is possible soften the elements with too few polygons and so on.

Anyway, as you know, REDEYE was working on a script for Blender. I wonder if he is continuing or if he has abandoned the project.
## Post #61
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2018-12-29T18:37:39+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from ShadyDub
>
> Oh, damn it! In any case, I'm sure that with a little extra work using the various tools that 3ds Max offers, probably is possible soften the elements with too few polygons and so on.

Anyway, as you know, REDEYE was working on a script for Blender. I wonder if he is continuing or if he has abandoned the project.

I know that he worked on a Blender tool, cause.. we worked more or less together on this project... but it isn't done so far "sadly"..
## Post #62
- Username: samsharam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 01, 2019 6:29 pm
- Post datetime: 2019-01-02T19:02:55+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> yes, really weird coordinate format 

Since there's not much demand for this obscure engine, first version only supports dinosaurs. But technically it must be possible to get anything from any game on this engine, because i already reversed the base of its data formats. I think even this tool MAY work with other games.

Tool usage:

drop .OVL file onto the tool.
ovs.textures_... files must be in the same dir if you want textures exported too.
Exported files will be in new ASCII format that supports bone rotations (as you may know).
Also OBJ file and SMD skeleton will be created.



Can anybody please point me how to extract animations, I am a noob but passionate to learn.

Thank you
## Post #63
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-02T23:47:39+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from samsharam
>
> how to extract animations
They are NOT supported by the tool.
## Post #64
- Username: robd123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 16, 2018 7:23 am
- Post datetime: 2019-01-10T05:14:50+00:00
- Post Title: Re: Jurassic World Evolution

So I've extracted the ovl files with the tool and have the textures, but Noesis can't open them nor can a dds converter convert them. Anyone have a way to get the textures on the model so I can see them? It seems very convoluted.
## Post #65
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-10T15:16:11+00:00
- Post Title: Re: Jurassic World Evolution

textures are standard DDS, they work with ANY texture tools or editors
## Post #66
- Username: robd123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 16, 2018 7:23 am
- Post datetime: 2019-01-10T20:35:23+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> textures are standard DDS, they work with ANY texture tools or editors

Ah, yes you're right. Noesis couldn't do it since I hadn't downloaded the update.
## Post #67
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-01-28T14:04:33+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> yes, really weird coordinate format 

Since there's not much demand for this obscure engine, first version only supports dinosaurs. But technically it must be possible to get anything from any game on this engine, because i already reversed the base of its data formats. I think even this tool MAY work with other games.

Tool usage:

drop .OVL file onto the tool.
ovs.textures_... files must be in the same dir if you want textures exported too.
Exported files will be in new ASCII format that supports bone rotations (as you may know).
Also OBJ file and SMD skeleton will be created.

Now, if you had finalized the program so that it would extract and animation, it would be very cool. And now the skeleton that is extracted with the models is absolutely useless. It can benefit only professional animators. I hope you will hear me, and make it so that the animations are extracted, too.
## Post #68
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-01-28T21:40:40+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Firephoenix1342
>
> And now the skeleton that is extracted with the models is absolutely useless.
Your so wrong on so many levels I don't even know where to begin, a static character mesh with out its original skeleton might be considered useless, maybe, because it would require someone to create another from scratch in its desired 3D software, and it would never match original skeleton with original weights and all data, but once you have original skeleton its golden, pure perfection I might add, be thankful it exists already and fully reversed.

> Reply from Firephoenix1342
>
> It can benefit only professional animators.
Wrong, wrong, wrong even the most noob/beginner can pose an original skeletal mesh, these models are NOT limited to a pro only, anyone can use it and pose/animate it how ever they see fit like any other skeletal mesh.
Just because the tool does NOT export in-game animations to a known format its another story, they are NOT easy to reverse, animations in general take weeks/months of intense hard reversing depending on the format/engine.
## Post #69
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-01-29T08:18:55+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from mono24
>
> Firephoenix1342 wrote:And now the skeleton that is extracted with the models is absolutely useless.
Your so wrong on so many levels I don't even know where to begin, a static character mesh with out its original skeleton might be considered useless, maybe, because it would require someone to create another from scratch in its desired 3D software, and it would never match original skeleton with original weights and all data, but once you have original skeleton its golden, pure perfection I might add, be thankful it exists already and fully reversed.
Firephoenix1342 wrote:It can benefit only professional animators.
Wrong, wrong, wrong even the most noob/beginner can pose an original skeletal mesh, these models are NOT limited to a pro only, anyone can use it and pose/animate it how ever they see fit like any other skeletal mesh.
Just because the tool does NOT export in-game animations to a known format its another story, they are NOT easy to reverse, animations in general take weeks/months of intense hard reversing depending on the format/engine.

I understand that it is difficult. But it would be good, because in this game there are great animations. And yet the animator from me no. That's why I ask someone to do extrator animations.
## Post #70
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-01-31T15:42:18+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from REDEYE
>
> Hey daemon1, I'm working on blender addon for importing OVL format models from Jurassic World Evolution git repo: https://github.com/REDxEYE/OVL_IO
But i need a bit of help, i can't quite understand what is happening in your tool


Thouse numXX are driving me nuts.
That might be reflector decompiled variables names wrong or you actually named them numXX?
Anyways, can you DM me source code or just explain what happaning in your tool?
How to use your utility?? I dont know((
## Post #71
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-01-31T15:48:05+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> isocloud wrote:What would I have to offer to get animation support? Would like to import into Ark for mods etc. I can make a donation for the time of work required!
sorry i'm not accepting donations
there are many other, much more interesting animation engines waiting for me to support them, like Horizon zero dawn, Quantum break and all frostbite games

So you still will not remove the animation? It is a pity((, please make at least a tutorial on creating such programs for extracting ovl files. To be able to do it yourself.
## Post #72
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-31T16:44:40+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Firephoenix1342
>
> please make at least a tutorial on creating such programs for extracting ovl files. To be able to do it yourself.
If you think you can do it yourself, you don't need a tutorial.

Animations is the hardest task in game reversing. If you think you can do such things, you must be very good coder and reverse engineer. Such people don't need tutorials.
## Post #73
- Username: Firephoenix1342
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jan 25, 2019 9:32 pm
- Post datetime: 2019-01-31T19:34:47+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from daemon1
>
> Firephoenix1342 wrote:please make at least a tutorial on creating such programs for extracting ovl files. To be able to do it yourself.
If you think you can do it yourself, you don't need a tutorial.

Animations is the hardest task in game reversing. If you think you can do such things, you must be very good coder and reverse engineer. Such people don't need tutorials.

Sad but okay so be it, I will accept this.
## Post #74
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-02-01T15:35:05+00:00
- Post Title: Re: Jurassic World Evolution

Firephoenix1342, so you're at least able to extract/import models like vehicles and so on?
## Post #75
- Username: DennisNedry1993
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 27, 2018 8:03 pm
- Post datetime: 2019-03-25T16:38:14+00:00
- Post Title: Re: Jurassic World Evolution

Sorry for the shameless plug  After the game came out last year I put together a tool called Barbasol for extracting and injecting meta data (and some experimental mdl2/tex parsing), never got around to finish it, but it might help some of you out! Have a nice day guys!
[https://www.vg-resource.com/thread-34327.html](https://www.vg-resource.com/thread-34327.html)
## Post #76
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-03-26T22:50:09+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DennisNedry1993 ↑Tue Mar 26, 2019 12:38 am at Tue Mar 26, 2019 12:38 am
>
> 
Sorry for the shameless plug  After the game came out last year I put together a tool called Barbasol for extracting and injecting meta data (and some experimental mdl2/tex parsing), never got around to finish it, but it might help some of you out! Have a nice day guys!
https://www.vg-resource.com/thread-34327.html

This looks great, but I haven't figured out how to use it. Can you help me?
## Post #77
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-03-31T11:40:42+00:00
- Post Title: Re: Jurassic World Evolution

Same Problem here... i have no idea how to use this tool...
## Post #78
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-31T12:27:33+00:00
- Post Title: Re: Jurassic World Evolution

It's a C# project, VS2015; someone will need to compile it.  (Afaics Barbasol does not handle the skeleton and animations.)

(And we'd need a sample of a static model/vehicle to check it.)
## Post #79
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-03-31T15:24:17+00:00
- Post Title: Re: Jurassic World Evolution

I would be thankful and happy happy if someone could find a way and fix the skin pattern textures xD
Good i tried to create a own pattern texture... but not really accurate to the game or movie
## Post #80
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-04-03T18:50:59+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1 ↑Sun Mar 31, 2019 11:24 pm at Sun Mar 31, 2019 11:24 pm
>
> 
I would be thankful and happy happy if someone could find a way and fix the skin pattern textures xD
Good i tried to create a own pattern texture... but not really accurate to the game or movie

Can I ask you a thing? I guess you have the game installed (but I don't, I only have archives), so I ask you: does ninja ripper works with JW Evolution?
## Post #81
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-04-04T14:59:03+00:00
- Post Title: Re: Jurassic World Evolution

Ninja Ripper.. rips the Environment : Mountains and Trees.. but not the Animals or Fences etc.
I tried it a while ago.. 3D Ripper and NR sadly dosn't work
## Post #82
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-04-08T12:05:19+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1 ↑Thu Apr 04, 2019 10:59 pm at Thu Apr 04, 2019 10:59 pm
>
> 
Ninja Ripper.. rips the Environment : Mountains and Trees.. but not the Animals or Fences etc.
I tried it a while ago.. 3D Ripper and NR sadly dosn't work

Really? This is fucking sad.

In any case, does Ninja Ripper capture at least the vehicles?
## Post #83
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-04-08T15:47:10+00:00
- Post Title: Re: Jurassic World Evolution

You can try it if you want, maybe get you any great result... i tried it but without result.. all i got out was the terrain asself... single parts of the ways what i build ingame.. the textures.. but not any building, dinosaur, vehicle or people...
## Post #84
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-04-09T17:02:38+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1 ↑Mon Apr 08, 2019 11:47 pm at Mon Apr 08, 2019 11:47 pm
>
> 
You can try it if you want, maybe get you any great result... i tried it but without result.. all i got out was the terrain asself... single parts of the ways what i build ingame.. the textures.. but not any building, dinosaur, vehicle or people...

At the moment I don't have the game, but if I have it one day, I'll try. There is a hat with folded sides that is great and I want to put my hands on it. Until today I have never found a good hat model with folded sides and I need it!
## Post #85
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-04-10T11:59:44+00:00
- Post Title: Re: Jurassic World Evolution

I created a hat like this in past for my muldoon model
## Post #86
- Username: ShadyDub
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 23, 2018 11:09 pm
- Post datetime: 2019-04-10T15:21:55+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1 ↑Wed Apr 10, 2019 7:59 pm at Wed Apr 10, 2019 7:59 pm
>
> 
I created a hat like this in past for my muldoon model

Woah, looks very good! Any chance to get it in obj format?
## Post #87
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-04-10T17:41:05+00:00
- Post Title: Re: Jurassic World Evolution

I create since soon 10 years JP models... some models self for events like this
## Post #88
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-04-20T12:26:43+00:00
- Post Title: Re: Jurassic World Evolution

Did anyone try to finish the Barbasol Tool ?

[https://www.vg-resource.com/thread-34327.html](https://www.vg-resource.com/thread-34327.html)
## Post #89
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-05-10T23:30:00+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from ShadyDub ↑Wed Apr 10, 2019 11:21 pm at Wed Apr 10, 2019 11:21 pm
>
> 
Mcflyhigh1 wrote: ↑Wed Apr 10, 2019 7:59 pm
I created a hat like this in past for my muldoon model 



Woah, looks very good! Any chance to get it in obj format?

Sure, i can send you a link for it if you want
## Post #90
- Username: sumimi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 12, 2015 4:34 pm
- Post datetime: 2019-06-07T08:06:00+00:00
- Post Title: Re: Jurassic World Evolution

Anyone want to try it?
Jeep_Wrangler_2018
[https://mega.nz/#!4FcVVCjI!OseKQsPCY2DH ... 6z7eoIF7SY](https://mega.nz/#!4FcVVCjI!OseKQsPCY2DHe6bXc_WAvTAGOxXGG38096z7eoIF7SY)
## Post #91
- Username: TheDragon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 14, 2019 7:44 pm
- Post datetime: 2019-06-14T11:52:02+00:00
- Post Title: Re: Jurassic World Evolution

Hi, I was doing a project for school and was wondering if there was a possibility of getting or extracting the dying triceratops model from evolution???
## Post #92
- Username: TPTech
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 18, 2019 8:33 am
- Post datetime: 2019-07-18T01:20:30+00:00
- Post Title: Re: Jurassic World Evolution

I've never used a tool like this before - and maybe I'm doing this wrong. I downloaded the rar and extracted it. I now have a folder with 3 files in it.
fmt_xps_ascii.py
JurassicWE
zlib.net.dll

I drag my ovl from the JW Evolution game files on to JurassicWE. It opens a command prompt, creates a folder with the name of the OVL then closes the command prompt. The folder is empty though.
## Post #93
- Username: robd123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 16, 2018 7:23 am
- Post datetime: 2019-07-27T05:58:22+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from TPTech ↑Thu Jul 18, 2019 9:20 am at Thu Jul 18, 2019 9:20 am
>
> 
I've never used a tool like this before - and maybe I'm doing this wrong. I downloaded the rar and extracted it. I now have a folder with 3 files in it.
fmt_xps_ascii.py
JurassicWE
zlib.net.dll

I drag my ovl from the JW Evolution game files on to JurassicWE. It opens a command prompt, creates a folder with the name of the OVL then closes the command prompt. The folder is empty though.

You're doing it right after dragging it onto the exe file it should display the prompt and then create a number of texture files and a obj file in the folder it creates. I just tried it myself and it doesn't work for me either. I almost have a suspicion the Frontier may have patched the code to prevent the tool from working.
## Post #94
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-07-27T11:29:30+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from robd123 ↑Sat Jul 27, 2019 1:58 pm at Sat Jul 27, 2019 1:58 pm
>
> 
TPTech wrote: ↑Thu Jul 18, 2019 9:20 am
I've never used a tool like this before - and maybe I'm doing this wrong. I downloaded the rar and extracted it. I now have a folder with 3 files in it.
fmt_xps_ascii.py
JurassicWE
zlib.net.dll

I drag my ovl from the JW Evolution game files on to JurassicWE. It opens a command prompt, creates a folder with the name of the OVL then closes the command prompt. The folder is empty though.


You're doing it right after dragging it onto the exe file it should display the prompt and then create a number of texture files and a obj file in the folder it creates. I just tried it myself and it doesn't work for me either. I almost have a suspicion the Frontier may have patched the code to prevent the tool from working.

Yep the tool crash with the last DLC Dinos, all other still working
## Post #95
- Username: robd123
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 16, 2018 7:23 am
- Post datetime: 2019-07-27T16:09:21+00:00
- Post Title: Re: Jurassic World Evolution

It actually doesn't seem to be working with any of the dinos now regardless of whether they're DLC or not. My guess is they stealth patched it since there's nothing in the patch notes about it. So yeah, RIP model converter.
## Post #96
- Username: TPTech
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 18, 2019 8:33 am
- Post datetime: 2019-07-31T00:39:47+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from robd123 ↑Sun Jul 28, 2019 12:09 am at Sun Jul 28, 2019 12:09 am
>
> 
It actually doesn't seem to be working with any of the dinos now regardless of whether they're DLC or not. My guess is they stealth patched it since there's nothing in the patch notes about it. So yeah, RIP model converter.

Sad news! I guess I was a month or so too late to this tool.
## Post #97
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-08-01T08:46:29+00:00
- Post Title: Re: Jurassic World Evolution

Nope the JWE Tool works still... it just dosn't work with Claire's DLC Dinos... i convert it good like everyday and it worked every time
## Post #98
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-09-12T23:04:06+00:00
- Post Title: Re: Jurassic World Evolution

Any Updates about animations or skin scales and wrinkles ?!?!?!?!
## Post #99
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-11-05T15:24:16+00:00
- Post Title: Re: Jurassic World Evolution

Can you please add support for Planet zoo?
an example of ovl-ovs_
[https://www.mediafire.com/file/1zhu4ls7 ... e.rar/file](https://www.mediafire.com/file/1zhu4ls7cnzoxrx/Mandrill_Female.rar/file)
## Post #100
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-11-05T15:41:33+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from fil1969 ↑Tue Nov 05, 2019 11:24 pm at Tue Nov 05, 2019 11:24 pm
>
> 
Can you please add support for Planet zoo?
sorry, not any soon
## Post #101
- Username: Harlequinz Eg0
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 28, 2018 1:17 am
- Post datetime: 2019-12-09T01:19:06+00:00
- Post Title: Re: Jurassic World Evolution

Today is the day, Mod tools have been released after months of hard work by Hendrix, Neptune and I! Please head on over to the two pages for both the tool set and the blender plugin. Make sure to read both readme's as they contain installation, tutorials and troubleshooting instructions. Any issues can be reported to the bug tracker on the GitHub website. I hope you all enjoy the start of the modding scene for both Planet Zoo and Jurassic World Evolution!

[https://github.com/OpenNaja/cobra-tools/releases](https://github.com/OpenNaja/cobra-tools/releases)

[https://github.com/OpenNaja/cobra-blender/releases](https://github.com/OpenNaja/cobra-blender/releases)
## Post #102
- Username: Mcflyhigh1
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Sep 28, 2018 10:59 pm
- Post datetime: 2019-12-12T08:47:50+00:00
- Post Title: Re: Jurassic World Evolution

Any chance to open the new ovl's to get the newer models ?
## Post #103
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2019-12-12T18:34:34+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Mcflyhigh1 ↑Thu Dec 12, 2019 4:47 pm at Thu Dec 12, 2019 4:47 pm
>
> 
Any chance to open the new ovl's to get the newer models ?

yes actually, i tested it with the Albertosaurus and it worked
## Post #104
- Username: brmbgb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 27, 2019 3:56 am
- Post datetime: 2019-12-26T20:07:21+00:00
- Post Title: Re: Jurassic World Evolution

I'm having issues getting this new tool to work, following the instructions, I double click on the OVL_tool.bat, but nothing happens, it wont open for me. I'm not fully convinced I've got everything I need to get his going, could someone point me in the right direction or even just tell me how to get this to work, basically I want to change textures of some of the dinosaurs, so if I can extract the current textures to edit, I think it'll be a good start.
thanks.
## Post #105
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-12-29T19:29:13+00:00
- Post Title: Re: Jurassic World Evolution

Seems that the new DLC dont work with anything. All the old files should work fine. 
Here is the truck to the new DLC if anyone wants to take a look at it. I tried Model Researcher, cant seem to find the algorithm. 
[https://drive.google.com/file/d/12sZNRO ... sp=sharing](https://drive.google.com/file/d/12sZNRO1WeIxJJ_UQgwaqKWXANi1HRnGF/view?usp=sharing)
I was able to decompress the file using Barbasol. It crashes or does something and just produces a .DAT file. 
Here is that file.
[https://drive.google.com/file/d/1b0wjc7 ... sp=sharing](https://drive.google.com/file/d/1b0wjc7l9YGS6EKSls-kDfUm2ZW9s4HRk/view?usp=sharing)
## Post #106
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-29T23:11:08+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from brmbgb ↑Fri Dec 27, 2019 4:07 am at Fri Dec 27, 2019 4:07 am
>
> 
I'm having issues getting this new tool to work, following the instructions, I double click on the OVL_tool.bat, but nothing happens, it wont open for me. I'm not fully convinced I've got everything I need to get his going, could someone point me in the right direction or even just tell me how to get this to work, basically I want to change textures of some of the dinosaurs, so if I can extract the current textures to edit, I think it'll be a good start.
thanks.Open run it in a cmd (type: python ovl_tool_gui.py) to see what error occurs; you probably did not follow the instructions correctly.

> Reply from Sharppy ↑Mon Dec 30, 2019 3:29 am at Mon Dec 30, 2019 3:29 am
>
> 
Seems that the new DLC dont work with anything. All the old files should work fine. 
Here is the truck to the new DLC if anyone wants to take a look at it. I tried Model Researcher, cant seem to find the algorithm. 
https://drive.google.com/file/d/12sZNRO ... sp=sharing
I was able to decompress the file using Barbasol. It crashes or does something and just produces a .DAT file. 
Here is that file.
https://drive.google.com/file/d/1b0wjc7 ... sp=sharing
Our tool (link posted by Harlequinz Eg0) works for the latest DLC still. Your RAR is missing the TourTruck.ovs.textures_l1 file, so the tool can not open the OVL archive.

Currently working on getting the tiled detail scales correctly into blender:
## Post #107
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-12-30T12:38:40+00:00
- Post Title: Re: Jurassic World Evolution

Yeah I cant figure it out. Tried for almost 4 hours now.. Nothing but errors. 
[](https://ibb.co/q92mYXG)
Could you maybe just open this file for me ?
[https://drive.google.com/open?id=12sZNR ... XANi1HRnGF](https://drive.google.com/open?id=12sZNRO1WeIxJJ_UQgwaqKWXANi1HRnGF)
BTW i do have the textures in the OVL folder. There are 2 files.
Greatly appreciate it.
## Post #108
- Username: quixotickel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 22, 2019 2:42 pm
- Post datetime: 2020-01-02T04:36:28+00:00
- Post Title: Re: Jurassic World Evolution

Hi all, 

I was able to get the OVL extractor installed and can successfully extract the MDL2, MS2 and PNG files (yay!). Per my blender add-ons, I've also been able to get them installed and have "checked" them to be enabled.  

However, when I try to "import" Cobra or anything similar isn't showing in the available options.  Is there something additional I need to do?

Thanks!
## Post #109
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-01-02T20:14:57+00:00
- Post Title: Re: Jurassic World Evolution

Either you haven't checked the box in the addons list to activate them or you're using a wrong blender version? 2.79 only for now, soon to migrate to 2.81. You can get support on this discord: [https://discord.gg/3AjAbdZ](https://discord.gg/3AjAbdZ)
## Post #110
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-01-03T17:05:46+00:00
- Post Title: Re: Jurassic World Evolution

hi, yhe cobra tool works perfectly with planet zoo, but with Jw every model i try to open in the ovl tool gui, i have this error.: Could not find a fragment matching header types(2.2)
any help, please?
## Post #111
- Username: MisterDino
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 06, 2020 6:10 am
- Post datetime: 2020-01-05T23:10:15+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Harlequinz Eg0 ↑Mon Dec 09, 2019 9:19 am at Mon Dec 09, 2019 9:19 am
>
> 
Today is the day, Mod tools have been released after months of hard work by Hendrix, Neptune and I! Please head on over to the two pages for both the tool set and the blender plugin. Make sure to read both readme's as they contain installation, tutorials and troubleshooting instructions. Any issues can be reported to the bug tracker on the GitHub website. I hope you all enjoy the start of the modding scene for both Planet Zoo and Jurassic World Evolution!

https://github.com/OpenNaja/cobra-tools/releases

https://github.com/OpenNaja/cobra-blender/releases

Hi, Thank, great job!!!

Perfecto con Planet Zoo
Con JWE tengo un error:  "unpack requires a buffer of 4 bytes"

Me puedes ayudar por favor. Muchas gracias.
## Post #112
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-01-08T19:28:55+00:00
- Post Title: Re: Jurassic World Evolution

Update cobra tools to latest release.
## Post #113
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-01-09T05:49:00+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Thu Jan 09, 2020 3:28 am at Thu Jan 09, 2020 3:28 am
>
> 
Update cobra tools to latest release.

updated, but still the same error
## Post #114
- Username: Hg9m720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 14, 2020 12:26 am
- Post datetime: 2020-01-13T16:48:44+00:00
- Post Title: Re: Jurassic World Evolution

Hi all,

I've been having trouble getting the ovl_tool.bat to work. When I first downloaded it and installed Python, every time I tried to run it, I'd get an error saying "This app can't run on your PC". I tried to retrace my steps and reinstalled Python numerous times. The tutorial says to use Python 3.6 or 3.7, I was using 3.8 so I uninstalled and reinstalled 3.7, I still got the same error. And yes I set it to the "path" whenever I tried to reinstall Python.

This morning I once again tried to retrace my steps by watching videos on how to properly install Python, as well as pyqt5 and imageio. I followed each one exactly and now when I try to reopen ovl_tool.bat I don't get the error message, but a command prompt window opens but closes after a second or two. Also when I try to run the file as administrator I get the "This app can't run on your PC" error again. I think another thing I should mention is whenever I try to run Python through the Run app on windows I get the "This app can't run on your PC" error.

All I want to do is increase the size of the Spinosaurus model, that's all. I'm no coder and I have no modding experience. I can't even get to editing models in Blender because I can't access MDL2 files because of these errors. I feel like I've followed every step exactly, but I can't get this to work. Any help would be greatly appreciated. If this thread isn't the right place to ask about this, where should I go? Sorry if that is a stupid question
## Post #115
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-01-13T20:13:03+00:00
- Post Title: Re: Jurassic World Evolution

If you have installed python with a launcher, you can also double-click the py files directly instead of the bat shortcuts. (for some reason they are no longer 'trusted' by default, lol - used to be different)

If that doesn't do the trick, open a cmd or powershell in the ovl-tools folder and type: python ovl_tool_gui.py
If it doesn't run, you've probably not installed a python dependency, post the whole error log.
## Post #116
- Username: Hg9m720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 14, 2020 12:26 am
- Post datetime: 2020-01-14T01:23:32+00:00
- Post Title: Re: Jurassic World Evolution

Thanks for replying.

I tried what you said in regards to opening a powershell in the folder (cmd isn't listed as an option for some reason.) I typed python ovl_tool_gui.py
and I got this message:

Traceback (most recent call last):
  File "ovl_tool_gui.py", line 9, in <module>
    from pyffi_ext.formats.ovl import OvlFormat
ModuleNotFoundError: No module named 'pyffi_ext.formats'

I'm not sure what you mean by a "python dependency". Do you mean pyffi 2.2.4.dev3, pyqt5 and imageio? I installed those, however I think I recall when installed imageio there was something in the message(I don't know proper coding vocabulary) that said something about the path or something. I don't know how to repeat the message.

I installed python with an exe file, Is that what you mean by launcher? Because when I do that a cmd window briefly pops up but disappears. Please excuse my complete noobiness and ignorance on figuring this out. Thank you for your help.

Update:

Good news, I was able to open the ovl_tool.bat. I used another version of cobra tool that I downloaded yesterday. It was simply called "cobra-tools" instead of "cobra-tools-master" in case anyone is wondering.

I was able to load the spino mdl2 file into blender and I seemed to scale it up as I wanted. Now I need to figure out how to actually get it to work in game. I followed the faq on GitHub on exporting it, but instead of applying the changes, it just made a copy of the original file(The unedited version). I'm not sure how you get modded models in game. I know it is really stupid to ask, but any help would really be amazing. Again, I have no modding experience nor am I a 3D modeler, I'm a complete noob on these sort of things
## Post #117
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-01-14T18:10:21+00:00
- Post Title: Re: Jurassic World Evolution

> ModuleNotFoundError: No module named 'pyffi_ext.formats'
You downloaded the dev branch instead of a release.

Follow the instructions and tutorials, it's all written down.
## Post #118
- Username: Hg9m720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jan 14, 2020 12:26 am
- Post datetime: 2020-01-15T00:24:23+00:00
- Post Title: Re: Jurassic World Evolution

I just downloaded the pyffi_ext-master file. I was missing that. I'm not sure what to do with it. I didn't see in the tutorials what to do with it and the readme doesn't say what to do with it. I tried putting it in the cobra tools folder and when I open powershell and type "python ovl_tool_gui.py" I get this:

"(null): can't open file 'ovl_tool_gui.py': [Errno 2] No such file or directory"

The file is clearly in the folder, and I'm using cobra-tools-1.4.1. I have no idea what I'm doing...

Update: Never mind. I've figured it out. Disregard my previous messages. Thank you for your help again.
## Post #119
- Username: PaleoKnight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 19, 2020 7:36 am
- Post datetime: 2020-01-19T00:24:38+00:00
- Post Title: Re: Jurassic World Evolution

I am unable to open ovl_tool.bat so how do I do it?
## Post #120
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-01-20T15:22:03+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from PaleoKnight ↑Sun Jan 19, 2020 8:24 am at Sun Jan 19, 2020 8:24 am
>
> 
I am unable to open ovl_tool.bat so how do I do it?
Follow the installation instructions.
## Post #121
- Username: PaleoKnight
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jan 19, 2020 7:36 am
- Post datetime: 2020-04-06T01:36:05+00:00
- Post Title: Re: Jurassic World Evolution

Just one more question: does this tool support mods?
## Post #122
- Username: Wildzooguy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 04, 2020 11:42 pm
- Post datetime: 2020-04-06T21:43:50+00:00
- Post Title: Re: Jurassic World Evolution

This worked momentarily for me but when I tried to load it in blender there's a Pyffi Something Traceback error.
## Post #123
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-04-07T07:24:16+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from PaleoKnight ↑Mon Apr 06, 2020 9:36 am at Mon Apr 06, 2020 9:36 am
>
> 
Just one more question: does this tool support mods?Yeah it does.

> Reply from Wildzooguy ↑Tue Apr 07, 2020 5:43 am at Tue Apr 07, 2020 5:43 am
>
> 
This worked momentarily for me but when I tried to load it in blender there's a Pyffi Something Traceback error.Follow the installation instructions.
## Post #124
- Username: Wildzooguy
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 04, 2020 11:42 pm
- Post datetime: 2020-04-07T10:47:16+00:00
- Post Title: Re: Jurassic World Evolution

blender is saying 
Traceback (most recent call last):
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\__init__.py", line 68, in execute
    from . import import_mdl2
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\import_mdl2.py", line 12, in <module>
    from .pyffi_ext.formats.ms2 import Ms2Format
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\pyffi_ext\formats\ms2\__init__.py", line 46, in <module>
    import pyffi.object_models.xml
ModuleNotFoundError: No module named 'pyffi'

location: <unknown location>:-1
## Post #125
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2020-04-08T20:13:17+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Wildzooguy ↑Tue Apr 07, 2020 6:47 pm at Tue Apr 07, 2020 6:47 pm
>
> 
blender is saying 
Traceback (most recent call last):
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\__init__.py", line 68, in execute
    from . import import_mdl2
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\import_mdl2.py", line 12, in <module>
    from .pyffi_ext.formats.ms2 import Ms2Format
  File "C:\Users\Wild\AppData\Roaming\Blender Foundation\Blender\2.81\scripts\addons\cobra-blender\pyffi_ext\formats\ms2\__init__.py", line 46, in <module>
    import pyffi.object_models.xml
ModuleNotFoundError: No module named 'pyffi'

location: <unknown location>:-1

You didn't install pyffi for blender, follow the installation instructions!
## Post #126
- Username: Furia504
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon May 01, 2017 4:36 am
- Post datetime: 2020-07-21T19:14:10+00:00
- Post Title: Re: Jurassic World Evolution

Eh leído todo el post y la verdad es que no me funciona, tengo windows 7 32bits, instale el tool de cobra y no me deja abrirlo, necesito convertir unos dinosaurios a .obj pero no consigo lograrlo, y creo que esta es la única forma de hacerlo, ya que investigue y no consigo mas, por favor alguien que me ayude o me oriente. gracias
## Post #127
- Username: jamesmiller57
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 15, 2020 7:50 am
- Post datetime: 2020-08-09T23:56:47+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Mon Dec 30, 2019 7:11 am at Mon Dec 30, 2019 7:11 am
>
> 
brmbgb wrote: ↑Fri Dec 27, 2019 4:07 am
I'm having issues getting this new tool to work, following the instructions, I double click on the OVL_tool.bat, but nothing happens, it wont open for me. I'm not fully convinced I've got everything I need to get his going, could someone point me in the right direction or even just tell me how to get this to work, basically I want to change textures of some of the dinosaurs, so if I can extract the current textures to edit, I think it'll be a good start.
thanks.
Open run it in a cmd (type: python ovl_tool_gui.py) to see what error occurs; you probably did not follow the instructions correctly.
Sharppy wrote: ↑Mon Dec 30, 2019 3:29 am
Seems that the new DLC dont work with anything. All the old files should work fine. 
Here is the truck to the new DLC if anyone wants to take a look at it. I tried Model Researcher, cant seem to find the algorithm. 
https://drive.google.com/file/d/12sZNRO ... sp=sharing
I was able to decompress the file using Barbasol. It crashes or does something and just produces a .DAT file. 
Here is that file.
https://drive.google.com/file/d/1b0wjc7 ... sp=sharing

Our tool (link posted by Harlequinz Eg0) works for the latest DLC still. Your RAR is missing the TourTruck.ovs.textures_l1 file, so the tool can not open the OVL archive.

Currently working on getting the tiled detail scales correctly into blender:
can you tell me how you got the scale normal maps on the spinosaures pls there is no normal map for it when i drag it to daemeons jw program pls tell
## Post #128
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-11-12T00:02:54+00:00
- Post Title: Re: Jurassic World Evolution

Anyone know whats up with the new Jurassic World Evo 2 ?
[](https://ibb.co/jzqCdBr)

Does the tool need updated or am I missing something ?
## Post #129
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2022-01-22T20:49:47+00:00
- Post Title: Re: Jurassic World Evolution

Guys, Has anyone tried to unpack and open the models?
## Post #130
- Username: JulyNine
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 02, 2022 12:32 pm
- Post datetime: 2022-06-02T04:34:50+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from MichaelBFS ↑Sun Jan 23, 2022 4:49 am at Sun Jan 23, 2022 4:49 am
>
> 
Guys, Has anyone tried to unpack and open the models?
Hi，have you unpack and open the models in blender successfullly？
## Post #131
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2022-06-05T07:22:08+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from JulyNine ↑Thu Jun 02, 2022 12:34 pm at Thu Jun 02, 2022 12:34 pm
>
> 
MichaelBFS wrote: ↑Sun Jan 23, 2022 4:49 am
Guys, Has anyone tried to unpack and open the models?

Hi，have you unpack and open the models in blender successfullly？

Hi, 
 no, I didn't, I don't know how. (((
## Post #132
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2022-06-18T17:52:01+00:00
- Post Title: Re: Jurassic World Evolution

Latest update for JWE2 has completely changed the structure of ms2 files. It appears to be an optimization to allow for effective instancing and alpha blending of many small mesh chunks (feathers). If anyone is up for the challenge, feel free to help.
Scratch that, got it!
## Post #133
- Username: jamesmiller20110
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 02, 2023 10:56 am
- Post datetime: 2023-01-02T03:01:23+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Sun Jun 19, 2022 1:52 am at Sun Jun 19, 2022 1:52 am
>
> 
Latest update for JWE2 has completely changed the structure of ms2 files. It appears to be an optimization to allow for effective instancing and alpha blending of many small mesh chunks (feathers). If anyone is up for the challenge, feel free to help.
Scratch that, got it!
have you figured out how to add the tiled details into the dinosaur im still stuck on that and i really want to add them because of how much realistic it would look please let me know if you figured out how to add the tiled details of the scales and stuff
## Post #134
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-05-11T17:50:34+00:00
- Post Title: Re: Jurassic World Evolution

We have worked out the uncompressed variant of the animation format (vec3f translation, quat4h rotation, float scale) and are able to export custom animations with correct transforms from blender. However, on most animations the animation keys are compressed with an unknown algorithm. Anyone interested in helping to figure that algorithm out?
## Post #135
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-06-15T14:06:19+00:00
- Post Title: Re: Jurassic World Evolution

We have managed to read the structure of compressed animations and can read the frame at the start of each 32-frame segment. The relative keys that follow can't be interpreted yet.
## Post #136
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-08-26T10:46:21+00:00
- Post Title: Re: Jurassic World Evolution

Somone knows how i can extract/ convert the animation files (*.manis) into blender?
## Post #137
- Username: RemyDemy
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Apr 08, 2021 5:17 am
- Post datetime: 2023-08-29T14:50:26+00:00
- Post Title: Re: Jurassic World Evolution

I search animation for the Dinos in Blender too and  extract all the other Assets T, please anybody out there who can help????
## Post #138
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-08-29T15:57:02+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from RemyDemy ↑Tue Aug 29, 2023 10:50 pm at Tue Aug 29, 2023 10:50 pm
>
> 
I search animation for the Dinos in Blender too and  extract all the other Assets T, please anybody out there who can help????

I think there's no one outside, not for a very long time.
## Post #139
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-08-31T08:22:15+00:00
- Post Title: Re: Jurassic World Evolution

My post on the previous page just stated that that animations can be partially read by the blender cobra plugin.
## Post #140
- Username: weekstonz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 01, 2023 7:20 pm
- Post datetime: 2023-09-01T11:37:58+00:00
- Post Title: Re: Jurassic World Evolution

I see.. i'm not a extraction profi.. i'm rather 3d designer
## Post #141
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-02T13:01:11+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Thu Aug 31, 2023 4:22 pm at Thu Aug 31, 2023 4:22 pm
>
> 
My post on the previous page just stated that that animations can be partially read by the blender cobra plugin.

In the blender plug-in is just an option to do this, but its not working
## Post #142
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-02T13:02:12+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Jan666 ↑Sat Sep 02, 2023 9:01 pm at Sat Sep 02, 2023 9:01 pm
>
> 
DMZT2 wrote: ↑Thu Aug 31, 2023 4:22 pm
My post on the previous page just stated that that animations can be partially read by the blender cobra plugin.


In the blender plug-in is just an option to do this, but its not working, have you  tried to open any *.manis File?
## Post #143
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-09-04T10:12:23+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Jan666 ↑Sat Sep 02, 2023 9:02 pm at Sat Sep 02, 2023 9:02 pm
>
> 
Jan666 wrote: ↑Sat Sep 02, 2023 9:01 pm
DMZT2 wrote: ↑Thu Aug 31, 2023 4:22 pm
My post on the previous page just stated that that animations can be partially read by the blender cobra plugin.


In the blender plug-in is just an option to do this, but its not working, have you  tried to open any *.manis File?

you have to follow the installation instructions properly, you are likely missing a python module in blender, resulting in garbled animations.
## Post #144
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-04T14:18:21+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Mon Sep 04, 2023 6:12 pm at Mon Sep 04, 2023 6:12 pm
>
> 


you have to follow the installation instructions properly, you are likely missing a python module in blender, resulting in garbled animations.

I think i have installed it right, in every forum i read Animations aren't importable and on github "No animation export. Animation import is limited to Banis files and only works on some files.", are you sure you can import *.manis files into  blender?
## Post #145
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-09-06T08:19:32+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Jan666 ↑Mon Sep 04, 2023 10:18 pm at Mon Sep 04, 2023 10:18 pm
>
> 
DMZT2 wrote: ↑Mon Sep 04, 2023 6:12 pm


you have to follow the installation instructions properly, you are likely missing a python module in blender, resulting in garbled animations.


I think i have installed it right, in every forum i read Animations aren't importable and on github "No animation export. Animation import is limited to Banis files and only works on some files.", are you sure you can import *.manis files into  blender?
Yes, I know that they work because I have programmed the code myself:
[https://i.imgur.com/rC2B3ca.mp4](https://i.imgur.com/rC2B3ca.mp4)
[https://i.imgur.com/g4IaF6g.mp4](https://i.imgur.com/g4IaF6g.mp4)
The docs just have not been updated yet.
## Post #146
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-06T14:44:04+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Wed Sep 06, 2023 4:19 pm at Wed Sep 06, 2023 4:19 pm
>
> 
Jan666 wrote: ↑Mon Sep 04, 2023 10:18 pm
DMZT2 wrote: ↑Mon Sep 04, 2023 6:12 pm


you have to follow the installation instructions properly, you are likely missing a python module in blender, resulting in garbled animations.


I think i have installed it right, in every forum i read Animations aren't importable and on github "No animation export. Animation import is limited to Banis files and only works on some files.", are you sure you can import *.manis files into  blender?

Yes, I know that they work because I have programmed the code myself:

https://i.imgur.com/rC2B3ca.mp4
https://i.imgur.com/g4IaF6g.mp4
The docs just have not been updated yet.
I dont know what ia m doing Wrong, this is my Error Message, waht i am doing Wrong?
Python: Traceback (most recent call last):
  File "C:\Users\Jan\AppData\Roaming\Blender Foundation\Blender\3.5\scripts\addons\cobra-tools-master\plugin\modules_import\operators.py", line 38, in execute
    return import_manis.load(**keywords)
  File "C:\Users\Jan\AppData\Roaming\Blender Foundation\Blender\3.5\scripts\addons\cobra-tools-master\plugin\import_manis.py", line 56, in load
    for p_bone in b_armature_ob.pose.bones:
AttributeError: 'NoneType' object has no attribute 'pose'
## Post #147
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-09T05:26:37+00:00
- Post Title: Re: Jurassic World Evolution

Are there any other ways to insert animations into Blender besides using the Cobra tool? I've tried everything with Cobra across all Blender versions, but it simply doesn't work.
## Post #148
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2023-09-11T13:32:28+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from Jan666 ↑Sat Sep 09, 2023 1:26 pm at Sat Sep 09, 2023 1:26 pm
>
> 
Are there any other ways to insert animations into Blender besides using the Cobra tool? I've tried everything with Cobra across all Blender versions, but it simply doesn't work.No.
## Post #149
- Username: Jan666
- Rank: veteran
- Number of posts: 125
- Joined date: Thu Nov 01, 2018 1:26 am
- Post datetime: 2023-09-11T13:59:45+00:00
- Post Title: Re: Jurassic World Evolution

> Reply from DMZT2 ↑Mon Sep 11, 2023 9:32 pm at Mon Sep 11, 2023 9:32 pm
>
> 
Jan666 wrote: ↑Sat Sep 09, 2023 1:26 pm
Are there any other ways to insert animations into Blender besides using the Cobra tool? I've tried everything with Cobra across all Blender versions, but it simply doesn't work.
No.
Can you tell me with what kind of versions of Blender, python stuff and JWE2 do you handle this?
