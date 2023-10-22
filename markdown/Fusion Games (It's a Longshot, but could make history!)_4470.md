## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-17T23:06:21+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Well folks, this is the big one. I have no other alternative now but to ask for help. If we unravel this we'll have the entire web gaming community handled. I'm of course talking about Multimedia Fusion games. Part of my project consists of obtaining the graphics from three different games all made in Multimedia Fusion. If you didn't know, Multimedia Fusion is a gaming and animation engine similar to flash but more geared towards making games. It outputs EXE files and sometimes configuration files. Now, mind you I will only be supplying the EXE's as they will not work without the other files. However, the graphics are clearly contained within the EXE's. What I need is a method to extract the graphic resources of these files. If we here at Xentax manage to clear this hurdle we will make history.

Contained in the rar file below are the three EXE files I require the graphics from. Have a look as you wish, and see what you can do. With any luck it'll be a simple operation.
[http://www.sendspace.com/file/syp4pl](http://www.sendspace.com/file/syp4pl)
## Post #2
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-05-19T17:51:34+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

I'm usually behind stuff like this, and this is no exception. However, it's a bit much to ask considering it would unravel an entire game engine format. Despite this, I am fully behind this project and am willing to offer any help I can, be it providing new games to analyze and various information I can gather, or keeping in contact with other people working on this.

I hope we can get these unraveled. It would be a real gift to decompilers and sprite rippers, and people who need to recover their files from an already-made exe.

I've run through them with Filestripper, for a lot of false positives with it, saying it saves files but fails to produce anything. I know the files are there though.
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-20T00:21:32+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

The reason people will get a lot of false positives from scanning these Exe files with a bruteforcescanner is because they are compressed,
i did unpack Lop.exe so far by executing it, dumping the RAM image of what the application used. (this was Stdrt.exe) and then scanned it manually,
lots of RIFF/WAVE files could be ripped. i could see graphics with a raw scanner, however i cannot determine on how to rip out the graphics yet in a decent manner.

Ive got all the sounds though =P
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-20T04:38:27+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

What I'm concerned on is graphics. Specifically NL and NL2's graphics. LOP is just there for research purposes and a side-project to me if I ever get around to it.
We've made progress at least now!

Just remember to post detailed instructions on how to do the dumping when you've got it figured out!

Thanks a lot for the quick help!
## Post #5
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-05-20T15:10:17+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Good work! Sounds are a plus! Though we're searching for graphics, finding ANYTHING is always a good thing.

I've added some games for research purposes, and I highly reccomend playing one called 'Aquaria' by Derek Yu. Not only is it a great game, but the graphics are stunning and would be a grand acquirement for someone like me. However I have not included it in this little pack as it is a paid game.
The games included in this pack are:
-Super Mario World Dark Horizon
-I'm OK
-Eternal Daughter
-Spelunky
[http://www.sendspace.com/file/gvyv4z](http://www.sendspace.com/file/gvyv4z)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-05-20T16:08:44+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Okay, managed to decompress a whole Exe file with some Zlib bruteforcing. everything is open now.
the only bad thing about this is that the graphicsfiles in the exefile are totally without any headers, so this is gonna
take some time to make up a nice detector. =X
## Post #7
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-20T18:12:21+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Wow! You're awesome. I can't wait to see what comes out of this.

Figuratively of course. I CAN wait, but don't WANT to, understandably. In any case, I'm patient, and I can tell you've got a good mind for this! Keep up the good work!
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-23T12:47:33+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

The PE is just an unpacker/linker for the actual game exe etc. At the end of the PE there is each time an extra bulk that contains exe, dll and resource files. In NL2 and LOP the resources are Zlib packed. In the NL they are not. I'm investigating a plugin for MultiEx Commander for this.
## Post #9
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-24T15:03:05+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Huh, so is it possible to extract anything properly?

I still have yet to donate my $10 to the MultiEx Commander project and get the full version, mainly due to my card STILL being delayed. Anyway, I'll get to it once I have a chance.
## Post #10
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-05-25T18:41:15+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

I'd assume the difference in the files would have to do with the version of Multimedia Fusion it was made with. There's probably going to be different unpacking methods for some of these files. I'd love to see what comes from this.
## Post #11
- Username: Zazz
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 25, 2010 2:39 pm
- Post datetime: 2010-05-26T03:15:54+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

> Reply from EldritchDecross
>
> I've added some games for research purposes, and I highly reccomend playing one called 'Aquaria' by Derek Yu. Not only is it a great game, but the graphics are stunning and would be a grand acquirement for someone like me. However I have not included it in this little pack as it is a paid game.
You might not know yet, but Aquaria along with several other indie games are going open source, so all of its resources should become more readily accessible.

[http://www.wolfire.com/humble](http://www.wolfire.com/humble)

And yes it's an awesome game.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-27T21:46:41+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

```
2322	Unknown	Unknown		
2422	String	Game name	Noitu Love 2: Devolution	
2F22	String	Game original file path	D:\Mina Egna Spel\Devolution\Compiled\Build Versions\0.9c\Noitu Love 2 - Devolution.exe	
2E22	String	Game resource file?	D:\Mina Egna Spel\Devolution\devolution6.mfa	
3522	Image	Game icon 16x16		This contains the 256 colour palette as well
2622	Button captions	Title buttons?		
2C22	Unknown	0	4 zero-bytes	Is not compressed, and next log is size of data (4) and data is 4 0 bytes
3422	mfx file information 	properties of mfx (executables for the game)	........%.Y........kcwctrl.mfx.......%.Y........kcdirect.mfx.......%.Y........KcArray.mfx.......%.Y........txtblt.mfx.......%.Y........AssArray.mfx..3....%.Y........clickteam-movement-controller.mfx..!....%.Y........ModFusionEX.mfx.......%.Y........KcBoxB.	mfx files are also packed before the PAME
3122	name property	name of a dll 	..cctrans.dll.	
2922	archive	contains other files		Is not compressed, and next long is size of data 
		file starts with a uint32 and then all entries		
4444	Unknown	Unknown		Sound info?
4544	String	Title of a MFX ?	ModFX 3: ModFusion eX	
4644	Unknown	Unknown		got something like FMCA
7F7F	Empty/End	either an empty entry (null) or end of something	followed by 4 zero-bytes	
4544 (nc)	String	Title of a MFX ?	Active	
4644	Unknown	Unknown		got something like SPRI
7F7F	Empty/End	either an empty entry (null) or end of something	followed by 4 zero-bytes	
---				
4544	String	Title of a MFX ?	Active 2	
4644	Unknown	Unknown		got strings: SPRI, STDTFADE, cctrans.dll. Note that cctrans has something to do with transition, and STDTFADE would be standard fade? 
--				
4544	String	Title of a MFX ?	Text Blitter	
		these seem to point to Game Factory  extensions ....		Counter 2....Letter Rating and more
3722	Unknown	Unknown		
2B22	Unknown	Unknown		
4022	Unknown	Unknown	one byte	the DATASIZE uint32 that follows says 1, and then the var comes, a zero byte.
3333	archive	contains other files		Is not compressed, and next long is size of data 
		file starts with entries immediately		
3433	Unknown	Unknown		Maybe graphics info?
4233	Unknown	Unknown		Again, graphics info?
3533 (nc)	String	Name of graphics?	Black	This was not compressed, so followed by size var and then the string
3733	256-c palette	256 colour RGBA pallette		The palette starts with an uint16 that is 768, and then a uint16 that is 256. So the ALPHA is ignored (RGB = 3 bytes x 256 = 768)
4133	Unknown	Unknown		Says "Layer 1" at the end
3833				
3d33	Unknown	Unknown		This starts with ER>> and ends with <<ER and contains various info
3c33	Unknown	Unknown		Again talking about STDTFADE and cctrans.dll
7F7F	Empty/End	either an empty entry (null) or end of something		

```


I'm busy figuring this format out.
## Post #13
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-29T20:16:34+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

This clearly won't be a simple BMS script when finished. Out of curiosity though, do you plan on making it a plugin of MultiEx Commander, or will it be possible to have a seperate program to extract everything from these files?

I'm glad we've got interest in this format. I'm optimistic of course with such intelligent people working on this project. Hopefully we can get it figured out soon with our combined forces. Let me know if you need any other examples of this format. I have many readily available.

Thanks a lot for the help so far!
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-05-30T20:40:29+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

I haven't decided on a plugin or stand-alone yet.
## Post #15
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-05-31T02:56:38+00:00
- Post Title: Fusion Games (It's a Longshot, but could make history!)

Well, good luck in any case! I hope you decide on standalone, as I have limited access to my home computer due to classes.
## Post #16
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-06-02T14:53:03+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

I personally believe a standalone would be better as it would most likely be more customizable and easier to make detections. I have no idea how MultiEx Commander works though so I may be wrong. Standalone seems ideal however as many people need to extract from these types of games and hopefully would not have to make a purchase to do so.
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-02T15:49:25+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

> Reply from EldritchDecross
>
> Standalone seems ideal however as many people need to extract from these types of games and hopefully would not have to make a purchase to do so.

Nobody buys MultiEx Commander, they donate to XeNTaX and as a return favour they get more MultiEx Commander options. It is a token of gratitude for all the hard work, the many, many, many hours that went into it. A plugin for MultiEx Commander would take less time. A standalone would take considerably more effort and time. And what is the reward for that?
## Post #18
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-06-02T18:23:15+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

I see. Well, go with what works best and takes less work to do. I'm horribly uneducated to the world of programming, ahahaha. Just as long as it happens. Out fo curiosity though, what are the extra features that get added when one donates?
## Post #19
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-06-11T22:36:08+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

I'm looking forward tot he outcome of this project. It would be a real breakthrough for sprite rippers, comic makers, those with an interest on how the games works...it could help a lot of people out!
## Post #20
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-08-23T11:41:05+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

It's been a while, but I'm here for at least one day. Has there been any progress on this? I like to stay informed. Is there anything I can do to help anyone? I really would like to have these figured out...
## Post #21
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-10-26T19:15:01+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

Has this project been abandoned?

I know Strobe got something out of these files.

Anyway, here's something you guys could tinker around with. A protected CCA file. Not mine obviously but I was wondering if it was possible to extract these as well.

[http://www.sendspace.com/file/b9evb5](http://www.sendspace.com/file/b9evb5)

It may be easier just to find a way to unprotect this, as they are able to be opened by Multimedia Fusion itself and can be extracted if unprotected.
## Post #22
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2011-04-26T19:40:35+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

Don't mean to necropost but what ever happened to this? It's a major format used all over the place and cracking it would be a major breakthrough. Does anyone know what happened to Strobe?
## Post #23
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-12-25T01:28:17+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

[http://forums.sonicretro.org/index.php?showtopic=24592](http://forums.sonicretro.org/index.php?showtopic=24592)
Someone apparently unraveled the CCA format properly, and if you snoop around a bit you can get a program that views the cca contents properly...unfortunately neither of these work with NL or NL2...
## Post #24
- Username: Corak
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 13, 2014 9:34 am
- Post datetime: 2016-04-28T23:05:14+00:00
- Post Title: Re: Fusion Games (It's a Longshot, but could make history!)

How's Progress with ripping Fusion Games game resources from .exe? (mmf2)
I wanted to rip music from game "Castle In The Darkness". Tried from memory dump.. But it dumps only songs that must be active in part of the game, so I have to complete whole game to dump all the song.
Game can be downloaded from here.
[http://m.vk.com/doc-62542735_437463511](http://m.vk.com/doc-62542735_437463511)
