## Post #1
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-03-27T02:29:51+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Hey guys,

I'm very interested in a particular game that has some great 3d models, and I'd be willing to dish out the bucks for someone to work out a Noesis or 3ds Max script that can correctly import fully rigged and textured models from the game Warhammer 40,000 Inquisitor: Martyr. Basically a set of tools for extracting useable models, both static and rigged, from the game. I'm willing to pay someone 60 USD via paypal or Google Wallet to help me do this. Is anyone interested?

I can share game files if needed. The game is produced by NeoCore Games, and uses the Coretech3 Game engine, very similar to the Van Helsing game engine.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2018-03-27T07:23:41+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Wow, this game was already released?! I'm a big fan of warhammer 40k universe. If you will provide samples I'll gladly take a look.
## Post #3
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-03-27T22:43:07+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Hey, thats awesome! I am too, thanks for the quick reply! I'm uploading some files as I type, I'll link them in an update to this post. So I see some things right off the bat with this game, its file structure is very tidy and organized, which will make it very easy to work with. 

The first thing I noticed is that model files are stored in compressed folders with a .N2PK file name. Each model has a "high" and "low" folder within its individual location, each containing a N2PK file, and a single N2PK file called Files.N2PK in the base folder of each model.

I'm guessing the "High" and "Low" folders refer to LOD quality of the model and textures. In the uploads I'm sharing, I include all the files for some sample models, excluding the "low" folder, for obvious reasons. 

I'm uploading a weapon model, and an enemy unit model, as samples. I also noticed that the level models, which are procedurally generated, are actually made up of what appears to be single room models, which the game combines to form the levels. The level models folder contains a bunch of textures, in DDS format, a "High" and "Low" folder, again for the models themselves, and a set of special files for each room model. 

I'll upload a set of the special files for the room models, I assume they contain meta data for the level models, for randomizing purposes. I doubt they will be of much use, as all I want from the level models is the rooms themselves, not the randomized obstacles, crates, etc.

EDIT:

Here is the link to a folder containing the files, I've zipped them using 7zip so I can upload them easier.
[http://www.mediafire.com/folder/vx8utwx ... s_for_Help](http://www.mediafire.com/folder/vx8utwxcys4wf/Inquisitor_Martyr_Files_for_Help)
## Post #4
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2018-04-10T13:59:54+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Hey Zaramot, have you made any progress?
## Post #5
- Username: LumberingTroll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 08, 2018 7:59 am
- Post datetime: 2018-06-10T02:29:35+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

I too am very interested in the results of this, Id really like to get my hands on these models as well.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-10T13:27:42+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

I'm really wondering why you guys never seem to use forum's search?
If anyone had given the following hint we would have had the result 2 months earlier.  

Look here at Szkaradek's Deathtrap script for blender 249b:
[viewtopic.php?f=16&p=103512#p103512](http://forum.xentax.com/viewtopic.php?f=16&p=103512#p103512)

It helps to unpack the n2pk to vhm (and other files).

Use hex2obj for a quick approach getting the mesh (first SM only, as always):



nurgle_dreadnought-vhm.jpg (178.56 KiB) Viewed 444 times
## Post #7
- Username: shakotay2
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-06-10T14:34:40+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

here is a quickbms script for extracting the archives.

```
math msize * 2
getdstring uname msize
set MAGIC unicode uname
if MAGIC != "Neocore Package"
print "Not Supported %MAGIC%"
cleanexit
endif
goto 0x24
get tbloff longlong
savepos base
math tbloff + base
goto tbloff
get files long
for i = 0 < files
get hash long
get nsize long
math nsize * 2
getdstring uname nsize
set NAME unicode uname
get null short
get offset longlong
get size longlong
math offset + base
log name offset size
next i

```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-10T21:06:04+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

main submesh:



Nurgle_Dreadnought-vhm-tex.jpg (168.42 KiB) Viewed 425 times
## Post #9
- Username: LumberingTroll
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 08, 2018 7:59 am
- Post datetime: 2018-06-12T02:53:17+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

> Reply from shakotay2
>
> main submesh:
Nurgle_Dreadnought-vhm-tex.jpg

Im pretty new to this, would you mind explaining this process?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-12T18:17:01+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

> Reply from LumberingTroll
>
> Im pretty new to this, would you mind explaining this process?Talking about how to get addresses and counts? I've written a general tutorial about it (tut button in hex2obj, view link in my sig).
## Post #11
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-02-02T19:56:35+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Hey guys, so the blender script doesn't work at all, it doesn't even load. Also, I offered a commission on a 3ds max script, not a blender script. The offer still stands.
## Post #12
- Username: sparksisalwaystaken
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 24, 2018 4:26 pm
- Post datetime: 2019-02-25T04:43:55+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

I would also be willing to contribute some money towards this, if anyone can do it
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-26T11:13:42+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Can't serve with any scripts, sorry, but I've got the table data (for use with hex2obj). Seems there's 4 lod levels, the formula for lod1 meshes is
(n-1)x4 +1, so for 3rd mesh object lod1 is #9 (1, 5, 9, 13, ..).

FI addresses in parenthesis (1cf1e or 1e4c6), first one is for FVFsize of 32, second one for 36, you'll need to try out (uvpos 16 or 24), HF_UV

```
1st mesh object, number, vAddr, vCnt, FIcnt (FIaddr) 
# 1. 2abe 1650, FIcnt: 5172 (f8fe)  32/16
# 2. 121de 1386, FIcnt: 4134 (1cf1e or 1e4c6)
# 3. 1efe2 1114, FIcnt: 3099 (27b22 or 28c8a)
# 4. 293d0 846, FIcnt: 2064 (2fd90 or 30ac8)
2nd mesh object
# 5. 323d9 5736, FIcnt: 17967 (64a79)   36/24
# 6. 6d763 4953, FIcnt: 14370 (94283 or 98fe7)
# 7. a00b7 4057, FIcnt: 10776 (bfbd7 or c3b3b)
# 8. c8ff7 3112, FIcnt: 7185 (e14f7 or e4597)
3rd mesh object
# 9. e9cfb 6310, FIcnt: 16962 (121453)   36/24
# 10. 129977 5565, FIcnt: 13569 (155117 or 15a80b)
# 11. 1612ad 4606, FIcnt: 10176 (18526d or 189a65)
# 12. 18ea85 3486, FIcnt: 6780 (1a9e45 or 1ad4bd)

# 13. 1b2b72 27537, FIcnt: 78114 (2a4bd6)   36/24
# 14. 2caf82 24357, FIcnt: 62487 (3a10b6)
# 15. 3bfa4c 20022, FIcnt: 46866 (46f9e4)
# 16. 486970 15198, FIcnt: 31242 (50c2a8)

# 17. 51e731 851, FIcnt: 2352 (525191 or 525edd)
# 18. 526455 724, FIcnt: 1881 (52bed5 or 52ca25)
# 19. 52cdeb 594, FIcnt: 1407 (53182b or 532173)
# 20. 53238d 450, FIcnt: 936 (535bcd or 5362d5)

# 21. 53792f 11916, FIcnt: 32712 (5a04df)   36/24
# 22. 5b04d3 10658, FIcnt: 26169 (60df9b)
# 23. 61ac71 8815, FIcnt: 19623 (66840d)
# 24. 671dbf 6728, FIcnt: 13080 (6acfdf)

# 25. 70e12a 9940, FIcnt: 44598 (7656fa)   36/24
# 26. 77b406 8351, FIcnt: 35673 (7bc7e6 or 7c4a62)
# 27. 7d61b4 6673, FIcnt: 26754 (80a3d4 or 810c18)
# 28. 81ddbc 4992, FIcnt: 17838 (844dbc or 849bbc)

# 29. 855093 10, FIcnt: 30 (8551d3 or 8551fb)
```

The result:



Nurgle_Dreadnought.jpg (145.41 KiB) Viewed 241 times


btw: lower lods are rather detailed, too, so not sure, whether it's really lods or something else
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-02-26T12:09:02+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

I have a maxscript for geometry import only (characters, npc, enemies, weapons), bones might work only for characters, had no luck finishing it for the moment! I have plans later on, or more like I have a will for this - but not the strength aha ha ha
## Post #15
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-02-27T00:12:45+00:00
- Post Title: Inquisitor: Martyr Noesis plugin Commission

Awesome work on the format guys! and I'm very interested in your max script, if you ever get it finished to the point where it can import fully rigged and textured models from this game, there's a nice sack of cash in it for you C:
## Post #16
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-04-17T10:34:47+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from zaramot ↑Tue Feb 26, 2019 8:09 pm at Tue Feb 26, 2019 8:09 pm
>
> 
I have a maxscript for geometry import only (characters, npc, enemies, weapons), bones might work only for characters, had no luck finishing it for the moment! I have plans later on, or more like I have a will for this - but not the strength aha ha ha

I also would pay for a working version of that script.

I have been batch converting warhammer (and other) game models to (at some point) upload them to modelresource.
Here is what I have so far for those interested [https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ](https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ)
## Post #17
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-04-17T17:54:22+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Wow! It's an awesome job you have done    Thanks a lot fot Battlefleet Gothic 2 Armada files!
## Post #18
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-04-17T17:55:51+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from 09williamsad ↑Wed Apr 17, 2019 6:34 pm at Wed Apr 17, 2019 6:34 pm
>
> 
zaramot wrote: ↑Tue Feb 26, 2019 8:09 pm
I have a maxscript for geometry import only (characters, npc, enemies, weapons), bones might work only for characters, had no luck finishing it for the moment! I have plans later on, or more like I have a will for this - but not the strength aha ha ha


I also would pay for a working version of that script.

I have been batch converting warhammer (and other) game models to (at some point) upload them to modelresource.
Here is what I have so far for those interested https://mega.nz/#F!LLoByYIY!LEZ9B43WuQZRHsE7aQO5uQ

Holy crap, William! This is amazing, thanks for your dedicated efforts to extract all these!
## Post #19
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-07-19T19:11:35+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from zaramot ↑Thu Apr 18, 2019 1:54 am at Thu Apr 18, 2019 1:54 am
>
> 
Wow! It's an awesome job you have done    Thanks a lot fot Battlefleet Gothic 2 Armada files!

I don't suppose you have made any progress with the import script?
I have started ninjaripping from inquisitor martyr and it is a pain, models are in multiple parts and take multiple rips on the same scene to extract.
## Post #20
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-07-19T19:27:25+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Yeah, I'd like to see a functional 3ds max script sometime soon, I'm willing to pay 50-100 USD to anyone who can do this for us.
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-07-19T21:10:01+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Do you have discord or skype, where someone could test - provide samples realtime and discuss bug reports online too? The game was quite updated recently, someone said it's like a new game, I should check models once again xD
## Post #22
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-07-20T06:21:50+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from zaramot ↑Sat Jul 20, 2019 5:10 am at Sat Jul 20, 2019 5:10 am
>
> 
Do you have discord or skype, where someone could test - provide samples realtime and discuss bug reports online too? The game was quite updated recently, someone said it's like a new game, I should check models once again xD

Is that question directed at me, kingfisher13 or both?
## Post #23
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-07-20T07:26:09+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Either way, samples <Link removed due to site policy>
## Post #24
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-07-20T10:52:54+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from 09williamsad ↑Sat Jul 20, 2019 2:21 pm at Sat Jul 20, 2019 2:21 pm
>
> 
zaramot wrote: ↑Sat Jul 20, 2019 5:10 am
Do you have discord or skype, where someone could test - provide samples realtime and discuss bug reports online too? The game was quite updated recently, someone said it's like a new game, I should check models once again xD

Is that question directed at me, kingfisher13 or both?

Both! And thanks for samples  I'll take a look. lets hope if they changed something - they did it, and made it easier xD
## Post #25
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2019-07-20T11:19:33+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

> Reply from zaramot ↑Sat Jul 20, 2019 6:52 pm at Sat Jul 20, 2019 6:52 pm
>
> 
09williamsad wrote: ↑Sat Jul 20, 2019 2:21 pm
zaramot wrote: ↑Sat Jul 20, 2019 5:10 am
Do you have discord or skype, where someone could test - provide samples realtime and discuss bug reports online too? The game was quite updated recently, someone said it's like a new game, I should check models once again xD

Is that question directed at me, kingfisher13 or both?


Both! And thanks for samples  I'll take a look. lets hope if they changed something - they did it, and made it easier xD

Sent discord ID to you incase you need more samples or rips for comparison.
## Post #26
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-07-20T13:28:47+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Hmm, I haven't received your discord id    Maybe you sent it to someone else?
## Post #27
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-07-21T21:19:38+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Hey guys, I set up a discord server for the study and conversion of these models, here's the link: [https://discord.gg/B3bTSRx](https://discord.gg/B3bTSRx)

Let's use this server to coordinate and share our work.
## Post #28
- Username: tomke
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 12, 2019 2:36 am
- Post datetime: 2019-07-30T14:24:34+00:00
- Post Title: Re: Inquisitor: Martyr Noesis plugin Commission

Just BIG thank you
