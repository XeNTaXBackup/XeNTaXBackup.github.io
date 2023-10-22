## Post #1
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-19T10:53:12+00:00
- Post Title: Extract audio out off -> .XXX files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: mauzerX
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jul 01, 2010 8:48 pm
- Post datetime: 2010-10-19T19:16:37+00:00
- Post Title: Extract audio out off -> .XXX files

It's unreal engene,gildors tools will help U([http://www.gildor.org/downloads](http://www.gildor.org/downloads)),problem is in converting from *.SoundNodeWave to normal format...m.b. someone will help with script?
## Post #3
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-20T06:16:14+00:00
- Post Title: Extract audio out off -> .XXX files

What do you use to convert the soundnodewave files?
We use Oggextract for audio.
source:[http://gbxforums.gearboxsoftware.com/sh ... 194&page=6](http://gbxforums.gearboxsoftware.com/showthread.php?t=85194&page=6)

So I searched it and tryed it out. It says "0 files written" prob. because its unreadable/compressed.
[http://ner.mine.nu/oggextract/](http://ner.mine.nu/oggextract/)

I've used gildor's tools for extracting meshes, animation & textures but it doesn't seem to work with audio.

Where do you go from here?
## Post #4
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-10-20T20:22:03+00:00
- Post Title: Extract audio out off -> .XXX files

if its xbox 360 you add an xma header to 6 bytes before the fc01 flag.
## Post #5
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-20T21:03:39+00:00
- Post Title: Extract audio out off -> .XXX files

Ow right forgot to mention in my case its for the PC version,
my apologies.
## Post #6
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-10-23T04:36:36+00:00
- Post Title: Extract audio out off -> .XXX files

U3 Engine always uses .ogg.
## Post #7
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-23T07:03:09+00:00
- Post Title: Extract audio out off -> .XXX files

So how do I extract the ogg's out of .xxx files?
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-10-23T12:41:06+00:00
- Post Title: Extract audio out off -> .XXX files

The file dont' looks a vorbis, looks an EA dpcm, maybe a xma? but for me is not ogg vorbis.
## Post #9
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-10-24T13:23:31+00:00
- Post Title: Extract audio out off -> .XXX files

Urgh, it seems EA has decided to use their own audio formats instead of the native UT3 engine ogg vorbis and as usual, it is headerless. Strange, I would have expected ealayer3 but not this time.
## Post #10
- Username: sgtmoody1944
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 24, 2010 11:47 pm
- Post datetime: 2010-10-24T15:52:46+00:00
- Post Title: Extract audio out off -> .XXX files

Does this mean that the files will never be extractable?
## Post #11
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-24T17:25:39+00:00
- Post Title: Extract audio out off -> .XXX files

Say never never
## Post #12
- Username: sgtmoody1944
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 24, 2010 11:47 pm
- Post datetime: 2010-10-25T01:36:40+00:00
- Post Title: Extract audio out off -> .XXX files

Well I mean I also posted this topic over at the EA forums last week, but so far nobody's given it much consideration. I guess this is a harder problem than anyone had originally anticipated.

But hopefully somebody will come up with a solution at some point, because there are some really nice atmospheric tunes (not included in the game's soundtrack) and ambient and weapon sound effects that could come out of this extraction if done correctly...
## Post #13
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-25T08:15:09+00:00
- Post Title: Extract audio out off -> .XXX files

> Reply from Apollo
>
> Urgh, it seems EA has decided to use their own audio formats instead of the native UT3 engine ogg vorbis and as usual, it is headerless. Strange, I would have expected ealayer3 but not this time.

Interesting... I've uploaded(see below) a set of files that all include the charachteristics of the name "avalanche" plus with the audio tag in the name.

I notice that there are like alot of loc files I guess they stand for Localization files. 
Maybe that's where we need to look at? 
You talk about headerless so I thought maybe inside the loc files.

* snip *
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-10-25T12:04:37+00:00
- Post Title: Extract audio out off -> .XXX files

Did you try ea;ayer3 decoder posted in this forum?
## Post #15
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2010-10-25T15:49:38+00:00
- Post Title: Extract audio out off -> .XXX files

I've tryed out the tool but I get this error: The EALayer3 parser could not be initialized (the bitstream format is not readable).

I used this command

```
ealayer3.exe -e Aud_Ava_Music_track.xxx Aud_Ava_Music.xxx
```


Played abit with commands but doesn't seem to work for me. Who can crumble the wall?

I've included two files for those who like to download a smaller size of files.
* snip *
## Post #16
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-10-25T16:33:23+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Yeah, it is not ealayer3 data but eaxa, i've decoded the first file since it only holds one stream in it, unfortunately the other files got multiple after each other and would need a splitter script as my attempt to just put header in start of those did not give too great decoding results and cutting streams manually is harder due to lacking start header not being there for each file within.
## Post #17
- Username: Mrfusion1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 25, 2011 1:49 pm
- Post datetime: 2011-01-25T05:55:11+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Any progress on this? Also trying to extract some audio out of the medal of honor airborne .xxx files.


Textures etc can be extractor with model but it audio.
## Post #18
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-01-25T08:06:58+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Not on my behalf, don't have means to split the xas streams  from the xxx files plus differing block size issue i believe, else my converter is on nba elite thread but output is not very nice most of the time.
## Post #19
- Username: Mrfusion1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 25, 2011 1:49 pm
- Post datetime: 2011-01-27T04:03:21+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Mysterious problem.

Well if anyone can figure it out down the track give us the solution!
## Post #20
- Username: gildor
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 25, 2010 5:15 am
- Post datetime: 2011-02-13T12:08:31+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Umodel can extract sounds from some UE games now
[http://www.gildor.org/smf/index.php/topic,734.0.html](http://www.gildor.org/smf/index.php/topic,734.0.html)
## Post #21
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-02-13T20:30:03+00:00
- Post Title: Re: Extract audio out off -> .XXX files

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2011-02-14T08:32:26+00:00
- Post Title: Re: Extract audio out off -> .XXX files

if all else fails, try googling Unreal Engine OggExtract. works well with all ue games that i can think off.
## Post #23
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-02-14T14:50:19+00:00
- Post Title: Re: Extract audio out off -> .XXX files

ogg extract on xxx with audio in it doesn't work.
## Post #24
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-02-16T13:59:31+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Yeah can't work when its ea adpcm, just doesn't decode using dead space trick or otherwise correct.
## Post #25
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-04-08T18:40:54+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Apollo, how did you even decode the first stream?
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-09T16:12:52+00:00
- Post Title: Re: Extract audio out off -> .XXX files

He probably used zenchs ealayer3 tool.
## Post #27
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-04-09T21:52:46+00:00
- Post Title: Re: Extract audio out off -> .XXX files

but its not all ea layer 3 from the looks of it..

edit: ea layer 3 tool is a no go on most of the non ambient files...
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-04-09T22:23:10+00:00
- Post Title: Re: Extract audio out off -> .XXX files

if its headerless XA then its possible to convert those with an added header with towav. I remember posting the header on this forum in some thread but i don't remember which one it is.
## Post #29
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-04-10T04:09:16+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Did not work for me either, it was the nba elite thread. the audio format in MOH looks alot like the pc BC2 streams, except, in .xxx files.
## Post #30
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-04-10T13:18:23+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Well, the first decoded stream was xas adpcm stream, xas is the newest variant on the old EA xa codec. Anyway the problem with these xxx files or any container is that these streamed files are just in raw data chunks apart from ever repeating 8 byte header that points to next chunk start and until now i had trouble seeing where one streamed file end and another began since tend to be several files in one, luckily there is a marker that signals end of stream seemingly

in XXX files the first four bytes (32-bit integer) is the frame length 
in bytes 
the next four bytes (32-bit) looks to be number of samples 
and then data (thanks peter for initial info) which in this case is adpcm data chunks, when we reach the frame lenght amount minus -8 bytes we have another 8 bytes header start and again data follows. towav with dead space header knows to bypass the 8 byte header bits in decoding process but when towav won't decode, only choice is to clear out all the 8 byte repeating entries from the file for solid adpcm chunk decode which i did for first. could use more files to study tho as some files still won't decode correct despite i clear out the headers or towav trick fails.
## Post #31
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-04-10T14:07:14+00:00
- Post Title: Re: Extract audio out off -> .XXX files

* snip *

These were the smallest files I found that fit together by name (rem...). 
A collection of what looks like the Remagen map 
(this map was added through the last patch of the game).

These look like shortcuts, I picked all the files between 1 kB to 200 kB

* snip *
## Post #32
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2011-04-10T15:24:08+00:00
- Post Title: Re: Extract audio out off -> .XXX files

* snip * 

ZIP includes these:
Aud_Var01_Music_Track.xxx
Aud_Var01_Music.xxx
Aud_Var01_FakeWAV.xxx
Aud_Tra_SoundRiot_Stream.xxx
Aud_Tra_SoundRiot.xxx
Aud_Tra_FakeWav.xxx
## Post #33
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2011-04-11T10:16:56+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Here are two XXX files of Medal Of Honor 2010 (PC): * snip *
## Post #34
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-04-13T12:05:58+00:00
- Post Title: Re: Extract audio out off -> .XXX files

medal of honor 2010, the big one holds just ealayer3 compressed music, oddly enough zench's ealayer3 tool didnt automatically extract all with -s all so i cutted the first stream it extract amount of data for it to find rest.
## Post #35
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-07T15:11:19+00:00
- Post Title: Re: Extract audio out off -> .XXX files

I tried to extract " Aud_Weapons_All_SoundRiot_stream.xxx " ( from PC ) via Umodel with this command line:

```
pause
```

and the console told me this:

> "C:\Umodel>umodel.exe -sounds Aud_Weapons_All_SoundRiot_stream.xxx
>
> Found 5 game files (7 skipped)
>
> ******** Aud_Weapons_All_SoundRiot_stream.xxx ********
>
> *** ERROR: Wrong tag in package: C0070000
>
> FPackageFileSummary<<:Ver=0/0 <- UnPackage::UnPackage:Aud_Weapons_All_SoundRiot_
>
> stream.xxx, ver=99999/0, game=0 <- UnPackage::LoadPackage:Aud_Weapons_All_Sound
>
> Riot_stream.xxx <- Main"
Next, I deleted the 00 00 07 C0 offset ( with HxD ) from the .XXX file and the console told me this : *** ERROR: Wrong tag in package: 08600000 blablabla...

So, is it a problem with the offset?

INFO: Not working with ealayer3.exe either: " The EALayer3 parser could not be initialized (the bitstream format is not readable) ".

Thank's in advance

Vosvoy
## Post #36
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-04-08T08:55:52+00:00
- Post Title: Re: Extract audio out off -> .XXX files

Its not unreal package nor ealayer3, its just streamed ea adpcm file thus those don't work.
## Post #37
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-04-08T16:33:29+00:00
- Post Title: Re: Extract audio out off -> .XXX files

> Reply from Apollo
>
> Its not unreal package nor ealayer3, its just streamed ea adpcm file thus those don't work.

I see. But what's wrong with this type of file exactly?
## Post #38
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-06-03T13:37:41+00:00
- Post Title: Re: Extract audio out off -> .XXX files

i see lot of this type file 
someone can help
