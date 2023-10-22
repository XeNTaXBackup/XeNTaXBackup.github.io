## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-08T15:30:29+00:00
- Post Title: Heavy Rain BIGFILE

i have here three samples from this game a cut from a 1gig .dat file a .dep file and a sdat file. seems to be quantum dreams proprietary archive rather then sony's.




thanks appreciate it.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-09-09T00:51:07+00:00
- Post Title: Heavy Rain BIGFILE

.sdat is an encrypted Sony format.

Other formats don't look too difficult, interesting to know that Heavy Rain uses Lua for scripting.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-09T00:57:37+00:00
- Post Title: Heavy Rain BIGFILE

hmm okay if its not to difficult in trying to unpack them then nice
## Post #4
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-09T06:54:45+00:00
- Post Title: Heavy Rain BIGFILE

It seems, this game use the engine of Fahrenheit/Indigo Prophecy (of course upgraded newer version) or just the structure is very similar; Unicode text with ASCII ID, and DDS textures.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-09T12:51:23+00:00
- Post Title: Heavy Rain BIGFILE

Are there any tools to unpack this type of engine files? like for example indigo prophecy tools would work?
## Post #6
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2010-09-16T15:25:10+00:00
- Post Title: Heavy Rain BIGFILE

There is a tool for Fahrenheit, but it extracts only millions of small parts of it. The archives used in Heavy Rain are similar, but no one figured out yet, how this strange system works. You can scan the archives for some formats (the music is 128k MP3), but all you get are 1-second chunks. 
Merging those files together afterwards doesn't work, either. Every music file (chunk) consists of three parts, played one after the other. This may be some kind of surround thing. And even if you delete the last two parts of each chunk, the files don't fit together properly. Someone really needs to understand this archive format!

I uploaded the first music cue [here](http://www.multiupload.com/6LSPT1KXBV). It consists of 106 parts and runs about 1:45 min. I really give up on this one.
## Post #7
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-09-27T16:20:53+00:00
- Post Title: Heavy Rain BIGFILE

So, Extractor 2.5 unpack from heavy Rain .dat files .mp3 files, which appear pieces(dinamic music?).

STUNS unpack .dat files as LZO and Deflate.

Also I cut begin and end of BigFile_PS3.dat and BigFile_PS3.d01.

piece from BigFile_PS3.dat:

> QUANTICDREAMTABINDEX   
>
> --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------QZIP COM_CONT           i  и       LOADCONT       SINT_SEC      y      DifficultyLevel                   ConfusionLevel                    ProductionStoryboard        ~яяяяSCRIPT      ёз   
>
> HEAVY_RAIN ёМif (QDR.nScId == nil) then QDR.nScId = 0 end
>
> -- Context Table Creation
>
> QDR.HEAVY_RAIN_Var = { default_ctx = {} }
>
> QDT.GAME_MANAGER.New("HEAVY_RAIN", 2)
>
> 
>
> -- Template Declaration
>
> 
>
> -- Attribute Declaration
>
> QDT.THIRD_PERSON_GAMEPLAY.NewPlaced("HEAVY_RAIN_Var", "ThirdPersonGameplay", 0)
>
> QDR.HEAVY_RAIN_Var.ParSuccess = false
>
> QDT.VECTOR.NewPlaced("HEAVY_RAIN_Var", "VectorTempGlob", 0)
P.S.: By the way, where I can get Fahrenheit/Indigo Prophecy tools?
[heavy_rain.rar](https://xentaxbackup.github.io/file/3483_heavy_rain.rar)
## Post #8
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2010-12-07T15:30:19+00:00
- Post Title: Heavy Rain BIGFILE

[This](http://www.ps3news.com/forums/ps2-news/fahrenheit-tool-5282.html) is the only tool I know of. You can select the bigfile_xbox.idx table and the bigfile_xbox.dat archive of the XBOX version of Fahrenheit and somehow extract all files. However, the tool doesn't work with my PC version and I don't know, what type the extracted files have afterwards.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-03-18T04:12:25+00:00
- Post Title: Heavy Rain BIGFILE

Any update to this?
## Post #10
- Username: Venushja
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 19, 2010 11:13 pm
- Post datetime: 2011-05-27T13:31:59+00:00
- Post Title: Heavy Rain BIGFILE

Hey guys ... How I can unpack text file ? Thanks for answer.
## Post #11
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-01-14T01:53:52+00:00
- Post Title: Heavy Rain BIGFILE

does anyone know if quickbms can extract files from BIGFILE thing?
## Post #12
- Username: cyberpunk2012
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 16, 2012 10:54 pm
- Post datetime: 2012-01-16T15:18:57+00:00
- Post Title: Heavy Rain BIGFILE

> Reply from lion589
>
> does anyone know if quickbms can extract files from BIGFILE thing?
you need the game script to use quickbms with the BIGFILE as every game is different
## Post #13
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2012-03-02T21:27:26+00:00
- Post Title: Heavy Rain BIGFILE

I really want to translate this game! I still believe that someone will find a way around those BIGFILES. I saw that the russians has already translated the game so there is hope.
## Post #14
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2012-05-12T15:16:00+00:00
- Post Title: Heavy Rain BIGFILE

> Reply from evin
>
> It seems, this game use the engine of Fahrenheit/Indigo Prophecy (of course upgraded newer version) or just the structure is very similar; Unicode text with ASCII ID, and DDS textures.
I only managed to extract the music, speech and sfx from the game. Haven't found code that indicates DDS textures.
## Post #15
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-30T10:53:06+00:00
- Post Title: Heavy Rain BIGFILE

> Reply from FunnyML
>
> 
I only managed to extract the music, speech and sfx from the game. Haven't found code that indicates DDS textures.Because the DDS header is missing.

> Reply from 3pacalypse
>
> I really want to translate this game! I still believe that someone will find a way around those BIGFILES. I saw that the russians has already translated the game so there is hope.As you can see in the attachment, the Russian translation is official.


I could extract some texts.
No repacker, and the unpacker is still under develop!
[HeavyRainTextSample.zip](https://xentaxbackup.github.io/file/5474_HeavyRainTextSample.zip)
## Post #16
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2012-05-30T15:47:19+00:00
- Post Title: Re: Heavy Rain BIGFILE

We are waiting unpacker and repacker Evin
## Post #17
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-05-31T18:19:55+00:00
- Post Title: Re: Heavy Rain BIGFILE

What is done: text extractor, texture->DDS converter.
The game use a lot .segs file. Because I didn't find a lot texts, I'm working on, to I can unpack them. I know, it's use zlib compression.
## Post #18
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-01T00:41:16+00:00
- Post Title: Re: Heavy Rain BIGFILE

> Reply from evin
>
> What is done: text extractor, texture->DDS converter.
The game use a lot .segs file. Because I didn't find a lot texts, I'm working on, to I can unpack them. I know, it's use zlib compression.

wow great to see someone working on this game.
please man continue working till you reach extracting the characters models, thanks a billion.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-06-01T00:52:52+00:00
- Post Title: Re: Heavy Rain BIGFILE

How about sounds/music?
## Post #20
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-06-01T06:53:51+00:00
- Post Title: Re: Heavy Rain BIGFILE

My first priority is to edit the texts and textures. And because the most files are compressed into these .segs files, if I can unpack them, maybe there are the model/sound files too.
## Post #21
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-01T12:57:55+00:00
- Post Title: Re: Heavy Rain BIGFILE

> Reply from evin
>
> My first priority is to edit the texts and textures. And because the most files are compressed into these .segs files, if I can unpack them, maybe there are the model/sound files too.

you're making my dream come true
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-01T13:03:11+00:00
- Post Title: Re: Heavy Rain BIGFILE

segs are a common ps3 format. luigi made a script here for one game you can modify it easily for these segs files or into your code.
[http://aluigi.altervista.org/papers/bms/arcsys.bms](http://aluigi.altervista.org/papers/bms/arcsys.bms)
## Post #23
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-06-02T07:14:42+00:00
- Post Title: Re: Heavy Rain BIGFILE

I already tried, but it doesn't want to work. And I have to put back the files, and QBMS can't repack it.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-06-02T09:30:22+00:00
- Post Title: Re: Heavy Rain BIGFILE

if you want to work together on heavy rain let me know i did some work a while ago on the format. If you have some kind of im program let me know via pm.
## Post #25
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2012-06-07T19:15:08+00:00
- Post Title: Re: Heavy Rain BIGFILE

Guys, you're making my dream come true aswel
## Post #26
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-09T16:16:34+00:00
- Post Title: Re: Heavy Rain BIGFILE

have you finished writing the unpacker yet or still there is a long way to go?
## Post #27
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-06-09T19:10:37+00:00
- Post Title: Re: Heavy Rain BIGFILE

Long way. Look how "old" is this game. This won't solve in a couple of weeks. And I'm not working on it every day either.
## Post #28
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-06-09T20:20:16+00:00
- Post Title: Re: Heavy Rain BIGFILE

> Reply from evin
>
> Long way. Look how "old" is this game. This won't solve in a couple of weeks. And I'm not working on it every day either.
it looks gonna be a long wait
## Post #29
- Username: FunnyML
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 04, 2007 1:45 am
- Post datetime: 2012-06-10T01:30:45+00:00
- Post Title: Re: Heavy Rain BIGFILE

Regarding the music, I'm still working on it. Extracted and deinterleaved half the score in the game/setup fiiles. Have to stop for a while since I'm moving to another place and won't be able to use my notebook.
## Post #30
- Username: lion589
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Oct 13, 2011 12:48 am
- Post datetime: 2012-08-05T04:18:48+00:00
- Post Title: Re: Heavy Rain BIGFILE

is there a way to extract the segs from the bigfiles?
## Post #31
- Username: 3pacalypse
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Jul 08, 2010 10:17 am
- Post datetime: 2012-08-18T02:53:17+00:00
- Post Title: Re: Heavy Rain BIGFILE

Guys, please don't give up on this one!
## Post #32
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2012-08-25T08:32:57+00:00
- Post Title: Re: Heavy Rain BIGFILE

The tools, so far: [viewtopic.php?f=32&t=9544](http://forum.xentax.com/viewtopic.php?f=32&t=9544)
## Post #33
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2013-04-02T10:43:02+00:00
- Post Title: Re: Heavy Rain BIGFILE

Any news?
## Post #34
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2013-05-09T22:04:06+00:00
- Post Title: Re: Heavy Rain BIGFILE

Yeah, actually I'm curious too... are the models from this game extractable at all?
