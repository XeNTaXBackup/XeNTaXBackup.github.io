## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-07T13:37:51+00:00
- Post Title: Hitman 1 models

Getting models from the very first hitman was not very easy. So many things were done completely different in 2000 than today. I will probably make a new tutorial with this.

To unpack game level you will need these files: 
- Pack.SPK - level package
- PackRepeat.DXT - textures descriptions for this level
- Repeat.DXT - all textures package, located in game root

Put these files into the folder with a tool and run it. If one of DXT files will be missing, only models will be unpacked, no textures.

All objects are packed in an tree with links to textures, UVs, skeletons, and all the other model properties. So there's no other way to unpack them other than create the full tree. There will be many files and folders, so full directory/name length may exceed the limit. In this case, place files into short named directory, like "C:\hitman"


[Hitman1tool.rar](https://xentaxbackup.github.io/file/12266_Hitman1tool.rar)
## Post #2
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-09T10:27:25+00:00
- Post Title: Hitman 1 models

Greatly appreciate! I have been waiting this for years.
## Post #3
- Username: hhchunter
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Sep 08, 2015 4:51 pm
- Post datetime: 2017-01-11T19:21:58+00:00
- Post Title: Hitman 1 models

ha, nice!

How many poly's is the C47 model?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-11T19:30:41+00:00
- Post Title: Hitman 1 models

His main model (with two ties) has 1172.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-11T19:42:16+00:00
- Post Title: Hitman 1 models

Whole mesh is double faced. So half of it I suppose.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-12T15:14:45+00:00
- Post Title: Hitman 1 models

> Reply from Tosyk
>
> Whole mesh is double faced. So half of it I suppose.

Well, mesh is PARTIALLY double faced. So its somewhere around 700 or 900 polys.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-15T20:29:26+00:00
- Post Title: Hitman 1 models

Still need more testing. These modern technologies...
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-22T18:24:41+00:00
- Post Title: Hitman 1 models

Tool published.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-01-22T18:51:21+00:00
- Post Title: Hitman 1 models

> Reply from daemon1
>
> Tool published.great work on the formats. really appreciate for this!
## Post #10
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-01-22T19:43:22+00:00
- Post Title: Hitman 1 models

> Reply from daemon1
>
> Tool published.
That's impressive, but how does the game handle face animations when there's a bone only for head?
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-01-22T20:20:15+00:00
- Post Title: Hitman 1 models

> Reply from Nightstalkery
>
> That's impressive, but how does the game handle face animations when there's a bone only for head?

They are done with morphs.
## Post #12
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-02-24T14:11:44+00:00
- Post Title: Hitman 1 models

Thanks, but what about for .ANM, .PAL and .WAV files?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-25T06:36:12+00:00
- Post Title: Hitman 1 models

> Reply from AnonBaiter
>
> Thanks, but what about for .ANM, .PAL and .WAV files?

anm - animations
pal - paletted textures, the same as dds
wav- sounds
## Post #14
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-03-12T14:06:34+00:00
- Post Title: Hitman 1 models

The effort spent on this tool must be cosmic. There're some problems with it however. UVs usually turn out to be flipped vertically, but that's easy to fix. More problematic are .smds which aren't rigged to any bone, and import broken as the result. Could you take a chance at fixing it? 

That's Beretta92_Slide.smd located in Items/GunBeretta92
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-12T14:37:57+00:00
- Post Title: Hitman 1 models

> Reply from Nightstalkery
>
> The effort spent on this tool must be cosmic.
...
That's Beretta92_Slide.smd located in Items/GunBeretta92

Yes, I know those are broken. Those had additional weird table in the data, needed to be researched. However, I've spent so much time on this ancient game, so probably no, or much later.
## Post #16
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-03-17T04:57:03+00:00
- Post Title: Re: Hitman 1 models

> Reply from daemon1
>
> Nightstalkery wrote:The effort spent on this tool must be cosmic.
...
That's Beretta92_Slide.smd located in Items/GunBeretta92

Yes, I know those are broken. Those had additional weird table in the data, needed to be researched. However, I've spent so much time on this ancient game, so probably no, or much later.
That's a real shame, hope you manage to come up with something to fix that problem and also missing UVs on some models. By the way, do you have any plans for animation research for future extracting?
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-17T15:18:51+00:00
- Post Title: Re: Hitman 1 models

> Reply from Nightstalkery
>
> hope you manage to come up with something to fix that problem and also missing UVs on some models. By the way, do you have any plans for animation research for future extracting?

Animations - no, no plans on them.
## Post #18
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-03-18T04:02:58+00:00
- Post Title: Re: Hitman 1 models

Hate to bother you once again, but what could be the reason that not all the models unpack? Unpacking C3_1_Laptop.zip doesn't extract Weapons folder with high-res guns. The folder name for files extracting is 1 letter short and there're no Packs missing needed for unpacking.
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-18T05:19:01+00:00
- Post Title: Re: Hitman 1 models

> Reply from Nightstalkery
>
> Hate to bother you once again, but what could be the reason that not all the models unpack? Unpacking C3_1_Laptop.zip doesn't extract Weapons folder with high-res guns. The folder name for files extracting is 1 letter short and there're no Packs missing needed for unpacking.

There are no weapons folder in this file. There are no high-res guns.
## Post #20
- Username: Nightstalkery
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Aug 17, 2014 7:14 pm
- Post datetime: 2017-03-18T07:32:27+00:00
- Post Title: Re: Hitman 1 models

> Reply from daemon1
>
> Nightstalkery wrote:Hate to bother you once again, but what could be the reason that not all the models unpack? Unpacking C3_1_Laptop.zip doesn't extract Weapons folder with high-res guns. The folder name for files extracting is 1 letter short and there're no Packs missing needed for unpacking.

There are no weapons folder in this file. There are no high-res guns.
Oh, sorry for inconveniences then. I just didn't find some high-res weapons such as Oyabun knife, kitchen knife and Luger in other laptop archives so I assumed something was wrong with the tool itself.
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-03-18T08:13:00+00:00
- Post Title: Re: Hitman 1 models

> Reply from Nightstalkery
>
> Oh, sorry for inconveniences then. I just didn't find some high-res weapons such as Oyabun knife, kitchen knife and Luger in other laptop archives so I assumed something was wrong with the tool itself.

They must be somewhere else. The tool must unpack ALL models with more than 8 vertices. Because there are too many level parts having like 4 or 8 vertices I skipped them to save hard drive life.

I can't believe your high-res weapons have only 8 vertices in their models.

Also if there would be any problems unpacking, the tool should stop and give you error message.
## Post #22
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-04-26T18:17:41+00:00
- Post Title: Re: Hitman 1 models

You should try silent assassin next!
## Post #23
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-04-26T20:01:34+00:00
- Post Title: Re: Hitman 1 models

> Reply from Reddance
>
> You should try silent assassin next!

I already did them all, hitmans
## Post #24
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2017-04-28T01:36:41+00:00
- Post Title: Re: Hitman 1 models

> Reply from daemon1
>
> Reddance wrote:You should try silent assassin next! 

I already did them all, hitmans

Where's the tools for em then son?
## Post #25
- Username: Gelwe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 2:41 am
- Post datetime: 2019-02-26T15:54:22+00:00
- Post Title: Re: Hitman 1 models

There is a way to pack the modified files?
I want to make a "new" Repeat.DXT file.
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-03-01T18:16:15+00:00
- Post Title: Re: Hitman 1 models

its not supported
## Post #27
- Username: Gelwe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 31, 2019 2:41 am
- Post datetime: 2019-03-01T18:22:03+00:00
- Post Title: Re: Hitman 1 models

I hoped to modify this, but I will be still trying to do this. 
Thanks for this program anyway
## Post #28
- Username: BlaireVoltaire
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 26, 2021 1:03 pm
- Post datetime: 2021-02-26T05:08:15+00:00
- Post Title: Re: Hitman 1 models

> Reply from daemon1 ↑Sat Jan 07, 2017 9:37 pm at Sat Jan 07, 2017 9:37 pm
>
> 
Getting models from the very first hitman was not very easy. So many things were done completely different in 2000 than today. I will probably make a new tutorial with this.

To unpack game level you will need these files: 
- Pack.SPK - level package
- PackRepeat.DXT - textures descriptions for this level
- Repeat.DXT - all textures package, located in game root

Put these files into the folder with a tool and run it. If one of DXT files will be missing, only models will be unpacked, no textures.

All objects are packed in an tree with links to textures, UVs, skeletons, and all the other model properties. So there's no other way to unpack them other than create the full tree. There will be many files and folders, so full directory/name length may exceed the limit. In this case, place files into short named directory, like "C:\hitman"

Hi, I'm new to the forums. Someone directed me here as a way to get C47 models. I would very much like to extract them. As well as a way to add skins to C47.
