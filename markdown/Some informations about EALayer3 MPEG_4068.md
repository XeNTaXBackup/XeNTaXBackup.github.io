## Post #1
- Username: zano
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 30, 2009 12:40 am
- Post datetime: 2010-01-20T12:21:23+00:00
- Post Title: Some informations about EALayer3 MPEG

Hi all,

Is where anybody who can give me some good informations about the EALayer3 mpeg from Electronic Arts ?... It seems that EA don't give any information about this codec and all informations we can get from Wiki or else are out of date, obsolete, etc...

Is this codec / compression algorithm Confidential Defense ? lol   

Nice day to all.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-01-20T14:22:24+00:00
- Post Title: Some informations about EALayer3 MPEG

Don't think so, if you are lucky it has been reverse engineered in some project like ffmpeg.

Seems like there one was a description about EA's in-house audio library but it has gone. If you find it, tell me.
[http://wiki.multimedia.cx/index.php?tit ... ronic_Arts](http://wiki.multimedia.cx/index.php?title=Electronic_Arts)

I think EA's tool SoundXchange supports converting it.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-20T15:55:52+00:00
- Post Title: Some informations about EALayer3 MPEG

I don't think so. I tried it on some red alert 3 .cdata files and nfs undercovers mus but no luck.
## Post #4
- Username: zano
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 30, 2009 12:40 am
- Post datetime: 2010-01-20T16:47:16+00:00
- Post Title: Some informations about EALayer3 MPEG

Ok guys,

Thanks for your support and advices ... I see that I've only one way : reverse engineering because
ffmpeg is great but can't master this kind of compression   

No matter as soon as I find something interesting, I give you feedback.

So long.
## Post #5
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-01-21T21:40:53+00:00
- Post Title: Some informations about EALayer3 MPEG

Would be great to find a way to convert it. The music from Burnout Paradise still isn't extractable.
The thread is here: [viewtopic.php?f=10&t=2905](http://forum.xentax.com/viewtopic.php?f=10&t=2905)

aluigi wrote a script which extracts .dat files out of the .sns sound files, but no one knows what to do with it.
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-01-25T10:19:45+00:00
- Post Title: Some informations about EALayer3 MPEG

Well, having looked at the sns file, it is indeed ealayer3 like EALA has also used in Command & Conquer 3 while RA3 has an newer variant of it.
## Post #7
- Username: zano
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 30, 2009 12:40 am
- Post datetime: 2010-01-28T20:23:23+00:00
- Post Title: Some informations about EALayer3 MPEG

OK all,

Thanks a lot for these informations... I think I can do something usefull with them... I give you feedback as soon as possible.

So long.
## Post #8
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2010-01-28T23:19:07+00:00
- Post Title: Some informations about EALayer3 MPEG

Sounds cool.
## Post #9
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-01-31T13:13:40+00:00
- Post Title: Some informations about EALayer3 MPEG

> Reply from zano
>
> OK all,

Thanks a lot for these informations... I think I can do something usefull with them... I give you feedback as soon as possible.

So long.

This sounds awesome!:)
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-31T20:35:43+00:00
- Post Title: Some informations about EALayer3 MPEG

> Reply from zano
>
> OK all,

Thanks a lot for these informations... I think I can do something usefull with them... I give you feedback as soon as possible.

So long.

Great, looking forward to anything great about decoding this codec.
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-02T10:49:07+00:00
- Post Title: Some informations about EALayer3 MPEG

I've been looking at this a bit tonight, someone had sent me a sample of EA Layer 3 (I think from some C&C) called 166b084d.46410f77.03cfdd8a.96acd5f2.cdata.  I notice that it has the same kind of layout as EA's packed XMA thing, where it stores short frames/packets.  Unfortunately there's nothing resembling a standard MPEG-1 audio header there, so I'm having to poke around at random.

Pretty confident about the overall stream layout:
0x00-0x03: total frame size (including header, thus offset to next frame, if this is the last frame high bit is set)
0x04-0x07: samples in this frame (for layer 3 the first frame has a low count due to the decoder latency and the last frame has a high count due I guess to the same thing, all the frame in between have either 1152 or 2304 samples so one or two complete MPEG-1 frames).

I don't know how many of the following bytes are part of the header or which are the beginning of the MPEG frame body:
0x08: 00
0x09: 0xd4 or 0xd6 (in my sample file its d4: 1652 d6: 1435, very roughly an 8:7 ratio)
0x0A: a small byte value, never goes about 0x4e

Looking at the frame sizes, there is never a single frame (that is, a frame in this stream layout containing only 1 MPEG frame, distinguishable by the sample count, and 2304 sample ones are quite rare) that is > 0x417 bytes (though several at exactly that).  If we assume that this contains MPEG-1 Layer III, this corresponds almost exactly to 44100 Hz at 320kbps, which has a frame size of 0x414 (0x415 with padding which would be used about 90% of the time).  If they are encoding at 320kbps and getting rid of the padding, thus enabling them to get vbr performance without a vbr decoder, this would make sense.

8 bytes of each frame are occupied by stuff we know to be only stream framing material (the frame size and sample count), which leaves 0x40F bytes for the MPEG payload in the largest chunks.  Assuming a fixed MPEG header (4 bytes) is slapped on each frame as it comes across, this would put the largest total MPEG frame at 0x413 bytes, still short of the proper size.  If more than 8 bytes are stream framing then we come up even shorter.  I haven't been able to put together anything that generates a valid stream yet.  It may be that there's some deeper modifications, or I have to use the d4/d6 for different joint stereo modes, or some such.  I also haven't been able to spot where the second frame begins in the 2304-sample packets.

I've got a copy of the MPEG-1 Layer III standard so I'll try to get a feel for it from that angle, and I'll keep poking at it, but I thought I'd post my progress so far to help anyone else who wants a crack at it.
## Post #12
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-02T10:59:26+00:00
- Post Title: Some informations about EALayer3 MPEG

The contents of this post was deleted because of possible forum rules violation.
## Post #13
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-02T11:46:17+00:00
- Post Title: Some informations about EALayer3 MPEG

Interesting, here the d4/d6 I was looking at is instead c4/c6, and at a much different ratio (2098:5330).  The "small byte value" goes up to 0x58.  Otherwise seems the same.  Good to have more to chew on, in any case.
## Post #14
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2010-02-02T23:34:01+00:00
- Post Title: Some informations about EALayer3 MPEG

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-03T00:59:25+00:00
- Post Title: Some informations about EALayer3 MPEG

Hm, interesting to hear about sox, did it have some special support or was it just MP3?  Or does it come in through ffmpeg?  I'm hoping that all I'll have to do is reframe this data.
## Post #16
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-02-03T09:04:23+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

EA has also used it for 5.1 audio as apparently their ealayer3 encoder does multichannel as well. 
What is interesting is that EA has usually two variants of same format (shown in C&Cs), one is RAM one which gets a header in start to say freq/channels/format while the common streamed variant lacks start header and is more mp3 like working by each frame own header i believe. streamed files begin by 00 00 hex, ram one would begin 05 04 for example (05=ealayer3),(04=stereo)

[http://wiki.multimedia.cx/index.php?tit ... udio_Codec](http://wiki.multimedia.cx/index.php?title=EA_Command_And_Conquer_3_Audio_Codec)
## Post #17
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2010-02-03T12:44:56+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

The contents of this post was deleted because of possible forum rules violation.
## Post #18
- Username: zano
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 30, 2009 12:40 am
- Post datetime: 2010-02-03T19:33:44+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Hi All,

I THANK YOU ALL very very very MUCH for these informations... I think that with your info i shall be able to go a bit further   

I keep the job on and give you some feedback as soon as I discover something new.

One more time: THANKS and so long.
## Post #19
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-10T11:29:11+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Are there any updates on this?
## Post #20
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-02-10T11:48:37+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

This work on EALayer3 MPEG is GREAT to see and I am hopeful that the gurus here can figure it out (then I can finally add support for it to my C&C3/RA3 tools)
## Post #21
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-13T21:23:17+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Kataah, I just had another look at your Simpsons menu_mus, it's actually just XMA, in EA's XMA format.  For instance, there's a stream at 0x780 that you can get with "ea_multi_xma menu_mus -o 780".  There are more streams but you'll have to parse the header to find where they start.
## Post #22
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2010-02-13T21:34:15+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Hey nice thx hcs and i have though it was EA_L3 - maybe because of the similar structure
## Post #23
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-02-23T21:12:22+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Any progress?
## Post #24
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-07T18:39:38+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Is this project still alive?
## Post #25
- Username: zano
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 30, 2009 12:40 am
- Post datetime: 2010-05-04T15:23:26+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Alive ... yes it is   and i'm still working on it... whithout success... SOX can't decode these files / resources... We must to try to write our own tool!..

So long.
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-04T16:16:23+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Here is a sample from red alert 3.

Like hcs said it looks pretty similar to the ea packed xma.

man if someone can crack this codec i be real happy.

[http://www.megaupload.com/?d=BI3ZMHBV](http://www.megaupload.com/?d=BI3ZMHBV)
## Post #27
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-06-24T18:54:56+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

> Reply from zano
>
> SOX can't decode these files / resources
Beware that the EA tool is called sx: [http://wiki.multimedia.cx/index.php?tit ... d_eXchange](http://wiki.multimedia.cx/index.php?title=Electronic_Arts_Sound_eXchange)

sox is an open-source conversion tool: [http://sox.sf.net](http://sox.sf.net)
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-11T03:20:17+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Great excellent news!!

Zench has reversed engineer the codec and has hacked a tool to convert ea layer 3 audio, cdata input for now but its still experimental and works on winxp only, also does stereo music only so no background sounds.

here is the magic tool.

[http://www.box.net/shared/nocfoju0c9](http://www.box.net/shared/nocfoju0c9)
## Post #29
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-11T20:13:13+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Holy smoke, this is AWESOME!!!
Now I can convert the music from Burnout paradise.
Going to download it now, THANKS!
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-11T20:43:26+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Its still pretty buggy like you get a decoder crash error on some files but if you try it again on the same file it will convert, just gotta play around with it. im converting all of red alert 3 now.
## Post #31
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T07:53:45+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

At least now we can do more proper game rips when dealing with this codec. Thank you Zench for the tool.

At the moment, I'm having trouble converting some sims 3 world adventures loading screen music. I've tried multiple times but when it tries to convert, it breaks. And it's odd because the original sims 3 loading screen music converted just fine.

Anyone willing to take a look at it for me?
## Post #32
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-12T09:26:46+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Works for me, but it's a pain in the three letters to convert a whole soundtrack. 
Is there a way to let it convert everything automatically? Typing in every single filename is hard work.^^
## Post #33
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T09:40:10+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Yeah it works majority of the time for me too.

Just not exactly sure what causes the decoder to crash on these 4 files.

It might be just me doing something stupid (probably)

Here's a link to an archive with the songs I am unable to convert.

[http://www.flameupload.com/files/Q5AGEL ... dMusic.rar](http://www.flameupload.com/files/Q5AGELLA/S3WALoadMusic.rar)

As for your question Faqew, barnaby64 gave me a little batch script that converts any file with a .cdata extension to .wav using the tool as long as its in the same directory.

You might have to run the script a few times to get it done
## Post #34
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-12T09:48:22+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Can you give me the batch file?:)

The music from "Burnout Paradise The Ultimate Box" is in .SNS files, but since it also uses the EALayer3 codec, the program also works fine.

Are the output wave files really lossless wave files, or does the program convert the music into wav because it's easy to convert?
## Post #35
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-08-12T11:45:48+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Something like

```
FOR %%i IN (*.cdata) DO tool %%i
```

should do the job.

Wav is the easiest format and few information get lost.
## Post #36
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T12:11:53+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

I forgot to mention that the batch script is in the .rar I uploaded with the songs I couldn't convert.

It's more of an incentive to try and help me here.

.wav is the easiest format to convert to. But they're not going to be lossless unless the original audio files are already in a lossless format. And I doubt that's the case with anything encoded with EALayer3 MPEG.
## Post #37
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-12T12:21:43+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Something has to do with the offset of these files, because other ea layer 3 files i have converted have a 00 start stream followed by: 0000002F00E4 flag after a couple bytes.

i cannot find this in the loading screen's case, are these files extracted via hex or some program or are they founded in a folder?
## Post #38
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T12:38:55+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

The audio (music, SFX, voices) is all in one big .package archive file. I extracted the music files using S3PE.

I've re-extracted the loading screen music's additional files that come with the .sns (but I haven't needed for converting) to see if it helps you any Orange. I'm not sure what these .snr files contain as I don't know how to use hex at all.

[http://www.flameupload.com/files/1K1XDXRN/SNR.rar](http://www.flameupload.com/files/1K1XDXRN/SNR.rar)
## Post #39
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-12T12:54:41+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

These just contains sample rate and the segment info, but no start stream.

EDIT: Got it!  

Search for this string in a hex editor

0000002F00

the first 4 bytes before this flag is the start stream for the files, highlight from the first 4 bytes before the flag all the way to the end of the file, save as filename.cdata, then it should convert
## Post #40
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T13:01:47+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

[http://www.flameupload.com/files/1C5BUUBE/AUDTUN.zip](http://www.flameupload.com/files/1C5BUUBE/AUDTUN.zip)

the .audtun files as well. This is what most of the music comprises. A .sns (samples) .snr which contains the codec type, channels, Hz rate and how many samples and not I'm sure what the .audtun files contain.
## Post #41
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T13:10:10+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Like I said before, I really don't know how to hex edit.

I'm using HxD

Offset is set to hex

"0000002F00" turns up nothing. :/

EDIT: Sorry for the double post. Also, found it searching for a hex values.

EDIT #2 - Could you send me the conversions orange? Seems I'm doing something wrong here.
## Post #42
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-12T13:59:54+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

[http://www.megaupload.com/?d=W4B7R5KR](http://www.megaupload.com/?d=W4B7R5KR)
## Post #43
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-08-12T20:00:34+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Thanks to brendan19 and Rheini, the batch works now.
## Post #44
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-12T21:45:56+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Thanks a lot Orange.
## Post #45
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-14T23:38:08+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

A better decoder is coming, too! The cool part about this one is that the output is .mp3 and not .wav. EA Layer 3 is MP3 with a different framing mechanism. Stay tuned
## Post #46
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-15T00:29:05+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

SWEET zench!! i cant wait
## Post #47
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-15T02:05:51+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Can we have the option of exporting to either .wav or .mp3 Zench?

I'm not sure how it all works but isn't decoding lossy and then encoding back into lossy frowned upon?

Or is the way you're doing it not going to lose any quality at all during the process?
## Post #48
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-08-15T05:34:16+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

He is likely just doing a non-encode convert to normal mp3 which maintains original quality pretty much, still the option for mp3/wav pick should be kept especially since even C&C3 has multichannel ealayer3 files and you can't turn those to mp3 (unless separate to 3 stereo files) or in case of multichannel file, it should do automatically wav maybe.

I sure hope the multichannel support (and other windows support) is on cards too as C&C3 exe definitely has support for its decoding given game uses said files, still i wonder, C&C4 exe might have provided the latest decoder plus its unprotected exe that could be disassembled.

C&C3 has the ealayer3 variant 0x05, RA3 & C&C4 use 0x06 variant, battleforge has 0x07 variant, its unknown the need for different identifier and how that may affect the decoding if any.

neat hack tho
## Post #49
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2010-08-15T14:43:32+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

FYI, I took a look at RA3: Uprising (since it was the easiest thing I had handy to dig into) and found out that every compression type has a matching ID. The game grabs the ID for the given type and then searches for a decoder that matches that ID.
Types 0 and 1 have no type at all (type is NULL)
type 2 indicates no compression and has a type ID of P6B0
type 3 has a type ID of EXm0. There is no decoder for this in the PC version. My guess is that its the MS XMA Xbox 360 compression.
Type 4 is EA XAS ADPCM and has an ID of Xas1
Type 5 is EALayer3 and has an ID of EL31
Type 6 has a type value of L32P
Type 7 has a value of L32S

I took a look at the code for types 5,6 and 7 and its is very closely related (but not identical)

Zench, good news on the discovery that its standard MP3. I would like it very much if you released the source code to your new decoder as open source so it can be used in my C&C3 tools. If you release it under the right license it can also be included in FFMPEG (big tool/program/library that can decode a lot of video and audio file formats including many game related formats such as .cdata files with EA XAS ADPCM)
## Post #50
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-15T20:50:01+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

The xbox360 versions of cnc3 and kanes wrath use XMA packed in ea compression, pc versions use ea layer 3 multichannel, hopefully zench can support that in the tool update.

However i could decode Red alert 3 and uprising even 4 with the tool even if its from the cbnc3 decoder.
## Post #51
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-08-23T11:32:21+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Hmm anything?
## Post #52
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-24T18:13:01+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Released: [viewtopic.php?p=41828#p41828](http://forum.xentax.com/viewtopic.php?p=41828#p41828)

> Reply from jfwfreo
>
> FYI, I took a look at RA3: Uprising (since it was the easiest thing I had handy to dig into) and found out that every compression type has a matching ID. The game grabs the ID for the given type and then searches for a decoder that matches that ID.
Types 0 and 1 have no type at all (type is NULL)
type 2 indicates no compression and has a type ID of P6B0
type 3 has a type ID of EXm0. There is no decoder for this in the PC version. My guess is that its the MS XMA Xbox 360 compression.
Type 4 is EA XAS ADPCM and has an ID of Xas1
Type 5 is EALayer3 and has an ID of EL31
Type 6 has a type value of L32P
Type 7 has a value of L32S

I took a look at the code for types 5,6 and 7 and its is very closely related (but not identical)Thanks for the info.

And yes, no information is lost in the convert from EALayer3 to MP3. The quality is maintained.
## Post #53
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-08-28T14:45:59+00:00
- Post Title: Re: Some informations about EALayer3 MPEG

Thanks Zench for the tool.
