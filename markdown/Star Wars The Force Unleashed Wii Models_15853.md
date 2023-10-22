## Post #1
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-02-09T21:25:45+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

So there has been a lot of work in the past on Krome Studio's file format with games like Clone Wars Republic Heroes getting a Blender Plugin and a Noesis plugin for the textures, but one game seems to have been left out that still has a lot of good models in it that aren't in any other star wars game.

This format is older than Clone wars Republic Heroes with their format for the models being MDL5 and these for TFU Wii being MDL3 so it shouldn't be to hard to work on this version of the format when the newer version already work.

Now sometime ago i found a RKV program to unpack the Wii archive but i've seen lost it and can't find where i found it at and the BMS scripts RKV don't work on the Wii version, But as for the PS2 version i found a BMS script on another site that extracts that RKV but found out the .tex files are much smaller size and doesn't contain normal maps or spec maps for the models just a diffuse while the Wii version contains those textures.

Here is a Wii version model i happen to find on my PC [http://www.mediafire.com/file/6vgtbzd07 ... mmando.rar](http://www.mediafire.com/file/6vgtbzd079q0wtz/Heavy_Commando.rar)

Also if someone wants i can provide you with the Wii RKV if needed to help edit the BMS script to unpack it.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-13T02:27:41+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

this is the best i could do with it so far  



A105_HeavyCommando_B_mdg.png (71.09 KiB) Viewed 917 times


i have Noesis auto creating the faces here but it isn't right as you can see. 
i don't know a whole lot about PS2 or Wii model formats either and i usually
avoid them, i'm not sure how the face indices are stored in many of them.  

> Reply from JakeGreen
>
> Also if someone wants i can provide you with the Wii RKV if needed to help edit the BMS script to unpack it.
you should open a thread on Zenhax and see if aluigi can fix the script.
## Post #3
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2017-02-13T18:16:43+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

As a last resort, I recall Ninja Ripper can be used with Dolphin, which keeps the skeletal structure/t-pose for quite a few games. Then you'd have to sift through all the world models, however.
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-02-13T21:38:14+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from AceWell
>
> this is the best i could do with it so far  
A105_HeavyCommando_B_mdg.png
i have Noesis auto creating the faces here but it isn't right as you can see. 
i don't know a whole lot about PS2 or Wii model formats either and i usually
avoid them, i'm not sure how the face indices are stored in many of them.  
JakeGreen wrote:Also if someone wants i can provide you with the Wii RKV if needed to help edit the BMS script to unpack it.
you should open a thread on Zenhax and see if aluigi can fix the script.

That's awesome you got this far with the models, can't wait to see them fully working. and will post on there later tonight.

> Reply from Teancum
>
> As a last resort, I recall Ninja Ripper can be used with Dolphin, which keeps the skeletal structure/t-pose for quite a few games. Then you'd have to sift through all the world models, however.

Yeah i've tried NinjaRipper with Dolphin 5.0 64bit and NR version 1.5.2 it rips out most of the models but no characters and sometime before i don't remember if it was a 32bit version of Dolphin but i was able to get out characters but they weren't in a t-pose just whatever pose you capture them in.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-01T19:33:02+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

Tool for skeletal models, PS2 & Wii (now with cloth)

You need .mdl & .mdg files. Drop any of these onto the tool and it will make .obj file with exported model.

Tool for static models - force_unleashed_wii_static.exe


[swtfu.rar](https://xentaxbackup.github.io/file/14390_swtfu.rar)
## Post #6
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-10-01T22:55:54+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> Here's a quick test of this guy's geometry. Do you need him with bones, or static model is enough?

It doesn't matter. With how you got the model working would it be possible to do the same on others? and if so would you release your method?

Here is another one if you want to test it out as well with textures [http://www.mediafire.com/file/olhmqoklw ... rooper.rar](http://www.mediafire.com/file/olhmqoklwlg177k/BailTrooper.rar)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-02T16:18:57+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from JakeGreen
>
> Here is another one if you want to test it out as well with textures http://www.mediafire.com/file/olhmqoklw ... rooper.rar

This one is completely different. This is MDG3, and commando was MDG5. Also do you have any tool to open these textures?

Commando attached. If you send me some more in MGD5 format, I can check them and make my tool extract them. Without that, I think tool will only extract this commando.
[A105_HeavyCommando_B.rar](https://xentaxbackup.github.io/file/13370_A105_HeavyCommando_B.rar)
## Post #8
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-10-02T16:27:12+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> JakeGreen wrote:Here is another one if you want to test it out as well with textures http://www.mediafire.com/file/olhmqoklw ... rooper.rar

This one is completely different. This is MDG3, and commando was MDG5. Also do you have any tool to open these textures?

Reason probably for that is I think the file I posted in the op was from the ps2 version and the file I posted now is from the wii version,textures aren’t to important as I can get them from dolphin emulator but I would look into the threads for clone wars republic heroes as this has the same format but more updated and the texture format is the same.

I can supply you more of that version of the format when i’m able to get on my pc later today.
## Post #9
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-10-02T21:24:36+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

Sorry for the double post but didn't think you would see the models if i just edited my post.

Here is a mix of weapons,characters and vehicles so you can look at everything.
[https://www.mediafire.com/file/gxpuapf1 ... Models.rar](https://www.mediafire.com/file/gxpuapf1xqbyxb9/Wii_Models.rar)
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-03T16:46:07+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

wii models. almost there
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-03T18:31:14+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

here we go:


[A207_BailTrooper_F.rar](https://xentaxbackup.github.io/file/13383_A207_BailTrooper_F.rar)
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-10-03T18:33:57+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> here we go:

Very nice do you think your tool will be able to get the rest just fine and when you do think it'll be released?

Also did you get the textures working or get them from Dolphin?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-03T19:50:32+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from JakeGreen
>
> Very nice do you think your tool will be able to get the rest just fine and when you do think it'll be released?

Yes I think it will. If you provide a few more PS2 models, I can check it better. As for release, maybe tomorrow, or later this week.

> Reply from JakeGreen
>
> Also did you get the textures working or get them from Dolphin?

The day before yesterday was the first time I worked with PS2/wii models. I have no idea whats dolphin, or how exactly PS2 textures are represented. They look like DXT, maybe just swizzled. If you really need that, I can look into this, but I think this must be usual for PS2, and some tools must exist for them. Or noesis plugin.
## Post #14
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-10-03T21:33:00+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> JakeGreen wrote:Very nice do you think your tool will be able to get the rest just fine and when you do think it'll be released?

Yes I think it will. If you provide a few more PS2 models, I can check it better. As for release, maybe tomorrow, or later this week.
JakeGreen wrote:Also did you get the textures working or get them from Dolphin?

The day before yesterday was the first time I worked with PS2/wii models. I have no idea whats dolphin, or how exactly PS2 textures are represented. They look like DXT, maybe just swizzled. If you really need that, I can look into this, but I think this must be usual for PS2, and some tools must exist for them. Or noesis plugin.

Well I no longer have any ps2 files only wii files and those are more higher poly and have higher res textures as the ones from the ps2 only have a diffuse at lower res and nothing else.

When I say dolphin i’m talking about the dolphin emulator for wii games I can dump the textures with that game but it’s sometimes hard to find what you need because it dumps every texture from the whole scene.

But all the files I provided that wasn’t from the op are wii models and textures, but as for the textures you should look at this noesis plugin as it was created using the same format from the same company that created this game just the format may have been updated a bit. [viewtopic.php?f=18&t=14297](http://forum.xentax.com/viewtopic.php?f=18&t=14297)
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-04T16:19:57+00:00
- Post Title: Star Wars The Force Unleashed Wii Models

ok no problem. Tool posted up there in the thread - [viewtopic.php?p=134158#p134158](http://forum.xentax.com/viewtopic.php?p=134158#p134158)

Ship models which you provided will not work, because they naturally have different format, they have no weights, and so on. In case you need them, let me know.
## Post #16
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-21T10:25:30+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Did anyone figure out how to extract the Wii .rkv archives? None of the rkv extractors and scripts for other games work on it.
## Post #17
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2017-10-21T15:15:57+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from o0Crofty0o
>
> Did anyone figure out how to extract the Wii .rkv archives? None of the rkv extractors and scripts for other games work on it.

Same here i tried some tools while one tried to extract the content just end with files with 0 bytes and others just give me errors.
## Post #18
- Username: Javitolo98
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 20, 2017 3:09 am
- Post datetime: 2017-10-22T15:23:11+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

In the first page they said everything what you need ,at least for me it works, but for me the problem is not extract the models,is convert the textures from .tex to another format,I tried with the noesis plugin for The clone wars Republic Heroes and I get this message
## Post #19
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-22T15:38:41+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from Javitolo98
>
> In the first page they said everything what you need ,at least for me it works, but for me the problem is not extract the models,is convert the textures from .tex to another format,I tried with the noesis plugin for The clone wars Republic Heroes and I get this message
[img]https://i.imgur.com/lvYUei4.jpg[/im]
Would you eventually have a link to the rkv extractor that actually works with these archives?
## Post #20
- Username: Javitolo98
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 20, 2017 3:09 am
- Post datetime: 2017-10-22T15:48:40+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from o0Crofty0o
>
> Javitolo98 wrote:In the first page they said everything what you need ,at least for me it works, but for me the problem is not extract the models,is convert the textures from .tex to another format,I tried with the noesis plugin for The clone wars Republic Heroes and I get this message
[img]https://i.imgur.com/lvYUei4.jpg[/im]
Would you eventually have a link to the rkv extractor that actually works with these archives?

Is this one [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
and you need this script(the one in yellow) [http://aluigi.altervista.org/search.php?src=RKV](http://aluigi.altervista.org/search.php?src=RKV)

Then you will get the models in diferent files,for convert it to .obj  you should drop the .mdl and .mdg files of the character you want to convert to this tool  [viewtopic.php?f=18&t=14297](http://forum.xentax.com/viewtopic.php?f=18&t=14297)
## Post #21
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-10-22T21:29:01+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Thanks! The script version you linked didn't work with the Wii version for me but to anyone else searching the one that works type 'spyro rkv' in google. That bms works
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-23T01:06:57+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from Javitolo98
>
> and you need this script(the one in yellow) http://aluigi.altervista.org/search.php?src=RKV
wrong one, here is direct link to rkv2 script for Wii SWTFU rkv archives   
[http://aluigi.org/bms/rkv2.bms](http://aluigi.org/bms/rkv2.bms)

> Reply from Javitolo98
>
> Then you will get the models in diferent files,for convert it to .obj  you should drop the .mdl and .mdg files of the character you want to convert to this tool  viewtopic.php?f=18&t=14297
no thats a Noesis python texture script for PC Republic Heroes you linked to, and it won't work with Wii platform texture samples anyway.
the model conversion tool is posted on the first page of this very thread here
[viewtopic.php?p=134158#p134158](http://forum.xentax.com/viewtopic.php?p=134158#p134158)

edit

> Reply from daemon1
>
> They look like DXT, maybe just swizzled.
yes they look like this to me also, i wonder do all Nintendo Wii systems (Wii/Wii U/Wii Mini) use the same tiling algo?
## Post #23
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-24T10:45:13+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

the wii cpu is powerpc. big-endian. the gpu is ati tho. i had a sample from another wii game. i'm pretty sure it's dxt. as raw the texture pattern shows up. gotta read big-endian or bswap32. maybe 16 or 64 swap.
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-10-24T16:04:13+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

there's more to it than just a swap. Looks also swizzled. I have no info about wii swizzle.

I could try restoring it if I had both swizzled and non-swizzled image (to compare), but I don't have them.
## Post #25
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-24T17:40:07+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

yep. i swapped and it did nothing. and there's some swizzle code on github. that looks nasty tho.
## Post #26
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-24T22:27:24+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Wii version uses standard Wii texture formats. I've made a Noesis plugin, link is in my signature.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-11-10T21:58:34+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

wii cloth support:

[viewtopic.php?p=134158#p134158](http://forum.xentax.com/viewtopic.php?p=134158#p134158)
## Post #28
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-13T11:45:26+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

tool for static models

[viewtopic.php?p=134158#p134158](http://forum.xentax.com/viewtopic.php?p=134158#p134158)
## Post #29
- Username: CrazyGentleman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 20, 2018 12:57 am
- Post datetime: 2018-05-21T15:31:27+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Whenever I try to convert a .mdl to .obj, the UV seems to mess up pretty badly. How did you fix/handle this?

Example:
[hide]

[/hide]
## Post #30
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-21T17:36:14+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

i didnt check UVs on static models
now i dont have time for that
## Post #31
- Username: CrazyGentleman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 20, 2018 12:57 am
- Post datetime: 2018-05-21T18:20:08+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> i didnt check UVs on static models
now i dont have time for that

Ah okay, would you be willing to take a look at it when you have time?

Kind regards,

CrazyGentleman
## Post #32
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-21T19:46:31+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

...
## Post #33
- Username: CrazyGentleman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 20, 2018 12:57 am
- Post datetime: 2018-05-21T20:46:37+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

> Reply from daemon1
>
> ...

I'm not sure if this program is different from the one you posted earlier in this thread, but this one seems to crash everytime I import the converted .obj into an 3D Modelling application.

Kind regards,

CrazyGentleman
## Post #34
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-22T04:38:57+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

this was corrected version for static objects
it works with correct UVs for all static objects i checked
## Post #35
- Username: CrazyGentleman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 20, 2018 12:57 am
- Post datetime: 2018-05-22T07:44:51+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Sorry, was a mistake on my end. Thank you so much for taking the time to help me!

EDIT: Okay, the problem is still there for me, and it seems to show up for every .mdl with multiple meshes in them.

Kind regards,

CrazyGentleman
## Post #36
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-22T15:14:25+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

it works good for all .mdl that i tried, including those with multiple meshes in them
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-05-22T16:02:09+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

wii tools updated in the post above, UVs fixed

[viewtopic.php?p=134158#p134158](http://forum.xentax.com/viewtopic.php?p=134158#p134158)
## Post #38
- Username: CrazyGentleman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 20, 2018 12:57 am
- Post datetime: 2018-07-09T18:37:50+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Hello Daemon,

I'm afraid I still have the same problem for quite some models. I believe they seem to be models with physics/skeletons/animations originally in them, such as (certain) vehicles and turrets. Would you be willing to take another look at it if you have time? Sorry to ask it again.



Kind regards,

CrazyGentleman
## Post #39
- Username: EveryCafe44
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jul 14, 2021 4:01 am
- Post datetime: 2021-07-13T20:04:46+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

Does anyone happen to have the Clone Animations? I mean all the Clone Animations of the Force Unleashed Phase 3 Clone Troopers from the Wii/PS2 versions? If so that'd be great! It's kind of important!
## Post #40
- Username: GustavoPredador
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 25, 2020 4:55 am
- Post datetime: 2023-07-31T16:17:15+00:00
- Post Title: Re: Star Wars The Force Unleashed Wii Models

I'm trying to convert Darth Vader .anm to fbx. I already have the 3d model of it

A002_DarthVader_PC: PSP - PS2 - Wii 
[https://cdn.discordapp.com/attachments/ ... derTFU.zip](https://cdn.discordapp.com/attachments/543593726149394434/1135588788744245318/DarthVaderTFU.zip)
