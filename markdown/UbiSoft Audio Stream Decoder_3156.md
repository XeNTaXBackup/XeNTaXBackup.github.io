## Post #1
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-13T20:13:27+00:00
- Post Title: UbiSoft Audio Stream Decoder

I have been writing a program called DecUbiSnd to decode audio from UbiSoft streams. There is a command line part and a graphical part. For those of you who have been following along, this is just the next version. Most games that have been developed by UbiSoft use this codec, even for multiple platforms. Do I need to list any examples? The file extension usually has the mask *.SS plus a single digit number on the end to indicate which platform. Example: STREAM.SS0 (for PC). From looking at some old topics it seems there was quite a bit of frustration over this. Hopefully there will be no more.

For most files, it has two limitations:
1. It can't detect the sample rate
2. It can't detect the length of the stream but has a good guess
Without further delay, here are the current versions:
[Downloads page](https://bitbucket.org/Zenchreal/decubisnd/downloads)
DecUbiSnd-0.66.zip - Command line (including source code)
DecUbiSndGui-0.66.zip - Graphical user interface
DecUbiSndGui-0.66-src.zip - Graphical source code
Recent Changes:
Version 0.66
Fixed a very small scanning bug
Version 0.65
Added big-endian support for those streams
Fixed a scanning bug
Version 0.64
Added support for Splinter Cell Conviction interleaved streams
Version 0.63
Added support for old 4-bit mono files but there is still a bit of noise
Fixed a playback bug
Version 0.62
Added scan support for Old 6-Or-4 bit
Added decoding support for Old 6-Or-4 bit, except 4-bit mono
Version 0.61
Fixed a bug in the scanning system
Fixed a bug in the Ogg Vorbis checker
Fixed a bug in the playback system (GUI)
Notes:
I added support for PS2 SCDA streams. The graphical version is far from being 'completed', but this is just another step. There is no sound banks/maps loading yet either.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-13T20:18:48+00:00
- Post Title: UbiSoft Audio Stream Decoder

Hmm new thread, nice.

Thx zench.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-28T18:00:11+00:00
- Post Title: UbiSoft Audio Stream Decoder

Hey zench i have want to add support for the xbox 1 version of graw 1, here is the ss2 file.

[http://www.megaupload.com/?d=4HJP4TQF](http://www.megaupload.com/?d=4HJP4TQF)

I have looked into the file and it seems the start has extra data before the actual stream starts.
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-30T00:14:02+00:00
- Post Title: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> Hey zench i have want to add support for the xbox 1 version of graw 1, here is the ss2 file.

http://www.megaupload.com/?d=4HJP4TQF

I have looked into the file and it seems the start has extra data before the actual stream starts.Weird... it looks like UbiSoft ADPCM, but it doesn't decode properly.
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-30T00:22:16+00:00
- Post Title: UbiSoft Audio Stream Decoder

Could it be mixed with XBOX adpcm also?

I have tried also and yes it doesn't look like it decoded properly for me either, aslo i think there are multiple sounds in each ss2 file which filesizes range to the 40MB atleast.
## Post #6
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-30T00:52:03+00:00
- Post Title: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> Could it be mixed with XBOX adpcm also?It's definitely worth a try.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-30T00:55:12+00:00
- Post Title: UbiSoft Audio Stream Decoder

Yeah, also all the ss2 files start with the same data chunks at the beginning then go into there regular format, except this one.

[http://www.megaupload.com/?d=9NKPOEQC](http://www.megaupload.com/?d=9NKPOEQC)
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-30T02:07:41+00:00
- Post Title: UbiSoft Audio Stream Decoder

This has got to be definatly XBOX adpcm, i have tested the file with this tool.

[http://aluigi.altervista.org/papers/xbadpdec.zip](http://aluigi.altervista.org/papers/xbadpdec.zip)

Now it managed to play bits and peices of the file before it goes into static, then it plays some music again, i have decoded the file to raw and maanged to look at the waveform, there are some decoded music peices within the static.

So im guessing there are some 1-2 second segments to extract, then decode them with that program, but that could take a loong time., still gonna test it some more, you can try to with the program.
## Post #9
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2008-12-02T09:35:20+00:00
- Post Title: UbiSoft Audio Stream Decoder

Hi Zench,

thanks a million for the tool. It really made my day yesterday.  However, I tried to apply it on the music from the PC version of the first Splinter Cell game and, sadly, scanning gave no results...  Is that game not supported?

Sorry if I ask something that's been answered elsewhere, I only skimmed through the other thread.
## Post #10
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-02T15:27:48+00:00
- Post Title: UbiSoft Audio Stream Decoder

> Reply from clayman
>
> However, I tried to apply it on the music from the PC version of the first Splinter Cell game and, sadly, scanning gave no results...  Is that game not supported?For now it isn't. Unfortunately, I haven't been able to figure out the codec used by stress/fight music in this version of the game. You can, however, extract the music in STREAM.SS0. I'm glad you found my tool useful, though.
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-10T04:55:04+00:00
- Post Title: UbiSoft Audio Stream Decoder

hey zench i looked at prince of persia the new one, and it uses ogg vorbis just like assassins creed but the simple streams i cannot decode them. Also i have a feeling it could use interleaved streams but again i have not found one interleave stream yet.
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-11T22:06:20+00:00
- Post Title: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> hey zench i looked at prince of persia the new one, and it uses ogg vorbis just like assassins creed but the simple streams i cannot decode them. Also i have a feeling it could use interleaved streams but again i have not found one interleave stream yet.Perhaps you could post some pieces? I'd like to take a look at them.
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-11T23:28:07+00:00
- Post Title: UbiSoft Audio Stream Decoder

I am upping you the whole streamfile, should be much easier to understand it with the full file. 500MB.
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-12T00:31:40+00:00
- Post Title: UbiSoft Audio Stream Decoder

[http://www.megaupload.com/?d=BBQKPNQQ](http://www.megaupload.com/?d=BBQKPNQQ)

Okay here it is.
## Post #15
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-12-12T20:06:31+00:00
- Post Title: UbiSoft Audio Stream Decoder

Noooo not again!
Its very similar to assassins creed. 3 different audio types. 
Multichannel wav, voxware and ogg. The new problem is that the ogg tracks uses now different Serial Numbers. 
There is no more one serial number to one track. 
Anyway i will study this container later too.
## Post #16
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-12T20:08:42+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Thats crap, Its expected though wit there scimitar engine.
## Post #17
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-13T01:27:58+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

There are a bunch of simple streams in there, but due to a bug in the scanner it doesn't recognize them. If you manually find each one they can be decoded just fine, though. I probably won't get around to fixing the bug for a while. Perhaps it would be best to figure out the container format and go from there.
## Post #18
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-13T01:49:38+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Really because i found one and it cannot be decoded even with the command line app.
## Post #19
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-13T02:12:14+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> Really because i found one and it cannot be decoded even with the command line app.I didn't really study the file too closely, so I'm not sure. What offset is it at? Do you know if it can be decoded as raw?
## Post #20
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-13T02:33:15+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Search for this one

FILEDATACommon_BAO_0x00477953.

Wont decode even as raw, i have looked at other ones that were not ogg and so far wont decode.
## Post #21
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-12-13T10:53:21+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Looks like headerless voxware

Zench has right you can decode a few files when you cut the stream.
Anyway dont forget to look to the other files. Its very possibel that the stream is cutted like creed
## Post #22
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-13T15:45:37+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Yeah im still looking for a couple of file to decode but no luck, theres alot in there.
## Post #23
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-12-21T00:51:03+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

New version at the first post: 0.61 and beta 2. I fixed only a few bugs, and I wan't able to test it on the entire file. I haven't looked into the headerless stuff yet.

Edit: oh, must add: there are also some headerless interleaved streams in there too! That's probably what you found. We are going to have to find the headers for them.
## Post #24
- Username: creamycenter
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 22, 2009 5:56 pm
- Post datetime: 2009-04-22T10:21:36+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #25
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-04-23T02:50:54+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hmmmmm...

At first glance it doesn't look really similar to the other UbiSoft files, maybe it's compressed with IMA-ADPCM. I don't know right now. Maybe I'll look at it a little later.
## Post #26
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-07T22:57:28+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Arggg...

Sorry I really couldn't get this. I tried a few things but no luck. It isn't much like the other UbiSoft audio files, so I don't really know.
## Post #27
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-29T18:54:40+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I've cracked the audio codec used in XIII and Splinter Cell 1 PC, so stay tuned and I'll update DecUbiSnd soon.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-05-30T03:24:42+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

cool.

will be nice for XIII
## Post #29
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-30T21:17:40+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The new version is posted!  

I had absolutely no idea what to call the codec used by XIII and SC1 PC, so I went with 'UbiSoft Old 6-Or-4 bit' because the files can be either 6-bit (XIII) or 4-bit (SC1 PC). One little thing, though, is I didn't add support for 4-bit mono files. So if anyone wants to decode the voice tracks from SC1 PC (which is the only place I saw it), just tell me.
## Post #30
- Username: xkLOJ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 21, 2008 5:52 pm
- Post datetime: 2009-05-31T07:03:59+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Ok Zench, i begin testing new version of your tool. If you need, i can upload folder with music from game (~1.3 Gb).

upd: IT`S WORK   and decode sound(music) properly, thanks to you Zench  .
## Post #31
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2009-07-28T10:16:14+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hi Zench, and thanks again for your tool.  A quick one -- Does it support Prince of persia 2008 .forge files? I'm dying to be able to extract the music from the game.
## Post #32
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-07-28T21:46:17+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from clayman
>
> Hi Zench, and thanks again for your tool.  A quick one -- Does it support Prince of persia 2008 .forge files? I'm dying to be able to extract the music from the game.I don't know. It's probably like Assassin's Creed, doable but very very difficult. I'm probably not a good person to ask because I don't have the game. Perhaps Kataah can help you? We were just trying a few posts ago but I'm not sure what the verdict was. But hey just give it a shot and see if it works.
## Post #33
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-09-08T10:06:38+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Zench
>
> So if anyone wants to decode the voice tracks from SC1 PC (which is the only place I saw it), just tell me.

I want more than anyother sound streams! Coz I'm going to translate speeches for the game, so can I extract and import with your tool?
## Post #34
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-09-28T01:13:23+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hello zench i took a look at double agent for 360 and it seems to use a different ubi stream version rather than the pc version.

i provided the SS4 file below, this seems compressed as the pc's is 1gb, this is like 300mb.


Could it be XMA mixed?

[http://www.megaupload.com/?d=V048VJB6](http://www.megaupload.com/?d=V048VJB6)
## Post #35
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-01T23:33:10+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Yes. Here's a tool I made to more or less decode it automatically. First do a layer extract on the big file, then extract this ZIP to a directory with towave, and then run DecodeCurrentDir. It's more of a hack so it doesn't work 100 percent of the time but it should be okay.
[AddXMAHeader.zip](https://xentaxbackup.github.io/file/2406_AddXMAHeader.zip)
## Post #36
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-02T06:07:20+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Thx zench.

BTW will this work for other headerless xma's if i can edit the batch file?
## Post #37
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-02T15:39:24+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

plz Zench make so to extract wav/import in 1st splinter cell game's sound speech files, i want to translate it
## Post #38
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-02T22:22:55+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> BTW will this work for other headerless xma's if i can edit the batch file?I suppose it might. It just looks for the 08 00 00 00 pattern in the file and replaces what was before it with a generic header.

> Reply from Gocha
>
> plz Zench make so to extract wav/import in 1st splinter cell game's sound speech files, i want to translate itDon't worry, I haven't forgotten about you. I know it's been a long time, but I've been very busy recently so I just haven't had time to work on it. I assure you, it may take a long time (being a few months or more), but I will finish it.

Edit: Fixed little mistake in the search pattern.
## Post #39
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-03T01:34:17+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Zench
>
> OrangeC wrote:BTW will this work for other headerless xma's if i can edit the batch file?I suppose it might. It just looks for the 00 00 00 08 pattern in the file and replaces what was before it with a generic header..

Tried some hacks but didnt seem to work. it just generated the header only in the output xma file, i might be doing soemthing wrong but not sure.

My file only has the stream id at the beginning.
## Post #40
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-03T18:37:57+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I don't know if this will help or not but it actually searches for 08 00 00 00 with the 08 at the beginning, not the other way around like I wrote before. And that pattern has to be on an offset that is a multiple of 4 (for example 0 4 8 ...).
## Post #41
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-03T18:54:47+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Your right, however there are other xma types with different patters to decode from, like 1C 00 00 00  ect ect.

This tool has a lot of potential though, its such a pain doing headerless xma's one by one then renaming the decoded file again after you convert.
## Post #42
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-21T01:30:14+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #43
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-10-21T21:53:35+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Okay i have used the maki plug in to extract the BAO's it is indeed xma data, and the patter retaisn the same as zench said, so i put in the xma header before the 08000 pattern and it converted one of the files, i dont know how it willl work for interleaved files, but i will try.

EDIT: Okay interleaved streams didn't decode, i think this is our main problem here.

[http://www.megaupload.com/?d=C8QR17OQ](http://www.megaupload.com/?d=C8QR17OQ)

here is a sample
## Post #44
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-30T04:37:06+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hi all! It's been a while.

> Reply from OrangeC
>
> Okay i have used the maki plug in to extract the BAO's it is indeed xma data, and the patter retaisn the same as zench said, so i put in the xma header before the 08000 pattern and it converted one of the files, i dont know how it willl work for interleaved files, but i will try.

EDIT: Okay interleaved streams didn't decode, i think this is our main problem here.

http://www.megaupload.com/?d=C8QR17OQ

here is a sampleThis is more of an XMA issue rather than a UbiSoft stream issue, right? I really don't know that much about XMA. What we need to do is to parse the headers, I think. Sorry that I haven't been working on this. 

Status update for SC1 voice audio: I'm about 75% done with the decoder. There is still a little bit of noise in the decoded audio which I have to locate the source of.
## Post #45
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-30T08:17:33+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Thanks Zench! I'm just finished translating Splinter Cell 1 text and waiting you to finish it,

See your P.M.
## Post #46
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-10-30T15:24:17+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

S'okay. How would we go about to parse these headers?
## Post #47
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-10-31T21:16:09+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from pietastesgood
>
> S'okay. How would we go about to parse these headers?There's a header file floating around that contains some of the structures used. That would give us a big clue.
## Post #48
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-01T01:46:06+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I dont have the game so maybe pie guy can supply you with those.
## Post #49
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-01T15:25:04+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #50
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-11-05T17:15:45+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hi peaple,

Zench had updated Decoder version to 0.63, see the post #1

But I am very sad it could not encode back files. For example it looses the full price for me as I can't encode files back to make changes in game.

I hope one day that would be possible
## Post #51
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-05T17:28:11+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Would be very cool to add xma stream support for the gui.
## Post #52
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-11-06T01:06:57+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Gocha
>
> But I am very sad it could not encode back files. For example it looses the full price for me as I can't encode files back to make changes in game.

I hope one day that would be possibleWhen I said that, I spoke too soon.  

While we can't encode the format of SC1 voice files, we can (very easily) encode a different format that works just as well! Modify the MAPS.LM0 file a little bit, and it works!  

Sorry that I didn't think of it before.

> Reply from OrangeC
>
> Would be very cool to add xma stream support for the gui.It would be nice. I'll think about it.
## Post #53
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-06T01:52:46+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Any luck with those header xma parsings?
## Post #54
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-11-06T23:19:34+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> Any luck with those header xma parsings?Oh, oops. Totally forgot.
## Post #55
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-06T23:35:38+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

haha no problem man. if you need any samples let me know i have creed 1 also.

But i think ubisoft xma streams are all the same with the 08 offset thing.
## Post #56
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-12-11T09:15:51+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

pie brought this to my attention, I've written something to handle the Prince of Persia streams.  The files it produces have plain XMA after some header info.

The trouble I'm running into is that Maki + Elika is dumping 0x31 too few bytes of the Common_BAO_0x00440f00 file I'm using for testing.  It looks like it should start dumping the file 0x31 bytes later.  I'll give an example here of pointing my utility directly at the file within Data360_StreamedSounds.forge.

```

```

The offset is optional, if the files were extracted properly you could exclude it, but here we're pointing it at a file starting at 0x1BAA9B8 in the container.  PoP360XMA detects the end of stream properly.

It produces the following files:

```
1: Data360_StreamedSounds.forge_001 3977864 bytes
2: Data360_StreamedSounds.forge_002 3803684 bytes
3: Data360_StreamedSounds.forge_003 4201036 bytes
4: Data360_StreamedSounds.forge_004 3582464 bytes

```

Data360_StreamedSounds.forge_000 has the stream at 0x268, 001 at 0x288, 002 at 0x224, 003 at 0x24C, 004 at 0x200.  xma_parse 0.6 can handle all these (0.5 was tripped up by 003) but you don't actually have to parse the stream to get it, it's just the rest of the file.
PoP360XMA 0.1 and xma_parse 0.6 on my page [http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)
## Post #57
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-12-11T16:01:44+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Nice HCS!! Great work!
## Post #58
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-12-11T17:49:39+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Thanks HCS.
## Post #59
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-12-11T17:52:43+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Be sure that you look inside the the other sound container too - iam not sure if this game use the same sound system like Assassin's Creed 1 PC - had no time to look inside this game yet but if yes then you will find sound files and maybe headers for the main music inside the other container too.

great work hcs
## Post #60
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-12T19:47:16+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #61
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-19T12:16:46+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #62
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-03-08T08:34:05+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hello, guys.

During the extraction of some layers from STREAM.SS0 (SC: Double Agent) i receive an error:
[](http://img186.imageshack.us/i/errorms.jpg/)

Can anybody tell me - where is the problem? In Stream file or in decoder?

Thanks in advance!
## Post #63
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-03-12T23:42:17+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from prysm
>
> Can anybody tell me - where is the problem? In Stream file or in decoder?Most likely the decoder. You're just going to have to try decoding different combinations of segments, as I'm not sure what's wrong.
## Post #64
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-13T05:18:13+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Zench
>
> prysm wrote:Can anybody tell me - where is the problem? In Stream file or in decoder?Most likely the decoder. You're just going to have to try decoding different combinations of segments, as I'm not sure what's wrong.

I've tried to unpack resources from Splinter Cell 1(not Pandora Tomorrow, chaos theor....).


DecUbiSndGui-0.63 can process 
Music_Birmanie.SS0
Music_Common.SS0
Music_Georgie.SS0
Music_Usa.SS0


DecUbiSndGui-0.63 Can't extract "STREAM.SS0" sound files.
Most unpacked files have noisy and extened(?) sound(may be warping.......).

How can I extract this?
STREAM.SS0  ?
## Post #65
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-13T11:17:01+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Try to open it with MFAudio, it could be RAW PCM. Many Ubisoft games use a combination of their own codec and PCM, so it's likely that it's also the case with Splinter Cell.
## Post #66
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-03-14T06:16:34+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from AlphaTwentyThree
>
> Try to open it with MFAudio, it could be RAW PCM. Many Ubisoft games use a combination of their own codec and PCM, so it's likely that it's also the case with Splinter Cell.

MFAudio is a UBI utility for Playstation2.
Is this tools able to decompress a splinter Cell 1 of PC version?
## Post #67
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-03-15T17:26:18+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from wuixntx
>
> AlphaTwentyThree wrote:Try to open it with MFAudio, it could be RAW PCM. Many Ubisoft games use a combination of their own codec and PCM, so it's likely that it's also the case with Splinter Cell.

MFAudio is a UBI utility for Playstation2.
Is this tools able to decompress a splinter Cell 1 of PC version?
MFAudio isn't only for PS2 and it's not a Ubi Utility. It just has some formats implemented and can transcode between them. Thus it can also decode any of these formats.
## Post #68
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-16T14:21:55+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Im trying to make a list of the tracks inside the file menu.pk (from latest Splinter cell), and using the command line tool, but the tool it's bit.."strange"..

I want make a list, rigth? i do:

> DecUbiSnd.exe menu.pk  -n
According to the readme the parameter "-n"  it's 

> -n, --info            Output information about the file

But i get 

> Output file not specified
## Post #69
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-05-17T22:10:32+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

To list all of the tracks in a particular file, use the -S switch instead of the -n one.

All -n does is output some (usually useless) information about whatever it's currently decoding. Thus an output file would need to be specified. Although, I don't really like that the way it works now, but I haven't gotten around to changing it.
## Post #70
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-06-01T13:55:59+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Zench
>
> prysm wrote:Can anybody tell me - where is the problem? In Stream file or in decoder?Most likely the decoder. You're just going to have to try decoding different combinations of segments, as I'm not sure what's wrong.
Ok, i'll try. Thanks man!
## Post #71
- Username: iservealot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 06, 2010 4:08 pm
- Post datetime: 2010-07-07T20:59:07+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Really Really Really love your tool. Can't thank you enough for developing this. I was looking at some of the Splinter Cell games attempting to figure out how to extract OGG Vorbis information out of it.

I sent you a PM with a question about possibly creating new .sso data. Wanted to see if you had any ideas about Splinter Cell (and other Unreal powered Ubisoft games) work in conjunction with .sso sound files. The actual .uax Unreal sound file seems to just contain the name headers of sounds for that package, but I would imagine that it is somehow pointing the game to look at .sso data for actual sound content?

Could you shine some light on this for me?

Thanks!!
## Post #72
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-13T04:19:37+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

About the prince of persia for Wii the program wont recognise the smaller spk files.

[http://www.megaupload.com/?d=JWS09NK7](http://www.megaupload.com/?d=JWS09NK7)
## Post #73
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-13T18:13:45+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from iservealot
>
> Really Really Really love your tool. Can't thank you enough for developing this. I was looking at some of the Splinter Cell games attempting to figure out how to extract OGG Vorbis information out of it.I'm glad you found it useful  

Alright, this is what I know about how the Splinter Cell games interact with the actual sounds. From the original game to Double Agent the offsets/sizes and in some cases filenames are stored in .SM0 or .LM0 files, which also store sounds (that weren't meant to be streamed). Conviction uses something different that I haven't really looked at.

I'm not entirely sure, but I think that each sound (as specified in the .SM0/.LM0 file) has a resource ID that is referred to by a (possibly more than one) .UAX file. You can open these .UAX files in Game Extractor to get the contents. I'm not exactly sure what it's used for. It's been a while since I've looked at these files, which aren't as important as the .SM0/.LM0 files.

So your best bet in replacing sounds in the original through Double Agent would be to edit the MAPS.SM0 file for sounds and MAPS.LM0 for voices. Actually if you didn't change the length of the sound, you wouldn't even need to do that. Simply replace the data in the .SS0 file. I should mention that each game is a little bit different when it comes to audio, so creating a general sort of repacker would be harder than creating one for a particular game.

At the bottom I've attached something that might help you. It is an encoder for the sort of ADPCM that UbiSoft uses in the Splinter Cell series and some other games. Usage should be self explanatory.

> Reply from OrangeC
>
> About the prince of persia for Wii the program wont recognise the smaller spk files.

http://www.megaupload.com/?d=JWS09NK7 

I should have seen this coming. It's a big-endian version of new interleaved format. I'll add it shortly.
[EncUbiSnd.zip](https://xentaxbackup.github.io/file/3233_EncUbiSnd.zip)
## Post #74
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-13T18:38:20+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

sweet thanks zench.
## Post #75
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-13T22:15:44+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Updated at [the original post](http://forum.xentax.com/viewtopic.php?p=26497#p26497).
## Post #76
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-13T22:36:14+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

[http://www.megaupload.com/?d=5O04O8XH](http://www.megaupload.com/?d=5O04O8XH)


I have a problem with this file.
## Post #77
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-07-15T01:50:12+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from OrangeC
>
> http://www.megaupload.com/?d=5O04O8XH


I have a problem with this file.It doesn't have a header, that's all. Add "-i 96 --input-type ubi_raw" without the quotes to the command line and it should work. Also, that tool to add the header should work.
## Post #78
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-07-15T02:07:03+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

thx zench.
## Post #79
- Username: iservealot
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 06, 2010 4:08 pm
- Post datetime: 2010-07-30T07:17:57+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Zench
>
> iservealot wrote:Really Really Really love your tool. Can't thank you enough for developing this. I was looking at some of the Splinter Cell games attempting to figure out how to extract OGG Vorbis information out of it.I'm glad you found it useful  

Alright, this is what I know about how the Splinter Cell games interact with the actual sounds. From the original game to Double Agent the offsets/sizes and in some cases filenames are stored in .SM0 or .LM0 files, which also store sounds (that weren't meant to be streamed). Conviction uses something different that I haven't really looked at.

I'm not entirely sure, but I think that each sound (as specified in the .SM0/.LM0 file) has a resource ID that is referred to by a (possibly more than one) .UAX file. You can open these .UAX files in Game Extractor to get the contents. I'm not exactly sure what it's used for. It's been a while since I've looked at these files, which aren't as important as the .SM0/.LM0 files.

So your best bet in replacing sounds in the original through Double Agent would be to edit the MAPS.SM0 file for sounds and MAPS.LM0 for voices. Actually if you didn't change the length of the sound, you wouldn't even need to do that. Simply replace the data in the .SS0 file. I should mention that each game is a little bit different when it comes to audio, so creating a general sort of repacker would be harder than creating one for a particular game.

At the bottom I've attached something that might help you. It is an encoder for the sort of ADPCM that UbiSoft uses in the Splinter Cell series and some other games. Usage should be self explanatory.

Thanks again! I'll take a look at the tool over the weekend. Should really help with what I'm looking to do. 
If you don't mind me asking, what made you so interested in the Ubisoft packaging of sounds? Any close ties to Ubisoft?
## Post #80
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-04T18:25:23+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from iservealot
>
> If you don't mind me asking, what made you so interested in the Ubisoft packaging of sounds? Any close ties to Ubisoft?I don't mind at all. I don't have any ties with UbiSoft, except that I play some of their games and explore their data formats.  

I guess that when I like a game, I want to explore its data and usually rip the music from it, and I like the Splinter Cell series. UbiSoft uses similar data formats for its game audio, so I keep updating my tool with the help of others at this forum to support the other games.
## Post #81
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-09T12:21:02+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #82
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-10T11:00:59+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #83
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-10T20:41:56+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Will do
## Post #84
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-10T20:44:13+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Thanks for your efforts, Zench.
## Post #85
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-11T14:56:04+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #86
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-14T23:32:49+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #87
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-08-16T18:38:07+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #88
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-08-24T17:16:26+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #89
- Username: bmn
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2010-09-06T07:29:44+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #90
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-09-11T13:34:00+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Is there any advance?

It'll be good for me to use this tools for splinter cell series and assassin's creed 1.

Is it possible to extract sound files from forge format?
## Post #91
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2010-09-16T23:43:11+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #92
- Username: bmn
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2010-09-17T12:32:16+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #93
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-13T13:53:08+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I was just working on Jame's Cameron's Avatar (PC), when I found a lot of these OGG end parts again. But this time I'm not able to reproduce the streams because there are a bunch of different OGG start parts.
How can I recognize
- which part to use?
- where to cut off the start?
Any help is highly appreciated! Thanks in advance!
## Post #94
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-10-31T16:57:15+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Any progress?
Anyone CAN unpack sound files from Splinter cell brothers?
## Post #95
- Username: Goit
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 20, 2010 7:56 pm
- Post datetime: 2010-12-21T02:30:29+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I'm trying to extract the music from POP2008. I'm using the PC version of the game. However, I could only find music files in Datapcstream.forge, and not all pieces are in there. For example, the track "a fight between light and darkness" is not found in there. Does anyone know where the other files are stored?
## Post #96
- Username: derbleistift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 16, 2011 8:11 am
- Post datetime: 2011-02-16T00:37:24+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #97
- Username: derbleistift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 16, 2011 8:11 am
- Post datetime: 2011-02-17T23:44:35+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The contents of this post was deleted because of possible forum rules violation.
## Post #98
- Username: Arti
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 12, 2011 10:15 am
- Post datetime: 2011-07-12T02:34:17+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hello,

looking at the previous posts, how far are we from an encoder for 6-bit (XIII) files right now?

Is it possible at all?

Kind Regards
## Post #99
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-01-27T10:43:46+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hi Zench.I made to extract gameplay sound of prince of persia 2008 inclusive puzzle gameplay music.Please tell me,is any chance for extract cutscene music and main menu music A fight of light and darkness?
i scanned all files from the game but no results.
I use DecUbiSndGui 0.66
I wondering old version work but no links for downloading them.
Please answer me.My email is [nitoinviorel@yahoo.com](mailto:nitoinviorel@yahoo.com)
Also tell me is any chance to extract music from Prince_of_Persia_Trilogy_3D ps3(that include all pop 1 2 3)
and tell me any chance extract pop tfs wii ps3 and xbox music?Thank you and sorry for my english.
## Post #100
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-01-28T16:35:00+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from nitoiviorel
>
> Hi Zench.I made to extract gameplay sound of prince of persia 2008 inclusive puzzle gameplay music.Please tell me,is any chance for extract cutscene music and main menu music A fight of light and darkness?
i scanned all files from the game but no results.
I use DecUbiSndGui 0.66
I wondering old version work but no links for downloading them.
Please answer me.My email is nitoinviorel@yahoo.com
Also tell me is any chance to extract music from Prince_of_Persia_Trilogy_3D ps3(that include all pop 1 2 3)
and tell me any chance extract pop tfs wii ps3 and xbox music?Thank you and sorry for my english.
I'd like to request some support for the Prince of Persia HD Trilogy as well. I've posted the sound.big archive here: [viewtopic.php?f=10&t=8117](http://forum.xentax.com/viewtopic.php?f=10&t=8117)
## Post #101
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-01-28T22:44:08+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

ok droolie.i will wait forever that soundtracks.i have pop sot ww t2t ost(t2t are incomplete) and have ripped but t2t soundtracks ripped hear so bad with pops.that is the reason for i need to extract tracks from pop 3d.maybe that tracks are cleary without pops and scratches...thx and pray God someone ask our posts.I need very much prince of persia the two thrones soundtracks complete in good sound (wave) format.
## Post #102
- Username: JasonTodd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 29, 2012 9:35 am
- Post datetime: 2012-04-29T01:45:28+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hey - trying to use this thing with the PC version of Batman: Vengeance... I can't figure out what to rip; I can get what seem to be .wav files from the maps.SM0 and strm.SM0 files, but it's just static nonsense with what sounds like the voices [my target] intermixed - albeit horribly garbled, low and unintelligible. Any help would be appreciated; rips of the bgm are up on youtube and I'm sure they were done using this.
## Post #103
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2012-04-29T05:22:16+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from JasonTodd
>
> Hey - trying to use this thing with the PC version of Batman: Vengeance... I can't figure out what to rip; I can get what seem to be .wav files from the maps.SM0 and strm.SM0 files, but it's just static nonsense with what sounds like the voices [my target] intermixed - albeit horribly garbled, low and unintelligible. Any help would be appreciated; rips of the bgm are up on youtube and I'm sure they were done using this.Oh my god, you found some more of that stuff like from the PC version Splinter Cell 1 and XIII. Will investigate immediately.  

(Yes, I came out of hiding to post this  )

Update edit: As usual, the problem is a bug in DecUbiSnd. Expect a new version sometime soon (there will be other stuff I'm adding too). Thanks for the tip. I really like seeing this particular format.
## Post #104
- Username: JasonTodd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 29, 2012 9:35 am
- Post datetime: 2012-04-29T11:08:50+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Awesome, I'll stay tuned.
## Post #105
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-05T16:32:54+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Help me extract sound from nintendo ds file.pop the fallen king 2008
I wanna see what music they put in nintendo ds pop.
here is the link:Zench or anybody help me!
[http://www.mediafire.com/?cjwneq84s0yxqk2](http://www.mediafire.com/?cjwneq84s0yxqk2)

edit;
here is the tool who can extract content from nintendo ds file.
[Nds.rar](https://xentaxbackup.github.io/file/5821_Nds.rar)
## Post #106
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-20T11:08:05+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hello again.
I have made extract Data360_StreamedSounds_dlc.forge from Prince of Persia Epilogue Downloadable Content file.
I scanned with DecUbiSnd and i found 4 wav's unplayable.
Someone look here please and do a research.
Thank.
Here is the file where music is.
[http://www13.zippyshare.com/v/21002043/file.html](http://www13.zippyshare.com/v/21002043/file.html)
## Post #107
- Username: nitoiviorel
- Rank: beginner
- Number of posts: 21
- Joined date: Fri Oct 07, 2011 6:37 pm
- Post datetime: 2012-09-29T13:59:30+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Zench you are here,or you unsuscribbed to this topic?
I wanna help me with that dlc epilogue.
## Post #108
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-28T13:21:23+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Anyone knows how possible to save a massive(many files) of audio in any formats(save as common, extract as layers)?

I dont found it in latest version(0.80).
## Post #109
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2014-05-28T17:45:39+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Researchman
>
> Anyone knows how possible to save a massive(many files) of audio in any formats(save as common, extract as layers)?

I dont found it in latest version(0.80).
select all the files you want to export, click first one, hold shift, click last one, release shift, click the export option you want.

it does tend to freeze while exporting though, not that its not working on exporting files, it just sometimes doesnt update progress for a while or runs into a bad file and stalls.
## Post #110
- Username: Researchman
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Fri Jun 11, 2010 7:08 pm
- Post datetime: 2014-05-28T18:33:20+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I try it, but got 6 files max, not 8049.
Possible reason - files dont have normal names, only offsets(like 000C164D).
## Post #111
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2014-05-29T21:37:12+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

> Reply from Researchman
>
> I try it, but got 6 files max, not 8049.Fixed in version 0.81 (I'm back from the dead)
## Post #112
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2014-07-10T18:10:26+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

The watchdogs sound.dat file from the pc version will not scan.

Can you please look into it?
## Post #113
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2014-07-14T03:15:20+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

That's because sound.dat is larger than 2 GB, and DecUbiSnd is 32-bit and won't support files that big. You can either break sound.dat into smaller chunks and scan them, or use the Watch Dogs .dat file unpacker (I don't know the link offhand) and scan the resulting files. If there's need in the future I might update to support larger files.
## Post #114
- Username: exe64
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 24, 2014 4:01 am
- Post datetime: 2014-09-23T23:01:29+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

just saying hi and thanking Zench for making this
you made an impact on my life man, ive been looking for something to open
stream files in a game for the last 24 hrs and you helped me with your long-term work on this

honestly every search i did on sb0 or Ubisoft extensions in general files led me to forum conversations from 2005-2007 and i was getting kind of depressed,
until i finally found out that the tool i was using was unable to open stream files at all (like you said in 1st post ppl couldnt find a way around it)
kudos to you sir
## Post #115
- Username: MCSOBA
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 06, 2014 4:27 am
- Post datetime: 2014-10-05T20:42:44+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

hello am new here ...
im converting audio .spk .pk Ubisoft for my repacks.... 
I am observing this program DecUbiSndGui....

I can only extract the packages to .ogg wav and .layer 
how to pack again to spk? 

how to convert tracks .layer??

after extracting .wav .ogg the audio becomes futile,, What have to do??

TKX...
## Post #116
- Username: withmorten
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 28, 2012 11:03 pm
- Post datetime: 2015-07-17T01:19:02+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Hi there!

Love your DecUbiSndGui program. I want to use it to extract very specific files from Assassin's Creed 1, but only those with 2 channels.

For that I want to edit the source code and recompile it (to basically only show files with 2 channels in the list of Streams found). I didn't want to start getting into how your program works before actually figuring out how to recompile it. Which was a good thing, because I've run into a lot of troubles the past few hours with no solutions.

Edit: Scatch all that.

I managed to make a VS 12 2013 project, which I successfully opened in VS 2013 Express, resolved the various dependencies (vorbisfile.h, portaudio.h, ogg.h etc), now I'm having these 7 errors:

[http://puu.sh/j2uFz/504b0a24f8.png](http://puu.sh/j2uFz/504b0a24f8.png)
## Post #117
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-11-20T14:07:18+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

[http://www59.zippyshare.com/v/kAzuLYCz/file.html](http://www59.zippyshare.com/v/kAzuLYCz/file.html)
Can you please look into these unsupported files? They should be ubi adpcm but decubi doesn't find anything.
## Post #118
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-11-22T11:47:04+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Could you try to add support for Wii U audio streams?
[http://www.mediafire.com/download/2nrgu ... 00017d.rak](http://www.mediafire.com/download/2nrgueahl8s2bch/0000017d.rak) here is a sample
## Post #119
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2016-02-11T13:45:59+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

Can somebody tell me which command line option I have to use for DecUbiSnd.exe to extract individual ogg layers? I always get an error after about 20 secs.
## Post #120
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2016-08-08T17:51:52+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

SS6 PS3 Splinter Cell music file extract fails

Recent version used:
DecUbiSndGui-0.81

```
https://bitbucket.org/Zenchreal/decubisnd/downloads
```


Here are the samples of SS6 files 

```

```

Previous SS1 files of PS2 version of Pandora Tomorrow, extracted fine, but not the same music files from PS3 version - SS6, shows nothing after analyzing.
MFaudio extracts it well, just 36kHz set is needed (stream is in stereo), but segments are not recognized, everything from the file is played one by one. ADPCM Player not plays it, as well as all programs from here: 
Psound
jpsxdec
VideoGameSoundConverter_2.0
Watto Game Extractor

Any ideas?
Maybe other programs?
## Post #121
- Username: openyourmind
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 14, 2017 3:27 am
- Post datetime: 2017-06-13T21:06:34+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I know  Zench wasn't online since 2016, but I hope he reads this anyway

Thank you for creating this wonderfull tool. Absolutely amazing, what talents like you come up with.

When trying to extract music from SCDA both xbox and ps2 version have trouble extracting JBA HQ music (in stream.ss1 on ps2 or mus_jbahq.ss2 on xbox). All the other songs work absolutely wonderfully though.

I've read your post that you like splinter cell, so I hope you can help with this, please.
## Post #122
- Username: bsod49
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Jul 30, 2016 6:29 am
- Post datetime: 2018-02-25T13:28:36+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I would also find usefull potential adding option of splice RAW segments. Not just extracting single ones. Useful when RAW files not requires conversion - while they possess correct audio header. We can avoid making files bigger (by default filed are spliced in WAV only. In RAW (with option of changing extension in explorer [all files]) only as bunch of/single segments.

From the other hand, it happens that after splicing only part of the RAW files, result file not plays entirely, but it's divided to various streams inside e.g. in mpc hc. Foobar extracts even segments correctly, but it's exception.

But we can try on our own. File joiner will enough. It's just a matter of extracting segments, and picking some of them, and checking in MPC-HC whether something is in audio 2.
## Post #123
- Username: 3A2watup
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 16, 2018 8:04 am
- Post datetime: 2018-08-16T00:06:43+00:00
- Post Title: Re: UbiSoft Audio Stream Decoder

I would like to thank you for this tool, really helpful
