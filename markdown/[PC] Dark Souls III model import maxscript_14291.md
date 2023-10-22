## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-04-30T16:56:16+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Hi guys! Here's maxscript to import [PC] Dark Souls III character's/monster's models with bones (3ds max 2009-2012). Inside archive - maxscripts for models+.hkx bones. 



P.S. Script doesn't import weights (this part is disabled, you can check by yourself), you can enable it by uncommenting some areas in the script, but skeleton from model file will be twisted. Though, if you import model with weights and messed skeleton, I guess you will be able to use nice skeleton from .hkx file later  3ds max max users will understand, or any other who at least a bit experienced with 3 software. I will continue to work on Dark Souls 3 and DS2, so stay tuned if interested, I will show my progress here
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-01T17:38:38+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Here's Noesis plugin for .tpf texture containers, which should allow you to view and export textures for Dark Souls III
## Post #3
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-05-01T20:07:22+00:00
- Post Title: [PC] Dark Souls III model import maxscript

holy crap! thank you for your work!
may i ask what lines you need to change in the 3dsmax script to enable weighting/skinning? even if it's broken.

one more thing. it seems all of the uv's are broken. unfortunately the textures won't fit.

while the original diffuse looks like:
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-02T18:17:49+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Don't worry I know that   I'm working in order to solve any issues, though you can try this script, latest one I made. It will get you bones and weights+fixed uv's. I'm sure errors will be present, so fee free to report them here. 


[Dark_Souls_3.7z](https://xentaxbackup.github.io/file/10888_Dark_Souls_3.7z)
## Post #5
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-03T07:07:31+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Awesome job, man! Just reporting some errors I've encountered:
UV's are really weird: they look fine, but are over 100x bigger than the 0-1 UV space, and the faces/elements are improperly shaped or sized no matter what I try to do. This is on pretty much all characters and all the weapons I've tested.

Soul of Cinder's (C2580 in CHR folder) sword is messed up.

Latly, Yhorm the Giant (C2560 in CHR folder) only loads part of his armor, but not his body and the rest of his armor, nor his weapons.

Keep at it, mate, this is great stuff.
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-03T10:11:30+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Hmm, that's strange I don't have C2580, C2560 folder in that huge sample archive you sent me (tanks again for this). Are they from some other place? I can't test them right now unfortunately.

EDIT: I think I found models you talking about - messed sword in c5280 folder
## Post #7
- Username: foobarwtf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 03, 2016 3:45 am
- Post datetime: 2016-05-04T11:31:56+00:00
- Post Title: [PC] Dark Souls III model import maxscript

zaramot thanks!
Pity fire keeper(c1400) don't have much body mesh under her clothes...  
[](http://hostingkartinok.com/show-image.php?id=37082e5c00aa36475dd70205a6b5bb83)
(I believe I didn't apply the textures properly though, especially the files end with _r)

ps: the plugin for .tpf extension produces this image for 13th image in c2170.tpf:
[](http://hostingkartinok.com/show-image.php?id=af257fdbd87f33c5ada0515dd5851209)
(and it seems c2170 have uvw mapping problems?)
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-04T14:10:31+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Hmm, I don't have textures and .flver model for c2170. Can you provide them? Plus, what about meshes under clothes for c1400? You mean some meshes not importing?

EDIT: Just checked c1400, and I don't have texture + flver for this one too. It might be, that script requires fixing for models of their category xD

P.S. Guys what about player characters, I think I have none + I'm curious if Dark Souls III have some nice/cool looking armors? I need Lorian's Armor Set, Outrider Knight Armor Set, Wolf Knight Set.
## Post #9
- Username: foobarwtf
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 03, 2016 3:45 am
- Post datetime: 2016-05-04T16:45:51+00:00
- Post Title: [PC] Dark Souls III model import maxscript

I believe developers didn't put body meshes under clothes, and that's the reason I didn't see meshes under clothes.
And c5210 has some issues with it's clothes:
[](http://hostingkartinok.com/show-image.php?id=01a2abf9b957712bed0abaf3bc86154d)
## Post #10
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-04T17:00:17+00:00
- Post Title: [PC] Dark Souls III model import maxscript

A bit fixed version of Noesis plugin from DS3 .tpf files, fixed error with c5210, c1400 and c2170 .tpf
[fmt_DarkSouls_III_TPF.7z](https://xentaxbackup.github.io/file/10897_fmt_DarkSouls_III_TPF.7z)
## Post #11
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-06T06:42:16+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Wanted to inform you of an update, I tried your DSIII importer on Scholar of the First Sin FLV models, and it work 100% perfectly! I've been able to get all the DLC weapons, shields, and armors, but characters, maps, and objects can't be extracted from with any BinderTool version. Regardless, that's some awesome work!

As for more bugs with the script:
-Abyss Watchers (c3040) have some UV errors with their gauntlets.
-For the most part, models with the "goo" monsters inside of them (such as Iudex Gunder in c5110), the goo-monsters have improper UV's, although the rest of the model (such as Iudex Gunder himself) have proper UV's.

Thanks again for the great work! I'm really ecstatic that I finally got SotFS models working properly thanks to you.
## Post #12
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-06T10:00:44+00:00
- Post Title: [PC] Dark Souls III model import maxscript

Really nice to hear, that you managed to get models from SotFS! No need to thank me, I was very glad to help   Though, script isn't finished, I'm going to make it work properly with DS3 and even with SotFS, with time eventually xD
Thanks for the bug report, I'll take a look at models you said
## Post #13
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-06T11:23:52+00:00
- Post Title: [PC] Dark Souls III model import maxscript

but there are skeletons there are problems or not?
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-06T13:17:42+00:00
- Post Title: [PC] Dark Souls III model import maxscript

With Dark Souls 3 shouldn't be problems with skeleton. Well, actually with DS2 too, but about this I'm not at 100% certain. For all dark souls series + demon souls should be possible now to solve skeleton issues. But for Dark Souls 2 as I understand there's no proper extractor, right? Just for DLC and SotFS
## Post #15
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2016-05-06T17:49:00+00:00
- Post Title: [PC] Dark Souls III model import maxscript

That's what I was wondering. Does anyone know of a proper way of extracting the massive archive for SotFS so we can have the proper models? Bindertool doesn't work, nor does any of Rick's Tools.
## Post #16
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-06T18:29:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

if you can solve the problem of the skeletons of the demon's souls it would be a great thing. I promise that I'll thank me if you can live by my friend youtuber Italian.
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-07T07:37:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> if you can solve the problem of the skeletons of the demon's souls it would be a great thing. I promise that I'll thank me if you can live by my friend youtuber Italian.

I can't understand your last sentence. Though, if you have Demon's Souls extracted and could send me .hkx files from there (I think they are named skeleton.hkx too) I will make skeleton correct
## Post #18
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-07T07:48:44+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> dibe91 wrote:if you can solve the problem of the skeletons of the demon's souls it would be a great thing. I promise that I'll thank me if you can live by my friend youtuber Italian.

I can't understand your last sentence. Though, if you have Demon's Souls extracted and could send me .hkx files from there (I think they are named skeleton.hkx too) I will make skeleton correct

it is not necessary to extract. folders are already open and ready to watch the content.
[http://www.mediafire.com/download/756bi ... dy/obj.rar](http://www.mediafire.com/download/756bievo9f5b4dy/obj.rar)
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-07T08:55:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Dibe91, archive you provided contains objects, not characters/npc or monsters, so they mostly not rigged or skeleton is very simple. I guess, you need to send me char folder, so files with c***, something like that not o***?
## Post #20
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-07T09:30:27+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Dibe91, archive you provided contains objects, not characters/npc or monsters, so they mostly not rigged or skeleton is very simple. I guess, you need to send me char folder, so files with c***, something like that not o***?

I know and loading everything but my connection is slow and I do not know how long it takes. I step then the right link
## Post #21
- Username: Venom34
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 08, 2016 5:26 am
- Post datetime: 2016-05-08T00:44:36+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

How did you get the files inside of each data.bdt sorted out ? for me the data files get exported as separated bnd files with a random number as its prefix, e.g. "0332481108_Data4.bnd".

EDIT: What I mean is that I'm not getting the data exported into correct folders (like when exporting DS1 data, it shows you char folder, obj folder, etc.. and then their subfolders, but instead I'm getting .bnd files)
Also, every time I export tpfs I get corrupted textures (same format, same resolution, but they are just pure black).
I just tested the max script and when it's asking for an hkx file it won't find any in folders where I clearly have hkx files.

What the hell am I doing wrong ?
## Post #22
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-08T09:30:05+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I downloaded the appropriate files. I hope you can solve any soon. [http://www.mediafire.com/download/88h32 ... 5w/chr.rar](http://www.mediafire.com/download/88h32za28n8565w/chr.rar)

about Dark Souls 2, I can not take the models of SotFS version and if I use the basic version, there is the skeleton template files.
## Post #23
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-08T18:17:05+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

For SotFS, you'll only be able to take models from the "parts" folder, which means armour pieces and weapons, I've talked t Atvaark (developer of BinderTool) about the issue and I'm waiting on a response.

If you're wondering what skeleton to use for the armours and weapons, you can use the skeleton.hkx from any Dark Souls games.
## Post #24
- Username: BloatheadSorcerer
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Jan 16, 2015 5:10 am
- Post datetime: 2016-05-09T21:46:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I can't seem to find the download link for the MaxScript
where can i find it?
## Post #25
- Username: Glarkon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Jul 28, 2015 6:36 am
- Post datetime: 2016-05-09T23:11:05+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Where are the animations stored? Is it like DS1, where they were .anibnd files?
## Post #26
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-10T13:40:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

excuse me but then how do I get the models of dark souls 2?
## Post #27
- Username: amornthep
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 06, 2016 8:36 am
- Post datetime: 2016-05-12T11:43:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

any luck with the animations? files are using version 2014.1.0-r1 it seems.
## Post #28
- Username: HunterAP
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Aug 10, 2015 2:03 pm
- Post datetime: 2016-05-15T03:06:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey Zaramot, my friend has gone through all the character files and has this list of issues to share with you:
c1090 - broken UVs for black mass.
c2170 - missing entire meshes.
c2200 - mangled mesh.
c3040 - broken UVs for arms and possibly face.
c3140 - skeleton is completely misaligned; master at X: 9652.342, Y: 25911.4, Z: 8532.084. may be other problems.
c5030 - skeleton for nameless king off, probably not a huge problem though since he's intact in c5010.
c5110 - broken UVs for black mass.
c5140 - missing entire meshes.
c5160 - mangled torso mesh.
c5210 - skeleton might be incorrect.

The "black mass" is referring to the monster that comes out of Iudex Gundyr and some lesser hollows.
Good luck with these, and thanks again for all the work you put in to this.
## Post #29
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-15T08:36:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Ah, thanks a lot for the list. I will fix this as soon as it possible. Nice to see you guys interested in this
## Post #30
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-15T08:57:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

and as for demon's souls? you can solve the problem?
## Post #31
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-15T09:44:01+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Yup, I can xD I'm working on it now. I have several games to finish with. So, it's not as fast as I want it to be.
## Post #32
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-15T09:47:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I see. on your list there by chance darksider 2? because with some models, such as constructs, they do not have the skeleton and not the t-mode!
## Post #33
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-16T08:42:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Dibe91, here's skeleton.hkx from Demon's Souls, can you import/convert it with tools for Dark Souls 1 animations you told me about? Or with havoc tools? I need to know if I should make import-script for this, or we will do this in easier way xD
[skeleton.7z](https://xentaxbackup.github.io/file/10941_skeleton.7z)
## Post #34
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-16T09:58:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

to use that tool dark souls 1, it is necessary to convert it with HKX converter of skyrim. if you want to use what you have to adapt the converter for skeletons demon's souls. 

This is the instrument link.
[http://www.nexusmods.com/skyrim/download/37272](http://www.nexusmods.com/skyrim/download/37272) 

I also leave the link to the dark souls instruments 1.
[https://github.com/Danilodum/dark_souls_hkx/releases](https://github.com/Danilodum/dark_souls_hkx/releases)
## Post #35
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-16T10:38:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I think it will be easier for me to make my own script then xD I though, it might work just from the start
## Post #36
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-16T10:56:51+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> I think it will be easier for me to make my own script then xD I though, it might work just from the start

but then it begins again or fix your old script?
## Post #37
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-16T11:39:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Fix old + add new one for bones:)
## Post #38
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2016-05-16T14:37:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from HunterAP
>
> Hey Zaramot, my friend has gone through all the character files and has this list of issues to share with you:
c1090 - broken UVs for black mass.
c2170 - missing entire meshes.
c2200 - mangled mesh.
c3040 - broken UVs for arms and possibly face.
c3140 - skeleton is completely misaligned; master at X: 9652.342, Y: 25911.4, Z: 8532.084. may be other problems.
c5030 - skeleton for nameless king off, probably not a huge problem though since he's intact in c5010.
c5110 - broken UVs for black mass.
c5140 - missing entire meshes.
c5160 - mangled torso mesh.
c5210 - skeleton might be incorrect.

The "black mass" is referring to the monster that comes out of Iudex Gundyr and some lesser hollows.
Good luck with these, and thanks again for all the work you put in to this.

friend here - and cripes, i forgot to mention something: c2170 isn't missing any meshes. rather, it's an issue with how it's actually missing any sort of skin weights for a couple of meshes on it - particularly the cloth if you haven't checked it out yet. apologies for mixing that up.
## Post #39
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-16T17:12:21+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Fix old + add new one for bones:)

sorry if I'm pushy, but do you think you put so much time?
## Post #40
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-16T19:50:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Well, I guess I don't have a choice xD If someone would like to play with Havok tools and convert .hkx skeletons, it's possible to use animations too. I would make script just to pick existing skeleton, so basically you convert .hkx into any format for 3ds max, and then import model over it with my script
## Post #41
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-16T21:08:53+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I was wondering but it would be possible to get the NPC? for I have looked in the character there. I would love to be able to take a npc the demon's souls or dark souls and be able toglere or put the helmet.
## Post #42
- Username: Sundownsyndrome
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Jun 12, 2015 11:15 am
- Post datetime: 2016-05-17T15:05:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

you're asking for something that he can't really do. NPCs all have generated faces that come from the same base as the player face, meaning if you're going to recreate an NPC, you're going to have to either rip it or manually adjust every vert til you get the look of the NPC. of course, the NPC faces aren't generated randomly, they're consistent throughout. there's probably some data somewhere in the files detailing that sort of thing - where, i have no clue. best to just leave it be for now.
## Post #43
- Username: andrewcrinxi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 18, 2016 6:25 pm
- Post datetime: 2016-05-18T14:13:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi guys i have a question, it's possible open FLV file with Noesis? (dark souls III) or i need 3dsmax 2012 for open flv? thanks in advance
## Post #44
- Username: KingFisher
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 13, 2016 1:02 pm
- Post datetime: 2016-05-19T03:57:14+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Anyone know if this is compatible with 3ds Max 2014? When I run it, it just freezes up the entire program, but I could be using it wrong. If not, any word on a Noesis script?
## Post #45
- Username: andrewcrinxi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 18, 2016 6:25 pm
- Post datetime: 2016-05-19T09:34:38+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from KingFisher
>
> Anyone know if this is compatible with 3ds Max 2014? When I run it, it just freezes up the entire program, but I could be using it wrong. If not, any word on a Noesis script?
need 3dsmax 2012, launch script, select Skeleton.hkx, select c***.flever, done...but all bone are trash for now..but this script is cool because only this can open flever (and you can't import animation) and if you want open TPF, you need Noesis plugin! i hope a plugin for Flever! this guy's are awesome!
## Post #46
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2016-05-19T13:15:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

hey zaramot can you update your script to the newest versions(2014-2017)?
## Post #47
- Username: KingFisher
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 13, 2016 1:02 pm
- Post datetime: 2016-05-19T14:23:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Alright, turns out I was totally mistaken, and the script does indeed seem to work with Max 2014. I had been attempting to open cXXXX.hkx in the cXXXX folder with the .flver, whereas the script actually requires you to use skeleton.hkx, which is stored in either cXXXX.anibnd, cXXXX,behbnd, or cXXXX.chrbnd, I'm not sure which. Upon testing, it seems to work fine.
## Post #48
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-29T06:24:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

zaramot there are for the script of demon's souls?
## Post #49
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-29T08:54:41+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I will release it a bit later. I'm playing one MMO game a lot, recently. So, there's not much time for scripts ATM
## Post #50
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-05-29T11:29:38+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I just wanted to know if we're still working, that's all
## Post #51
- Username: nuke974
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 05, 2016 11:43 pm
- Post datetime: 2016-06-05T23:50:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi, I have a problem with the import of .flver.
I want to import the prop of the game, like the boreal valley buildings, and they don't have a skeleton, so I don't know how to transfer them in 3ds max.
I tried using noesis but the mesh appears corrupt.
I read that it's fault of the old plugins for noesis, but I can't find any recent plugins.
some help?
## Post #52
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-06-06T12:10:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You will have to share some samples of static models. I can remove bone-import part and edit some lines in the script to import them. Though, if it will require a lot of changes, I don't know how long it will take to fix them, I don't have time for scripting ATM, unfortunately
## Post #53
- Username: nuke974
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 05, 2016 11:43 pm
- Post datetime: 2016-06-06T15:02:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Sure, this is a jar of carthus catacombs.
[s09200.zip](https://xentaxbackup.github.io/file/11025_s09200.zip)
## Post #54
- Username: 42tenthlick
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 28, 2016 10:46 am
- Post datetime: 2016-06-09T03:21:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Big thanks Zaramot for making these scripts!  Whenever you get around to it and if you want to, I've got some static DS3 props for ya.

[Heres a collection of meshes](https://dl.dropboxusercontent.com/u/76961924/DS3-StaticProps_noTextures.zip) and [heres the same collection with textures.](https://dl.dropboxusercontent.com/u/76961924/DS3-StaticProps.zip)

Some of them have skeletons, but I think those are only for destructible objects (Barrels, Vases, Wagons, etc.) and it probably won't be necessary for those to have a rig.  Any model that had a skeleton has a "_1" in the name.

Edit: well disregard what I've said, I can import any .flver if I select any skeleton.  Instead, there are some problems with the UVs.
## Post #55
- Username: kheylnuel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 11, 2016 11:03 am
- Post datetime: 2016-06-11T11:58:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I cant see link for maxscript in this topic. Why ?
## Post #56
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-06-16T08:55:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have a question about Demon's Souls. I know very well that this is not the place here but only found that the positive answer so I try! I would be interested as well as models also have maps and I wonder if it was possible to import them on 3d studio max.
## Post #57
- Username: ForthwithUK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 25, 2016 8:17 pm
- Post datetime: 2016-06-25T12:20:13+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

How would I go about unpacking the Dks3 archives prior to importing them?  I have already tried Noesis but the .bdt archives are not being recognized.

I'm also not seeing any download links in the posts, am I doing something wrong?
## Post #58
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-07-11T17:05:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have questions about unpack DS3 files..   
How I can use Binder tool? I can't understant..what where must be placed for working?   
Also, binder will work on Windows XP 32? Or I no have chance for unpacking? 
Microsoft Visual СС I have.
Hope will have normal reply...
## Post #59
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2016-07-13T01:12:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

does anyone know what file holds the Wyvern boss? I cant seem to find it for some reason
## Post #60
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-07-21T13:33:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hmm.. strange - when I use this DS3 script I see only error with that [http://sta.sh/02f99hawz0w9](http://sta.sh/02f99hawz0w9) 
But if I use script for DarkSouls1 I see skeleton..  [http://sta.sh/0x59jgnws6q](http://sta.sh/0x59jgnws6q) 
What's wrong?
## Post #61
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2016-07-23T10:42:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

evidence of my cursed persistence, not a bad thing but I was surprised were the textures were found in, Data4 o330040.objbnd
## Post #62
- Username: nocalora29
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 27, 2016 5:02 am
- Post datetime: 2016-07-27T13:59:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Isn't it possible to also make a Importer for Dark Souls 2 model files?, I have several PC version models laying around here.

I can send them if needed.
## Post #63
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-27T16:04:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Absolutely possible, though I don't have free time to make this happen   Same with Demon's Souls, have no idea when but this is in my wip list at top.
## Post #64
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-07-27T16:44:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Absolutely possible, though I don't have free time to make this happen   Same with Demon's Souls, have no idea when but this is in my wip list at top.

If I can only know, if you can finish that business for darksiders 2 I leave you in peace!
## Post #65
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-27T17:32:51+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> zaramot wrote:Absolutely possible, though I don't have free time to make this happen   Same with Demon's Souls, have no idea when but this is in my wip list at top.

If I can only know, if you can finish that business for darksiders 2 I leave you in peace!

Well, to say truth I think I can, .o3d files looks like normal skeleton files to me, maybe something with transform matrices there, like inverted. Though, I think there's possibility to get skeleton and then to get those models (only in this order), because it's such type of meshes in darksiders, which require skeleton at first place. But it's all just a guessing, because I didn't look detailed and in near future wouldn't, I hope you will find solution!
## Post #66
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-07-27T17:47:22+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

thank you. It was what I wanted to know.
## Post #67
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-07-28T15:20:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from nocalora29
>
> Isn't it possible to also make a Importer for Dark Souls 2 model files?, I have several PC version models laying around here.

I can send them if needed.

I have old maxscrypt, can try to export
## Post #68
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-08-03T17:07:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Models extract by MorgothZeONE (big thanks!)
Convert to Xnalara and MMD by me


Downloadable  
[http://fav.me/daby07h](http://fav.me/daby07h)
[http://fav.me/dackmbd](http://fav.me/dackmbd)
## Post #69
- Username: longnguchicken
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 14, 2016 7:44 pm
- Post datetime: 2016-08-09T13:48:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Can someone give me the models(obj would be great) and textures of farron greatsword, onikiri and ubadachi, black knight greatsword and gotthard twinswords? I spent my whole day messing with Dark souls 3 data file but dont know how to find them
## Post #70
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2016-08-09T16:12:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

which max version is the .ms file?

And zaramot can you update the script for max 2014?
## Post #71
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2016-08-19T13:28:21+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

This is great work, thanks zaramot. Has anyone been able to extract the map models (for example, the Anor Londo castle)?
## Post #72
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2016-08-24T22:02:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from nocalora29
>
> Isn't it possible to also make a Importer for Dark Souls 2 model files?, I have several PC version models laying around here.

I can send them if needed. do you have Sinh, the Guardian dragon, and ancient dragon? if so i'd can you P.M. me the files i'd like to be able to use them when a Dark Souls 2 maxscript is available, if so then thanks
## Post #73
- Username: Alex2228
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 26, 2016 8:28 pm
- Post datetime: 2016-08-26T12:55:33+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Fantastic work !
But I have a big problem, when importing any models...
I can import the .hkx, then the .flver but the script return me an error :
--Runtime error: array index must be positive number, got: 0
I don't know what to do now since others have succeed... Am I doing Something wrong ?
## Post #74
- Username: nyxo
- Rank: advanced
- Number of posts: 68
- Joined date: Sun Jan 06, 2013 10:54 am
- Post datetime: 2016-09-08T23:30:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from MorgothZeONE
>
> 
evidence of my cursed persistence, not a bad thing but I was surprised were the textures were found in, Data4 o330040.objbnd

That's where I first thought I found the textures as well, but you'll notice the filenames don't match what the mesh is requesting -- the actual textures the mesh references are found in Data4: o009990.objbnd, except for c3140_jarei_body_01_a, which I have yet to locate _anywhere_ >_>;;;  (That's the texture used for the black mass around the dragon's foot, which you removed from your screenshot)
## Post #75
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-09-27T06:41:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have a problem with the script of Dark Souls III. He tells me that I have to import the files of the skeleton, but is off when I try the model. tells me to just open a file called: Skeleton.hkx 

I accidentally missed something?
## Post #76
- Username: UncleBorubon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 07, 2016 7:47 am
- Post datetime: 2016-10-06T23:56:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hopefully this thread is still up and about.

 So I really enjoy 3d printing, and am working on an Abyss Watcher costume, could anyone help me with obtaining models from the abyss watchers? the file type that my 3d printer uses is .stl, but I could convert from .3ds. 

I would very much appreciate the help!
## Post #77
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2016-10-13T13:43:16+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Have anyone a Model files list?

example:
c1000 - ...
c1070 - ...
## Post #78
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-16T22:08:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> I downloaded the appropriate files. I hope you can solve any soon. http://www.mediafire.com/download/88h32 ... 5w/chr.rar

made a Noesis python script to open your Demon's Souls tpf texture file samples  


 tex_DemonsSouls_PS3_tpf.zip
(766 Bytes) Downloaded 112 times


supports dxt1 and dxt5
## Post #79
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-10-21T13:41:07+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from UncleBorubon
>
> Hopefully this thread is still up and about.

 So I really enjoy 3d printing, and am working on an Abyss Watcher costume, could anyone help me with obtaining models from the abyss watchers? the file type that my 3d printer uses is .stl, but I could convert from .3ds. 

I would very much appreciate the help!

Here are downloadable final Abyss Watchers
[http://fav.me/dackmbd](http://fav.me/dackmbd)
Include FBX format, but I can make 3ds or obj for you
With full clothes and all weapons
## Post #80
- Username: chrisater245
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 23, 2016 7:30 pm
- Post datetime: 2016-10-23T11:46:42+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

hello 
I'm new in the forum and I opened only for this topic. I love this game but idk how to extract models.  can someone help to learn?¿or explain me how ¿? 
i would like to print some model
## Post #81
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-10-26T13:49:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AceWell
>
> dibe91 wrote:I downloaded the appropriate files. I hope you can solve any soon. http://www.mediafire.com/download/88h32 ... 5w/chr.rar

made a Noesis python script to open your Demon's Souls tpf texture file samples  
tex_DemonsSouls_PS3_tpf.zip
supports dxt1 and dxt5
Any chance for Dempn's Souls models script? Idk where found - old links not work (file deleted, 404)
## Post #82
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-26T17:17:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> Any chance for Dempn's Souls models script? Idk where found - old links not work (file deleted, 404)
there is attachment for maxscript in this thread in case you missed
[viewtopic.php?p=97614#p97614](http://forum.xentax.com/viewtopic.php?p=97614#p97614)
[viewtopic.php?p=99901#p99901](http://forum.xentax.com/viewtopic.php?p=99901#p99901)

and i just saw where Gh0stBlade already made a tpf script for Demon's Souls years ago   
it says for X360 but it looks like it will work with the PS3 tpf files too
[viewtopic.php?p=98043#p98043](http://forum.xentax.com/viewtopic.php?p=98043#p98043)
## Post #83
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-10-27T16:20:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AceWell
>
> TokiChan wrote:Any chance for Dempn's Souls models script? Idk where found - old links not work (file deleted, 404)
there is attachment for maxscript in this thread in case you missed
viewtopic.php?p=97614#p97614
viewtopic.php?p=99901#p99901

and i just saw where Gh0stBlade already made a tpf script for Demon's Souls years ago   
it says for X360 but it looks like it will work with the PS3 tpf files too
viewtopic.php?p=98043#p98043
Cool, thank you! 
Now I can start work with them! [http://sta.sh/010end2xiczo](http://sta.sh/010end2xiczo)
## Post #84
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2016-11-04T13:03:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi everyone!

I was wondering if there is a max script to import the Dark Souls 2 characters inside max? I was able to get to the c6191.bnd and c6191.texbnd files I was looking for and then further unpacked them (see image bellow) by using the Bindertools 0.3 on the original Dark Souls II (GameDataEbl.bdt).

However, when I run zaramot's Dark Souls III ms nothing shows up, although there are files inside that folder that match the extension you have there:



Am I doing something wrong?
## Post #85
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T15:51:07+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You need maxscript for Dark Souls 2 not 3, though I didn't post update for Dark Souls 2 with correct bones. So, if you want some model to be converted, you could upload it here, I will convert it with correct bones (need all. hkx files which comes with this model, inside one of them there are bones) or you could use maxscript for Dark Souls 2 (not 3) and get models, but without correct bones
## Post #86
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2016-11-04T16:25:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Thank you so much for your help!

Truth be told I don't need bones or rig. All I need is an obj (or .max or .maya) file and possibly the textures as well.

This is what I got thus far:

the original c6191.bnd and c6191.texbnd extracted from the GameDataEbl.bdt of Dark Souls 2 (original release)

As well as all the files further unpacked with BinderTools as shown in the image above.

[https://www.dropbox.com/s/tgit2ziphqecn ... 1.rar?dl=0](https://www.dropbox.com/s/tgit2ziphqecnar/c6191.rar?dl=0)

I really appreciate your help mate! Thank you so much! This willl probably take you 10m while I've been at it for 2 days already
## Post #87
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-04T17:47:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> You need maxscript for Dark Souls 2 not 3, though I didn't post update for Dark Souls 2 with correct bones. So, if you want some model to be converted, you could upload it here, I will convert it with correct bones (need all. hkx files which comes with this model, inside one of them there are bones) or you could use maxscript for Dark Souls 2 (not 3) and get models, but without correct bones

sorry I should do all the dark souls 2 models there is not a better solution?
## Post #88
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T18:45:05+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You need all models from DS2?! Sure, there's an other solution, for this I need to edit my sript for DS2 PC version a bit

c6191 in .obj + textures in .dds

[https://www.sendspace.com/file/m6qjxy](https://www.sendspace.com/file/m6qjxy)
## Post #89
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2016-11-04T19:54:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I cannot thank you enough man! I actually able to import through your old ms ds2 script but I was missing a lot of stuff plus none of the textures worked nor were they in sync with the uvs. You probably edited your script no? How did you do this so fast  

I can provide the contents of the entire folder if you want to pursue this quest of having all the models from the game. Either that or, if you wish to tweak your script in order to wide the compatibility or so I can keep testing it as I am going to need more characters in the future so I'd be glad to test it as much as you want.
## Post #90
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T22:18:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Yeah, I have modified script I posted earlier, not finished though, models in Dark Sould, unfortunatelly disapointed me. Don't like the design and proportions, not for my taste, so I lost interest. Though, if you people need models from DS2 PC much I could finish it, not too long and not to hard. Just post some characters extracted, with theit .hkx files too.
## Post #91
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2016-11-04T22:44:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Thank you kindly sir! It would be much appreciated if you were to finish the script! In the meanwhile (probably during the weekend/next week) I'll post some other models to take you up on that offer  Have a great weekend mate and thank you once again!
## Post #92
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-05T06:22:18+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Yeah, I have modified script I posted earlier, not finished though, models in Dark Sould, unfortunatelly disapointed me. Don't like the design and proportions, not for my taste, so I lost interest. Though, if you people need models from DS2 PC much I could finish it, not too long and not to hard. Just post some characters extracted, with theit .hkx files too.

thanks for your time! I hope it will end as soon as possible! moreover, there are also problems with the ds script 3. I tried it with nameless king but I always find the bones in the feet detached from the rest!
## Post #93
- Username: TehDave
- Rank: advanced
- Number of posts: 74
- Joined date: Tue Apr 21, 2009 12:24 pm
- Post datetime: 2016-11-05T06:26:42+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Would definitely be interested in seeing an updated script for 2. I want to export out the maps and get cleaner versions of the unused geometry with all the parts in the proper place. Someone ripped the unused geometry previously but half the stuff is out of place because it didn't rip the bones or weights, which is, I'm assuming, why there's a lot of stuff stuck in the origin of the mesh.
## Post #94
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-05T11:59:23+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Guys, please don't use names like - nameless king, soul of cinder, abyss watcher etc. When talking about models from Dark Souls games. I never played any of it lol I have no idea which model it is. Please use names like c6191 and so on, like they are in game files. Thanks

P.S. You can upload "nameless king" model, I'll take a look what's wrong with this one
## Post #95
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-05T14:09:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Guys, please don't use names like - nameless king, soul of cinder, abyss watcher etc. When talking about models from Dark Souls games. I never played any of it lol I have no idea which model it is. Please use names like c6191 and so on, like they are in game files. Thanks

P.S. You can upload "nameless king" model, I'll take a look what's wrong with this one

sorry, it's just that it seemed easier than trying the code name also because it takes more time to search for it.
## Post #96
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-05T14:19:06+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I understand, so I guess it could be a solution for anyone who's interested in DS models. Just when importing any model and having errors with it, note it's file name in notepad for example (their names like they appears after extraction)   Then, you can just post names here and I will check their errors (and if I don't have some of models, I can ask you about them) I don't have DS games (lol many games I made scripts for aha ha), so I can't extract all content and try them all with a script, so basically all files I have - kindly provided by all of you, xentax users!
## Post #97
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2016-11-05T16:28:51+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I will try to research a bit because I can't seem to find it right now but I know there was a list somewhere that had the file names of all the characters, weapons and armor from DS1 and DS2. I'll keep unloading characters for DS2 for you to keep improving on that script  regardless, ypi have to tell me how you did that so well and so fast. When I used your script on c6191 I had to cheat the script by changing the file extension from flv to flver and there was geometry missing and completely messes up uvs. Plus that convertion of textures from the native DS extension to dds was incredibly fast. You couldn't have done that alignement of uvs plus convertion etc so fast without scripting I assume? Anyway I'll keep uploading models for DS2. My hats off to you sir!
## Post #98
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-07T09:56:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Guys, please don't use names like - nameless king, soul of cinder, abyss watcher etc. When talking about models from Dark Souls games. I never played any of it lol I have no idea which model it is. Please use names like c6191 and so on, like they are in game files. Thanks

P.S. You can upload "nameless king" model, I'll take a look what's wrong with this one

Here are finally fixed/converted Nameless King with him's dragon   
[http://fav.me/daby07h](http://fav.me/daby07h)
If need, I can port him into .obj
## Post #99
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-07T09:57:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> zaramot wrote:Guys, please don't use names like - nameless king, soul of cinder, abyss watcher etc. When talking about models from Dark Souls games. I never played any of it lol I have no idea which model it is. Please use names like c6191 and so on, like they are in game files. Thanks

P.S. You can upload "nameless king" model, I'll take a look what's wrong with this one

sorry, it's just that it seemed easier than trying the code name also because it takes more time to search for it.

Was converted Nameless King with Stormlord [http://fav.me/daby07h](http://fav.me/daby07h)
If need, I can port him into .obj
## Post #100
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-07T10:52:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> dibe91 wrote:zaramot wrote:Guys, please don't use names like - nameless king, soul of cinder, abyss watcher etc. When talking about models from Dark Souls games. I never played any of it lol I have no idea which model it is. Please use names like c6191 and so on, like they are in game files. Thanks

P.S. You can upload "nameless king" model, I'll take a look what's wrong with this one

sorry, it's just that it seemed easier than trying the code name also because it takes more time to search for it.

Was converted Nameless King with Stormlord http://fav.me/daby07h
If need, I can port him into .obj

I do not want that model. I want to import it directly on 3d studio max so it's easier for me to do what I need.
## Post #101
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-08T08:11:42+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> 
I do not want that model. I want to import it directly on 3d studio max so it's easier for me to do what I need.

It's simply importing with XNALARA-Converter script 
Imported [https://mega.nz/#!HxB0VRCA!UjpUUUnpO5sI ... tATBkSHsCc](https://mega.nz/#!HxB0VRCA!UjpUUUnpO5sIotB3Llwhl6PuSRAD7HpU4tATBkSHsCc)
## Post #102
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-08T15:27:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Any chance for script for importing static objects (statues, items, misc)?
Or may be map/stages/locations import?
## Post #103
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-13T16:04:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Fire, Ice and crow's feathers   
So epic boss from DLC
And how about importing static script - weapons, statues, misc?
[Ariandel 1.png](https://xentaxbackup.github.io/file/11912_Ariandel 1.png)
## Post #104
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-13T16:34:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hmm, I think I did something for static/props meshes. Not ssure if I uploaded this though, if not, than you could comment or delete bone import part in my script and it should work for static meshes.
## Post #105
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-13T16:40:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Hmm, I think I did something for static/props meshes. Not ssure if I uploaded this though, if not, than you could comment or delete bone import part in my script and it should work for static meshes.
I'm not sure about correcting of you tools - plugins editing is not for me
## Post #106
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-17T06:50:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Hmm, I think I did something for static/props meshes. Not ssure if I uploaded this though, if not, than you could comment or delete bone import part in my script and it should work for static meshes.
I'm so sorry about spamming against, but when i try delete bone import section, max give me undefinied float error   
I no have ideas... I'm no have skills in scripting...
I need some statics. Can you make script?
## Post #107
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-22T12:12:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Dragonoids (parts archive, BD_0100 and HD_0100, head have skeleton additing, but it no work)
Different formats, include FBX with SFM-like bones (head and tail is edit weight)
Final link [http://fav.me/dapbw8v](http://fav.me/dapbw8v)



And I still need script for static... I'm noob in this
## Post #108
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-24T18:16:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Wolves and Greatwolf from dlc have broken Uvmap
(с6030, c6040, c6050)
How it must looks 

And how it looks for me
Any chance or I must fix UVmap in max?
[wolve.jpg](https://xentaxbackup.github.io/file/11952_wolve.jpg)
## Post #109
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-24T18:33:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Lol, what a strange looking dog xD Sure, I guess it could be fixed, but I don't have the game
## Post #110
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-24T19:57:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I can spend all models of Souls series. but I have to know what exactly
## Post #111
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-24T20:23:41+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Lol, what a strange looking dog xD Sure, I guess it could be fixed, but I don't have the game
Here are wolves  
[https://mega.nz/#!L4pVzLza!pZT_FKSbfWJI ... rXq9aIQ0kw](https://mega.nz/#!L4pVzLza!pZT_FKSbfWJIJG6qUbv6wg57BP27raywtrXq9aIQ0kw)
Idk about other ememies from DLC.. Corvians from that is correct and good   
I can send DLC files, if it be help

And I have similar problem with mail of hollow soldiers from original (c1101) 
fbx [https://mega.nz/#!voRngQZY!5daDmdlGM3bo ... L9-1-1TXYg](https://mega.nz/#!voRngQZY!5daDmdlGM3boi81V4gHlSGw1iNYIT66UoL9-1-1TXYg)
Originals files [https://mega.nz/#!Hwp1QJoS!Atzs0TEug-Rq ... 8DFo7Ckn0g](https://mega.nz/#!Hwp1QJoS!Atzs0TEug-RqDZV_sio8UmCljks1NiNiJ8DFo7Ckn0g)
## Post #112
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-24T20:31:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> I can spend all models of Souls series. but I have to know what exactly
Dom you have any DS2?
## Post #113
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-24T23:20:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> dibe91 wrote:I can spend all models of Souls series. but I have to know what exactly
Dom you have any DS2?

of course. but the question is which version? the base or the scholar?
## Post #114
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-25T15:42:36+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> 
of course. but the question is which version? the base or the scholar?
Scholar...
I have files, but can't unpack it (i try binder 3)
## Post #115
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-25T16:22:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> dibe91 wrote:
of course. but the question is which version? the base or the scholar?
Scholar...
I have files, but can't unpack it (i try binder 3)

noooooooooo There is a special version that opens only from the dark souls II files!
## Post #116
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-25T16:38:16+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> TokiChan wrote:dibe91 wrote:
of course. but the question is which version? the base or the scholar?
Scholar...
I have files, but can't unpack it (i try binder 3)

noooooooooo There is a special version that opens only from the dark souls II files!
Ohh... And what binder is current for scholar?  
Or may be just you have Sinh the dragon, Manus daughers and Prowling Magus?
## Post #117
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-25T19:07:59+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

if you go on the site, it explains everything. we can have all models

[https://github.com/Atvaark/BinderTool/releases](https://github.com/Atvaark/BinderTool/releases)
## Post #118
- Username: Rhoenicx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 25, 2016 9:19 pm
- Post datetime: 2016-11-27T01:11:55+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello everyone,

I am new to autodesk 3ds max, i managed to import a model (i took the soul of cinder) into autodesk but how do i put the uv map on the model?
Besides my question, is it possible to import items (swords, bows etc) into autdesk with the model import maxscript? because items do not have a skeleton.hkx file...

Thanks!
## Post #119
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-11-29T08:58:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Rhoenicx
>
> Hello everyone,

I am new to autodesk 3ds max, i managed to import a model (i took the soul of cinder) into autodesk but how do i put the uv map on the model?
Besides my question, is it possible to import items (swords, bows etc) into autdesk with the model import maxscript? because items do not have a skeleton.hkx file...

Thanks!
You mean add textures?
It's simple - see texture additing/put on youtube
Example (from 0:40) [https://www.youtube.com/watch?v=4Zt4yH_9LBs](https://www.youtube.com/watch?v=4Zt4yH_9LBs)
## Post #120
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2016-12-17T03:36:54+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

How are you guys extracting the flver´s?
Been reading thru a gazillion posts
## Post #121
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2016-12-30T14:01:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Anyone still work with file navigator?
(I mean - enemy and armor list like DS1)
I found one, but this is unfinal..
## Post #122
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2016-12-31T06:47:23+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi Zaramot, thanks for the amazing script.

I am working with the Static map meshes in an attempt to rebuild the castles from the game. The script works well with static meshes when I select a random skeleton.hkx, except I notice that the UV's that are loaded seem to belong to the lightmap textures or something. 

As an example, I picked m31_00_00_00_000100.flver which is the details of a primitive stone house.

I looked through the flver file and see the following textures referenced:

m31_00_woodenhouse_00
m31_00_woodenhouse_01
m31_00_woodenhouse_02
m31_00_woodplank_04
m31_00_brickwall_06_block
m31_00_base

and also the following 2 small lightmap images, which correspond to the UVs as you can see in the screenshot:

g_DisplacementTexture 31000000_m000100_gi_0000_00_dol_00
g_DOLTexture1 31000000_m000100_gi_0000_00_dol_01

When I load the flver in Max via the script, I see the UVs correspond to the last 2 lightmap textures instead of the previous 7 correct textures.

Example with diffuse textures is here:
- PM per forum rules -

Is it possible to alter the existing script to remove the bone reference and pick the right UVs for the map meshes?
[LightmapExample.jpg](https://xentaxbackup.github.io/file/12142_LightmapExample.jpg)
## Post #123
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-01-03T13:44:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zardalu
>
> Hi Zaramot, thanks for the amazing script.

I am working with the Static map meshes in an attempt to rebuild the castles from the game. The script works well with static meshes when I select a random skeleton.hkx, except I notice that the UV's that are loaded seem to belong to the lightmap textures or something. 

As an example, I picked m31_00_00_00_000100.flver which is the details of a primitive stone house.

I looked through the flver file and see the following textures referenced:

m31_00_woodenhouse_00
m31_00_woodenhouse_01
m31_00_woodenhouse_02
m31_00_woodplank_04
m31_00_brickwall_06_block
m31_00_base

and also the following 2 small lightmap images, which correspond to the UVs as you can see in the screenshot:

g_DisplacementTexture 31000000_m000100_gi_0000_00_dol_00
g_DOLTexture1 31000000_m000100_gi_0000_00_dol_01

When I load the flver in Max via the script, I see the UVs correspond to the last 2 lightmap textures instead of the previous 7 correct textures.

Example with diffuse textures is here:
- PM per forum rules -

Is it possible to alter the existing script to remove the bone reference and pick the right UVs for the map meshes?
How do you import static?   
I try import some static objects with random skeletons, but it give me errors without model
## Post #124
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2017-01-04T19:34:22+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> 
How do you import static?   
I try import some static objects with random skeletons, but it give me errors without model

I extracted all of the files from the game using BinderTool v 0421. I searched for skeleton.hkx and picked the smallest one (2k). I copied it to a working directory that I created.

I run the script in max (2013 64 bit), which automatically prompts me for a skeleton. I selected my skeleton.hkx from above.

The script then prompts for a flver file. I have tested many static flver files from the 'maps' and 'obj' directories. 

Many of the 'obj' files work with correct UV's. I suspect it is those that have skeletons. Some do not load at all.

Most of the 'map' files work, and are static meshes from the maps.  The UV's are not working, however, because they are using a channel devoted to lightmaps.  There are no other channels loaded, so far as I can tell.

Hope that makes sense. Cheers, z
## Post #125
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-01-07T20:27:33+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zardalu
>
> TokiChan wrote:
How do you import static?   
I try import some static objects with random skeletons, but it give me errors without model

I extracted all of the files from the game using BinderTool v 0421. I searched for skeleton.hkx and picked the smallest one (2k). I copied it to a working directory that I created.

I run the script in max (2013 64 bit), which automatically prompts me for a skeleton. I selected my skeleton.hkx from above.

The script then prompts for a flver file. I have tested many static flver files from the 'maps' and 'obj' directories. 

Many of the 'obj' files work with correct UV's. I suspect it is those that have skeletons. Some do not load at all.

Most of the 'map' files work, and are static meshes from the maps.  The UV's are not working, however, because they are using a channel devoted to lightmaps.  There are no other channels loaded, so far as I can tell.

Hope that makes sense. Cheers, z

I mean, what (which one) skeleton.hkx you use for static meshes?
I use max 2010, but he doesn't convert all static, with any skeletons from chr archive
## Post #126
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-01-23T20:35:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I again have problem with importing...
When I try get Pontiff Sullivanh (c5140) he no have hands-wrist meshes, legs meshes and head mesh.
I try re-extract and re-import, but it still no give me that meshes.
Any idea?


This how he must lookslike

[Ashampoo_Snap_2017.01.23_23h27m52s_001_.png](https://xentaxbackup.github.io/file/12272_Ashampoo_Snap_2017.01.23_23h27m52s_001_.png)
## Post #127
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-24T12:12:44+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I'm sure this model have some unknown "vertex type", need to look at this one more closely.
## Post #128
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-01-28T19:14:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I checked my DS3 files, and didn't find c1540. Can you send me him?
## Post #129
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-01-28T19:48:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> I checked my DS3 files, and didn't find c1540. Can you send me him?
Sure! I am despaired
(I am wrong write - need c5140)
[https://drive.google.com/open?id=0B25vR ... TJkRzFYaWM](https://drive.google.com/open?id=0B25vRFsoP3MqLUNpcTJkRzFYaWM)
## Post #130
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2017-02-04T19:04:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> A bit fixed version of Noesis plugin from DS3 .tpf files, fixed error with c5210, c1400 and c2170 .tpf
Thanks you for this plugin.

Did someone ever tried to extract Lothric Castle's / Kiln of the First Flame's eclipsed black sun textures?
I'm trying to do it right now, but it seems to be not an easy job. There are seems around 400000 textures to parse, but maybe somehow managed to get it already?

P.S. Actually, i found that file o008966.tpf crash Noesis when opening or exporting. Here is that file - [https://cloud.mail.ru/public/CuVv/UC5iXEacG](https://cloud.mail.ru/public/CuVv/UC5iXEacG)
Also several (many) files cannot be opened or exported too with the error. I can send their samples too.

[https://cloud.mail.ru/public/7T1J/2kG6GWQ78](https://cloud.mail.ru/public/7T1J/2kG6GWQ78) - here is that error:
## Post #131
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-02-16T21:31:39+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> I checked my DS3 files, and didn't find c1540. Can you send me him?
Sorry for bother you, but any prigress with Pontiff what I send?   
(i just promise convert him for my friend)
## Post #132
- Username: eycaramba
- Rank: veteran
- Number of posts: 86
- Joined date: Wed Sep 02, 2009 8:52 pm
- Post datetime: 2017-02-19T15:57:51+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Amazing work as always, zaramot! Thanks a lot.
## Post #133
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-03-03T18:55:59+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have a question for Zaramoth but the script for demon's souls?
## Post #134
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-06T13:03:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Skeletons from  c5210 (Rosaria) and c6020 (Sister Friede, DLC) are twisted
[Ashampoo_Snap_2017.03.06_16h02m48s_001_.png](https://xentaxbackup.github.io/file/12558_Ashampoo_Snap_2017.03.06_16h02m48s_001_.png)
## Post #135
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2017-03-16T12:02:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi Zaramot,

Could I ask you to do your magic once again and convert me 2 models? The script does import them but, again, with errors on the uvs and some missing parts, as before, with the chariot!

[https://www.dropbox.com/s/tua0zisldxme3 ... e.rar?dl=0](https://www.dropbox.com/s/tua0zisldxme3a3/c1180-hollowmage.rar?dl=0)

[https://www.dropbox.com/s/mtvkunpdgjj8y ... s.rar?dl=0](https://www.dropbox.com/s/mtvkunpdgjj8ycx/c1570-skeletons.rar?dl=0)

Thank you kindly sir!
## Post #136
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-16T16:57:33+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Not sure if I can help you. I can get you the geometry and uv's, but not rigged models. In order to import them with bones and weights I need skeleton.hkx for those models, not their ragdoll or cloth .hkx
## Post #137
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2017-03-16T17:10:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Not sure if I can help you. I can get you the geometry and uv's, but not rigged models. In order to import them with bones and weights I need skeleton.hkx for those models, not their ragdoll or cloth .hkx

Hi Zaramot,

Thank you kindly mate, that's really all I need. Just like with the Chariot (previous model), all I really need is the geometry (with proper uvs) and the textures!
## Post #138
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-16T18:00:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Here's the script, should import models you want and other you may want xD I disabled bone-import part, so it will be faster and easier for you.


[Dark_Souls_2_3_PC_UPD.7z](https://xentaxbackup.github.io/file/12635_Dark_Souls_2_3_PC_UPD.7z)
## Post #139
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2017-03-16T18:11:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You good sir are a star! Thank you kindly. Will test asap and get back to you . For some reason the previous script would not import some parts of the model, uvs would be wrong and not a match. As far as textures goes how do you converter them and so fast?
## Post #140
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-16T18:26:39+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I made Noesis plugin for the textures, it's on the first page, but I will attach it here too. Just download Noesis (awesome and epic tool), copy extracted file into plugins/python folder inside Noesis folder and you should be able to view and then export textures in various formats
[fmt_DarkSouls_III_TPF.7z](https://xentaxbackup.github.io/file/12636_fmt_DarkSouls_III_TPF.7z)
## Post #141
- Username: completenoob
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 04, 2016 12:48 am
- Post datetime: 2017-03-16T20:10:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Testing as I write this! Thank you again and again
## Post #142
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-03-17T17:45:33+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Here's the script, should import models you want and other you may want xD I disabled bone-import part, so it will be faster and easier for you.

but to the question of the skeletons and skins?
## Post #143
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-17T18:50:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You can enable bone import part in the script using 3ds max very easy, should work. It's not removed just disabled.
## Post #144
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-03-18T00:18:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I got it. how does it work? forgive me I know very little about coding, what should I change the script?

just a clarification: the script of Dark Souls 2 will only work with the basic version, with version "scholar of the first sin" no. if you have chance to fix it, it would be greatly appreciated!
## Post #145
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-18T22:40:01+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Here's the script, should import models you want and other you may want xD I disabled bone-import part, so it will be faster and easier for you.

So strange, but now all models (all - from chr, parts and obj) are invisible for import window
It's normal?
[trouble.png](https://xentaxbackup.github.io/file/12655_trouble.png)
## Post #146
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-03-18T22:59:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I think, samples were from DS2 not DS3 - so, as you can see it's asking you for .flv but you have .flver files. I'm almost certain xD Previous script for static models was made for completenoob, by his request, I will edit it later for most of users.
## Post #147
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-19T09:26:39+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> I think, samples were from DS2 not DS3 - so, as you can see it's asking you for .flv but you have .flver files. I'm almost certain xD Previous script for static models was made for completenoob, by his request, I will edit it later for most of users.
Ah, now understand 

With ds2 it work for get static, not for ds3

Any chance for analogy for ds3? And do you have progress with ds3 script? (I still wait c5140 mesh fix)
## Post #148
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-03-20T19:59:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

but sorry as I enable the script to import models with the skin and bones?
## Post #149
- Username: TwiChill
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 21, 2017 9:03 pm
- Post datetime: 2017-03-21T13:35:21+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

hello,i open the data3 ,but i can not see the C1400(someone said it is firekeeper...).i dont know why.
and could u tell the number of abyss watcher?
[[DK2)3NYYWJW0CMU245O8S3.png](https://xentaxbackup.github.io/file/12667_[DK2)3NYYWJW0CMU245O8S3.png)
## Post #150
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-21T19:13:19+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TwiChill
>
> hello,i open the data3 ,but i can not see the C1400(someone said it is firekeeper...).i dont know why.
and could u tell the number of abyss watcher?

Number of Abyss Watchers is c3040
Firekeeper is c1400 
(I get almost full lists of characters and armors)
And they ready in some formats (include FBX and OBJ)
[http://fav.me/dackmbd](http://fav.me/dackmbd)
[http://fav.me/dao6bj7](http://fav.me/dao6bj7)
## Post #151
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2017-03-26T20:16:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I'm so sorry to Necro this thread (at least I think it is necro) but I really need help here, I am trying to 3d print the Dancer of boreal valley's armor for myself as a cosplay costume, but no one anywhere has ripped her 3d model. I am so stuck, can anyone who already knows how to rip these models possible send me her model and textures? I don't own the game or I would seriously just do it myself. any help on this would be much appreciated.
## Post #152
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-27T18:17:54+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Xr79
>
> I'm so sorry to Necro this thread (at least I think it is necro) but I really need help here, I am trying to 3d print the Dancer of boreal valley's armor for myself as a cosplay costume, but no one anywhere has ripped her 3d model. I am so stuck, can anyone who already knows how to rip these models possible send me her model and textures? I don't own the game or I would seriously just do it myself. any help on this would be much appreciated.

This is no necro, just not at all time work 
Dancer of the Boreaql Valley (c5270, broken rigging) [https://drive.google.com/file/d/0B25vRF ... sp=sharing](https://drive.google.com/file/d/0B25vRFsoP3MqZDZDZ2J0cTFUTW8/view?usp=sharing)

Dancer armor for character [https://drive.google.com/file/d/0B25vRF ... sp=sharing](https://drive.google.com/file/d/0B25vRFsoP3MqR2FZVm9STVdwRzA/view?usp=sharing)
[Dancer armor.png](https://xentaxbackup.github.io/file/12702_Dancer armor.png)
## Post #153
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2017-03-28T03:53:47+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Wow thank you so so much, that was very kind of you to do! I absolutely love this boss (even though she kicked my ***) thank you again for getting back to me, I can't wait to work with her!

Okay wow (just opened her up), she is more than I could have asked for, her model is so perfect! thank you once again, this is amazing.
## Post #154
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2017-03-29T00:52:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

How do you enable bones and skinning?
## Post #155
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-29T07:48:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Rin
>
> How do you enable bones and skinning?
Use Skeleton.hkx and previous version of script - need load skeleton, then load model
But some models like Dancer, Friede and Rosaria have broken rig, some hollows and weapons - broken UV, Pontyff have disabled head and skin meshes, but armor almost always is good.

If need, I recognise all armors inlcude unused and almost all enemies as numbers in files
## Post #156
- Username: illincrux
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 16, 2010 11:46 pm
- Post datetime: 2017-03-29T22:12:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Any news on a Noesis plugin that can view and convert flver and tpf files?
## Post #157
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-03-30T13:57:01+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from illincrux
>
> Any news on a Noesis plugin that can view and convert flver and tpf files?
All TPF from chr and parts is good with present Noesis script, flver can be get only from character and parts still
## Post #158
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-04-01T22:36:19+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

When im trying to export textures from tpf im get this error message and only can export diffuse texture without normal or specular.
## Post #159
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-04-04T12:56:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff
>
> When im trying to export textures from tpf im get this error message and only can export diffuse texture without normal or specular.
May be you have alternative python using TPF in your python folder (example, DemS)?
Or your noesis is no latest - I use 425 [http://www.richwhitehouse.com/index.php ... project=91](http://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
## Post #160
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-04-10T20:54:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

sorry there's any news, for the script of dark souls 2 and 3?
## Post #161
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2017-04-14T19:18:36+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I didn't find any, so while I was checking some files, I created a spreadsheet for DS3 characters/folders.

[https://docs.google.com/spreadsheets/d/ ... D5m-RR-VE/](https://docs.google.com/spreadsheets/d/1Gi7vF5bnVxgQGSJrlWrpdtc-JlJ0XQMliaD5m-RR-VE/)

I still have to complete it.
It seems like a mess, but it's not that bad:
- Bosses are blue
- NPCs are purple
- Monsters I know (confirmed) are in green.
- My doubts are in red.
- Empty spots: I did not check yet.

As I keep working on this, it would be nice if anyone helped! Anyone can comment, really!
Or if there is a list created, I'd love to see it! 

Right now, it takes me a lifetime to find something I want - I'm searching for Havel, for example. No luck yet.
Hope it's helpful, somehow.
## Post #162
- Username: steB
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 18, 2017 4:27 am
- Post datetime: 2017-04-17T21:17:22+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi all, i'm new. Is there a program for Windows (.exe) for extract 3D models (.Obj) of dark souls III Data file?
## Post #163
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-04-19T11:30:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I discovered that the zaramot script also works with Dark Souls models 1. I hope the problem will be resolved soon skeleton. I have a request for zaramot. There are 3 models that I can not upload to 3d studio max. I want you to create a special script for one of these models. They are the same model in different sizes.

[http://www.mediafire.com/file/750582wqyt01bqp/chr1.rar](http://www.mediafire.com/file/750582wqyt01bqp/chr1.rar)
## Post #164
- Username: steB
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 18, 2017 4:27 am
- Post datetime: 2017-04-19T13:54:18+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Using BinderTool I can extract the file contain on Data0-5; in Data3 I have found a folder named "obj".. but contain HKX, HKT, TAE and OBJBND. How I can open this on Maya? Or convert in obj?
## Post #165
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-04-19T19:59:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from lolwatt
>
> I didn't find any, so while I was checking some files, I created a spreadsheet for DS3 characters/folders.

https://docs.google.com/spreadsheets/d/ ... D5m-RR-VE/

I still have to complete it.
It seems like a mess, but it's not that bad:
- Bosses are blue
- NPCs are purple
- Monsters I know (confirmed) are in green.
- My doubts are in red.
- Empty spots: I did not check yet.

As I keep working on this, it would be nice if anyone helped! Anyone can comment, really!
Or if there is a list created, I'd love to see it! 

Right now, it takes me a lifetime to find something I want - I'm searching for Havel, for example. No luck yet.
Hope it's helpful, somehow.

Good! I have something similar and recognize all armors
It first (Idk, who is creator) [https://docs.google.com/spreadsheets/d/ ... sp=sharing](https://docs.google.com/spreadsheets/d/1aqa9Q2xKLIiAuvvNLAEq1oZrwduTL7BpGOxMxAkodSQ/edit?usp=sharing)
It by Jean-Maxime, edit by me [https://docs.google.com/document/d/1tAY ... sp=sharing](https://docs.google.com/document/d/1tAYGq49U6DbGJos1l6PtRkJmguoU2roMPL_MZeEOJ20/edit?usp=sharing)
## Post #166
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-04-19T20:05:50+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> I discovered that the zaramot script also works with Dark Souls models 1. I hope the problem will be resolved soon skeleton. I have a request for zaramot. There are 3 models that I can not upload to 3d studio max. I want you to create a special script for one of these models. They are the same model in different sizes.

http://www.mediafire.com/file/750582wqyt01bqp/chr1.rar

They are use animated effest - unlikelly they can be converted
Try rip them with Ninjaripper or 3d ripper dx - fore me it will be long to go to them
## Post #167
- Username: jmaxime89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 24, 2017 10:57 am
- Post datetime: 2017-04-20T21:41:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> lolwatt wrote:I didn't find any, so while I was checking some files, I created a spreadsheet for DS3 characters/folders.

https://docs.google.com/spreadsheets/d/ ... D5m-RR-VE/

I still have to complete it.
It seems like a mess, but it's not that bad:
- Bosses are blue
- NPCs are purple
- Monsters I know (confirmed) are in green.
- My doubts are in red.
- Empty spots: I did not check yet.

As I keep working on this, it would be nice if anyone helped! Anyone can comment, really!
Or if there is a list created, I'd love to see it! 

Right now, it takes me a lifetime to find something I want - I'm searching for Havel, for example. No luck yet.
Hope it's helpful, somehow.

Good! I have something similar and recognize all armors
It first (Idk, who is creator) https://docs.google.com/spreadsheets/d/ ... sp=sharing
It by Jean-Maxime, edit by me https://docs.google.com/document/d/1tAY ... sp=sharing

Hey TokiChan ! Glad to meet you here ! I'm trying to 3d print some more characters. By the way thanks for crediting me for the sheet. You are awesome and I need to thank you again for all the help you gave me trough devianart
## Post #168
- Username: Zapper11
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 28, 2017 7:16 pm
- Post datetime: 2017-04-29T16:40:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi,zaramot.This script is really helpful.
I found the firelink shrine model but there is a problem with the bottom part of it.Its all twisted.The twisted part[high light] should be stairs.

m40_00_00_00_004600 - m40_00_00_00_004644 shrine[origin]
m41_00_00_00_004600 - m41_00_00_00_004645 shrine[soul of cinder]

m41_00_00_00_004600 below
m40_00_00_00_004601 also twisted
[Capture.JPG](https://xentaxbackup.github.io/file/12836_Capture.JPG)
## Post #169
- Username: Igrokez
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 08, 2017 3:42 am
- Post datetime: 2017-05-07T19:46:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey guis! Plz Help me to find a solution. How to find 3d models or how to extract them from Dark souls 3?
## Post #170
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-05-07T21:13:22+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Igrokez
>
> Hey guis! Plz Help me to find a solution. How to find 3d models or how to extract them from Dark souls 3?
Most of Dark Souls 3 will be upload here [http://tokami-fuko.deviantart.com/galle ... Dark-Souls](http://tokami-fuko.deviantart.com/gallery/55391377/Dark-Souls)

Like all games, you need unpack general archive and included archives, like ds1 - general archive, 2 under-archive - with skeleton and mesh, and texture archive
Then import midels with script in 3ds max
## Post #171
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-05-22T16:20:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I try to get rid of tread. I would like to know by zaromot if there is any progress for the script of demons's souls and dark souls 2 and 3
## Post #172
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-05-22T17:20:18+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

No, no any updates or fixes. Completely abandoned those games (and many others xD). Anyone, feel free to continue research, update mine or create new scripts/tools!
## Post #173
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-22T21:48:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> No, no any updates or fixes. Completely abandoned those games (and many others xD). Anyone, feel free to continue research, update mine or create new scripts/tools!
Same goes for LotF, huh?(
## Post #174
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-05-23T09:16:47+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

"Yes - is the word to everything. To liberty, to sweetness, to peace and construction"
## Post #175
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-05-23T10:03:34+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I would just have one request and then I'll leave you in peace. Do you have your last script? You said you had disconnected the skins and the skeleton. Could you reactivate it again? Or at least tell me how can I do it?
## Post #176
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-05-29T02:10:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Script doesnt support multiple uv channels i see,maps have lightmaps in first uv channel and texture on second i think,but second channel is messed up. Someone can help with that? Im really want to import hollow arenas and thats why i cant rip it from game with ninja ripper. Or maybe someone know way to rip it?
## Post #177
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-29T13:12:50+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

NinjaRipper works fine with DarkSouls 3, even in online.
If you are afraid of being softbanned, create new account, family share games, play on newly created acc (yeah you have to play through to unlock arena, or just use existing saves, copy them into other user's folders).
I've ripped several times and what comes to level geometry, it is ripped pretty nicely. Though you have to align uv scale down to smth like 0.00049 or so.
## Post #178
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-05-29T14:28:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from georgesears
>
> NinjaRipper works fine with DarkSouls 3, even in online.
If you are afraid of being softbanned, create new account, family share games, play on newly created acc (yeah you have to play through to unlock arena, or just use existing saves, copy them into other user's folders).
I've ripped several times and what comes to level geometry, it is ripped pretty nicely. Though you have to align uv scale down to smth like 0.00049 or so.

Thanks,but i dont have steam copy of game,because im playing in ds3 on ps4 and dont want to buy it on steam too,and download pirate copy just for content extracting. Maybe you can help? I think i can teleport to this arena with trainer,but i need coordinates of it.I need only round plaza arena.
## Post #179
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-05-29T19:41:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I'll be glad to see latest script too   
Both version - with skeleton import and for static extract without bones
## Post #180
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2017-06-30T12:48:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Heya Guys can som one explain to me why the 3dsmax importer script imports the mesh and the bones but no texture/material?. im using 3ds max 2017
## Post #181
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-03T19:25:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Someone have filenames list for Dark Souls 2 and Demon's souls?
## Post #182
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-07-04T06:17:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I do not know if you need it, but long ago I made a list of the characters of dark souls 2 I hope you can serve. 

> c1000=forrest grotesque
>
>  c1010=Kobold
>
>  c1020=Hollow Soldier
>
>  c1021=Royal Soldier
>
>  c1030=Hollow Infantry
>
>  c1031=Infantry
>
>  c1050=Amana Shrine Maiden
>
>  c1060=Dark Cleric
>
>  c1062=Dark Priestess
>
>  c1070=Parasitized Undead
>
>  c1080=Hollow Rouge
>
>  c1130=Varangian Sailor
>
>  c1150=Undead Traveler
>
>  c1170=Stone Soldie
>
>  c1180=Hollow Mage1
>
>  c1182=Hollow Mage2
>
>  c1210=gigant
>
>  c1230=Suspicious Shadows
>
>  c1240=Manikin
>
>  c1250=Rupturing Hollow
>
>  c1270=Abandoned Hollow
>
>  c1271=Abandoned Hollow1
>
>  c1290=Witchtree
>
>  c1292=Witchtree2
>
>  c1310=Lindelt Cleric
>
>  c1320=skeleton
>
>  c1330=skeleton2
>
>  c1340=Gyrm
>
>  c1350=Gyrm warrior
>
>  c1370=Aldia Warlock
>
>  c1380=Torturer
>
>  c1390=Artificial Undead
>
>  c1400=oniflex
>
>  c1410=Undead Aberration
>
>  c1460=Headless Vengarl
>
>  c1470=?????
>
>  c1480=undead peasan
>
>  c1490=Undead Steelworker
>
>  c1500=Stone Knight
>
>  c1510=Ironclad Soldier
>
>  c1520=royal soldier
>
>  c1530=Syan Soldier
>
>  c1540=The Skeleton Lords
>
>  c1550=Lizard Man
>
>  c1570=skeletons boos
>
>  c2011=small pig
>
>  c2020=big pig
>
>  c2021=big pig 2
>
>  c2030=Parasite Spider
>
>  c2040=poison moth
>
>  c2050=Poison Brumer 
>
>  c2051=Poison Brumer1
>
>  c2060=Cragslipper
>
>  c2090=Swollen Mongrel
>
>  c2100=Basilisk
>
>  c2120=dragon
>
>  c2130=cristal lizard
>
>  c2131=cristal lizard2
>
>  c2140=more big pig
>
>  c2170=Dark Stalker
>
>  c2200=big Poison Brumer 
>
>  c2230=Mongrel Rat 
>
>  c2240=Darksucker
>
>  c2250=unknow
>
>  c2260=Hunting Rat
>
>  c2261=Hunting Rat1
>
>  c2262=Hunting Rat2
>
>  c2263=Hunting Rat3
>
>  c2270=Stray Dog
>
>  c2271=Stray Dog1
>
>  c3000=ogre
>
>  c3010=Heide Knight
>
>  c3020=Gaoler
>
>  c3033=Flexile Sentry
>
>  c3040=nifanito
>
>  c3050=Smelter Demon
>
>  c3052=Smelter Demon2
>
>  c3060=captain knight
>
>  c3070=vergard body
>
>  c3071=vergard
>
>  c3080=Lion Clan Warrior
>
>  c3081=Lion Clan Warrior1
>
>  c3090=Giant Warrior
>
>  c3096=The Last Giant
>
>  c3097=Giant Lord
>
>  c3110=Banedigger
>
>  c3120=Grave Warden
>
>  c3130=Hollow Falconer
>
>  c3140=Hollow Primal Knight
>
>  c3150=Primal Knight
>
>  c3160=Desert Sorceress
>
>  c3170=Dragon Acolyte
>
>  c3180=The Pursuer
>
>  c3190=alonne knight
>
>  c3210=mimic
>
>  c3240=Belfry Gargoyles
>
>  c3250=Ruin Sentinels
>
>  c3260=The Rotten
>
>  c3270=dragon bones
>
>  c3300=Old Knight 
>
>  c3310=Drakekeeper
>
>  c3330=Velstadt, The Royal Aegis
>
>  c3340=Throne Defender
>
>  c3370=Abandoned Hollow 
>
>  c5000=Covetous Demon
>
>  c5001=Covetous Demon1
>
>  c5010=Mytha, the Baneful Queen
>
>  c5020=Manscorpion Tark
>
>  c5030=Scorpioness Najka
>
>  c5040=Looking Glass Knight
>
>  c5061=Darklurker1
>
>  c5062=????
>
>  c5065=Grave Warden Agdayne
>
>  c5090=Leydia 
>
>  c5110=Imperious Knight
>
>  c5120=Leydia Witch
>
>  c5146=hollow Vendrick
>
>  c6000=Ancient Dragon
>
>  c6010=Flame Lizard
>
>  c6020=Rampart Hedgehog
>
>  c6030=The Duke's Dear Freja
>
>  c6070=Old Iron King
>
>  c6080=Rotten Vermin
>
>  c6110=Dragonrider
>
>  c6115=Dragonrider1
>
>  c6191=Executioner's Chariot
>
>  c6250=Old Dragonslayer
>
>  c6260=Lost Sinner
>
>  c6270=Nashandra
>
>  c6280=Royal Rat Authority
>
>  c6500=Iron Warrior
>
>  c6510=Fume Sorcerer
>
>  c6530=Ashen Warrior
>
>  c6540=Ashen Crawler
>
>  c6560=Possessed Armor
>
>  c6570=Barrel Carrier
>
>  c6580=Retainer Rouge
>
>  c6590=Rampart Golem 
>
>  c6600=Crystal Golem
>
>  c6610=Frozen Reindeer
>
>  c6620=Rampart Hedgehog
>
>  c6630=Rampart Spearman
>
>  c6650=Sanctum Knight
>
>  c6660=Sanctum soldier
>
>  c6700=Sanctum Priestess
>
>  c6710=Poison Statue Cluster
>
>  c6711=Poison Statue Cluster1
>
>  c6720=Corrosive Egg Crawlers
>
>  c6740=creazy tree
>
>  c6750=Fume Knight
>
>  c6770=Retainer Sorceror
>
>  c6780=Mastodon Halberd Archdrake
>
>  c6790=tiger
>
>  c6791=tiger1
>
>  c6800=ser alonne
>
>  c6810=Sinh, the Slumbering Dragon
>
>  c6820=Elana, Squalid Queen
>
>  c6830=The Imperfect
>
>  c6840=Vendrick
>
>  c6880=Loyce Knight
>
>  c6890=Charred Loyce Knight
>
>  c6900=Burnt Ivory King
>
>  c7005=Shanalotte
>
>  c7015=unknow
>
>  c7036=Nashandra human
>
>  c7045=Laddersmith Gilligan
>
>  c7050=Strowen
>
>  c7051=Morrel
>
>  c7053=Griant
>
>  c7055=Strowen1
>
>  c7056=Griant
>
>  c7058=Griant
>
>  c7210=Chancellor Wellager
>
>  c7230=Milibeth 
>
>  c7240=Captain Drummond
>
>  c7250=Darkdiver Grandahl
>
>  c7300=phantom
>
>  c7310=phantom1
>
>  c7420=Creighton the Wanderer
>
>  c7430=Benhart of Jugo
>
>  c7440=Mild Mannered Pate
>
>  c7600=milfanito
>
>  c7601=milfanito1
>
>  c7602=milfanito2
>
>  c7620=Stone Trader Chloanne
>
>  c7640=Blacksmith Lenigrast
>
>  c7643=Steady Hand McDuff
>
>  c7680=Straid of Olaphis
>
>  c7690=Licia of Lindeldt
>
>  c7700=Felkin the Outcast
>
>  c7710=Royal Sorcerer Navlaan
>
>  c7770=Sweet Shalquoir
>
>  c7830=Titchy Gren
>
>  c7850=Blue Sentinel Targray
>
>  c8050=unknow
## Post #183
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-07-06T13:27:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> I do not know if you need it, but long ago I made a list of the characters of dark souls 2 I hope you can serve.

Oh, thanks you - It's great help!   
Do you have similar for armors? Just a question, no worry, if no
## Post #184
- Username: Mater85913
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 03, 2017 7:56 am
- Post datetime: 2017-08-11T02:23:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have been trying to get certain armor models from DS3 with Ninja Ripper and Binder tool and max scripts but Ninja Ripper doesn't work and it imports with the scripts like this...
How would I go about fixing this or am I doing something wrong..?



*if anyone has the working model and textures for Abyss Watcher, the Knight start set and Artorias/Black Knight please send me them*



I will hate doing the chest and others...
## Post #185
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-08-11T10:09:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Could you attach here model from first screenshot (3ds max viewport)? I would like to take a look. Thanks
## Post #186
- Username: Mater85913
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 03, 2017 7:56 am
- Post datetime: 2017-08-11T11:03:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

here.
Hope I added it right  XD
[https://www.mediafire.com/file/m82jv38b ... irassM.max](https://www.mediafire.com/file/m82jv38byi0xis8/AbyssCuirassM.max)
no idea how to link here
## Post #187
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-08-11T12:08:19+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Mater85913
>
> 

I have been trying to get certain armor models from DS3 with Ninja Ripper and Binder tool and max scripts but Ninja Ripper doesn't work and it imports with the scripts like this...
How would I go about fixing this or am I doing something wrong..?



*if anyone has the working model and textures for Abyss Watcher, the Knight start set and Artorias/Black Knight please send me them*


I will hate doing the chest and others...

Abyss Watchers - fully rigged, fixed meshes [https://tokami-fuko.deviantart.com/art/ ... -625779193](https://tokami-fuko.deviantart.com/art/Abyss-Watchers-png-mmd-xps-625779193)
[https://mega.nz/#!KsAQTa6K!cqogdbOS-G-9 ... 4UD2Lffq60](https://mega.nz/#!KsAQTa6K!cqogdbOS-G-9jJfByHqWzI6CaSwnb6nR-4UD2Lffq60)
Blackknights i process, but why not use BK and Artorias from DS1? This is similar, different normals only

MAxscript for XNAlara meshes [https://onedrive.live.com/embed?cid=6AC ... QXNW4XCKXs](https://onedrive.live.com/embed?cid=6ACACDEE9B1161E3&resid=6ACACDEE9B1161E3%21746&authkey=AJW1iQXNW4XCKXs)
## Post #188
- Username: tobiasxz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 13, 2017 6:40 am
- Post datetime: 2017-08-13T12:48:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I seem to be having an issue trying to import file c5160 from DS3.

I have managed to decompile it using Binder, however if I attempt to view it in 3DSMax using the script provided in the 3rd~ post, the mesh appears to all be screw up(at least the bottom half of it).

Here is what I'm talking about:

[http://i.imgur.com/kQSbc1d.png](http://i.imgur.com/kQSbc1d.png)

If someone could provide me with a method to fix this that would be amazing. I'll provide a download link for the model in case you need it.

[https://www.dropbox.com/s/rbynbykh6rxhu ... 0.zip?dl=1](https://www.dropbox.com/s/rbynbykh6rxhupp/c5160.zip?dl=1)
## Post #189
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-09-18T21:26:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from tobiasxz
>
> I seem to be having an issue trying to import file c5160 from DS3.

I have managed to decompile it using Binder, however if I attempt to view it in 3DSMax using the script provided in the 3rd~ post, the mesh appears to all be screw up(at least the bottom half of it).

Here is what I'm talking about:

http://i.imgur.com/kQSbc1d.png

If someone could provide me with a method to fix this that would be amazing. I'll provide a download link for the model in case you need it.

https://www.dropbox.com/s/rbynbykh6rxhu ... 0.zip?dl=1

Idk howto fix - when I have similar bugs I rip needed with Ninja Ripper and rigg in max from zero weight.
## Post #190
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-09-22T18:36:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Someone found skeleton of 6070 (corvian knight) in DLC1 chr (Ashes ofAriandel)?
Can't find it, and skeleton of corvian sattlers no work correctly 

UPD: fount it 
I hate twisted dlc files
## Post #191
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-10T23:30:42+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zardalu
>
> Hi Zaramot, thanks for the amazing script.

I am working with the Static map meshes in an attempt to rebuild the castles from the game. The script works well with static meshes when I select a random skeleton.hkx, except I notice that the UV's that are loaded seem to belong to the lightmap textures or something. 

As an example, I picked m31_00_00_00_000100.flver which is the details of a primitive stone house.

I looked through the flver file and see the following textures referenced:

m31_00_woodenhouse_00
m31_00_woodenhouse_01
m31_00_woodenhouse_02
m31_00_woodplank_04
m31_00_brickwall_06_block
m31_00_base

and also the following 2 small lightmap images, which correspond to the UVs as you can see in the screenshot:

g_DisplacementTexture 31000000_m000100_gi_0000_00_dol_00
g_DOLTexture1 31000000_m000100_gi_0000_00_dol_01

When I load the flver in Max via the script, I see the UVs correspond to the last 2 lightmap textures instead of the previous 7 correct textures.

Example with diffuse textures is here:
- PM per forum rules -

Is it possible to alter the existing script to remove the bone reference and pick the right UVs for the map meshes?

Sorry for necro,but im really interested in statics too,maybe someone know what to do? I cant rip some zones from game,so only way is to export it.
## Post #192
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2017-10-15T23:35:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I'm sorry to bother but well, whenever I try to import this set (Garl Vinland's from Demon's Souls) it always lacks the main part of the helm. It's so close yet unfortunately this one part keeps lacking... 

I included the script with every flver parts of the armor if needed as samples to figure this missing mesh problem

[http://www.mediafire.com/file/iauqckqp8 ... Vinland.7z](http://www.mediafire.com/file/iauqckqp8n5cxft/Garl+Vinland.7z)




And to be perfectly honest if someone wants to figure out the same missing mesh problem on the Phalanx here are all its parts

[http://www.mediafire.com/file/zc1mm514c ... Phalanx.7z](http://www.mediafire.com/file/zc1mm514cfvc7ow/Phalanx.7z)
## Post #193
- Username: Madein
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Oct 19, 2017 5:10 am
- Post datetime: 2017-10-18T21:22:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Greetings, I have read all the post from this discussion and I could not find my answer. I would like to import dark souls 3 combat animations into unreal engine. How would I go about doing that? I am using 3ds max.
## Post #194
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-19T17:08:23+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Madein
>
> Greetings, I have read all the post from this discussion and I could not find my answer. I would like to import dark souls 3 combat animations into unreal engine. How would I go about doing that? I am using 3ds max.

I also want to import animation, take a look at this topic: [https://forum.xentax.com/viewtopic.php? ... 20#p134620](https://forum.xentax.com/viewtopic.php?f=16&t=16451&p=134620#p134620)
## Post #195
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-26T13:20:19+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

My friend and I did some tests with Dark Souls 3, and I updated script. So, this version should work better for Dark Souls 3. Anyone could try this one out, if interested xD
[Dark_Souls_3_PC_UPD_B.7z](https://xentaxbackup.github.io/file/13608_Dark_Souls_3_PC_UPD_B.7z)
## Post #196
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-27T17:19:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I tried the new script but the skeleton did not follow the model.
## Post #197
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-27T17:57:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

It's model from dark souls 3? Original game or DLC? If you will send me this file, maybe I could fix it.
## Post #198
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-27T18:34:06+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> It's model from dark souls 3? Original game or DLC? If you will send me this file, maybe I could fix it.

It's the original game but I do not know if it's because it's the same thing with another model. I recommend you review it in general.

edit:I have a question what version did you and your friend use? for pc or console?
## Post #199
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-11-28T10:35:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have similar problem...
DS3 PC, no DLC, Sullyvanh's beast (c2250)
Before that skeleton was just moved, but no have right weight, and now...
Files [https://drive.google.com/open?id=1Z0NME ... ApMiLU1iCU](https://drive.google.com/open?id=1Z0NMEHrqqD4ymOWOSfnHzpApMiLU1iCU)
[1-.PNG](https://xentaxbackup.github.io/file/13604_1-.PNG)
## Post #200
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-28T11:32:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Such a shame to admit, but it was totally my mistake. Script was correct, just with disabled skeleton.hkx import part. Sorry for that, I updated it in previous post
## Post #201
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-28T13:15:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

ok there is now the skeleton but skinning does not work ie I get this on all parts:
## Post #202
- Username: MeinKampfyCouch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 29, 2017 9:03 am
- Post datetime: 2017-11-29T01:12:22+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi guys I don't know if anyone would be able to help me or not but I was recommended this thread off of Reddit.  I'm a cosplayer that just got into Dark Souls recently and has started building a Ringed Knight armor set, I've collected quite a few reference pics but it would be super helpful if I had the original 3d model to reference.  I was wondering if anyone would be able to help me?  I'd do it myself but I have like 0 skill with extracting and rigging models, and I also play DS3 on console.  If you guys can't help no worries just thought I'd ask.
## Post #203
- Username: solenrael
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 29, 2017 9:23 am
- Post datetime: 2017-11-29T01:45:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi! I was wondering if there was a way to do this with Blender? I don't have access to 3ds max currently and can't find the Noesis plugin mentioned at the start of the thread. 
I was hoping to access and convert Prince Lothric's (c5251) skeleton and animation files to be used along with his model, to show off cut content (everything in the c5251 folder is unused). There was another thread about animation extract, but it used a skeleton file that was already converted for the player character, with no mention of how to convert other skeleton.hkx files to be used. 

I have all of his files extracted already, if that's necessary.

Thanks in advance.
## Post #204
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-29T03:12:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> I have similar problem...
DS3 PC, no DLC, Sullyvanh's beast (c2250)
Before that skeleton was just moved, but no have right weight, and now...
Files https://drive.google.com/open?id=1Z0NME ... ApMiLU1iCU

BTW, I fixed skeleton placement for this file, you could try it with script in previous post. Checked uv's and weights they're looking correct

dibe91, if you upload this character you're having troubles with like TokiChan did, I could check it and see what I can do.
## Post #205
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-29T07:00:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

[http://www.mediafire.com/file/i4ws6yta7s76o3d/c1070.rar](http://www.mediafire.com/file/i4ws6yta7s76o3d/c1070.rar)
## Post #206
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-11-29T20:11:36+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

BTW, daemon1 just released tool for bloodborne - I bet it's the same as DS3, you all should try his tool!

EDIT: I checked c1070, it has extra bones, which aren't used - but rigging is there. Hammer don't have weights because it's like static object referenced to 1 bone. Even uv's looks quite correct, can't check it 100% but in generally this model is quite okay. Not like totall disaster, useable I think.
## Post #207
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-11-29T21:32:34+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from solenrael
>
> There was another thread about animation extract, but it used a skeleton file that was already converted for the player character, with no mention of how to convert other skeleton.hkx files to be used.

Just load skeleton of that model in havok,then export it as i say in tutorial. And you dont need to apply animations to model,you can see it in havok.
## Post #208
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-30T13:31:29+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

OK, but now how do I get the textures of the models?
## Post #209
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-11-30T15:52:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> OK, but now how do I get the textures of the models?
Use tpf plugin for noesis.
## Post #210
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-11-30T18:48:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

well, but can the script give the right name to the texture? you know I'd be very comfortable
## Post #211
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-11-30T19:26:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> well, but can the script give the right name to the texture? you know I'd be very comfortable
They are in same archive as a model. They should be.
## Post #212
- Username: jnnpsubm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 01, 2017 4:59 pm
- Post datetime: 2017-12-02T09:01:55+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Can any one send me a copy of the max script? I cannot find it in this post...... my e-mail is [jnnpsubm@hotmail.com](mailto:jnnpsubm@hotmail.com), much thanks!
## Post #213
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-02T12:48:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Last post

[viewtopic.php?f=16&t=14291&start=180](http://forum.xentax.com/viewtopic.php?f=16&t=14291&start=180)
## Post #214
- Username: jnnpsubm
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 01, 2017 4:59 pm
- Post datetime: 2017-12-02T14:00:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Last post

viewtopic.php?f=16&t=14291&start=180

Thank you very much!  With you max script and some other tools , I am able to add some DSIII char to my game engine base on DirectX12:


not used normal map yet,still working on some dds texture format.
[无标题.png](https://xentaxbackup.github.io/file/13630_无标题.png)
## Post #215
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-02T16:34:21+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from jnnpsubm
>
> zaramot wrote:Last post

viewtopic.php?f=16&t=14291&start=180

Thank you very much!  With you max script and some other tools , I am able to add some DSIII char to my game engine base on DirectX12:
not used normal map yet,still working on some dds texture format.

I'm glad, that you've found it useful so far!
## Post #216
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-12-09T09:48:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Newscript will work with maps and static?
## Post #217
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-09T21:10:34+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

For static should work, for maps I don't know! Never tried to import them actually.
## Post #218
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-12-09T21:44:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> For static should work, for maps I don't know! Never tried to import them actually.
Maps have more than 1 uv maps and your tool import uv only for lightmaps.
## Post #219
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-09T21:54:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Ah, didn't know this. It's not very hard to implement though.
## Post #220
- Username: fine197612
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 11, 2017 4:04 pm
- Post datetime: 2017-12-11T10:29:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

help~~ Script keeps asking to open hkx file first but I want to see static meshs only in the map folder (guess they are in data5)~
## Post #221
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-11T11:34:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Here's the script, same script just without bones. Though, as dropoff said maps has more than one uv channel - script should be updated for them. And I don't have any map/level file.
[Dark_Souls_3_PC_UPD_B_no_bones.7z](https://xentaxbackup.github.io/file/13675_Dark_Souls_3_PC_UPD_B_no_bones.7z)
## Post #222
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-12-12T00:32:12+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Here's the script, same script just without bones. Though, as dropoff said maps has more than one uv channel - script should be updated for them. And I don't have any map/level file.

Here is round plaza arena map models and textures.
[https://mega.nz/#!pg1E0BII!x_izi3dsV_KC ... 4B4R_WJIpE](https://mega.nz/#!pg1E0BII!x_izi3dsV_KCGgsIhWf-b26XzQL-wNCA-4B4R_WJIpE)
## Post #223
- Username: fine197612
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 11, 2017 4:04 pm
- Post datetime: 2017-12-12T05:09:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

WOW~ You are the Hero! The script works as fine as Super!!! for both Characters and Objects~! Also I don't see any trouble on texturing. UV was so perpectly extracted too!



maxscriptok1.jpg (80.26 KiB) Viewed 144 times
## Post #224
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-12-14T17:37:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

error with the c1200. the skeleton does not follow the model
## Post #225
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-12-18T23:18:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> error with the c1200. the skeleton does not follow the model

I want to point out two other models that have problems with the skeleton: the c1390, c1391
## Post #226
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2017-12-20T22:37:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi guys, I digged into the Data 3/chr folder and here are my findings for all characters I found there, yeah that means I checked all CHRBND files lol took me some time:
OBS: Some of them I didn't remember the proper name so I named whatever name & sorry for my non sense english because sometimes you will find something weird to read but I hope you get the basic idea.
If you wanna do a quick search the main tags: glitched, fixed, boss, pet, NPC
unknown c0000
unknown c0100
unknown c1000
mob unknown glitched c1070
mob transformed undead c1090
mob undead with crossbow c1100
mob undead with crossbow c1101
mob undead with crossbow c1102
mob undead with big axe c1105
mob undead with big axe c1106
mob slug c1130
mob with 2 swords c1170
mob with twin daggers c1180
mob steel knight c1190
mob tiny with wizard hat c1200
mob from swamp glitched c1210
mob from swamp c1211
unknown goop mob c1220
mob big fat witch c1230
mob with big fork c1240
unknown mob c1241
mob from pontiff's place c1250
mob big chains and cage c1260
mob knight c1280
mob knight c1281
mob knight c1282
mob fat armored flying c1290
mob black knight c1300
cool armor set i forgot the name c1310
wizard savage boss with ball c1320
wizard savage boss c1321
mob from grand archives c1340
unknown mob c1350
mob with cross c1360
mob with tree c1370
unknown mob with whip c1380
mob snake c1390
mob with chains and axe c1391
NPC Firekeeper c1400
mob silver knight c1410
mob pyromancer c1430
mob pyromancer c1440
mob pyromancer c1441
NPC wizard c1442
mob undead big axe c1445
mob wizard c1446
mob gnome NPC c1450
mob spinner skull c1470
cool armor set i dont remember the name c1480
dancer boss c1490
dog glitched c2020
dog glitched c2021
mob from pontiff's place c2030
unknown crazy dog glitched c2040
mob jelly goop c2060
unknown dog glitched c2070
dog glitched c2080
unscaled baby dragon boss c2090
unknown mob c2100
mob rat glitched c2110
mob mimic c2120
unknown pieces from some mob c2130
unknown pieces from some mob c2131
unknown pieces from some mob c2132
mob basilisk frog c2140
mob crystal lizard c2150
old witch NPC c2160
unknown NPC c2170
mob goop c2180
mob gargoyle fixed c2190
mob gargoyle glitched c2191
unknown glitched c2200
mob raven glitched c2210
mob witch with horseshoe fire c2230
valdrit dog boss c2240
unknown dragon glitched c2250
artillery crossbows c2260
mob big crag glitched c2270
mob big crag c2271
mob big rat c2280
dog glitched c2290
mob giant from cathedral with ball c3020
mob giant from cathedral c3021
the abyss watcher boss c3040
fire demon boss fixed c3050
fire demon boss c3060
mob from swamp i guess c3070
unknown c3071
ornstein's pet phoenix c3080
weird abyss watchers c3090
unknown mob too much glitched c3100
mob big spider c3110
mob from swamp c3120
dragon from prince's place c3140
dragon from prince's place c3141
ornstein boss c3160
mob darkwraith c3170
blacksmith c3190
old oracle with eyes band c3200
mob bug c3210
baby dragon c3220
fire fat dragon statue c3230
old oracle c3250
nameless boss c5010
nameless pet c5030
transformed undead c5110
yorn the giant boss glitched c5140
aldrich boss form anorlondo glitched c5150
big skull king boss c5160
big tree boss c5180
fire demon boss glitched c5200
princess c5210
pope boss c5220
mob fat pope fixed c5221
mob pope fixed c5222
mob pope fixed c5223
mob fat pope c5225
mob pope c5226
mob pope c5227
mob fire staff from pontiffs place c5240
prince boss c5250
yorn the giant boss c5260
mob from pontiffs place c5270

***I also have DS1 Data/chr name list for all characters, let me know if you want me to share that.***
## Post #227
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2017-12-21T18:20:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from rafak
>
> Hi guys, I digged into the Data 3/chr folder and here are my findings for all characters I found there, yeah that means I checked all CHRBND files lol took me some time:
OBS: Some of them I didn't remember the proper name so I named whatever name & sorry for my non sense english because sometimes you will find something weird to read but I hope you get the basic idea.
If you wanna do a quick search the main tags: glitched, fixed, boss, pet, NPC
unknown c0000
unknown c0100
unknown c1000
mob unknown glitched c1070
mob transformed undead c1090
mob undead with crossbow c1100
mob undead with crossbow c1101
mob undead with crossbow c1102
mob undead with big axe c1105
mob undead with big axe c1106
mob slug c1130
mob with 2 swords c1170
mob with twin daggers c1180
mob steel knight c1190
mob tiny with wizard hat c1200
mob from swamp glitched c1210
mob from swamp c1211
unknown goop mob c1220
mob big fat witch c1230
mob with big fork c1240
unknown mob c1241
mob from pontiff's place c1250
mob big chains and cage c1260
mob knight c1280
mob knight c1281
mob knight c1282
mob fat armored flying c1290
mob black knight c1300
cool armor set i forgot the name c1310
wizard savage boss with ball c1320
wizard savage boss c1321
mob from grand archives c1340
unknown mob c1350
mob with cross c1360
mob with tree c1370
unknown mob with whip c1380
mob snake c1390
mob with chains and axe c1391
NPC Firekeeper c1400
mob silver knight c1410
mob pyromancer c1430
mob pyromancer c1440
mob pyromancer c1441
NPC wizard c1442
mob undead big axe c1445
mob wizard c1446
mob gnome NPC c1450
mob spinner skull c1470
cool armor set i dont remember the name c1480
dancer boss c1490
dog glitched c2020
dog glitched c2021
mob from pontiff's place c2030
unknown crazy dog glitched c2040
mob jelly goop c2060
unknown dog glitched c2070
dog glitched c2080
unscaled baby dragon boss c2090
unknown mob c2100
mob rat glitched c2110
mob mimic c2120
unknown pieces from some mob c2130
unknown pieces from some mob c2131
unknown pieces from some mob c2132
mob basilisk frog c2140
mob crystal lizard c2150
old witch NPC c2160
unknown NPC c2170
mob goop c2180
mob gargoyle fixed c2190
mob gargoyle glitched c2191
unknown glitched c2200
mob raven glitched c2210
mob witch with horseshoe fire c2230
valdrit dog boss c2240
unknown dragon glitched c2250
artillery crossbows c2260
mob big crag glitched c2270
mob big crag c2271
mob big rat c2280
dog glitched c2290
mob giant from cathedral with ball c3020
mob giant from cathedral c3021
the abyss watcher boss c3040
fire demon boss fixed c3050
fire demon boss c3060
mob from swamp i guess c3070
unknown c3071
ornstein's pet phoenix c3080
weird abyss watchers c3090
unknown mob too much glitched c3100
mob big spider c3110
mob from swamp c3120
dragon from prince's place c3140
dragon from prince's place c3141
ornstein boss c3160
mob darkwraith c3170
blacksmith c3190
old oracle with eyes band c3200
mob bug c3210
baby dragon c3220
fire fat dragon statue c3230
old oracle c3250
nameless boss c5010
nameless pet c5030
transformed undead c5110
yorn the giant boss glitched c5140
aldrich boss form anorlondo glitched c5150
big skull king boss c5160
big tree boss c5180
fire demon boss glitched c5200
princess c5210
pope boss c5220
mob fat pope fixed c5221
mob pope fixed c5222
mob pope fixed c5223
mob fat pope c5225
mob pope c5226
mob pope c5227
mob fire staff from pontiffs place c5240
prince boss c5250
yorn the giant boss c5260
mob from pontiffs place c5270

***I also have DS1 Data/chr name list for all characters, let me know if you want me to share that.***

C0000 - alternative character skeletons for all Souls 

Some late,dude - in this forum almost all characters are recognised and writed in lists, include DLC, see files posting before 
And CHR list for DS1, DS2, DemS and BB is late too 
Weapon and armors for DS3 almost done too, not have weapons/armors part list fr DS2 and Dems
Anyway, you have great work
## Post #228
- Username: epikus29
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 11, 2016 1:28 am
- Post datetime: 2017-12-28T12:26:11+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Glad to see people are still working on extracting the files. Now that a new version of BinderTool is out, that supports all the DS2 model files, could you please, Zaramot, revise your import script, or make a tutorial for using it? When I tried enabling the bone importing part (script DS_2_3_PC_UPD) I keep getting errors when using it on DS2's .hkx files. With bones disabled, script imports models perfectly. I also have your old "DS_2_PC_UPD" script, which loads SotFS models, and when used on a DS2 model, can weight it to a DS3 skeleton (but crashes on DS2's .hkx's). I've had no luck trying to merge the scripts...
## Post #229
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-12-28T18:29:38+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from rafak
>
> Hi guys, I digged into the Data 3/chr folder and here are my findings for all characters I found there, yeah that means I checked all CHRBND files lol took me some time:
OBS: Some of them I didn't remember the proper name so I named whatever name & sorry for my non sense english because sometimes you will find something weird to read but I hope you get the basic idea.
If you wanna do a quick search the main tags: glitched, fixed, boss, pet, NPC
unknown c0000
unknown c0100
unknown c1000
mob unknown glitched c1070
mob transformed undead c1090
mob undead with crossbow c1100
mob undead with crossbow c1101
mob undead with crossbow c1102
mob undead with big axe c1105
mob undead with big axe c1106
mob slug c1130
mob with 2 swords c1170
mob with twin daggers c1180
mob steel knight c1190
mob tiny with wizard hat c1200
mob from swamp glitched c1210
mob from swamp c1211
unknown goop mob c1220
mob big fat witch c1230
mob with big fork c1240
unknown mob c1241
mob from pontiff's place c1250
mob big chains and cage c1260
mob knight c1280
mob knight c1281
mob knight c1282
mob fat armored flying c1290
mob black knight c1300
cool armor set i forgot the name c1310
wizard savage boss with ball c1320
wizard savage boss c1321
mob from grand archives c1340
unknown mob c1350
mob with cross c1360
mob with tree c1370
unknown mob with whip c1380
mob snake c1390
mob with chains and axe c1391
NPC Firekeeper c1400
mob silver knight c1410
mob pyromancer c1430
mob pyromancer c1440
mob pyromancer c1441
NPC wizard c1442
mob undead big axe c1445
mob wizard c1446
mob gnome NPC c1450
mob spinner skull c1470
cool armor set i dont remember the name c1480
dancer boss c1490
dog glitched c2020
dog glitched c2021
mob from pontiff's place c2030
unknown crazy dog glitched c2040
mob jelly goop c2060
unknown dog glitched c2070
dog glitched c2080
unscaled baby dragon boss c2090
unknown mob c2100
mob rat glitched c2110
mob mimic c2120
unknown pieces from some mob c2130
unknown pieces from some mob c2131
unknown pieces from some mob c2132
mob basilisk frog c2140
mob crystal lizard c2150
old witch NPC c2160
unknown NPC c2170
mob goop c2180
mob gargoyle fixed c2190
mob gargoyle glitched c2191
unknown glitched c2200
mob raven glitched c2210
mob witch with horseshoe fire c2230
valdrit dog boss c2240
unknown dragon glitched c2250
artillery crossbows c2260
mob big crag glitched c2270
mob big crag c2271
mob big rat c2280
dog glitched c2290
mob giant from cathedral with ball c3020
mob giant from cathedral c3021
the abyss watcher boss c3040
fire demon boss fixed c3050
fire demon boss c3060
mob from swamp i guess c3070
unknown c3071
ornstein's pet phoenix c3080
weird abyss watchers c3090
unknown mob too much glitched c3100
mob big spider c3110
mob from swamp c3120
dragon from prince's place c3140
dragon from prince's place c3141
ornstein boss c3160
mob darkwraith c3170
blacksmith c3190
old oracle with eyes band c3200
mob bug c3210
baby dragon c3220
fire fat dragon statue c3230
old oracle c3250
nameless boss c5010
nameless pet c5030
transformed undead c5110
yorn the giant boss glitched c5140
aldrich boss form anorlondo glitched c5150
big skull king boss c5160
big tree boss c5180
fire demon boss glitched c5200
princess c5210
pope boss c5220
mob fat pope fixed c5221
mob pope fixed c5222
mob pope fixed c5223
mob fat pope c5225
mob pope c5226
mob pope c5227
mob fire staff from pontiffs place c5240
prince boss c5250
yorn the giant boss c5260
mob from pontiffs place c5270

***I also have DS1 Data/chr name list for all characters, let me know if you want me to share that.***

could you put the names of the wiki? it would be easier for me to understand everything. I have to give a list of models that do not work properly.
## Post #230
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-12-30T08:04:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

can you tell me how do I get the models of the dlc? I can not understand it by extracting the files
## Post #231
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-12-30T16:54:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> can you tell me how do I get the models of the dlc? I can not understand it by extracting the files
Same as from original game but files will be without names.
## Post #232
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2017-12-31T08:36:53+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

is there a faster way? I should see files by file and they are many
## Post #233
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-12-31T08:56:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> is there a faster way? I should see files by file and they are many
As i know is the only way.
## Post #234
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-01T10:23:38+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello people, i could extract all dark souls 1 & 3 sounds, but i got a bunch of wav files which would take a lot of time to check one by one, I'm looking for walk/running and hammer sounds, anyone could find it?
## Post #235
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-01-01T22:45:01+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> is there a faster way? I should see files by file and they are many
It must be extract file tofile allnumbered crazy archives, then you'll get (may be use search about format .flver and tpf) all DLC's - I use that way. No have faster
## Post #236
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-01-01T22:46:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from rafak
>
> Hello people, i could extract all dark souls 1 & 3 sounds, but i got a bunch of wav files which would take a lot of time to check one by one, I'm looking for walk/running and hammer sounds, anyone could find it?
Nope, only checking file to file 
Good work!
## Post #237
- Username: LutwidgeDalberg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 29, 2017 9:25 am
- Post datetime: 2018-01-02T02:40:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi There
Is there a way to convert hkx files to bvh files?
## Post #238
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-01-02T17:14:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

for those interested, I put the files of the first dlc in this archive. you will find the chr, the map and the objects, I will also put the contents of the second dlc

[http://www.mediafire.com/file/n46y86hgmfa43bs/dlc1.rar](http://www.mediafire.com/file/n46y86hgmfa43bs/dlc1.rar)
## Post #239
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-04T05:25:13+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I found the walk/running/attacking/rolling most of the character main sounds from Dark Souls PTDE at dvdbnd1.bdt data in its sound folder there's a file named frpg_main.fsb. Just extract it using the fmod_extr.exe.

Now I need the Estus Flask model & its textures, anyone could find it?
## Post #240
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-01-05T10:32:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

[http://www.mediafire.com/file/g1yph64d1xf1dyr/dlc2.rar](http://www.mediafire.com/file/g1yph64d1xf1dyr/dlc2.rar)

the second dlc has been done. I noticed that there are models with problems in the following will make the complete list
## Post #241
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-06T19:24:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Never mind guys, I found a better version of Estus Flask at:
[https://www.thingiverse.com/thing:1543005](https://www.thingiverse.com/thing:1543005)
& a Dark Souls III Estus Flask texture:
[https://www.nexusmods.com/darksouls/mods/1220/](https://www.nexusmods.com/darksouls/mods/1220/)?

The mesh is in .STL, & sadly when you try to edit it by using Blender at least you will get a poor performance due to high complexity of vertices/polygons, what I suggest you to do is adding a decimate modifier & setting the ratio to 0.031 so you can work with the UV map process without compromising the performance. It worked for me here's the following link how it looked like after that:
[https://ibb.co/gKAibb](https://ibb.co/gKAibb)

P.S. By the way I'm looking for a python script which converts the Dark Souls Bones to whatever game platform like for Second Life, I mean by just renaming the bones is not enough what if a skeleton has more bones than you need for another skeleton sctructure?
How to deal with the conversion?
## Post #242
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-11T00:41:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> rafak wrote:Hello people, i could extract all dark souls 1 & 3 sounds, but i got a bunch of wav files which would take a lot of time to check one by one, I'm looking for walk/running and hammer sounds, anyone could find it?
Nope, only checking file to file 
Good work!

Are you Tokami Fuko from DeviantArt?
I've noticed your great job on Alva, by the way I'm looking for her Arbalest crossbow, can you tell me where the file is located?
## Post #243
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-01-11T17:14:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I'm looking for Stray Demon, can you tell me what the number is?
## Post #244
- Username: rafak
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu Dec 21, 2017 12:19 am
- Post datetime: 2018-01-11T18:58:35+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> I'm looking for Stray Demon, can you tell me what the number is?

Here we go:
If you're looking for the ones from Dark Souls PTDE here's the following file locations:

dvdbnd0.btd/chr/c2230.chrbnd.dcx (Stray Demon).
dvdbnd0.btd/chr/c2231.chrbnd.dcx (Stray Demon missing TPF file but comes with additional files for bones/animations I guess).
dvdbnd0.btd/chr/c2232.chrbnd.dcx (Asylum Demon).

If you're looking for the ones from Dark Souls III & similars Demons:

Data3/chr/c3050.chrbnd (Old Demon King).
Data3/chr/c3060.chrbnd (Demon).
Data3/chr/c5200.chrbnd (Stray Demon, it may seen glitched but it is not, basically it's a lot of parts together you hafta separate them).
## Post #245
- Username: kuma
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2017 7:25 am
- Post datetime: 2018-01-22T11:13:51+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from epikus29
>
> Glad to see people are still working on extracting the files. Now that a new version of BinderTool is out, that supports all the DS2 model files, could you please, Zaramot, revise your import script, or make a tutorial for using it? When I tried enabling the bone importing part (script DS_2_3_PC_UPD) I keep getting errors when using it on DS2's .hkx files. With bones disabled, script imports models perfectly. I also have your old "DS_2_PC_UPD" script, which loads SotFS models, and when used on a DS2 model, can weight it to a DS3 skeleton (but crashes on DS2's .hkx's). I've had no luck trying to merge the scripts...
Does someone have the old script for sotfs models? It disappeared from the thread.
## Post #246
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-01-23T19:36:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

[https://www.dropbox.com/s/pn09zoa99wz4g ... t.rar?dl=0](https://www.dropbox.com/s/pn09zoa99wz4ga8/script.rar?dl=0)

there is the new version and the old version
## Post #247
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-02-07T20:52:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Tools for Bloodborne actually working with DS3, in sometimegive better skeleton that DS3 script
## Post #248
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-02-08T12:42:50+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I would like to know if anything can be done for dark souls 2
## Post #249
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2018-02-27T16:44:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey uh...while the DS3 tools seem to work for SotFS filess as well, I'm still having trouble locating Aldia's model itself. Can anyone help me out? Point me in the right direction? I need to get his model for a project of mine.

Okay so I found it, but the current scripts seem to error with it, the one using no bones does not acquire UV's, and any others seem to distort it heavily.
[https://www.dropbox.com/s/jg14w2ymq6wke ... a.zip?dl=0](https://www.dropbox.com/s/jg14w2ymq6wke5j/Aldia.zip?dl=0)
## Post #250
- Username: mostlyhuman
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 01, 2018 9:42 am
- Post datetime: 2018-03-03T00:47:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Is there a way to matchup which textures go with which models if they have different file numbers in different directories?

Thanks in advance!
## Post #251
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-03-13T08:57:59+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot
>
> Here's the script, should import models you want and other you may want xD I disabled bone-import part, so it will be faster and easier for you.

This not work with c6920 (Aldia, Dark Souls 2)
Polys are twisted
[Ashampoo_Snap_2018.03.jpg](https://xentaxbackup.github.io/file/14025_Ashampoo_Snap_2018.03.jpg)
## Post #252
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-03-19T02:26:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> 
This not work with c6920 (Aldia, Dark Souls 2)
Polys are twisted

It doesn't work for ds2 armors either atleast not for the helms and half of the chestpieces. I have yet to try it on softs armors. (btw would someone know the forlon set, scythe and sword id?)
## Post #253
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-03-20T17:25:24+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Lorian Elder Prince
>
> TokiChan wrote:
This not work with c6920 (Aldia, Dark Souls 2)
Polys are twisted

It doesn't work for ds2 armors either atleast not for the helms and half of the chestpieces. I have yet to try it on softs armors. (btw would someone know the forlon set, scythe and sword id?)

I try with SotFS, but for me not working too... (I can't make armor lists)
Maybe you'll have a luck?
## Post #254
- Username: iliketocode123
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 10, 2018 3:01 am
- Post datetime: 2018-04-09T20:29:06+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Has anyone found Champion Gundyr? Not sure which number he is
## Post #255
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-10T18:22:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from iliketocode123
>
> Has anyone found Champion Gundyr? Not sure which number he is

Yup, you can get him in different formats here (obj,3ds,fbx, xps) 
[https://tokami-fuko.deviantart.com/art/ ... -663752976](https://tokami-fuko.deviantart.com/art/Ludex-Gundyr-663752976)
[https://p3dm.ru/files/characters/supern ... ndyr-.html](https://p3dm.ru/files/characters/supernatural/9017-ludex-gundyr-.html)
## Post #256
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-10T18:26:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

EDIT: Ok, I get the Fume knight, but skeleton is twisted and working incorrect.

And also - do someone edits the ds2 import script? First not give me correct bones, 2_3 no give bones at all.
## Post #257
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-04-16T17:37:31+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> Does anyone have the Fume Knight model? Dark Souls 2. I found textures only, but no have .flv model.
I unpack all files from HQchr and other addition archives and try to check with search, but no luck.
Here is Raime, the Fume Knight I also added his shield and sword from the hqpart folder, Raime's textures come from the hqchr folder. 
[http://www.mediafire.com/file/66dcn4ugm ... Knight.zip](http://www.mediafire.com/file/66dcn4ugm3qxui7/Raime%2C%20the%20Fume%20Knight.zip)
## Post #258
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-17T10:03:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Lorian Elder Prince
>
> TokiChan wrote:Does anyone have the Fume Knight model? Dark Souls 2. I found textures only, but no have .flv model.
I unpack all files from HQchr and other addition archives and try to check with search, but no luck.

Here is Raime, the Fume Knight I also added his shield and sword from the hqpart folder, Raime's textures come from the hqchr folder. 
http://www.mediafire.com/file/66dcn4ugm ... Knight.zip

Thanks you! I already found the .flv model of him, but from me this bug..
Dou have the same problems with skeleton/weights and missed UV like me or I'mcuriou?
## Post #259
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-04-17T15:17:18+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> Lorian Elder Prince wrote:TokiChan wrote:Does anyone have the Fume Knight model? Dark Souls 2. I found textures only, but no have .flv model.
I unpack all files from HQchr and other addition archives and try to check with search, but no luck.

Here is Raime, the Fume Knight I also added his shield and sword from the hqpart folder, Raime's textures come from the hqchr folder. 
http://www.mediafire.com/file/66dcn4ugm ... Knight.zip

Thanks you! I already found the .flv model of him, but from me this bug..
Dou have the same problems with skeleton/weights and missed UV like me or I'mcuriou?

Well, I also get a problem with the skeleton/weights but not with the UV. And the DS2 scriptwithout bones works fine on him.
## Post #260
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-17T15:24:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Lorian Elder Prince
>
> 

Well, I also get a problem with the skeleton/weights but not with the UV. And the DS2 scriptwithout bones works fine on him.

So, thanks you! 
Now need to remember, how to rigg armors...
## Post #261
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-04-22T17:58:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

If some people are still looking for items like throwing knife, firebombs, arrows, weapon arts parts, magic, etc... they are located inside the sfx folders for instance the estus flask is found in the DATA1, sfx folder in the common effect ressource and its ID is s07002. Friede's magic Scythe part is found in the DLC1, sfx player version is inside the data1 though.
## Post #262
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-23T17:02:14+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

So, it's me again...
UV maps and bones for Aava and his brother (dark souls 2, c6970 and 6971) is broken.
Not include that ds2_pc script no open that - I change .flver parameter to .flv in script.
So, someone else working with DS2 importing script?
[00bug.jpg](https://xentaxbackup.github.io/file/14256_00bug.jpg)
## Post #263
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-04-23T19:46:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

And for Traveling Merchant Set this is same
DS2, parts 1140
I can import only with ds_2_3 script (without bones) butthis is no save UV too
[bug.jpg](https://xentaxbackup.github.io/file/14257_bug.jpg)
## Post #264
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-04-29T07:56:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Lorian Elder Prince
>
> If some people are still looking for items like throwing knife, firebombs, arrows, weapon arts parts, magic, etc... they are located inside the sfx folders for instance the estus flask is found in the DATA1, sfx folder in the common effect ressource and its ID is s07002. Friede's magic Scythe part is found in the DLC1, sfx player version is inside the data1 though.

ok I managed to get the objects of ds3 but unfortunately I can not take those of ds1 and ds2 because the bindel tool can not open the Archive files. is there a way to contact the creator of the tools and tell him if he can help me?
## Post #265
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2018-05-10T17:44:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Pardon me, does anyone have the Silver Knight model in DS3?
## Post #266
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-05-12T09:55:44+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AltoRoark
>
> Pardon me, does anyone have the Silver Knight model in DS3?

I have Black knight and Silver knight and their armor for Player. Do u need the numbers or ready for using models?
## Post #267
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2018-05-12T19:24:06+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> AltoRoark wrote:Pardon me, does anyone have the Silver Knight model in DS3?

I have Black knight and Silver knight and their armor for Player. Do u need the numbers or ready for using models?

I don't have the game on PC, so I'm gonna need the models themselves.

From DS3 specifically, not DS1.
## Post #268
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2018-05-16T22:04:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Is there any way for a console peasant like me to aquire these models? ._.
## Post #269
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2018-05-17T12:53:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AltoRoark
>
> Is there any way for a console peasant like me to aquire these models? ._.
Just get files from internet. I think you will find a way to do this.
## Post #270
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2018-05-17T17:07:29+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff
>
> AltoRoark wrote:Is there any way for a console peasant like me to aquire these models? ._.
Just get files from internet. I think you will find a way to do this.
I've tried finding them online many times and all I could ever find was:

-tutorials for PC gamers on how to extract models from the game
-original creations, as opposed to files straight from the game
-DS1 models, and not DS3 models, most of which I have already

I'm specifically looking for the Silver Knight enemy model from the game, as well as many weapon and armor models, and I can't find those anywhere.
## Post #271
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-05-20T13:19:12+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AltoRoark
>
> TokiChan wrote:AltoRoark wrote:Pardon me, does anyone have the Silver Knight model in DS3?

I have Black knight and Silver knight and their armor for Player. Do u need the numbers or ready for using models?

I don't have the game on PC, so I'm gonna need the models themselves.

From DS3 specifically, not DS1.

Okay, I'll up it for you 
Which formats do you need?
## Post #272
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2018-05-20T18:37:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> 

Okay, I'll up it for you 
Which formats do you need?
Obj files. Many thanks in advance!
## Post #273
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-06-09T00:12:08+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Actually, does someone know, what's be with DS2?

Which Bindertoolversion must I use? 0.3? 
Because I try to get some armors from files, but this always gives me wrong UV maps.

And does anyone working with ds2 script for correct bones and UV? Ormay be adopt Bloodborne tools for that?
## Post #274
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-06-09T11:15:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> 
Which Bindertoolversion must I use? 0.3?

yes, the most up-to-date version can open the ds2 archives
## Post #275
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-06-10T13:14:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dibe91
>
> TokiChan wrote:
Which Bindertoolversion must I use? 0.3? 


yes, the most up-to-date version can open the ds2 archives

No recently? Because 0.5.2 is not work
## Post #276
- Username: DarkSouls333
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 22, 2018 3:55 pm
- Post datetime: 2018-06-22T10:02:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Is there still no definite tutorial how to export DS3 models? I understand you guys are good at what you do, and if I really wanted a specific model I could probably just ask, but there are a ton of people like me who'd like to do to this themselves and not have to rely on someone sending them stuff. Also, I'm just naturally curious.

I've managed to extract all the dataX files with BinderTool, and can open some pieces of armor (.flver files) with the "no bones" Max script but I don't know how to open character files. Also when I extract Data3, I get only like ten or so cXXXX folders/files, nowhere near as much as others.
## Post #277
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2018-07-29T22:59:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Are all DS3 armor and weapons models extractable or some have errors?

P.S. Also, is there a possibility to update script for viewing/unpacking .TPF files in Noesis? Looks like files that were updated or added with TRC DLC #2 cannot be extracted and opened.
[Снимок экрана (1043).png](https://xentaxbackup.github.io/file/14696_Снимок экрана (1043).png)
## Post #278
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-08-08T21:55:39+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from fullinu
>
> Are all DS3 armor and weapons models extractable or some have errors?

P.S. Also, is there a possibility to update script for viewing/unpacking .TPF files in Noesis? Looks like files that were updated or added with TRC DLC #2 cannot be extracted and opened.

For me almost all armors/parts are working, and nosee errors with DLC2 tpf.. what you try to open? If map/obj files, it sometime wrong from basic game too
## Post #279
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2018-08-09T23:57:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> For me almost all armors/parts are working, and nosee errors with DLC2 tpf..
What version of Noesis TPF script are you using?
## Post #280
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-08-12T15:49:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from fullinu
>
> TokiChan wrote:For me almost all armors/parts are working, and nosee errors with DLC2 tpf..
What version of Noesis TPF script are you using?
Latest from that topic.
Also forme good working Bloodborne textures unpacker from here [https://forum.xentax.com/viewtopic.php?f=16&t=17332](https://forum.xentax.com/viewtopic.php?f=16&t=17332)
## Post #281
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2018-08-13T10:27:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> Latest from that topic.
Also forme good working Bloodborne textures unpacker from here https://forum.xentax.com/viewtopic.php?f=16&t=17332
Are you unpacking PS4 game files or PC?
## Post #282
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-08-18T10:17:36+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from fullinu
>
> TokiChan wrote:Latest from that topic.
Also forme good working Bloodborne textures unpacker from here https://forum.xentax.com/viewtopic.php?f=16&t=17332
Are you unpacking PS4 game files or PC?

My PC game
## Post #283
- Username: Lorian Elder Prince
- Rank: n00b
- Number of posts: 12
- Joined date: Fri May 13, 2016 12:11 am
- Post datetime: 2018-08-20T17:37:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Ok so guys good news! I found the whole Forlorn set and both its weapons from the ds2 softs edition. It's also the max texture res possible available.
set ID was 6940
scythe ID was 3080
greatsword ID was 1997

Anyway here it is. It would be nice to test the max script on them.
[http://www.mediafire.com/file/b8yx90s9k ... s.zip/file](http://www.mediafire.com/file/b8yx90s9kbre8kj/Forlorn_set_High_Res.zip/file)
## Post #284
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2018-08-25T20:29:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan
>
> fullinu wrote:TokiChan wrote:Latest from that topic.
Also forme good working Bloodborne textures unpacker from here https://forum.xentax.com/viewtopic.php?f=16&t=17332
Are you unpacking PS4 game files or PC?

My PC game

This is strange.
I am using BB Texture unpacker from [this](http://forum.xentax.com/viewtopic.php?p=135673#p135673) post and TPF script from [this](http://forum.xentax.com/viewtopic.php?p=118396#p118396) post.
BB texture unpacker never working with TPF from Dark Souls III.
## Post #285
- Username: japaokiko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 05, 2018 4:13 am
- Post datetime: 2018-09-07T20:39:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

can anyone explain how to use it ?
when i try to 'run' the script e got the 'count' error.....
when i open and evaluate all, i got partial model..... 
[https://i.imgur.com/IwN7LpN.png](https://i.imgur.com/IwN7LpN.png)
what i am doing wrong ? or, there is a pack with monster + animations 3ds in somewhere? ( not find yet )

tnks
## Post #286
- Username: jonten
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 09, 2018 11:45 pm
- Post datetime: 2018-09-09T17:53:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Does anyone know where Sage's big hat is located? Cant find it, its a real hassle looking through all the bnds. Any help would be appreciated.
## Post #287
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-09-21T11:51:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from jonten
>
> Does anyone know where Sage's big hat is located? Cant find it, its a real hassle looking through all the bnds. Any help would be appreciated.
Yes, I get it
Check the number when back
## Post #288
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2018-11-05T06:56:14+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I have a problem with normal. should i change color or create a correct version how can i do?
## Post #289
- Username: gonica
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 24, 2018 3:19 am
- Post datetime: 2018-11-23T22:34:54+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Yoel of londor c2160 the skeleton does not follow the model.
## Post #290
- Username: ODoctor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 05, 2018 11:45 am
- Post datetime: 2018-12-05T03:54:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey guys,
I'm trying to get Iudex Gundyr model in fase one with the halberd if possible (or the halberd separately). But I don't know where to start, i just want to make a miniature of him to print in 3d to give to my girlfriend.

If someone could help me I would be really happy. I don't even have any idea if when i extract the model it comes in the vitruvian men pose, or i can get in other, of alter it some how. I'm really new to this and just trying to give a nice present.
## Post #291
- Username: Porvia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 05, 2018 8:13 pm
- Post datetime: 2018-12-05T13:12:54+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello all,
I'm looking for the chalice of Wolnir (the cup you touch to initiate the boss battle). However, I can't find it in the long list of file names. Does anyone know what the code for this model is? Thanks in advance.
## Post #292
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2018-12-14T18:30:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from ODoctor
>
> Hey guys,
I'm trying to get Iudex Gundyr model in fase one with the halberd if possible (or the halberd separately). But I don't know where to start, i just want to make a miniature of him to print in 3d to give to my girlfriend.

If someone could help me I would be really happy. I don't even have any idea if when i extract the model it comes in the vitruvian men pose, or i can get in other, of alter it some how. I'm really new to this and just trying to give a nice present.
[https://www.deviantart.com/tokami-fuko/ ... -663752976](https://www.deviantart.com/tokami-fuko/art/Ludex-Gundyr-663752976)
Here are full Gundyr with weapons, abyss and Firelink sword.
FBX format included
## Post #293
- Username: burningchicken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 15, 2018 11:11 pm
- Post datetime: 2018-12-20T23:09:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello guys,
I'm tying to get all weapons in Dark Souls III. 
but i have a problem with UV.
some of weapons UV doesn't fit with textures.
how can i fix it?

(this model name is WP_A_0506)
## Post #294
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2018-12-21T10:45:27+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from burningchicken
>
> Hello guys,
I'm tying to get all weapons in Dark Souls III. 
but i have a problem with UV.
some of weapons UV doesn't fit with textures.
how can i fix it?
Try 180 degrees on U.
## Post #295
- Username: burningchicken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 15, 2018 11:11 pm
- Post datetime: 2018-12-21T18:55:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Kunzt
>
> burningchicken wrote:Hello guys,
I'm tying to get all weapons in Dark Souls III. 
but i have a problem with UV.
some of weapons UV doesn't fit with textures.
how can i fix it?
Try 180 degrees on U.
I tried that first, but i think that is not the solution
## Post #296
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2018-12-21T20:57:43+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from burningchicken
>
> Kunzt wrote:burningchicken wrote:Hello guys,
I'm tying to get all weapons in Dark Souls III. 
but i have a problem with UV.
some of weapons UV doesn't fit with textures.
how can i fix it?
Try 180 degrees on U.
I tried that first, but i think that is not the solution
It works for me, but I'm not using this script, I'm using bindertool and a smd importer.
## Post #297
- Username: burningchicken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 15, 2018 11:11 pm
- Post datetime: 2018-12-22T00:23:42+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Kunzt
>
> 
It works for me, but I'm not using this script, I'm using bindertool and a smd importer.
smd importer? is that 3dsmax plugin? and can i import flv files with that?
## Post #298
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2018-12-22T12:58:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from burningchicken
>
> Kunzt wrote:
It works for me, but I'm not using this script, I'm using bindertool and a smd importer.
smd importer? is that 3dsmax plugin? and can i import flv files with that?

Yes it's a plugin (by Wunderboy) and it imports smd (a format by Valve) you can get from flver through Bindertool.
## Post #299
- Username: burningchicken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 15, 2018 11:11 pm
- Post datetime: 2018-12-23T13:46:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Kunzt
>
> burningchicken wrote:Kunzt wrote:
It works for me, but I'm not using this script, I'm using bindertool and a smd importer.
smd importer? is that 3dsmax plugin? and can i import flv files with that?

Yes it's a plugin (by Wunderboy) and it imports smd (a format by Valve) you can get from flver through Bindertool.

I don't understand what you mean.
i got flv files with bindertool.
but, smd importer seems won't import flv files.
what is the connection between smd importer and flv file?
can i export flv file to smd file with bindertool?
## Post #300
- Username: Klaus
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Mar 01, 2016 5:59 am
- Post datetime: 2018-12-23T18:58:04+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from burningchicken
>
> 
I don't understand what you mean.
i got flv files with bindertool.
but, smd importer seems won't import flv files.
what is the connection between smd importer and flv file?
can i export flv file to smd file with bindertool?
Ah yes I forgot to mention between flv and smd, I'm using the model converter by daemon1 meant for Bloodborne, working with DS3 too.
## Post #301
- Username: burningchicken
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Oct 15, 2018 11:11 pm
- Post datetime: 2018-12-24T02:19:29+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Kunzt
>
> Ah yes I forgot to mention between flv and smd, I'm using the model converter by daemon1 meant for Bloodborne, working with DS3 too.
OMG! thank you! it worked!!
## Post #302
- Username: daemius
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 6:10 am
- Post datetime: 2019-04-05T23:34:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi there, I'm trying to import a model from Sekiro for modding. 
Using the last version I found of the script([https://drive.google.com/open?id=1H_6NI ... fiXJz-6zsJ](https://drive.google.com/open?id=1H_6NIlOgDYP6Se24YEf8h3fiXJz-6zsJ)), it imports with some errors in the mesh, but there are no bones since that version was modified by op to not include them. 


Using the previous version, it apparently imports the bones ok, but there's an error when importing the meshes. Here's the pastebin file with the listener details: [https://pastebin.com/kmFB91T2](https://pastebin.com/kmFB91T2)


Here is the link for the model files: [https://drive.google.com/open?id=14YVWF ... UEa5qmYR3r](https://drive.google.com/open?id=14YVWFN3aGvtXpoOqDHPKNUUEa5qmYR3r) 
if the author or anyone could help it would be awesome, I want to modify the skinned meshes in the game.
## Post #303
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-04-06T00:31:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

You're using my script, right? Well, I can edit it, though guys here are saying, that bloodborne tool work fine for DS3 too, so you might want to check it out?
## Post #304
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-04-06T11:01:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from daemius ↑Sat Apr 06, 2019 7:34 am at Sat Apr 06, 2019 7:34 am
>
> 
Hi there, I'm trying to import a model from Sekiro for modding. 
Using the last version I found of the script(https://drive.google.com/open?id=1H_6NI ... fiXJz-6zsJ), it imports with some errors in the mesh, but there are no bones since that version was modified by op to not include them. 


Using the previous version, it apparently imports the bones ok, but there's an error when importing the meshes. Here's the pastebin file with the listener details: https://pastebin.com/kmFB91T2


Here is the link for the model files: https://drive.google.com/open?id=14YVWF ... UEa5qmYR3r 
if the author or anyone could help it would be awesome, I want to modify the skinned meshes in the game.

Use my tool from here https://forum.xentax.com/viewtopic.php? ... &start=270 or daemon tool for bloodborne, but with daemon tool you wont get all uvs correctly.
## Post #305
- Username: daemius
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 6:10 am
- Post datetime: 2019-04-06T11:56:02+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Sat Apr 06, 2019 7:01 pm at Sat Apr 06, 2019 7:01 pm
>
> 
daemius wrote: ↑Sat Apr 06, 2019 7:34 am
Hi there, I'm trying to import a model from Sekiro for modding. 
Using the last version I found of the script(https://drive.google.com/open?id=1H_6NI ... fiXJz-6zsJ), it imports with some errors in the mesh, but there are no bones since that version was modified by op to not include them. 

Using the previous version, it apparently imports the bones ok, but there's an error when importing the meshes. Here's the pastebin file with the listener details: https://pastebin.com/kmFB91T2

Here is the link for the model files: https://drive.google.com/open?id=14YVWF ... UEa5qmYR3r 
if the author or anyone could help it would be awesome, I want to modify the skinned meshes in the game.


Use my tool from here https://forum.xentax.com/viewtopic.php? ... &start=270 or daemon tool for bloodborne, but with daemon tool you wont get all uvs correctly.

Thanks, with your tools I managed to import the mesh with correct UVS using this SMD importer: [https://forum.facepunch.com/fbx/qxgb/3D ... Plugins/1/](https://forum.facepunch.com/fbx/qxgb/3DS-Max-SMD-Plugins/1/)

Do you plan to support the skeleton + skin weights import in the future? 
Also, is it possible to make the way back from SMD > .flver?
## Post #306
- Username: daemius
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 06, 2019 6:10 am
- Post datetime: 2019-04-06T12:03:26+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot ↑Sat Apr 06, 2019 8:31 am at Sat Apr 06, 2019 8:31 am
>
> 
You're using my script, right? Well, I can edit it, though guys here are saying, that bloodborne tool work fine for DS3 too, so you might want to check it out?

Hi zaramot, thanks for your reply, yes I am using your script. 
I've used @dropoff tool and imported the mesh+uvs correctly, but currently there is no skeleton+weight support like your tool has. 
Would it be possible for you to make a new version for sekiro, when you have the time?
## Post #307
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-05-10T14:59:18+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

hey i was wondering if anybody could help me. i'm new to all this and i just wanted to port some Sekiro models and textures for a personal Skyrim mod. i feel like i'm not using Noesis right/haven't installed it correctly or i'm missing code or just not extracting correctly. the models show in Noesis but i get an error warning regardless of whether the files are in .dds or .tpf . I've got the Dark Souls III TPF python plugin so i'm really lost can anybody help?

PS. for the mod i am using an already existing Sekiro mod that changes the armor texture and this is literally the first time I've never commented on a public forum so apologies if this is thread hijacking
[issue.jpg](https://xentaxbackup.github.io/file/16213_issue.jpg)
## Post #308
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-05-11T23:10:41+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from EDXZ23 ↑Fri May 10, 2019 10:59 pm at Fri May 10, 2019 10:59 pm
>
> 
hey i was wondering if anybody could help me. i'm new to all this and i just wanted to port some Sekiro models and textures for a personal Skyrim mod. i feel like i'm not using Noesis right/haven't installed it correctly or i'm missing code or just not extracting correctly. the models show in Noesis but i get an error warning regardless of whether the files are in .dds or .tpf . I've got the Dark Souls III TPF python plugin so i'm really lost can anybody help?

PS. for the mod i am using an already existing Sekiro mod that changes the armor texture and this is literally the first time I've never commented on a public forum so apologies if this is thread hijacking

Use yabber for tpf https://www.nexusmods.com/sekiro/mods/42
## Post #309
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-05-12T03:17:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Sun May 12, 2019 7:10 am at Sun May 12, 2019 7:10 am
>
> 
EDXZ23 wrote: ↑Fri May 10, 2019 10:59 pm
hey i was wondering if anybody could help me. i'm new to all this and i just wanted to port some Sekiro models and textures for a personal Skyrim mod. i feel like i'm not using Noesis right/haven't installed it correctly or i'm missing code or just not extracting correctly. the models show in Noesis but i get an error warning regardless of whether the files are in .dds or .tpf . I've got the Dark Souls III TPF python plugin so i'm really lost can anybody help?

PS. for the mod i am using an already existing Sekiro mod that changes the armor texture and this is literally the first time I've never commented on a public forum so apologies if this is thread hijacking


Use yabber for tpf https://www.nexusmods.com/sekiro/mods/42

hey thanks for getting back to me, I've used yabber before and bellow was the result. any idea as to why?
[e.jpg](https://xentaxbackup.github.io/file/16234_e.jpg)
## Post #310
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-05-12T11:18:53+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from EDXZ23 ↑Sun May 12, 2019 11:17 am at Sun May 12, 2019 11:17 am
>
> 
dropoff wrote: ↑Sun May 12, 2019 7:10 am
EDXZ23 wrote: ↑Fri May 10, 2019 10:59 pm
hey i was wondering if anybody could help me. i'm new to all this and i just wanted to port some Sekiro models and textures for a personal Skyrim mod. i feel like i'm not using Noesis right/haven't installed it correctly or i'm missing code or just not extracting correctly. the models show in Noesis but i get an error warning regardless of whether the files are in .dds or .tpf . I've got the Dark Souls III TPF python plugin so i'm really lost can anybody help?

PS. for the mod i am using an already existing Sekiro mod that changes the armor texture and this is literally the first time I've never commented on a public forum so apologies if this is thread hijacking


Use yabber for tpf https://www.nexusmods.com/sekiro/mods/42


hey thanks for getting back to me, I've used yabber before and bellow was the result. any idea as to why?
Uh, noesis should be able to open them, maybe you have old version.
## Post #311
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-05-12T17:50:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Sun May 12, 2019 7:18 pm at Sun May 12, 2019 7:18 pm
>
> 
EDXZ23 wrote: ↑Sun May 12, 2019 11:17 am
dropoff wrote: ↑Sun May 12, 2019 7:10 am


Use yabber for tpf https://www.nexusmods.com/sekiro/mods/42


hey thanks for getting back to me, I've used yabber before and bellow was the result. any idea as to why?

Uh, noesis should be able to open them, maybe you have old version.

Worked!!! thanks bro!!! didnt realise that i an old version, i cant however get the textures to show on the model
## Post #312
- Username: devilblades
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Nov 24, 2015 11:56 pm
- Post datetime: 2019-05-15T00:06:39+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello, I was wondering if anyone has been able to get the Firelink armor set? I would like to cosplay this armor, and this would be an awesome starting point.
## Post #313
- Username: zdkliu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 30, 2019 10:17 pm
- Post datetime: 2019-05-30T14:19:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

This must be learned.
## Post #314
- Username: iBott777
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 01, 2019 4:06 pm
- Post datetime: 2019-06-01T08:12:14+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Cool! Thanks
## Post #315
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-07-09T11:39:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey ya!
Can someone give me a cool tutorial how to make retexture mod for DS3 dragonoid? I made new textures, but can't find the ways how to make it work.

(Or may be add dragonoid as playable character in Sekiro? Hahaha)
## Post #316
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-07-09T11:41:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Also - UV pairs with unused AM_M_2000 is broken. I try different tools and fix it, but when I collapse all modifiers in 3ds max it made broken against.
## Post #317
- Username: qq531620267
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 04, 2019 1:27 pm
- Post datetime: 2019-07-12T01:51:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot ↑Sun Nov 26, 2017 9:20 pm at Sun Nov 26, 2017 9:20 pm
>
> 
My friend and I did some tests with Dark Souls 3, and I updated script. So, this version should work better for Dark Souls 3. Anyone could try this one out, if interested xD

hello,it's can't be work.thx.
## Post #318
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-07-19T10:06:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello against!
1) Do someone know number of Iron Dragonslayer armor for main character in DS3 parts folder? I check it all, but can't find, maybe I skip it  
Nevermind, I found Dragonslayer armour in reunpacked DLC (bindertool no unpack it, I use Yabber)

2) Do someone know where find good tutorial for creating retexture mods for DS3?
## Post #319
- Username: pok8573
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 03, 2018 1:19 pm
- Post datetime: 2019-08-05T04:02:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi,
I have one question.
I tried using various scripts, but there is a uv error in the ds2 model.
Do you know how to fix this?
## Post #320
- Username: korribanscion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 07, 2019 9:56 am
- Post datetime: 2019-08-07T02:00:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Alright, request time, since I have no idea how everyone is doing this:

Anyone have model files for:

Corvian Knight (armored rapier version)
Farron Follower
Milllwood Knight
Giant Fly

Harald Legion Knight
Angel
White-faced Locust
Murkman

I don't need UVs, textures, skeletons or weights, just the model files (.obj or whatever is fine)
## Post #321
- Username: UncleBorubon
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 07, 2016 7:47 am
- Post datetime: 2019-08-26T15:48:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Does anyone have the Faraam armor set model?
## Post #322
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-11-09T17:27:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs
## Post #323
- Username: Nahsch
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 10, 2019 3:01 am
- Post datetime: 2019-11-09T19:09:41+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Where is the script?
## Post #324
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-11-09T20:18:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Sun Nov 10, 2019 1:27 am at Sun Nov 10, 2019 1:27 am
>
> 
Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs

For Sekiro? Anything that is hosted on Xentax is old af.
## Post #325
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-11-11T07:27:52+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from fullinu ↑Sun Nov 10, 2019 4:18 am at Sun Nov 10, 2019 4:18 am
>
> 
TokiChan wrote: ↑Sun Nov 10, 2019 1:27 am
Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs


For Sekiro? Anything that is hosted on Xentax is old af.

So, I found an interesting way for Sekiro and DS3 using Unity, but it no working after I try to open anything from that...
And the creator of that tools (I mean for Unity tools) doesn't make any tutorial..
## Post #326
- Username: isshininu
- Rank: advanced
- Number of posts: 43
- Joined date: Fri May 13, 2016 6:56 pm
- Post datetime: 2019-11-11T12:16:49+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Mon Nov 11, 2019 3:27 pm at Mon Nov 11, 2019 3:27 pm
>
> 
So, I found an interesting way for Sekiro and DS3 using Unity, but it no working after I try to open anything from that...
And the creator of that tools (I mean for Unity tools) doesn't make any tutorial..

Right approach. You just need to export required objects using FBX Export plugin from Unty Store.
## Post #327
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2019-11-13T07:45:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Mon Nov 11, 2019 3:27 pm at Mon Nov 11, 2019 3:27 pm
>
> 
fullinu wrote: ↑Sun Nov 10, 2019 4:18 am
TokiChan wrote: ↑Sun Nov 10, 2019 1:27 am
Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs


For Sekiro? Anything that is hosted on Xentax is old af.


So, I found an interesting way for Sekiro and DS3 using Unity, but it no working after I try to open anything from that...
And the creator of that tools (I mean for Unity tools) doesn't make any tutorial..

Here are some Tools that i use to view models from Sekiro but i currently dont have the time to make something with the models.
You can also join the Sekiro/DS/BB modding discord [https://discordapp.com/invite/mT2JJjx](https://discordapp.com/invite/mT2JJjx)

You can also view the models/edit bones/export it without unity you just need the FLVER Viewer [https://github.com/asasasasasbc/FLVER_Editor](https://github.com/asasasasasbc/FLVER_Editor) from ForsakenSilver its a quite nice tool.

or you can use the BB Model converter [viewtopic.php?f=16&t=17332](https://forum.xentax.com/viewtopic.php?f=16&t=17332) from deamon1 to convert .flver files to another format.

UXM to unpack The game archives: [https://www.nexusmods.com/sekiro/mods/26](https://www.nexusmods.com/sekiro/mods/26)

and Yabber to unpack the dcx/tpf... archives: [https://www.nexusmods.com/sekiro/mods/42](https://www.nexusmods.com/sekiro/mods/42)

and a Tutorial for changing the player model in Sekiro: [https://www.youtube.com/watch?v=KcXyABspyMM](https://www.youtube.com/watch?v=KcXyABspyMM) i think you can look what hes doing and see if that helps you weight and UV Problems.

I hope it this post with the tools and the discord helps anybody that comes in this thread in hope to find something useful information.
## Post #328
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-11-14T12:48:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Sun Nov 10, 2019 1:27 am at Sun Nov 10, 2019 1:27 am
>
> 
Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs

Dstools is best way atm (use fbx export plugin from plugin manager, not from store), and it works for all soulsgames except DeS. Also it have instruction on github page. And everything related to soulsgames modding is in discord server which is posted above, model formats are reversed for souls games for a long time.
## Post #329
- Username: meruna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 14, 2019 10:15 pm
- Post datetime: 2019-11-14T14:20:37+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi guys, could anyone help me export the Yuria of Londor (or Black Set) from the game?

Edit: I figured it out myself!
## Post #330
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-11-22T19:14:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Shiroleinchen ↑Wed Nov 13, 2019 3:45 pm at Wed Nov 13, 2019 3:45 pm
>
> 
TokiChan wrote: ↑Mon Nov 11, 2019 3:27 pm
fullinu wrote: ↑Sun Nov 10, 2019 4:18 am


For Sekiro? Anything that is hosted on Xentax is old af.


So, I found an interesting way for Sekiro and DS3 using Unity, but it no working after I try to open anything from that...
And the creator of that tools (I mean for Unity tools) doesn't make any tutorial..


Here are some Tools that i use to view models from Sekiro but i currently dont have the time to make something with the models.
You can also join the Sekiro/DS/BB modding discord https://discordapp.com/invite/mT2JJjx

You can also view the models/edit bones/export it without unity you just need the FLVER Viewer https://github.com/asasasasasbc/FLVER_Editor from ForsakenSilver its a quite nice tool.

or you can use the BB Model converter viewtopic.php?f=16&t=17332 from deamon1 to convert .flver files to another format.

UXM to unpack The game archives: https://www.nexusmods.com/sekiro/mods/26

and Yabber to unpack the dcx/tpf... archives: https://www.nexusmods.com/sekiro/mods/42

and a Tutorial for changing the player model in Sekiro: https://www.youtube.com/watch?v=KcXyABspyMM i think you can look what hes doing and see if that helps you weight and UV Problems.

I hope it this post with the tools and the discord helps anybody that comes in this thread in hope to find something useful information.

I see that tutorial of character changing, after that I start to try myself.

I unpack all from chr folder with UXM and Yabber, then I try BB tools, but it no correct with some bosses (for example, Divine dragon and Sekiro weapons no have weights and some UVs is broken)
Then I try to use DStools with Unity (I know abot export function, this is not first my experience with Unity)
But when I try steps like "open the latest DS tools and this must open new window" anything has no happen.
Also it sometime crush my system

Thanks for Flver editor - I'll try also that way
## Post #331
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-11-24T12:40:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Thu Nov 14, 2019 8:48 pm at Thu Nov 14, 2019 8:48 pm
>
> 
TokiChan wrote: ↑Sun Nov 10, 2019 1:27 am
Hey, guys!
DO someone know a better way for extracting Sekiro?
I still can't get alot of this with correct rigging using DS3 script and Bloodborne tools
Always I get broken weight and some broken UVs


Dstools is best way atm (use fbx export plugin from plugin manager, not from store), and it works for all soulsgames except DeS. Also it have instruction on github page. And everything related to soulsgames modding is in discord server which is posted above, model formats are reversed for souls games for a long time.

I know about exprt in Unity. I read intro on Github.
But it still no work. I use latest Unity, but when I try open DStools (when it must open new windows for import files) I no have it window and my system is crash sometime.

FLver editor export only mesh without bones.
## Post #332
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-11-29T00:44:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Sun Nov 24, 2019 8:40 pm at Sun Nov 24, 2019 8:40 pm
>
> 
I know about exprt in Unity. I read intro on Github.
But it still no work. I use latest Unity, but when I try open DStools (when it must open new windows for import files) I no have it window and my system is crash sometime.

Because you have to use unity 2019.1, not latest.
## Post #333
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-12-04T16:54:07+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Fri Nov 29, 2019 8:44 am at Fri Nov 29, 2019 8:44 am
>
> 
TokiChan wrote: ↑Sun Nov 24, 2019 8:40 pm
I know about exprt in Unity. I read intro on Github.
But it still no work. I use latest Unity, but when I try open DStools (when it must open new windows for import files) I no have it window and my system is crash sometime.


Because you have to use unity 2019.1, not latest.

I use Unity 2019.2.11f1 (64-bit)
## Post #334
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-12-07T14:54:25+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Thu Dec 05, 2019 12:54 am at Thu Dec 05, 2019 12:54 am
>
> 
dropoff wrote: ↑Fri Nov 29, 2019 8:44 am
TokiChan wrote: ↑Sun Nov 24, 2019 8:40 pm
I know about exprt in Unity. I read intro on Github.
But it still no work. I use latest Unity, but when I try open DStools (when it must open new windows for import files) I no have it window and my system is crash sometime.


Because you have to use unity 2019.1, not latest.


I use Unity 2019.2.11f1 (64-bit)

Well dont do that, dstools doesnt work with latest unity, use one i said.
## Post #335
- Username: ickey
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Dec 25, 2019 12:04 am
- Post datetime: 2019-12-24T19:53:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello, I know it might be a little bit late but, does anybody have Yhorm's (c5260) model? If so, could you please upload a download link? 

Thank you!
## Post #336
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-12-26T14:14:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Sat Dec 07, 2019 10:54 pm at Sat Dec 07, 2019 10:54 pm
>
> 
Well dont do that, dstools doesnt work with latest unity, use one i said.

So, I try unity 2019.1.5 it give me eternal loading when I try update hd-something-thing

But maybe someone uploads or make BB tool adopt to Sekiro and Ds2?
Because I still wait for ds2 script with correct UV and bones
And correct UV and weight for Sekiro
## Post #337
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-12-27T13:13:56+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Thu Dec 26, 2019 10:14 pm at Thu Dec 26, 2019 10:14 pm
>
> 
But maybe someone uploads or make BB tool adopt to Sekiro and Ds2?
Because I still wait for ds2 script with correct UV and bones
And correct UV and weight for Sekiro
Im not here most of times and cant answer, also flver formats for all souls games are mapped for a long time in modding discord server, you can ask here about dstools and things: [https://discord.gg/mT2JJjx](https://discord.gg/mT2JJjx). Bruh we can even import custom models into any souls flver. And dstools is best way to export models right now, also most of souls games tools posted here are outdated.
## Post #338
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2019-12-29T14:49:07+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Fri Dec 27, 2019 9:13 pm at Fri Dec 27, 2019 9:13 pm
>
> 
Im not here most of times and cant answer, also flver formats for all souls games are mapped for a long time in modding discord server, you can ask here about dstools and things: https://discord.gg/mT2JJjx. Bruh we can even import custom models into any souls flver. And dstools is best way to export models right now, also most of souls games tools posted here are outdated.

I know about input some models to game (I make a mod for Sekiro using flver editor)
And I check discord before asking here - anything I try by instructions gives me nothing.
I think this method is just not for me.
 And also use bb methods not give me correct scenes - all game maps have a different and so parted fragments like a mosaic. I must find and convert alot parts like windows, walls and grounds and try to collect it use in-game screenshots.
## Post #339
- Username: Mobs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 03, 2020 12:20 am
- Post datetime: 2020-01-02T16:26:46+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Howdy all, sorry to just bust in, but I've been trying to work my way through extracting models from DS3 with Flver, and I found this. Unfortunately all I've got is Blender, no 3dsMax :/ . I was wondering if anyone could extract me a model, its textures, and bones? I can do all the weight painting and what-not myself. The model I'm looking for is the Elder Ghru (c3120).
## Post #340
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-01-02T23:10:41+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from Mobs ↑Fri Jan 03, 2020 12:26 am at Fri Jan 03, 2020 12:26 am
>
> 
Howdy all, sorry to just bust in, but I've been trying to work my way through extracting models from DS3 with Flver, and I found this. Unfortunately all I've got is Blender, no 3dsMax :/ . I was wondering if anyone could extract me a model, its textures, and bones? I can do all the weight painting and what-not myself. The model I'm looking for is the Elder Ghru (c3120).
I can get almost all character sets, weapons and enemies
So, which one you need?
## Post #341
- Username: Mobs
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jan 03, 2020 12:20 am
- Post datetime: 2020-01-14T19:37:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Fri Jan 03, 2020 7:10 am at Fri Jan 03, 2020 7:10 am
>
> 
Mobs wrote: ↑Fri Jan 03, 2020 12:26 am
Howdy all, sorry to just bust in, but I've been trying to work my way through extracting models from DS3 with Flver, and I found this. Unfortunately all I've got is Blender, no 3dsMax :/ . I was wondering if anyone could extract me a model, its textures, and bones? I can do all the weight painting and what-not myself. The model I'm looking for is the Elder Ghru (c3120).

I can get almost all character sets, weapons and enemies
So, which one you need?

Sorry for late, late response, got caught up in stuff. I just need the Elder Ghru model, bones, textures and all (enemy id is c3120). That's about it.
## Post #342
- Username: Zalor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 17, 2018 8:56 am
- Post datetime: 2020-02-07T15:41:00+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Fri Jan 03, 2020 7:10 am at Fri Jan 03, 2020 7:10 am
>
> 
I can get almost all character sets, weapons and enemies
So, which one you need?
Hey Toki, it's cool to see you on here because I've probably visited your Deviantart gallery about a hundred times, because you seem to upload the most interesting game models from Dark Souls/Bloodborne.
Is there any way you could get me the Pilgrim models, such as Yoel of Londor (c2160)?  Nobody has really ripped those or uploaded them anywhere so far that I can find.

I tried to rip him a long time ago but I'm pretty sure it came out wrong, as the textures were entirely unusable.  I've been teaching myself Blender, and I'd love to take another crack at him.
## Post #343
- Username: pasunna
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 30, 2020 5:15 pm
- Post datetime: 2020-03-30T09:22:45+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

hi... is it hard to port mod model from Sekiro to ds3

[https://www.nexusmods.com/sekiro/mods/403?tab=files](https://www.nexusmods.com/sekiro/mods/403?tab=files)
I like these mod from sekiro

but as I check out
the parts mod is in the difference number of file
so I wonder is it hard or even imposible to port from these file
and need to rework from the original model instead
I never do any 3d modding 
just do some skin from other game
so if it too hard I will stop here

thank you
## Post #344
- Username: ZFPInTheAir
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Feb 24, 2020 2:27 am
- Post datetime: 2020-08-19T10:25:32+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

is getting the areas possible? i wanna rip Firelink if its doable
## Post #345
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-10-23T15:38:13+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I still wanna have tools like this script or BB tools for DS2. 
Because actually DS2 PC script gets no bones and lost some UVs. I can't use the Unity way because this is hard for my notebook.
But I create some fan project based Souls series and then I need DS2 sets and enemies. 
Yeah, I can add bones by myself, but making 100500+ parts for different assets is making me hungry. I also fix the DS3 extractions for better working so I no have time for rigging DS2.

And please update Sekiro extractor - it lost bones weights for bosses
## Post #346
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2020-12-01T08:58:15+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Fri Oct 23, 2020 11:38 pm at Fri Oct 23, 2020 11:38 pm
>
> 
I still wanna have tools like this script or BB tools for DS2. 
Because actually DS2 PC script gets no bones and lost some UVs. I can't use the Unity way because this is hard for my notebook.
But I create some fan project based Souls series and then I need DS2 sets and enemies. 
Yeah, I can add bones by myself, but making 100500+ parts for different assets is making me hungry. I also fix the DS3 extractions for better working so I no have time for rigging DS2.

And please update Sekiro extractor - it lost bones weights for bosses

Just join modding discord server and follow our progress here, i posted tool that can export ds2 models with skeleton long ago somewhere in chat, also dstools is best way to export maps anyway atm. And it also loads placement of meshes and stuff.
https://discord.gg/mT2JJjx
## Post #347
- Username: BebopxRocksteady
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 04, 2020 6:26 am
- Post datetime: 2020-12-31T20:31:23+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

So Dark souls 2 still Not available ??
## Post #348
- Username: nahui
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 01, 2021 6:47 pm
- Post datetime: 2021-01-01T10:50:10+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hello. I want to make animations in Blender by using DS3 models such as weapons, armor and maps. How do I extract these?
## Post #349
- Username: 希劳汉
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 22, 2021 3:14 pm
- Post datetime: 2021-01-22T07:24:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

nice
## Post #350
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2021-02-05T17:14:03+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Tue Dec 01, 2020 4:58 pm at Tue Dec 01, 2020 4:58 pm
>
> 
TokiChan wrote: ↑Fri Oct 23, 2020 11:38 pm
I still wanna have tools like this script or BB tools for DS2. 
Because actually DS2 PC script gets no bones and lost some UVs. I can't use the Unity way because this is hard for my notebook.
But I create some fan project based Souls series and then I need DS2 sets and enemies. 
Yeah, I can add bones by myself, but making 100500+ parts for different assets is making me hungry. I also fix the DS3 extractions for better working so I no have time for rigging DS2.

And please update Sekiro extractor - it lost bones weights for bosses


Just join modding discord server and follow our progress here, i posted tool that can export ds2 models with skeleton long ago somewhere in chat, also dstools is best way to export maps anyway atm. And it also loads placement of meshes and stuff.
https://discord.gg/mT2JJjx

I try, but browser's discort not working (bug with birthday - I can't put anuthing or select). It say "Invite as unavailable"
Can you send it to me again or send tools privatelly?
## Post #351
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2021-02-05T19:36:12+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from TokiChan ↑Sat Feb 06, 2021 1:14 am at Sat Feb 06, 2021 1:14 am
>
> 
dropoff wrote: ↑Tue Dec 01, 2020 4:58 pm
TokiChan wrote: ↑Fri Oct 23, 2020 11:38 pm
I still wanna have tools like this script or BB tools for DS2. 
Because actually DS2 PC script gets no bones and lost some UVs. I can't use the Unity way because this is hard for my notebook.
But I create some fan project based Souls series and then I need DS2 sets and enemies. 
Yeah, I can add bones by myself, but making 100500+ parts for different assets is making me hungry. I also fix the DS3 extractions for better working so I no have time for rigging DS2.

And please update Sekiro extractor - it lost bones weights for bosses


Just join modding discord server and follow our progress here, i posted tool that can export ds2 models with skeleton long ago somewhere in chat, also dstools is best way to export maps anyway atm. And it also loads placement of meshes and stuff.
https://discord.gg/mT2JJjx


I try, but browser's discort not working (bug with birthday - I can't put anuthing or select). It say "Invite as unavailable"
Can you send it to me again or send tools privatelly?
That link is permanent, it will never expire. And im using browser discord just fine.
## Post #352
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2021-02-07T15:55:30+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from dropoff ↑Sat Feb 06, 2021 3:36 am at Sat Feb 06, 2021 3:36 am
>
> 
That link is permanent, it will never expire. And im using browser discord just fine.
Okay, I'm here now.
Looks too easy to find needed tools
## Post #353
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2021-02-10T16:50:58+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I found blender tools, but with DSIISotFS it gives me that
Idk what version of blender or bindertool must be used for that. But I against spending more time because tool author does not write it in Readme
UPD: the same problem with all souls games, I trying ds1-2-3, always like this error
Uses latest blender 2.91...



0.jpg (192.36 KiB) Viewed 297 times
## Post #354
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2021-02-11T14:22:59+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Ok, I get it working for import-export and more UVs is rights. But DS2 bosses still unrigged. It's no problem (but a waste of time) for basig rigg, but with faces (i mean dragon faces or Iron king) is problem
## Post #355
- Username: hiaki
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 17, 2021 1:57 am
- Post datetime: 2021-02-16T17:59:20+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hi! i know it´s been a while since someone ask on this topic but someone can get me the dragonslayer armor set and the dragonscale armor set ?

I think the codes are 5700 for dragonscale and c3160 for dragonslayer
## Post #356
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2021-02-20T21:01:14+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I think I found young Gwin... Or his Firstborn aka Nameless king XD
It's Dark souls 2 files 



1111.JPG (106.13 KiB) Viewed 271 times
## Post #357
- Username: andreyu144
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 02, 2021 10:57 am
- Post datetime: 2021-09-02T04:31:48+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

I am sorry for an idiot like me being here, but can anyone guide me to how to export dark souls model in blender? I managed to export smd files alone using the programs above and others, but after that it just gives me a model without texture, can anyone help me and guide me by baby steps?
## Post #358
- Username: AltoRoark
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 09, 2018 11:26 am
- Post datetime: 2022-01-05T20:16:23+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Hey, guys! Since I'm a console player and can't really rip models, would anyone mind posting the assets of Unbreakable Patches from Dark Souls 3?

Just the texture images will be fine. All his armor sets would be appreciated.
## Post #359
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-02-16T13:36:17+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from AltoRoark ↑Thu Jan 06, 2022 4:16 am at Thu Jan 06, 2022 4:16 am
>
> 
Hey, guys! Since I'm a console player and can't really rip models, would anyone mind posting the assets of Unbreakable Patches from Dark Souls 3?

Just the texture images will be fine. All his armor sets would be appreciated.

Getting characters models from files is impossible, I can find on;y his set and try to rip face from ninjaripper. But with ninja it has been deformed and lost UVs.
## Post #360
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2022-03-06T06:07:55+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from zaramot ↑Tue May 03, 2016 2:17 am at Tue May 03, 2016 2:17 am
>
> 
Don't worry I know that   I'm working in order to solve any issues, though you can try this script, latest one I made. It will get you bones and weights+fixed uv's. I'm sure errors will be present, so fee free to report them here.

Hello zaramot. I'm sorry to contact you suddenly. Your DS3 max script is really perfect. I was able to import DS3 flever file in perfect condition without distortion of the bones. You may know that 'Elden Ring' was recently released. I tried to import new ER flever file with your script, but it didn't work.

I know that the structure of fromsoftware game is mostly similar. If you don't mind, could you revise this DS3 script and provide a new ER script for this game?
## Post #361
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-07-19T13:42:40+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from uroborostestsubject ↑Sun Mar 06, 2022 2:07 pm at Sun Mar 06, 2022 2:07 pm
>
> 
Hello zaramot. I'm sorry to contact you suddenly. Your DS3 max script is really perfect. I was able to import DS3 flever file in perfect condition without distortion of the bones. You may know that 'Elden Ring' was recently released. I tried to import new ER flever file with your script, but it didn't work.

I know that the structure of fromsoftware game is mostly similar. If you don't mind, could you revise this DS3 script and provide a new ER script for this game?

Dude, try this [viewtopic.php?f=16&p=185645#p185645](https://forum.xentax.com/viewtopic.php?f=16&p=185645#p185645)
Bones and most of UV is good
But I still don't know, how to extract fur correctly
## Post #362
- Username: siyamint
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 18, 2017 2:45 am
- Post datetime: 2022-08-18T16:54:57+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Skeleton change name when import 3dsmax
It is different from the skeleton name in skeleton.hkx
If the ds3 model is imported using this script, this problem does not occur.
Can someone please fix this script to work with eldenring as well?
## Post #363
- Username: testimesti
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 30, 2022 11:28 pm
- Post datetime: 2023-01-07T11:13:29+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

So I managed to import some models from ELDEN RING by converting the skeleton from Havok 2018 to Havok 2014 but some models give an error where the script calculates the vertex offset.I attached an image with the error.
[Error.png](https://xentaxbackup.github.io/file/23269_Error.png)
## Post #364
- Username: siyamint
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 18, 2017 2:45 am
- Post datetime: 2023-01-27T23:18:44+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from testimesti ↑Sat Jan 07, 2023 7:13 pm at Sat Jan 07, 2023 7:13 pm
>
> 
So I managed to import some models from ELDEN RING by converting the skeleton from Havok 2018 to Havok 2014 but some models give an error where the script calculates the vertex offset.I attached an image with the error.

how to change version?
## Post #365
- Username: gcldberry
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 09, 2023 6:51 pm
- Post datetime: 2023-05-09T11:02:28+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

Extremely late to the party but I'm a console player and can't really grab models/textures myself, would anyone mind posting just the textures of the Herald Armor - Chest from Dark Souls 3?

I was really wanting to do my Ashen One cosplay but I’m having a hard time getting the exact design of the embroidery on the tunic. Thank you!
## Post #366
- Username: msquidoo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 26, 2021 2:06 pm
- Post datetime: 2023-05-11T04:04:09+00:00
- Post Title: Re: [PC] Dark Souls III model import maxscript

> Reply from testimesti ↑Sat Jan 07, 2023 7:13 pm at Sat Jan 07, 2023 7:13 pm
>
> 
So I managed to import some models from ELDEN RING by converting the skeleton from Havok 2018 to Havok 2014 but some models give an error where the script calculates the vertex offset.I attached an image with the error.

how did you do this? sorry if im late but any help would be appreciated
