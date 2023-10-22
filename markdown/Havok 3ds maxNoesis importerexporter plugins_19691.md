## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-03-21T22:18:02+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

So, it was over year since I posted something relevant, it's time to show some evil horns.
Starting with this one.
Following plugin will let you import skeletons and few animation formats from all known Havok packfiles (hkx).
In addition, you can export your own skeletons and animations into Havok format.
Enjoy.



Supported animation formats:
hkaInterleavedUncompresedAnimation
hkaDeltaCompressedAnimation
hkaSplineCompressedAnimation

Here is source animation in 3ds max.


Here is animation exported into Havok format, inside Havok preview tool.


Here is Havok animation imported back to 3ds max.



Master page for 3ds max plugin.
Master page for Noesis plugin.

I will also require from you any and every feedback you can think of.
For plugin, you can create issues in repo.
For everything else here, or on blog. 
Thank you.
## Post #2
- Username: ChaoticFusion40
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2019-03-22T00:25:51+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

the page above is gone
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-03-22T09:27:30+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

Link has been fixed.
## Post #4
- Username: kong1313113
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 09, 2017 2:47 pm
- Post datetime: 2019-04-21T12:09:08+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

Cool, that's great!Can animation be supported in the future?
## Post #5
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-13T14:59:36+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.1 has been released.

Fixed loading version 2016 files under 32bit build.
Fixed wrong class name links for XML exported files.   
Maxscript listener will now show whenever plugin tries to print any information and from now on, user will be always informed properly. User no longer needs to open listener manually.
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-13T16:48:30+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

Added plugin for Noesis.



Link at first post.
## Post #7
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-18T12:12:17+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

this tools are very interesting but I would like to ask some questions. Is it possible that when I add a skeleton the skin of the model is preserved? I would like to use it for the models of the characters of the souls series. then is it possible to recover the animations done with the havok?
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-20T15:33:10+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dibe91 ↑Sat May 18, 2019 8:12 pm at Sat May 18, 2019 8:12 pm
>
> 
this tools are very interesting but I would like to ask some questions. Is it possible that when I add a skeleton the skin of the model is preserved? I would like to use it for the models of the characters of the souls series. then is it possible to recover the animations done with the havok?

When importing skeleton, it always looks up for existing bones, but will always apply transformations/user props/parent links, etc.
Sometimes, it will mess up skin, however you can reset(refresh) skin pose(not weights) inside skin modifier.
What I always do, is I'll load Havok skeleton first, then model itself. Note this, that some tools/scripts will create their own bones, despite they are already loaded from skeleton file.
1st round of animation support comes this week or so, only for 3ds max.
## Post #9
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-20T18:32:24+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

this is a good news! I tried with the skeletons of sekiro but I can't import them. Is it possible to do something?
## Post #10
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-20T18:37:05+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dibe91 ↑Tue May 21, 2019 2:32 am at Tue May 21, 2019 2:32 am
>
> 
this is a good news! I tried with the skeletons of sekiro but I can't import them. Is it possible to do something?

Sekiro might use new version, 2017 - 2018? Mine supports only 2016 from the new ones so far.
## Post #11
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-20T18:38:36+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.2 has been released.

Added ability to export/import animations.
Added Environment generation for exported file.
Added skeleton pose capture frame for export.

Imported animations only interleaved and delta compressed so far.

Also, if anyone has ever worked with wavelets, please let me know.
## Post #12
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-20T19:00:19+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

I see. if you want I can pass you the skeletons of sekiro to see how they are
## Post #13
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-20T19:02:44+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

then I wanted to ask something. in bloodborne there are many furry creatures and I am wondering if it is possible that there are also bones in the skeleton for hair. do you think this thing is possible?
## Post #14
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-20T19:15:55+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dibe91 ↑Tue May 21, 2019 3:02 am at Tue May 21, 2019 3:02 am
>
> 
then I wanted to ask something. in bloodborne there are many furry creatures and I am wondering if it is possible that there are also bones in the skeleton for hair. do you think this thing is possible?

I have BB files, never used them so far, but I have no idea how hair is made, I assume its treated as cloth, or real time ragdoll.

> Reply from dibe91 ↑Tue May 21, 2019 3:00 am at Tue May 21, 2019 3:00 am
>
> 
I see. if you want I can pass you the skeletons of sekiro to see how they are
You can.
## Post #15
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-20T21:46:50+00:00
- Post Title: Havok 3ds max/Noesis importer/exporter plugins

ok try this:

[http://www.mediafire.com/file/itmcqv110 ... 0.rar/file](http://www.mediafire.com/file/itmcqv1100q0wb2/c1070.rar/file)
## Post #16
- Username: ChaoticFusion40
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2019-05-21T05:03:25+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

are you planning on supporting spline compressed animations.
## Post #17
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-21T10:17:14+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.3 has been released.

Added support for loading 2016.2 toolset formats.
Fixed crash, when loading incomplete 2016+ formats.

> Reply from ChaoticFusion40 ↑Tue May 21, 2019 1:03 pm at Tue May 21, 2019 1:03 pm
>
> 
are you planning on supporting spline compressed animations.
Eventually.
## Post #18
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2019-05-21T11:03:17+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

THanks you for this tool. It's amazing !

I got a question : does this' tool support FInal fantasy XIV Skeleton and animation? DId anyone already tried ?
## Post #19
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2019-05-21T19:45:18+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Would it be possible to add support for... Shadow warriors 2? It uses havok 2013 3.0 (judging from file headers), i tried with both base skeleton or animations but none works, animation are also all compressed together in a big file.
Shadow warriors 1, instead get the bones loaded and... the first frame of the animation.
## Post #20
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-22T14:12:20+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Allanoon ↑Wed May 22, 2019 3:45 am at Wed May 22, 2019 3:45 am
>
> 
Would it be possible to add support for... Shadow warriors 2? It uses havok 2013 3.0 (judging from file headers), i tried with both base skeleton or animations but none works, animation are also all compressed together in a big file.
Shadow warriors 1, instead get the bones loaded and... the first frame of the animation.

SW2 uses binary tagfiles, they are much different than standard format, (more like binary XML).
They can be converted into standard packfiles (or should).
Back in a day, I was able to open them with standard tools (2014.1), so I assume they are convertable.

As for my opinion, tagfiles shouldn't be ever used in final product.
They take way too much time to load, compared to traditional format.
Devs probably chose this format, so they don't need to generate packfiles for each platform, at the expense of time.
And we all know how long are loading times in SW2...
I still don't understand their system of asset handling, it's way too chaotic and redundant.
I mean they still use Zlib algo, I have nothing against Zlib, but there are much faster compression libraries like ZStandard, Brotli, LZHAM. And all of these are free and open source...

About the first frame of animation, there is a bug with loading delta compressed animations rn.

EDIT:
Animsets in SW2 have stored multiple hkt files inside, they are basically archives (a very bad ones).

Here is rough script for QuickBMS, that will extract them:

```
# Author Lukas Cone in 2019, Version 1
# script for QuickBMS http://quickbms.aluigi.org

idstring "as_head\x09\x98\x1e\x00"
set thisOffset 11
get fileSize asize
goto 19

for
	findloc nextOffset longlong 0xd011facecab00d1e "" # doll face cab die

	if nextOffset == ""
		math nextOffset = fileSize
	endif
	
	math cSize = nextOffset
	math cSize - thisOffset
	
	log "" thisOffset cSize
		
	if nextOffset == fileSize
		break
	endif
	
	math thisOffset = nextOffset
	math nextOffset += 8
	goto nextOffset
next
```


You can then normally open them with Havok 2014 tools, convert them into havok packfiles, and load them into 3ds max.
They are using spline compression, so you'll need to wait for version 1.4.
## Post #21
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-24T14:38:23+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Anybody said Spline Compression?

HavokMax V1.4 has been released.

Added ability to load Spline Compressed animations.
Fixed issue, when loading Delta Compressed animations, only first 2 frames were processed.
## Post #22
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-05-26T17:47:54+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I have a question to ask. since you are very capable with maxscripts if you pass the script to import demon's souls models would you be able to arrange the skeleton part?
## Post #23
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-05-26T18:00:17+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dibe91 ↑Mon May 27, 2019 1:47 am at Mon May 27, 2019 1:47 am
>
> 
I have a question to ask. since you are very capable with maxscripts if you pass the script to import demon's souls models would you be able to arrange the skeleton part?

You're question is very vague, so I'll try to answer as best as I can.
I'm no longer producing maxscripts, last script I made, was more than year ago. But you're not the only one who thinks I still make them.
I know that flver files have "broken" rotations in skeletons, and I had never found the fix for that, at least so far.

The common answer is, if it's Havok skeleton, it can be loaded. You have all the options you need, you can make presets, you can rotate and scale whole skeleton. You can access bones in different ways. Everything is explained in blog page.
## Post #24
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2019-05-28T21:48:11+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I was wondering if you also figured out how to reverse havok script. HKS.
The recompilation is easy with anarchy tools but none of the existing lua decompilers work
## Post #25
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2019-05-29T14:41:12+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Fri May 24, 2019 10:38 pm at Fri May 24, 2019 10:38 pm
>
> 
Anybody said Spline Compression?

HavokMax V1.4 has been released.

Added ability to load Spline Compressed animations.
Fixed issue, when loading Delta Compressed animations, only first 2 frames were processed.

from which game the model cames from?
## Post #26
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-06-02T06:27:32+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I tried to import a DARK SOULS REMASTERED animation but this error happens to me



I used 3d studio max 2017
## Post #27
- Username: Snapdragons
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 04, 2018 5:02 am
- Post datetime: 2019-06-03T05:54:18+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I'm likely missing something obvious, but does your Noesis plugin support animations? The HKX skeleton for bloodborne models load just fine, but any of the animations (lowercase .hkx) are invisible/don't load.
## Post #28
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-04T08:24:22+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Drawing ↑Wed May 29, 2019 10:41 pm at Wed May 29, 2019 10:41 pm
>
> 
from which game the model cames from?

XenobladeX

> Reply from Snapdragons ↑Mon Jun 03, 2019 1:54 pm at Mon Jun 03, 2019 1:54 pm
>
> 
I'm likely missing something obvious, but does your Noesis plugin support animations? The HKX skeleton for bloodborne models load just fine, but any of the animations (lowercase .hkx) are invisible/don't load.

Noesis plugin loads only skeleton files so far, my main focus is on 3ds max.

> Reply from dibe91 ↑Sun Jun 02, 2019 2:27 pm at Sun Jun 02, 2019 2:27 pm
>
> 
I tried to import a DARK SOULS REMASTERED animation but this error happens to me

I used 3d studio max 2017

Post sample please.
Animations for versions 2015+ are not supported atm.
## Post #29
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-06-04T11:31:00+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

ok this is an example of the animations of the model. was taken from the version prepared to die. it should not change anything as there have been few changes in general 

[http://www.mediafire.com/file/faxp62by4 ... 0.rar/file](http://www.mediafire.com/file/faxp62by4tt0o2z/c1200.rar/file)
## Post #30
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-04T18:43:44+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.5 has been released.

Fixed not loading of newly added external presets for first time
Added ability to choose animation index, in case of multiple animations in single file.
Added ability to load config file with suppressPrompts enabled.
Added ability to load bones by their hkaBone user property, in case of not being as annotation.
Added ability to load additive animations.
## Post #31
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-06-04T18:53:32+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dibe91 ↑Tue Jun 04, 2019 7:31 pm at Tue Jun 04, 2019 7:31 pm
>
> 
ok this is an example of the animations of the model. was taken from the version prepared to die. it should not change anything as there have been few changes in general 

http://www.mediafire.com/file/faxp62by4 ... 0.rar/file

You sent wrong files, remastered must use new havok version, this is version 2010, which loads fine.
## Post #32
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-06-05T10:55:19+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

OK OK, try this too. 

[http://www.mediafire.com/file/sp6dxum2e ... k.rar/file](http://www.mediafire.com/file/sp6dxum2eny5cno/c1200.anibnd_unpack.rar/file)
## Post #33
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-06-07T05:42:10+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Tue May 21, 2019 3:15 am at Tue May 21, 2019 3:15 am
>
> 
I have BB files, never used them so far, but I have no idea how hair is made, I assume its treated as cloth, or real time ragdoll.
Not really ragdoll as i understand. Cloth and fur in bloodborne/ds3/sekiro is in *_c.hkx files next to flver model file. If your will look at this you can unpack bloodborne dcx files with yabber tool https://www.nexusmods.com/sekiro/mods/42, it works with all souls games btw. 

P.S. Drop them on regular yabber.exe to unpack, not on yabber dcx one.
## Post #34
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-06-07T17:56:07+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I guess those files were the skeletons for the physical part. I hope you can find a way to make it work
## Post #35
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-06-13T18:39:34+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

some news?
## Post #36
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-07T16:05:59+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.6 has been released

Fixed loading incorrect animation track for bone without annotation name and bind remaps.
Fixed loading spline compressed animations when float tracks are present.
Added Motion ID var into config file.
## Post #37
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-07T20:37:53+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.7 has been released

Added support for loading version 2015 and 2017 skeletons.
Added support for loading version 2015 interleaved animations.
Added support for loading version 2015 - 2017 spline compressed animations.
Fixed crash, when loading animations caused by 0 scale values.
## Post #38
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-08T19:54:35+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.8 has been released.

Fixed logging for non-unicode builds (2010 - 2012). 
Fixed crash caused by dialog for some versions (mainly 2012 as reported in #4 ).
Fixed plugin registration bug reported in #5.
## Post #39
- Username: Icarus2001
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 14, 2017 3:22 pm
- Post datetime: 2019-07-11T15:07:29+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Are you planning to add hkaQuantizedAnimation class support?
## Post #40
- Username: qq531620267
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 04, 2019 1:27 pm
- Post datetime: 2019-07-12T10:05:16+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Tue Jul 09, 2019 3:54 am at Tue Jul 09, 2019 3:54 am
>
> 
HavokMax V1.8 has been released.

Fixed logging for non-unicode builds (2010 - 2012). 
Fixed crash caused by dialog for some versions (mainly 2012 as reported in #4 ).
Fixed plugin registration bug reported in #5.

where is website?
## Post #41
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-14T01:47:31+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from qq531620267 ↑Fri Jul 12, 2019 6:05 pm at Fri Jul 12, 2019 6:05 pm
>
> where is website?
Ummm. Did it occur to you to check first post?
## Post #42
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-07-16T18:45:55+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

From wich games can we import the models and animations? I guess not ALL the games made with Havok are compatible right?
Is there some kind of list of wich games are supported and from whom the models and animations can be imported into 3ds max?
## Post #43
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-21T09:14:56+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from WollieWoltaz ↑Wed Jul 17, 2019 2:45 am at Wed Jul 17, 2019 2:45 am
>
> 
From wich games can we import the models and animations? I guess not ALL the games made with Havok are compatible right?
Is there some kind of list of wich games are supported and from whom the models and animations can be imported into 3ds max?

There are hundreds, if not thousands games, that uses Havok.
The games are not made with Havok. The Havok is made for them.
It's the game developer's wish, if they want to use serialize part of Havok.
Not all games are using Havok binaries.

But in short, every single Havok file (not including XML and Tag files) ever made is compatible with my library.
The list of compatible/importable animation compressions is in the first post.
There won't be added support to import meshes in a near future and I don't plan on making it.
Only crazy person would actually use Havok format for rendering (*couch* FWH *couch*).
I mean they can be used instead of FBX files to store data as 3rd party container, I have seen such pipelines.
But since Havok was never actually made public, nobody would ever wanted to do so.
## Post #44
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-07-23T21:10:16+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I tried to load Demons Souls animations. Skeleton loads fine but animations not with this error 

I hope you can take a look, here is example files: https://cdn.discordapp.com/attachments/ ... /c0000.rar
## Post #45
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-07-24T05:59:26+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dropoff ↑Wed Jul 24, 2019 5:10 am at Wed Jul 24, 2019 5:10 am
>
> 
I tried to load Demons Souls animations. Skeleton loads fine but animations not with this error.

The animations are using wavelet compression, such compression won't be supported for a long time.
I had already posted if anyone worked with wavelets before, nobody answered or nobody knows.
I have spent quite some time on this already, but my little knowledge about wavelets limits my ability to finish decompressor.
## Post #46
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-03T12:19:55+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.9 has been released.

Added "disable scale" tracks option. (#3 )
Added keyboard shortcuts for dialogs. (#6 )
Changed first dialog item focus on process buttons. (#6 )

HavokMax V1.10 has been released.

Fixed crash, when loading corrupted skeletons. ( #8 )
Added hka into file extensions.
## Post #47
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2019-08-04T07:39:44+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Marvelous plugins!
There is a chance to support Sekiro animation?
## Post #48
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-04T18:45:57+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Skykila ↑Sun Aug 04, 2019 3:39 pm at Sun Aug 04, 2019 3:39 pm
>
> 
Marvelous plugins!
There is a chance to support Sekiro animation?

Sekiro uses version 2016, but also uses thing called compendium (a single file with shared information) making them impossible to load atm.

I'm not sure, if compendium is a new Havok standard or is it tied only to Sekiro. 
So far, I don't know if it's worth an effort to implement that.
## Post #49
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2019-08-05T14:35:15+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Mon Aug 05, 2019 2:45 am at Mon Aug 05, 2019 2:45 am
>
> 
Skykila wrote: ↑Sun Aug 04, 2019 3:39 pm
Marvelous plugins!
There is a chance to support Sekiro animation?


Sekiro uses version 2016, but also uses thing called compendium (a single file with shared information) making them impossible to load atm.

I'm not sure, if compendium is a new Havok standard or is it tied only to Sekiro. 
So far, I don't know if it's worth an effort to implement that.

Sad news...
## Post #50
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-08-05T15:10:42+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Skykila ↑Sun Aug 04, 2019 3:39 pm at Sun Aug 04, 2019 3:39 pm
>
> 
Marvelous plugins!
There is a chance to support Sekiro animation?

Use tagtools to convert sekiro anims to 2012 havok, its in #tools-and-resources channel in this discord server https://discordapp.com/invite/mT2JJjx

P.S. or just here https://github.com/blueskythlikesclouds/TagTools
## Post #51
- Username: Skykila
- Rank: advanced
- Number of posts: 47
- Joined date: Sat Apr 03, 2010 3:03 pm
- Post datetime: 2019-08-06T06:02:50+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from dropoff ↑Mon Aug 05, 2019 11:10 pm at Mon Aug 05, 2019 11:10 pm
>
> 
Skykila wrote: ↑Sun Aug 04, 2019 3:39 pm
Marvelous plugins!
There is a chance to support Sekiro animation?


Use tagtools to convert sekiro anims to 2012 havok, its in #tools-and-resources channel in this discord server https://discordapp.com/invite/mT2JJjx

P.S. or just here https://github.com/blueskythlikesclouds/TagTools

Super!
## Post #52
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-08-08T18:08:02+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Some crazy person actually managed to take the time and research TBOD tag for new Havok format.
Well kudos to them.
It might be actually possible to make a binary exporter in a future.
## Post #53
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-08-09T02:18:57+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Fri Aug 09, 2019 2:08 am at Fri Aug 09, 2019 2:08 am
>
> 
Some crazy person actually managed to take the time and research TBOD tag for new Havok format.
Well kudos to them.
It might be actually possible to make a binary exporter in a future.
TBOD is same as TBDY iirc, because tagtools wasnt working with sekiro animations before just because of tags names, also TNAM should be same as TNA1.
## Post #54
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2019-08-09T03:57:01+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

These models from SpongeBob's Truth or Square crash both 3DS Max and Noesis immediately.
[https://puu.sh/E30NX.zip](https://puu.sh/E30NX.zip)
## Post #55
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2019-09-19T12:07:28+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

is there any news? Do you support other games?
## Post #56
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-27T16:10:14+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

hi, PredatorCZ.

I found PREDICTIVE_COMPRESSED_ANIMATION files.
I attached sample. if you can, please check it. thanks!

*EDIT
I added skelton files.
game title: Gunslinger Stratos Reloaded

I knew that "PREDICTIVE_COMPRESSED" existed as a format, but it was the first time I actually saw it.
All other animations seem to have been created with PREDICTIVE_COMPRESSED.
It can be played without problems with HavokTool2014.
Of course it would be nice if the reverse was successful, but it would be greatly appreciated if it could be used as a document.
[skelton_and_anim.zip](https://xentaxbackup.github.io/file/16960_skelton_and_anim.zip)
## Post #57
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-17T22:44:07+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

hi, PredatorCZ.

I have a file from DDO online which is supposed to run  Havok 5.5, i have been unable to locate the skeleton files for the game and was hoping if you could just take a look and tell  me if it looks to contain only animation or skeleton as well.

the game has everything Hashed so there would be no actual bone names and such, i also added the .hkx extension manually since file was extracted with zlib without a proper extension. (if i doesn't contain the skeleton i am back to square one ..)

Thanks in advance 

link to sample
[https://drive.google.com/open?id=12xzNK ... pCpAA66D8f](https://drive.google.com/open?id=12xzNKphdR9prKJl2bobWaKpCpAA66D8f)
## Post #58
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-11-18T09:07:42+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from einherjar007 ↑Mon Oct 28, 2019 12:10 am at Mon Oct 28, 2019 12:10 am
>
> 
...
I found PREDICTIVE_COMPRESSED_ANIMATION files.
...

I'm not sure, when or even if I'll add this feature.

> Reply from jayn23 ↑Mon Nov 18, 2019 6:44 am at Mon Nov 18, 2019 6:44 am
>
> 
I have a file from DDO online which is supposed to run  Havok 5.5, i have been unable to locate the skeleton files for the game and was hoping if you could just take a look and tell  me if it looks to contain only animation or skeleton as well.
...

Following file is a tag format, you must convert it to the a packfile.
This file contains animation.
You can look for skeletons by searching text within files hkaSkeleton (with total commander, krusader, etc)
## Post #59
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-18T09:25:06+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Thanks for the fast response.

> You can look for skeletons by searching text within files hkaSkeleton (with total commander, krusader, etc)
Well thats a shame i was hoping my search was at on end   
I dont know where to find these hkaSkeleton files , but ill try with total commander to scan all files, for this

> Following file is a tag format, you must convert it to the a packfile.
ill do some research how this is done

Thanks again
## Post #60
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-21T21:31:35+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> You can look for skeletons by searching text within files hkaSkeleton (with total commander, krusader, etc)
So i managed to find the skeleton files thanks to your advice and total commander, but when trying to convert them to a packfile using Havok content filter manager tools i get the following error " Unable to detect format from stream" i am guessing its missing some header?
could you please take a look and see if there is something i can do to allow for format to be recognized?

thanks in advance

link to sample:
[https://drive.google.com/open?id=1Ggprb ... 0EPJEk0ov5](https://drive.google.com/open?id=1GgprbcbrGHE7fAmAjtIvzH0EPJEk0ov5)

Edit:
I managed to make a script  to read the file in tag format and create the skeleton - still cant read all of them(really weird format) but at least some is a good start, thanks for your help.
this thread and another plus some game specific script i got helped find all the data/tools i needed to do this .
## Post #61
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-11-28T07:24:41+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from jayn23 ↑Fri Nov 22, 2019 5:31 am at Fri Nov 22, 2019 5:31 am
>
> 
...but when trying to convert them to a packfile using Havok content filter manager tools i get the following error " Unable to detect format from stream" i am guessing its missing some header?

Tag format is really not my expertise, basically I know nothing about this one.
You could try to use assetCC programs (inside batch folder I think).
Or try to convert them to a xml format, then convert them to a packfile.
## Post #62
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-11-28T17:43:22+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hello, thank you for your tool, can Marvel Ultimate Alliance 2 PC (released in 2016) hkx works with your 3DS max plugin ? I tried, but crashed 3DS MAX 2019:
Samples if needed : 
[https://www.mediafire.com/file/h2x6smut ... le.7z/file](https://www.mediafire.com/file/h2x6smutm9m67wd/MUA_2_PC_Sample.7z/file)
## Post #63
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2019-12-16T06:40:51+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

PredatorCZ,can you look at this file? [la_noire_examples.zip](https://drive.google.com/file/d/1W6k58FiEWLhLtx95EOu845m9sRhbUeYt/view?usp=sharing) it's from LANoire
I'm interesting in animations mostly. but if you can inspect models that would be just great!

as I see in HEX it's a havok


edit: found skeletons. attached here


 packed_skeletons.zip
(95.32 KiB) Downloaded 42 times
## Post #64
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2019-12-30T22:29:29+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from huitbgoiouythy ↑Fri Nov 29, 2019 1:43 am at Fri Nov 29, 2019 1:43 am
>
> 
Hello, thank you for your tool, can Marvel Ultimate Alliance 2 PC (released in 2016) hkx works with your 3DS max plugin ? I tried, but crashed 3DS MAX 2019:
Files are using version 6.1.0, this version is unsupported.

> Reply from Tosyk ↑Mon Dec 16, 2019 2:40 pm at Mon Dec 16, 2019 2:40 pm
>
> 
PredatorCZ,can you look at this file?

It seems to be some kind of arbitrary format, any format structures anywhere? Don't want to start from scratch.
## Post #65
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-01-01T13:48:56+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Tue Dec 31, 2019 6:29 am at Tue Dec 31, 2019 6:29 am
>
> <...>
Tosyk wrote: ↑Mon Dec 16, 2019 2:40 pm
PredatorCZ,can you look at this file? 


It seems to be some kind of arbitrary format, any format structures anywhere? Don't want to start from scratch.I have a maxscript for head models:

```
    hf=readshort fstream #unsigned
    sign = bit.get hf 16
    exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
    fraction = bit.and hf (bit.hexasint "03FF")
    if sign==true then sign = 1 else sign = 0
    exponentF = exponent + 127
    outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
    (bit.shift exponentF 23)) (bit.shift sign 31)
    return bit.intasfloat outputasfloat*2
    )


vertArray=#()
faceArray =#()
UVarray=#()

function ReadModelFile fName=
(     
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"          -- Open the file for reading
    fSeek stream 0x194 #seek_set
    vertCount = readlong stream       -- vertex count of (first) submesh
    faceCnt     = readlong stream
    vertStride= 36
   
    --print ("@ 0x"+ bit.intAsHex(ftell stream) as string)      

    fSeek stream 0x3150 #seek_set   -- vertex block
    for i=1 to vertCount do (      --
       x  = readShort stream #signed
       y  = readShort stream #signed
       z  = readShort stream #signed
       fSeek stream (26) #seek_cur
       tu  = readHalfFloat stream; tv  = readHalfFloat stream
       append vertArray ([x,y,z]/127.0)   
      --format "v %\n" vertArray[i]
       append UVarray [tu,tv,0]             
    )
    print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
   
    for x = 1 to faceCnt do (
        fa= readshort stream #unsigned
        fb= readshort stream #unsigned
        fc= readshort stream #unsigned
            format "f % % %\n" fa fb fc
        append faceArray[fa+1,fb+1,fc+1]   
   )   
    msh = mesh vertices:vertArray faces:faceArray
    msh.numTVerts = vertCount
    buildTVFaces msh
    for j = 1 to vertCount do setTVert msh j UVarray[j]
    for j = 1 to faceCnt do setTVFace msh j faceArray[j]

    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open L.A. Noire 3D Model" \
types:"3D Model (*.chunk)|*.chunk"
--historyCategory:"3D Model chunk
format "fname: %\n" fname
   
ReadModelFile fname
```


I attached it to this message:


 adam's_head_import.zip
(1.02 KiB) Downloaded 23 times



also I have this info:

> For other chunk files you'll need to adjust the start address of the vertices block (0x3150 here)
>
> and (possibly) the address of the vertex count: 0x194


all the info took [from here](https://forum.xentax.com/viewtopic.php?p=118039#p118039)
## Post #66
- Username: Backtotheroot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 16, 2020 7:37 pm
- Post datetime: 2020-01-16T14:47:17+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hi, first of all, great plugin and cheers for all the hard work you put into it and also for making it public. I'm trying to use animations from Darksouls 3 for an educational Project and the import in 3Ds Max 2018 works perfectly with your plugin, I just got an issue with the rootmotion data. All animation i import are in place even though I would suspect DS3 uses rootmotion. Maybe you could hint me in the right direction, are there any special settings I got to consider when importing? Or is there actually no rootmotion data in the clips?
I added a link to the Skeleton and an animation file as an example.
[https://drive.google.com/open?id=1VQ2Bb ... quyxONUZWU](https://drive.google.com/open?id=1VQ2Bbw0QRMK_CrG9BxAx1AquyxONUZWU)

Any help would be appreciated
## Post #67
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-01-20T11:49:44+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Backtotheroot ↑Thu Jan 16, 2020 10:47 pm at Thu Jan 16, 2020 10:47 pm
>
> 
Hi, first of all, great plugin and cheers for all the hard work you put into it and also for making it public. I'm trying to use animations from Darksouls 3 for an educational Project and the import in 3Ds Max 2018 works perfectly with your plugin, I just got an issue with the rootmotion data. All animation i import are in place even though I would suspect DS3 uses rootmotion. Maybe you could hint me in the right direction, are there any special settings I got to consider when importing? Or is there actually no rootmotion data in the clips?
I added a link to the Skeleton and an animation file as an example.
https://drive.google.com/open?id=1VQ2Bb ... quyxONUZWU

Any help would be appreciated

Hi,
rootmotion is not yet supported.
I'll add it, when I'll got the chance.
## Post #68
- Username: Backtotheroot
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 16, 2020 7:37 pm
- Post datetime: 2020-01-23T11:58:37+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Thanks for the clearfication. I'll keep an eye out for future updates
## Post #69
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-02-09T18:27:18+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Please tell me this works with Dead Space 1-3

Edit: Damnit, I knew it wouldn't work.
I forgot that hkx format in Dead Space series only stores collision data so even if this worked, it'd be useless for me.
## Post #70
- Username: Yrruf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 16, 2014 2:25 am
- Post datetime: 2020-03-11T16:28:29+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

What are the problems right now that keep Sekiro anims from loading? I want to try to understand it to see if I can help with it.
## Post #71
- Username: Yrruf
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 16, 2014 2:25 am
- Post datetime: 2020-03-19T22:31:46+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Okay, I've got Sekiro animations imported converting them first to 2012 version, but indeed rootmotion is missing. 
Can we lend a hand in any way to be able to import rootmotion?

Thanks for your work.
## Post #72
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-04-07T07:46:48+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I found that Mafia 3 utilizes havok as the base animation system — version hk_2014.2.0-r1. None of the existing tools work with this version.
however I found a [page with description](https://zeldamods.org/wiki/Havok) of exact same version and header seem absolutely the same. That link lead me to [this python tool](https://pypi.org/project/botw-havok/) which should convert mafia 3 havok files into JSON but I couldn't get it to work. So I contacted to the python tool dev and he told me that files I have are wrongly extracted (by having extra zeros after header). But I think these files extracted alright — extra zeroes just additions to the files for some reason, maybe engine needs them.

so here's examples: [https://drive.google.com/file/d/1_Mx7ZU ... sp=sharing](https://drive.google.com/file/d/1_Mx7ZUyZFwDw3eAmVUS94VdmXMxwCE5k/view?usp=sharing)

p.s.: I'm making a shooting game, just for practicing and this animations would be really cool to have. hope can find some time
## Post #73
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-04-25T13:40:39+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Here's another findings: 

 AW_maine.zip
(182.11 KiB) Downloaded 30 times


Alan Wake animations. Seems like plain Havok-5.5.0-r1 files though plugin just crashes max when I'm trying to load them.
However skeletons work just fine
## Post #74
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-05-14T06:39:05+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Is ur Importer Support Final Fantasy 14!

Thank u for ur answer!

Best Regards
## Post #75
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-14T12:24:06+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from KingJuls ↑Thu May 14, 2020 2:39 pm at Thu May 14, 2020 2:39 pm
>
> 
Is ur Importer Support Final Fantasy 14!

Thank u for ur answer!

Best Regards

To import skeleton and ani from ff14 we need first of all a 3.5 client ( the last supported by ff14 explorer) export them. Load in havok 2014 . save them in havok 2014 format. The main problem is that all the animation are inside an .hka archive so we should take them out the archive... Without samples files got from the procedure I explained predator couldn t take a look on them. I remeber one guy that succeded in importing them in blender with a long work around method. Don t know if he used predator importer or other script.
## Post #76
- Username: y0ur5h4d0w
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 24, 2020 8:11 pm
- Post datetime: 2020-05-26T19:40:37+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

guys i have the latest noesis version and the latest noesis havok importer, i'm opening my DS3 abyss watchers SMD (and works fine) then i drag and drop the HKX file to apply the leap attack animation, i apply it to the preview i'm looking at and literally nothing happens! how can i fix this problem in order to be able to export a frame as OBJ?
## Post #77
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2020-06-09T01:41:56+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hello friends.

I have little to zero knowledge of Havok stuff but I was wondering if someone could take a look at these files from WWE2K19 for me. I don't know if this is the same type of havok stuff this plugin is for so let me know, I just know that if I rename them HKT and import to Noesis i get invalid tag errors, so it reads some of it. 

All I know is that these files are hitboxes for the prop they're included with. I've attached a few samples. Let me know .


[sample.rar](https://xentaxbackup.github.io/file/18301_sample.rar)
## Post #78
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-07-03T15:34:35+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I think I'm gonna need to focus on Noesis as well. It uses like the first version of library or something...

EDIT:
Noesis will have to wait until or even when x64 support is released.
## Post #79
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-07-07T09:50:47+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hey there!
I love the work you did on the Havok-animation format!
Backyard Wrestling - Don't Try This at Home uses this physic engine aswell. However, the only script available for the games main archive just seperates the extracting files in meshes and data.
All Data-Files here: [https://we.tl/t-EdnyhkDSLI](https://we.tl/t-EdnyhkDSLI)

Your plugin sadly does not recognize any of these files...or shows em in the noesis file-tree when trying to access the folder.
Can you tell me which files are havok animation files? There must be a way to find out right?
Alot of the files just contain textures and sounds. See more about that in my thread here: [viewtopic.php?t=19370](https://forum.xentax.com/viewtopic.php?t=19370)

Id love to have some of the finishing moves available for some blender project!
Appreciate your work on this man!
## Post #80
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-07-09T09:54:03+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Henchman800 ↑Tue Jul 07, 2020 5:50 pm at Tue Jul 07, 2020 5:50 pm
>
> 
...
Backyard Wrestling - Don't Try This at Home uses this physic engine aswell. 
...
Can you tell me which files are havok animation files? There must be a way to find out right?
...

This title uses only a physics module.
There aren't any Havok files to begin with.
A lot of games are using physics module, but only for simulations.
Animations must be a custom format.
## Post #81
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-07-09T09:58:07+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Thu Jul 09, 2020 5:54 pm at Thu Jul 09, 2020 5:54 pm
>
> 
This title uses only a physics module.
There aren't any Havok files to begin with.
A lot of games are using physics module, but only for simulations.
Animations must be a custom format.

Good to know!
And thank you for taking your time
## Post #82
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-11-16T23:44:19+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.11 has been released.

More stable library version.
Fixed incorrect old format additive animations.
Added new format additive animations.
Added root motion support.
Moved to new config format (xml schema), presets will be migrated from old config format to new.
External presets can be still loaded with both old version and new version format. Old format is not recommended to use anymore.
Added support for 2020 and 2021 versions.
Dropped 32bit support.
Added support for exporting selected items (Export/Export Selected)


Also V1.11.1 hotfix that fixes crash for first-time users.
## Post #83
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2020-11-17T15:16:23+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

I thought this tool was now abandoned! thank you that you continue to work on it
## Post #84
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-21T02:37:29+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Can anyone provide a Havok file that contains a hkaDelta Compressed Animation in a format that can be read by this plugin?
Delta Compressed Animation, such as version 6.0, probably has a different format. Unable to load with HavokTool 2014.That is, this plugin will not work either.
However, HavokTool2010 can read it and convert it to xml. may be able to compare the xml that works in 2014 with the xml that works in 2010 and earlier, and fix it if it's just a tag format difference.

Data check from FFXIV, Gunslinger Stratos, and Dungeons and Dragons Online gave us a better understanding of the structure of Havok xml.
Most of all, it's only in terms of formatting, no knowledge of reverse...
## Post #85
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-11-22T19:03:19+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from einherjar007 ↑Sat Nov 21, 2020 10:37 am at Sat Nov 21, 2020 10:37 am
>
> 
Can anyone provide a Havok file that contains a hkaDelta Compressed Animation in a format that can be read by this plugin?
Delta Compressed Animation, such as version 6.0, probably has a different format. Unable to load with HavokTool 2014.

Delta Compressed Animation was removed since 2011.
What you can do, is to load it in 3ds max and export it back (it will be exported as interleaved, so you can apply spline compression in tool)
## Post #86
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2020-11-22T19:05:39+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

HavokMax V1.12 has been released.

 Fixed specific crash when importing incomplete skeletons. (#18 )
 Fixed wrong root motion rotation directions.
 Added hkaLosslessCompressedAnimation custom class support (library feature).
 Attempt to remove inter-frame gimbal lock issues.
## Post #87
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2020-11-26T14:50:57+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Thanks for huge update! Tried with the files I earlier attached to the tread — 1 passed 2 to go 

1. LANoire. Still can't load any of the samples, max just crashing
[viewtopic.php?p=158366#p158366](https://forum.xentax.com/viewtopic.php?p=158366#p158366)

2. Mafia 3. Same crashes
[viewtopic.php?p=161912#p161912](https://forum.xentax.com/viewtopic.php?p=161912#p161912)

3. Alan Wake. This samples seems work fine with latest release 
[viewtopic.php?p=162531#p162531](https://forum.xentax.com/viewtopic.php?p=162531#p162531)

Do you it is possible to add support for these files?

Again big thanks for supporting Havok!
## Post #88
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2021-01-15T08:39:45+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hello, thank you   is it possible to import the animation without it changing the bone lenght of original skeleton ?
I'd like to import animations without it changing bone lenght/scaling.
## Post #89
- Username: biankagentis9
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 15, 2021 6:51 pm
- Post datetime: 2021-01-15T17:07:42+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Cool, that's great!Can animation be supported in the future?  What software do you use?
## Post #90
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2021-01-22T20:08:28+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Tosyk ↑Thu Nov 26, 2020 10:50 pm at Thu Nov 26, 2020 10:50 pm
>
> 
1. LANoire. Still can't load any of the samples, max just crashing
Hey.
packedragdoll files are custom format, each of them have 4 embedded havok files. None of them loads.
packedskeleton files are custom format, no havok files inside
animset files are custom format, they use one embedded havok file. Doesn't load.
Unless there isn't any extractor for those, you gonna need to trim them by hand

> Reply from Tosyk ↑Thu Nov 26, 2020 10:50 pm at Thu Nov 26, 2020 10:50 pm
>
> 
2. Mafia 3. Same crashes

skeletons.bin is a custom format, it includes one large havok file with all skeletons. Version is not supported and it does some weird shit that needs to be looked at. It also includes 3 more smaller files with physics or something.
basic_anim.bin is same format as skeletons.bin. It contains single file with all animations. Again, version is not supported and extracted file doesn't load, because of version and custom stuff.

> Reply from huitbgoiouythy ↑Fri Jan 15, 2021 4:39 pm at Fri Jan 15, 2021 4:39 pm
>
> 
Hello, thank you   is it possible to import the animation without it changing the bone lenght of original skeleton ?
I'd like to import animations without it changing bone lenght/scaling.

Did you know there is a dedicated control in UI that shows when you import stuff? The dialog that shows is much smaller than the main window. In that dialog are many things that you can do. There are two large buttons at the bottom, where you can confirm import or cancel import. If you look at the top of that small dialog, you will see a text that saysScale, right next to it is a control where you can set your scale value.

In case, you're lost, I've added a screenshot.
The import dialog I was writing about is highlighted within green rectangle.
The scale control is highlighted within red rectangle.


If you need more help, let me know
## Post #91
- Username: Mahone
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Apr 17, 2021 6:20 pm
- Post datetime: 2021-04-20T13:02:49+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

okey technicly not working. Hkx-files empty. i can get the models with correct skeleton but no anim when open hkx-files. What i doing wrong? tried: ds3,bloodborne

Just get grey screen when i open the users uploaded files too in here
## Post #92
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2021-04-23T15:18:58+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Mahone ↑Tue Apr 20, 2021 9:02 pm at Tue Apr 20, 2021 9:02 pm
>
> 
okey technicly not working. Hkx-files empty. i can get the models with correct skeleton but no anim when open hkx-files. What i doing wrong? tried: ds3,bloodborne

Just get grey screen when i open the users uploaded files too in here

Same here. Tried to get animations from Bloodborne, I get nothing. The HKX files which contain the skeletons are showing and working. Sample files here: [https://mega.nz/file/mVVnCIRZ#tiIJvyRe5 ... P0DTojoNLc](https://mega.nz/file/mVVnCIRZ#tiIJvyRe5nb0y1AYYKg9AV_3H3KjsV_AuP0DTojoNLc) Please fix.

the Skeleton.HXK loads perfectly.
## Post #93
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-05-28T06:16:25+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hey,

anyone check Swords of Legends Online?
## Post #94
- Username: Nostritius
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Nov 11, 2019 6:18 pm
- Post datetime: 2021-06-10T14:24:43+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from Tosyk ↑Sat Apr 25, 2020 9:40 pm at Sat Apr 25, 2020 9:40 pm
>
> 
Here's another findings: AW_maine.zip
Alan Wake animations. Seems like plain Havok-5.5.0-r1 files though plugin just crashes max when I'm trying to load them.
However skeletons work just fine

Alan Wake (and Alan Wakes Amerian Nightmare) have modified havok files which are not really standard compliant. I have made a slight modification of the  3ds max plugin here: [https://github.com/OpenAWE-Project/HavokMax](https://github.com/OpenAWE-Project/HavokMax), which fixes the problem.
## Post #95
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2021-08-05T16:27:10+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from PredatorCZ ↑Sat Jan 23, 2021 4:08 am at Sat Jan 23, 2021 4:08 am
>
> 
Tosyk wrote: ↑Thu Nov 26, 2020 10:50 pm
1. LANoire. Still can't load any of the samples, max just crashing

Hey.
packedragdoll files are custom format, each of them have 4 embedded havok files. None of them loads.
packedskeleton files are custom format, no havok files inside
animset files are custom format, they use one embedded havok file. Doesn't load.
Unless there isn't any extractor for those, you gonna need to trim them by hand
yeah I know it doesn't load, I tried them all. The question is how to make them load? what version I need to make this files to make them load? 

> Reply from PredatorCZ ↑Sat Jan 23, 2021 4:08 am at Sat Jan 23, 2021 4:08 am
>
> 
Tosyk wrote: ↑Thu Nov 26, 2020 10:50 pm
2. Mafia 3. Same crashes


skeletons.bin is a custom format, it includes one large havok file with all skeletons. Version is not supported and it does some weird shit that needs to be looked at. It also includes 3 more smaller files with physics or something.
basic_anim.bin is same format as skeletons.bin. It contains single file with all animations. Again, version is not supported and extracted file doesn't load, because of version and custom stuff.
also, this one. how I need to change the files to load them?

I kindly ask your help. What I need to do with these files to load them with the tools?
## Post #96
- Username: LIANGJJ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jan 30, 2021 2:31 pm
- Post datetime: 2022-03-10T12:23:52+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Hello, what's the problem invalid version:2018 when importing? 
Is there any way to solve this problem?
## Post #97
- Username: pepsiguy2
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Apr 17, 2012 10:08 am
- Post datetime: 2022-03-21T02:09:25+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Is this tool abandoned?
## Post #98
- Username: testimesti1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 22, 2022 8:18 pm
- Post datetime: 2022-05-27T10:28:42+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

Is it possible to import root motion animations?
## Post #99
- Username: AlexPaul99
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 16, 2023 2:54 pm
- Post datetime: 2023-02-16T06:58:21+00:00
- Post Title: Re: Havok 3ds max/Noesis importer/exporter plugins

> Reply from testimesti1 ↑Fri May 27, 2022 6:28 pm at Fri May 27, 2022 6:28 pm
>
> 
Is it possible to import root motion animations?

I tried importing .hkx animations from Dark Souls III and it does not appear to support root motion.
