## Post #1
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-24T18:07:20+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Hi all!

Just a few notes on usage before the link. The program can output either Microsoft .WAV (for multichannel, use switch -mc) and .MP3 (with no information loss; EALayer3 uses the MPEG audio layer 3 codec). If you don't want to output to a multichannel wave, you can uses the switch -s all to extract the streams to different files.

It can read a few different variations on EALayer3 including version 5, version 6 and 7 (though it might be either 6 or 7), two .ASF formats (SCHl PT and SCHl GSTR), and this one ([http://hcs64.com/mboard/forum.php?showthread=18598](http://hcs64.com/mboard/forum.php?showthread=18598) though only two files of the archive posted there are EALayer3). I'm sure there are more variations out there though.

After browsing a few forums it looks like there is interest in converting from .MP3 or .WAV to EALayer3. This is definitely doable, and shouldn't be too difficult either. 

On the download page there is a link to the source code, which you're free to use in any project in whole or in part.

[http://bitbucket.org/Zenchreal/ealayer3/downloads](http://bitbucket.org/Zenchreal/ealayer3/downloads)

Your feedback is greatly appreciated
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-24T18:11:06+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Thanks so much zench!!
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-24T18:13:29+00:00
- Post Title: EA Layer 3 Extractor/Decoder

> Reply from Zench
>
> http://bitbucket.org/Zenchreal/ealayer3/downloads
Your feedback is greatly appreciated
Nice that you use bitbucket/mercurial
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-24T18:24:18+00:00
- Post Title: EA Layer 3 Extractor/Decoder

> Reply from Rheini
>
> Zench wrote:http://bitbucket.org/Zenchreal/ealayer3/downloads
Your feedback is greatly appreciated 
Nice that you use bitbucket/mercurialYeah, and actually you had something to do with it. When I was downloading your OpenBB project I actually thought BitBucket was pretty convenient so I decided to use it. 


EA Layer 3 Format:

Or at least some of it. The format used for the blocks is omitted, and all the MPEG stuff is omitted. This should be enough for someone familiar with MPEG to figure it out, though. I'm not an expert, though, so my terminology might be slightly incorrect.

```

	if version 5:
	
		8 bits - nonzero indicates the presence of uncompressed samples at the end of the granule 
	
	if version 6 or 7 (CHECK):
	
		1 bit - there is an extended header
		1 bit - unknown
		2 bits - unused
		12 bits - total granule size including this small header and uncompressed samples
		
		if extended header:
		
			2 bits - mode
			10 bits - sample frames to discard (mode == 0) or skip (mode == 1 or 2) before outputting the uncompressed samples (CHECK!)
			10 bits - number of uncompressed sample frames at the end of the granule
			10 bits - granule size (can be zero)
	
	all versions:
	
		2 bits - MPEG version
		2 bits - MPEG sample rate index
		2 bits - MPEG channel mode
		2 bits - MPEG mode extension
		1 bit - which granule
		
		if granule is 1 and version is 3 (MPEG 1.0):
		
			channels * 4 bits - MPEG scfsi
			
		MPEG side info beginning after scfsi for each channel
		MPEG data
		
	if version 5 and there are uncompressed samples:
	
		32 bits - number of uncompressed sample frames
		32 bits - offset in the outputted granule these samples go (CHECK)
		channels * uncompressed * 16 bits - uncompressed PCM samples
	
	if version 6 or 7 and there are uncompressed samples:
	
		channels * uncompressed * 16 bits - uncompressed PCM samples


That was one granule. No go back to the beginning!
```
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-24T18:44:26+00:00
- Post Title: EA Layer 3 Extractor/Decoder

> Reply from Zench
>
> Yeah, and actually you had something to do with it. When I was downloading your OpenBB project I actually thought BitBucket was pretty convenient so I decided to use it.
Yep, I use Mercurial more and more for all my active projects
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-24T18:52:28+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Ladies and gentlemen - Zench scores AGAIN!!!!!

Gotta grab this and try it out on some files! THANKS A LOT!!
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-24T18:58:51+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Yep zench you did it again! 

Works fawlessley on nfs world sns files and Tiberian Twiliight
## Post #8
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-24T19:11:55+00:00
- Post Title: EA Layer 3 Extractor/Decoder

You are my hero now.
I've waited sooooo long for a decoder.
## Post #9
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-08-25T09:23:57+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Thank you for this decoder, I will be using your code in my C&C3/RA3/C&C4 tools so that my extractor can extract EALayer3 as well as ADPCM.
## Post #10
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2010-08-25T15:08:25+00:00
- Post Title: EA Layer 3 Extractor/Decoder

It works perfect with SNS files of Burnout: Paradise. Thank You Soooooo much!
## Post #11
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-25T20:36:29+00:00
- Post Title: EA Layer 3 Extractor/Decoder

To everyone who replied: you're welcome. I had fun making it.
## Post #12
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-08-27T21:54:41+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Zench, you are the man.  I would click the Thank Post button, were it not that it has gone missing after a phpbb upgrade.
## Post #13
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-28T14:44:17+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Thank you very much Zench for this tool. Glad I can output to .mp3 .wav or even multi-channel .wav (wasn't expecting that but there you go)

Once again, cheers for all your hard work.
## Post #14
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-29T01:34:07+00:00
- Post Title: EA Layer 3 Extractor/Decoder

I feel absolutely honored
## Post #15
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-08-29T16:12:42+00:00
- Post Title: EA Layer 3 Extractor/Decoder

Your code is great, I already added it to my C&C3/RA3/C&C4 tools.
I also pointed some Sims 3 guys towards your code (because Sims 3 uses EALayer3 for music)
## Post #16
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-29T22:52:32+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I've already re-ripped all the Sims 3 games' music.

But this tool will make it even easier when I rip the next one which comes out in just over a week's time.
## Post #17
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2010-09-16T13:40:25+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

It works great!!! you are god Zench!

But pls do you know how i can convert an mp3 file back to .sns?? or any other ? wav,ogg?  i want to replace the songs in EA Sports FIFA 11 PC demo.
## Post #18
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-16T23:45:59+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from XStalker
>
> But pls do you know how i can convert an mp3 file back to .sns?? or any other ? wav,ogg?  i want to replace the songs in EA Sports FIFA 11 PC demo.I'm working on that right now. Actually I'm going to work on it Friday. Shouldn't actually take too long.
## Post #19
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2010-09-17T12:57:28+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from Zench
>
> XStalker wrote:But pls do you know how i can convert an mp3 file back to .sns?? or any other ? wav,ogg?  i want to replace the songs in EA Sports FIFA 11 PC demo.I'm working on that right now. Actually I'm going to work on it Friday. Shouldn't actually take too long.

Thank you so much Zench! you will be remembered for this in FIFA modding community, i tell you
## Post #20
- Username: GodOfWar
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Apr 05, 2010 11:35 am
- Post datetime: 2010-09-18T01:05:36+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #21
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-18T01:15:33+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2010-09-18T10:04:07+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Later edit : nvm
## Post #23
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-09-27T21:48:42+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #24
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-09-28T06:34:50+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I think those are EA's ADPCM what i tried decode earlier.
## Post #25
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-10-08T18:46:57+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

[Encoding support added in version 0.6.0](http://bitbucket.org/Zenchreal/ealayer3/downloads)  

Currently the only output format supported is headerless version 5, which looks to be the most common format (should work with FIFA). Also, uncompressed samples aren't supported yet; it only makes a difference on tracks that need seamless looping.

Example usage: ealayer3 -E mp3file.mp3 [-o ealayer3file.sns]

And yes, the input has to be an MP3 file. I didn't really want to have to include an MP3 encoder in the tool, so you can use just about any encoder and bitrate you like. Side note: it looks like I forgot to update the usage inside the program. I'll do that when I make some other fixes as well.
## Post #26
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-10-08T18:53:22+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Thanks a lot Zench. Good to see you're still working on this tool
## Post #27
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-10-09T00:36:10+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Do you know if this encoder will produce files that can be used with Command & Conquer 3 or Red Alert 3?
## Post #28
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-10-09T06:25:43+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo
>
> Do you know if this encoder will produce files that can be used with Command & Conquer 3 or Red Alert 3?I believe so. And if not it wouldn't be too hard to add support.
## Post #29
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-10-09T08:19:53+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Works with Battleforge .SNS(but dont work with .SNR)

Do not quite understand what you want to use decoding options for Red Alert 3 .cdata files.
## Post #30
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2010-10-09T10:43:22+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from Zench
>
> Encoding support added in version 0.6.0  

Currently the only output format supported is headerless version 5, which looks to be the most common format (should work with FIFA). Also, uncompressed samples aren't supported yet; it only makes a difference on tracks that need seamless looping.

Example usage: ealayer3 -E mp3file.mp3 [-o ealayer3file.sns]

And yes, the input has to be an MP3 file. I didn't really want to have to include an MP3 encoder in the tool, so you can use just about any encoder and bitrate you like. Side note: it looks like I forgot to update the usage inside the program. I'll do that when I make some other fixes as well.

Thats simply great Zench!  you're the man man!! 

Sorry for the noobie question, but how do i do it now? i drag the mp3 file into the ealayer3.exe but it doesnt want to convert to .sns. What i am missing   ?
## Post #31
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-10-09T16:17:30+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Its command line tool, use cmd.exe to command it with the command when you are in same folder as tool and file to convert should be same folder or make yourself a bat file.

Anyway tested on C&C3, plays the converted file flawless. Just needed use same khz as original or bad crash due to separate stream header elsewhere which may apply to other EA games using same ealayer3 format style.
## Post #32
- Username: XStalker
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 16, 2010 9:28 pm
- Post datetime: 2010-10-09T17:39:35+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from Apollo
>
> Its command line tool, use cmd.exe to command it with the command when you are in same folder as tool and file to convert should be same folder or make yourself a bat file.

Anyway tested on C&C3, plays the converted file flawless. Just needed use same khz as original or bad crash due to separate stream header elsewhere which may apply to other EA games using same ealayer3 format style.

Can you post the example in a screenshot pls? i cannot figure out the [-o ealayer3file.sns] line. 

I did C:\Documents and Settings\STALKER\Desktop\ealayer3-0.6.0-win32\ealayer3.exe" -E "C:\Documents and Settings\STALKER\Desktop\ealayer3-0.6.0-win32\2.mp3" 

And it converts, but to .ealayer3 format.

Oh nevermind   i figured it out finally. It was those brackets fault [ ] thanks for the tip btw 

Ok tested it in FIFA 11 PC, it works , i can hear the song, but at the same time the other sounds starts acting crazy. Could it be because i need to change the bitrate to the correct one? gonna try it now.
Yea well so the solution to that stretchy sound is clearly the correct mp3 settings. Decoding the original songs and encoding them with Zench tool works top notch. I get a dont send error when trying to encode the original song, but it doesnt really matter, since it still converts the song just fine. Weird. Im using Win XP SP2

Yea everything works perfect now. The .mp3 file first must have the bitrate 210+ in order to play fine. Thanks again Zench, you are amazing!
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-10T01:23:59+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

[http://www.megaupload.com/?d=A6CSWSKY](http://www.megaupload.com/?d=A6CSWSKY)

Having problem decoding this ea layer 3 track from medal of honor, tells me a bug is in the program.
## Post #34
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2010-11-27T08:47:52+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

EA Layaer 3 Extractor doesn't work properly with xxx files of Medal Of Honor 2010(PC). it seems these files contain more than one stream and EA Layaer 3 Extractor only extract first stream.
Is there any option in EA Layaer 3 Extractor to extract all streams?
## Post #35
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2010-12-03T13:24:30+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

On cncmods.net have info about extracting music from RA3 and Uprising - [http://www.cncmods.net/forums/index.php?t=msg&th=212](http://www.cncmods.net/forums/index.php?t=msg&th=212)

Main problem is mus.exe. Same crash on my system (Win 7)(APPCRASH).

Need help.
## Post #36
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-12-11T00:50:22+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from RedDeadRedemption
>
> EA Layaer 3 Extractor doesn't work properly with xxx files of Medal Of Honor 2010(PC). it seems these files contain more than one stream and EA Layaer 3 Extractor only extract first stream.
Is there any option in EA Layaer 3 Extractor to extract all streams?Yes: -s all
It will create an MP3 file for each stream.
## Post #37
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2010-12-14T09:22:45+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Yes: -s all
>
> It will create an MP3 file for each stream.

Thanks for reply. but it didn't work.

Here are two sample files of Medal Of Honor 2010 (PC): [link](http://www.box.net/shared/p2l03ukofp) ( one of these files is just a little directory archive. )
Can ealayer3.exe extract/decode these files?
Thanks for helping!
## Post #38
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-05-02T00:08:36+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #39
- Username: amik91
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 13, 2011 1:41 am
- Post datetime: 2011-06-12T17:44:37+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Is there any way to get a count of the number of samples in a .sns file encoded using ealayer3.exe?

The Sims 3 stores what appears to be a sample count as the last 3 bytes of the accompanying .snr files, and in order to swap in custom-encoded music, I need to be able to edit that sample count. I've tried using the sample count of the source mp3, but there's clearly a bit of difference.
## Post #40
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2011-06-13T04:11:03+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Well, there isn't at the moment but it should be trivial to add. Unfortunately I found a bug related to that in the latest version of ealayer3 and I don't have the willpower to test everything right now. (During encoding the program writes the incorrect number of samples to the file.) I'll see when I can get to it.

brendan19, RedDeadRedemption, Apollo, I released a new version a few weeks ago but was too lazy to announce it here. It now tries to decode the entire file, not just the first track. So you should take a look and see if the problems are fixed.

Man I've gotta find time to come here more often
## Post #41
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-06-13T05:14:41+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Thank you Zench, it worked perfectly
## Post #42
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-28T02:37:12+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

For some reason the offset thing doesn't work, just gives me not a readable file format, however if i cut off the header of an ea layer 3 file it works when doing it straight without the offset specifying.

This bug happens in ver 7.
## Post #43
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-01-30T19:46:35+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Sorry but how do i use this program?
I press double click on ealayer3 file but nothing hapening.
Please reply Zench.Ty.
## Post #44
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-01-31T01:47:19+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

You have to run the program in the command prompt to use it properly.
## Post #45
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-02-09T13:07:11+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I drag ealayer3 into cmd windows and say :you must specify an input filename.
ok.
i typed hero.sns(from nfs word music folder) and said hero sns is not recognized as an internat or external comand,operable program or batch file.

please reply.i want extract that music ....

help me please.i am noob.
## Post #46
- Username: flaaaat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 08, 2012 12:52 pm
- Post datetime: 2012-02-09T16:03:55+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

It seems to choke on many of the RA3 Uprising cdata files.

edit - nevermind, it didn't work because I haven't used mus.exe to demux the files.
## Post #47
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2012-02-13T19:57:50+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

[http://www.mediafire.com/?ek2zc3d11f8tf32](http://www.mediafire.com/?ek2zc3d11f8tf32)

Zench or if anyone can help this seems to be a new EA xa variant that can support and is multichannel and it might be mpeg based as well.

Greatly appreciated if you can add support for this format.
## Post #48
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-15T03:39:31+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

i  try simpson the game is ea this tool can do it ? i don't find the cmd  i need use

for this time i have  parser could not be initialized 
the bitstream format is nor readable
## Post #49
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2013-04-03T20:12:57+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Im putting this out there!!

If anyone can continue zenchs work on updating the ea layer 3 tool for newer EA variants it would greatly help!
## Post #50
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2013-04-08T19:11:26+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I'm not sure if it's ok to post this here, but I think that these are related. Any help is appreciated. Thanks!

[viewtopic.php?f=10&t=10295](http://forum.xentax.com/viewtopic.php?f=10&t=10295)
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-31T16:19:22+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Hello all!

I was able to compile Zench's project and make some corrections so now it can convert all Dead Space 2/3 files it was unable to convert before. I'm not an MP3 format expert, but let's hope with minor changes of headers I can now make it extract any new Ealayer3 game files.

I don't know how to handle Zench's license and everything, so here is the new .exe for now.
[ealayer3.rar](https://xentaxbackup.github.io/file/8916_ealayer3.rar)
## Post #52
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2015-04-01T02:40:01+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from daemon1
>
> Hello all!

I was able to compile Zench's project and make some corrections so now it can convert all Dead Space 2/3 files it was unable to convert before. I'm not an MP3 format expert, but let's hope with minor changes of headers I can now make it extract any new Ealayer3 game files.

I don't know how to handle Zench's license and everything, so here is the new .exe for now.

hi~daemon~Can support the Dragon Age Inquisition?thanks!
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-02T19:54:39+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from mappy2012
>
> hi~daemon~Can support the Dragon Age Inquisition?thanks!

Ok, the format of these files have something different in them. This is not header, but the mp3 data itself. Every 40-60 kbytes it stops with an error, without even producing any output.

This is what I did for now: I made it not stop, but try and continue decoding. The resulting mp3 files are playable, but distorted (have skips) in many places. This way we can at least listen to it in cases like this.

Now I will try to find out what is wrong with the format.
[ealayer3.rar](https://xentaxbackup.github.io/file/8930_ealayer3.rar)
## Post #54
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-03T17:20:09+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Considering the last files mappy2012 gave me, I'm sure now: the files were extracted wrong.
There are occasional 8 bytes missing or 8 extra bytes in the audio string.
So we have to find the problem in the extractor whatever that was.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-04T16:56:32+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Ok, problem localized. Example:

DAI tools finds music file inside the game named "mus_main_theme_51" and saves it as 14MB chunk. This chunk is a complete mess, combined from many cut parts of the original file contained in cas_13.cas. I don't know why it happens.

So I've extracted that file with my own tool, converted it with "old" Zench's Ealayer3 and got a perfect 6-channel 3,5 minutes WAV file with the main theme.

I'm trying to find someone who can correct this problem in DAI tools now.
## Post #56
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-16T09:45:49+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Does anyone know where I can get the latest most up to date source code for the EALayer3 decoder?
Reading the license file for the code it looks like BSD (so daemon1 can feel free to share any changes he has made since that's allowed by the license).

Also if anyone on here still cares about actually properly reverse engineering the beast that is EALayer3 (anyone with any kind of reverse engineering skills that is), I have recently come into possession of a sever executable for one of the Battlefield games. This executable is very useful to anyone wanting to reverse engineer EALayer3 (and who knows how to use IDA and HexRays and stuff to do such reverse engineering) because it has full debug symbols AND it has an EALayer3 decoder (for 3 different variants of EALayer3) AND it has a decoder for regular MP3 audio (and the code used by both the EALayer3 and MP3 decoders is shared making it even easier to see which bits are the same between MP3 and EALayer3 and which bits are different)
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-16T18:37:44+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Why do you even need that? Ealayer3 decoder is working fine and had no problems for many years. All changes needed were only about some header flags, and don't have any connection to the decoding process itself.
## Post #58
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-16T22:24:17+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

The header is one thing this binary can help figure out since it gives useful names for flags and things that come from those headers.
Hence why I want the latest code so I can fiddle with it 
Even if I dont find anything new, it will still be a fun exercise fiddling with this binary...
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-18T16:23:24+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I don't think you need debug symbols to figure out the header. I mean you don't need a debugger to tell that 1 is mono ans 2 is stereo. So if I remember correctly, changes I made were:

1. stop after end of the stream. useful for some games, but not for others
2. continue after sync lost. May be useful in case of damaged files, but in general its bad idea.
3. support for some codec/format combinations that were absolutely obvious, just Zench never seen this kind, so he decided NOT to decode such files for some reason.

Thus, I'm not going to post my changed sources, because I see no reason for this, and I even think using them will be wrong and not recommended. So just take the latest Zench version.
## Post #60
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-18T16:27:14+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

p.s. I compiled his code in .net, which required some changes. His original source was for usual c++. It also required some tricks to make it compile, but unfortunately I don't remember now what it was. I remember I found some clues googling about his tools. It was somewhere on someones blog or something. It was NOT mentioned in his source package.
## Post #61
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-19T00:07:45+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

There is at least one unknown flag in the EALayer3 stuff (at least in the latest version posted by Zench) and I am getting close to identifying that flag based on the BF3 information.

Maybe I dont find anything new but hey, if I do, great, I will share it with everyone.
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-19T15:42:03+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Since all sounds from BF3 can be decoded properly without that flag, then I'd say this flag is not needed.
## Post #63
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-19T23:18:25+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

There are many EA games using the exact same EALayer3 codec (the one labeled 6/L32P/7/L32S), any one of those could have EALayer3 audio with that particular bit set.

It just happens that the Battlefield 3 binary is the first one to show up with enough debugging information to make it easier to reverse engineer the code.
The point here is not what some specific subset of EALayer3 encoded audio looks like but what the decoder does for all possible inputs so that it can decode every possible file encoded with the 3 codecs in question (the one labeled 5/EL31, the one labeled 6/L32P and the one labeled 7/L32S) in exactly the same way the official decoder decodes them.

I have already identified at least one case where there is data being read by the official code but not by the ealayer3 code although I haven't quite figured out exactly which combination of header bits in the "EALayer3 Header" (the one with the version/sample rate/mode in it) causes this data to be read yet.

In any case fiddling with this stuff is FUN
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-20T05:47:40+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo
>
> I have already identified at least one case where there is data being read by the official code but not by the ealayer3

Can you send me that file? You know, I just can't believe that can be. I converted dozens of games, and it never happened.
## Post #65
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-20T10:25:16+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I haven't seen a file that has this particular information in it. But that doesn't mean it doesn't exist. What matters to me is that every single piece of data that the official decoder will read and decode is also decoded by the ealayer3 code so it can be 100% accurate in case there IS audio out there that uses this stuff.

I doubt you have seen every EALayer3 encoded file that has ever been produced...

And again, like I said, its fun so even if no files exist using this particular data, figuring out all this stuff is still interesting to me 

Question: Are you aware of any EALayer3 encoded files that have a value in the MPEG version field other than 3? (representing MPEG version 1) If you know of such files, please tell me where to find them (what game, whatever) as there are some interesting things in the code that may be triggered only for files where the version field != 3 and if I get the files I can see what they look like and maybe answer some questions.
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-20T12:50:07+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo
>
> I doubt you have seen every EALayer3 encoded file that has ever been produced...

Yes, but statistically, after I've seen 1000s of files, chances I've seen all types are closing to 99%.

Ok, you can find MPEG2 in low quality SFXs like explosions or gunshots, usually in sound banks, for example in Dead Space 2. But they were all converted properly. Believe me, I listened to them all. I can suppose that official decoder may apply some filter for such low-freq files, but this is not about the actual decoding process or flags.

Also, nowadays devs are more and more returning to ADPCM and even using PCM or FLAC, so I don't think low quality mpeg such as 22000 hz is any useful now.
## Post #67
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-20T13:02:24+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Can you point me to an example of an EALayer3 compressed file with a version field not equal to 3? Yes I know you say they all convert properly but I still want to look at it anyway to see what it looks like inside.
I am also after an EALayer3 compressed file of type EL31 (also known as "type 5") that has uncompressed data following the compressed data (should have 0xEE in the first byte of the granule rather than 0x00) as its the other thing I dont have an example of at this point.

Oh and you say you have seen/converted many many different EALayer3 compressed files. Have you seen/converted the EALayer3 audio connected to the PathMusic data in Red Alert 3, Red Alert 3 Uprising and Command & Conquer 4 Tiberian Twilight? Specifically the large blob that contains multiple different pieces of EALayer3 compressed audio? (and if you HAVE been able to convert the audio data inside it, please tell me how you did it as I would love to know
## Post #68
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T03:39:39+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Does EALayer3 (either the original code or your changed code) handle EALayer3 audio using MPEG-2 Low Sampling Frequency? Do any EALayer3 files exist that use this?

BINGO, I figured it out. Turns out the "unknown data" I was staring at is the MPEG Side Info and I just found the code that reads it in the EALayer3 codebase so no its not "data ealayer3 doesn't read" like I first thought. It was confusing me until I realized the reason the ealayer3 code wasn't actually making use of the "side info" is that it doesn't actually decode MPEG audio, it just passes it to mpg123 (which DOES make use of the side info).

So yeah I dont need an example of MPEG-2 LSF anymore now that I understand what is really going on in the decoder (or an example of EALayer3 audio that has version != 3).
I dont need a "type 5" file with "uncompressed samples" either.

But if you know how to decode the "path music" large blobs from RA3/Uprising/C&C4, I would love to know how...
## Post #69
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-21T06:06:19+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Good that you got it. You see, in "mp3" mode ealayer3 doesn't even decode anything, it just puts the parts of data to standard mp3.

> Reply from jfwfreo
>
> But if you know how to decode the "path music" large blobs from RA3/Uprising/C&C4, I would love to know how...

Can you send me example of such file, because I don't quite understand what are you talking about.
## Post #70
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T06:57:36+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Its a large data file containing a bunch of separate pieces of EALayer3 audio.
But if you dont know what PathMusic or PathMusicTrack or PathMusicMap or .mpf or .mus files are, you probably dont know how to unpack this data.

[https://mega.nz/#!u50nzRQK!ZWBhTO8awlhe ... ALxFDxgQL8](https://mega.nz/#!u50nzRQK!ZWBhTO8awlheToSDkTfXvn_894-kRZFZGALxFDxgQL8) is an example of one of these files with all the audio chunks in it in case you want to have a look
## Post #71
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-21T07:32:37+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo
>
> But if you dont know what PathMusic or PathMusicTrack or PathMusicMap or .mpf or .mus files are, you probably dont know how to unpack this data.

Don't underestimate me  If you check my profile, you can see I'm a reverse engineering specialist.

That was very easy. This file is a sound bank containing 17 sounds. In the beginning you see a table with all of them. It contains size, data offset, hash, header size and header offset for all sounds. Then go all sounds according to that table. You can take all of this info, get the data, and decode individual files with ealayer3.
## Post #72
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T07:56:04+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Can you show me the data structure(s) needed for this file? Its not obvious from your description (and looking at the file in a hex editor) just what size the fields are.
Is there a count stored anywhere of how many tracks are in the .mus file?
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-21T08:00:32+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

all fields are 32-bit words.

Count is at offset 4. Table starts from 0x1C

Table fields:

hash
number of file
header offset (multiply by 0x10)
data offset (multiply by 0x80)
header size
data size
zero (or unknown)

You don't actually need headers, because sample freq and channel number already contained in mp3 data
## Post #74
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T08:16:43+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Are you sure you dont mean 0x28? Looks that way to me with the first hash being C5C98A9C
And do you have any idea what the other fields in the file header (other than the count) might be?

Oh and I see what you mean about EALayer3 being very close to MP3, I see large chunks of the low-level decoding stuff (DecodeHuffman, Dequantize, others) shared between the EALayer3 decoder and the MP3 decoder. I do wonder why they invented a format that is almost but not quite MP3...
## Post #75
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-21T08:57:35+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo
>
> Are you sure you dont mean 0x28?

Oh, sure its 0x28. A little misplace when writing. The other fields must be something to connect this data to other game files. And I don't have them.

Well, their format IS actually normal mp3. The only thing they did is storing mp3 data in their own structure. Why? No idea.
## Post #76
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T09:04:31+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from daemon1
>
> jfwfreo wrote:Well, their format IS actually normal mp3. The only thing they did is storing mp3 data in their own structure. Why? No idea.
Its normal MP3 with their own custom header and the weird "uncompressed samples" stuff at the end.
## Post #77
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-21T09:08:30+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

uncompressed samples may also be in the beginning if i remember correctly
## Post #78
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-21T13:07:06+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Ok so I think I finished playing with EALayer3 now. Things I discovered (and that aren't in the "ea layer 3.txt" file in the ealayer3 code)
For "version 5" data, the first 8 bits have to be 0xEE for the "uncompressed samples present" code to trigger, not "non zero" as the docs imply.
For "version 6/7" data, the second bit in the header (currently marked "unknown") is channel count - 1 (so 0 for mono and 1 for stereo)
The enum used for the "mode" flag in the extended header for "version 6/7" data looks like this
enum rw::audio::core::BlockOffsetMode
{
  BLOCKOFFSETMODE_IGNORE = 0x0,
  BLOCKOFFSETMODE_PRESERVE = 0x1,
  BLOCKOFFSETMODE_MUTE = 0x2,
  BLOCKOFFSETMODE_MAX = 0x3,
};
And finally, the function that decodes the "uncompressed" sample data in "version 5" files is named DecodeSpecialBlock. For "version 6/7" files the decode function is named DecodePcm. Not sure why they called it a "special block" for the "version 5" files, just seems weird that they did that.

That's it for interesting EALayer3 discoveries
## Post #79
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-22T07:37:59+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Just wanted to say thanks for figuring out that .mus stuff.
There is a related file format (doesn't contain actual audio data but will contain references to the .mus file) called .mpf. I have uploaded a sample mpf file here. The MPF file is connected to data called "PathMusicMap" by the game.
[https://mega.nz/#!e9ExFLbY!7uqs3qW-uHb0 ... Nq_FgdpBB0](https://mega.nz/#!e9ExFLbY!7uqs3qW-uHb0u1yPas_1W26qnB2FTXndxNq_FgdpBB0)
If anyone can help me figure out its format, I would be very grateful (its one of the only formats in Red Alert 3 that can't currently be edited)
## Post #80
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-23T16:07:09+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Checked the file. If anyone will be going to figure out its format, he will also need the files that its connected to. Maybe even the whole game. Because it doesn't contain actual data, but only references, its natural that'd be impossible to figure anything out without the actual data it refers to.
## Post #81
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-23T21:01:50+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

As far as I am aware, the only data that the mpf file (which goes with the PathMusicMap data) should be referencing is the PathMusicTrack data (the .mus file). The game has 2 of them, the smaller of the 2 is what I uploaded earlier.

I suspect the best way forward is to go back to my reverse engineering notes from before and continue reverse engineering as much as I can and then write it all up (with data structure definitions, notes and mega.nz links to the various data files involved) and then see if anyone out there can help me fill in the blanks.
## Post #82
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2016-08-25T10:54:26+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I have posted all my notes on the PathMusic stuff in [viewtopic.php?f=17&t=14927](http://forum.xentax.com/viewtopic.php?f=17&t=14927)
Hopefully someone will be able to help me reverse engineer all the remaining pieces in the files so its possible to change these files and mess with this data...
## Post #83
- Username: PixelBoyZ69
- Rank: n00b
- Number of posts: 13
- Joined date: Sat May 13, 2017 2:05 am
- Post datetime: 2017-05-13T02:10:26+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Sorry to bump this forum but i just want to ask...

searching the BF1 Soundtrack somewhere in "sound" folder, found all the EBX File but dunno how to figure out where is the audio (Soundtrack) files located, because some of them are kinda like a trap file for me (some of the EBX are not the Audio Files)
## Post #84
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-05-15T12:42:53+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from PixelBoyZ69
>
> Sorry to bump this forum but i just want to ask...

searching the BF1 Soundtrack somewhere in "sound" folder, found all the EBX File but dunno how to figure out where is the audio (Soundtrack) files located, because some of them are kinda like a trap file for me (some of the EBX are not the Audio Files)

Did you look in the "Levels" subfolder in the main folder "Sounds" after sound extraction? I remember clearly finding musics loops and stuff in that subfolder (like the epic fight music "Metal Frenzy" in the Storm of Steel mission: "Sounds\Levels\SP\E0\Music\SP_E0_Prologue_CombatInfantry4CH_Loop_Wave 0 0 0.wav"). You will even be able to find unique sound effects only used in those levels, in the same directory (like, again in the prologue, the scream of the guy who's rushing at the character in the outro), if you're interested.

But, if you're looking for the musics in the background from the main menu (like Dawn of a New Time, that I personaly love to the bones), check this subfolder: "Sounds\Music\FrontEnd"

Cordialy
## Post #85
- Username: fuzneck
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 16, 2021 1:21 am
- Post datetime: 2021-06-15T18:37:19+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Heya. I was curious is there a read me file or tutorial somewhere for this tool? 
I'm trying to extract need for speed hot pursuit 2010's audio files from their BNDLs, but can't extract them into a readible file format for the exe only as empty .ealayer3 files.
I'm sure the issue is user error on my behalf.

I've attached pics of the console commands ive tried and the current folder setup if that helps.
## Post #86
- Username: stamkaly
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 09, 2021 8:40 pm
- Post datetime: 2021-07-09T13:08:41+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Hello everyone, I am trying to use EA Layer 3 to decode an SPS sound file from NFS Most Wanted 2012 of PS Vita but it doesn't work. It says:

```
EA Layer 3 Stream Extractor/Decoder 0.7.0. Copyright (C) 2010-11, Ben Moench.

L: single block loader incorrect because of compression
L: header B loader incorrect because of block type
L: headerless loader incorrect because of flags
The input is not in a readable file format.
```

It works fine when extracting the same sound from the PC version of the game, but I want to be able to use my Vita files.
Here are the files mentioned:
[PS Vita 14729.SPS](http://stamkaly.pythonanywhere.com/PSVita14729.SPS)
[PC 14729.SPS](http://stamkaly.pythonanywhere.com/PC14729.SPS)
[PC extracted 14729.mp3](http://stamkaly.pythonanywhere.com/PC14729.mp3)
## Post #87
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2021-07-10T08:46:53+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

That PS Vita file seems to be compressed or encrypted.
## Post #88
- Username: stamkaly
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 09, 2021 8:40 pm
- Post datetime: 2021-07-10T12:55:26+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

> Reply from jfwfreo ↑Sat Jul 10, 2021 4:46 pm at Sat Jul 10, 2021 4:46 pm
>
> 
That PS Vita file seems to be compressed or encrypted.
I figured that might be the case. I guess they might be compressed since the majority of them have almost half the size of the PC version. I tried looking for any possible headers of this filetype in the PS Vita version of SPEECHEVENTSEQUENCES.SWC0 (in the PC version it's [multiple SPS files glued together](https://forum.xentax.com/viewtopic.php?p=174498#p174498)). Unfortunately I wasn't able to figure anything out on my own.

I would be very grateful if you could give me a hint or two as to how to go about this. I can provide the whole PS Vita game files and any from the PC version for comparison if needed.

Essentially what I want to do is replace the sound files the game uses for when you are near a jackspot with a file of no sound. It's pretty annoying when it plays on top of the in-game music and there's no way to turn it off..
## Post #89
- Username: Hinki
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Apr 25, 2021 3:41 pm
- Post datetime: 2022-01-04T10:25:53+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

I have no idea how to create files for Def Jam Icon but if I use --verbose on one of the files it gives me 

```
L: header B loader incorrect because of block type
L: headerless loader correct
P: EAL3 ver. 6 and 7 incorrect with exception: Ver. 6 and 7 header: granule size set incorrectly.
P: EAL3 ver. 5 correct
Parsing blocks...
P: EAL3 ver. 5: null granule encountered, end of block
```
## Post #90
- Username: perqosuette
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 22, 2023 4:30 pm
- Post datetime: 2023-07-22T08:31:30+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

Hello does this work for windows 10?
## Post #91
- Username: RRJOKER
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 29, 2023 6:47 pm
- Post datetime: 2023-07-29T23:38:26+00:00
- Post Title: Re: EA Layer 3 Extractor/Decoder

But how about game theme song that use .sps type file and how can i change it
