## Post #1
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-11T22:07:37+00:00
- Post Title: Prototype

I did some research on the new prototype game and came across the game's format of .Rcf files. To which I found the scarfaceexplorer program works wonders on, extracts just fine. Problem is, it extracts .p3d files which are completely useless to me cause I cannot find a player/decoder/converter to hear the sounds. Anyone know of anything out there that could make these p3d files playable or even converted?

I've attached one of the files for a reference. 

Thanks.
[alex_hammerfist.rar](https://xentaxbackup.github.io/file/2092_alex_hammerfist.rar)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-12T00:18:43+00:00
- Post Title: Prototype

This game uses voxware music system, i don't think there any appz for it, one would have to create a vox header for these types of files.
## Post #3
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-06-12T02:58:36+00:00
- Post Title: Prototype

There is a codec out there, that voxware released in feb 2008 but even with that and using some of the audio programs I've got and recently downloaded trials or freeware. The codec doesn't recognize the file nor does changing the extension to .vox and then running it in a raw mode to change the frequency. Any coders or wise people know of any solutions for this file extension?
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-06-12T12:44:21+00:00
- Post Title: Prototype

Well problem  is that these vox files are headerkless, like is aid no appz will read them because this is s aspcial voxware one would have to write e header for EACH file, every header is deifferent for eatch file, and decode with towav which ya can find easily.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-15T19:39:48+00:00
- Post Title: Prototype

Those files seem to be containers themselves.
They may contain vox audio data, movie subtitles, ..., even shader data.
[files.rar](https://xentaxbackup.github.io/file/2104_files.rar)
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2009-07-12T14:08:28+00:00
- Post Title: Prototype

> Reply from DerPlaya78
>
> just to let you know: i figured out the format of the sound files:

the raw sound data is stored as intel/dvi adpcm

Files which contain audio data have this format:

…header data…
FourCC = ‘RADP’
uint Channels
uint SampleRate
uint unk
uint Length

then follow blocks of 20 bytes each:

struct block {
short[2] // [0] = index, [1] = sample
byte[16] // codes
}

for multichannel files these blocks are interleaved.

i will post something more soon…

I like how you guys always jump to the conclusion something is headerless voxware if it's tricky.
## Post #7
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-07-12T15:45:42+00:00
- Post Title: Prototype

Not sure about voxware (i was not able to decode the stream) but its of course an adpcm variation
## Post #8
- Username: Drossel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 16, 2009 5:56 pm
- Post datetime: 2009-07-16T21:03:36+00:00
- Post Title: Prototype

Pretty bizarre I google the exact same thing for the exact same game and this pops up. I got as far as the p3d's but I'm stumped now. I have a friend who's working on it for me, if he finds anything I'll be happy to share. I hope someone can eventually lend a hand in this as I would love to have all the CG movies and all the dialogue for this game ^.^
## Post #9
- Username: duncanmackirik
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 27, 2009 9:22 pm
- Post datetime: 2009-08-27T14:06:08+00:00
- Post Title: Prototype

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-08-27T18:53:11+00:00
- Post Title: Prototype

Wow great thx a lot duncanmackirik
## Post #11
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2009-09-02T20:06:04+00:00
- Post Title: Prototype

Hi, first of all I'd like to thanks the cretor and the uploader of the extractor and the converter, anyway I found something not working good...
I explain better, I extracted and converted many sounds from prototype(really a bad job without the possibility of convert group of files instead of 1by1, I had to create some batch files, anyway this is not the point...)but they don't convert well some files.
They are located inside "01audio.rcf" and are the mb the mnis and the nis files(inside 01audio.rcf : "mb_3_1_1_mix.p3d", "mnis_4_3_1_mix.p3d" and "nis0-3a_mix.p3d" just to name a few).
Well these files cannot be converted properly by radp2wav, it creates the wav file from the radp file(the extraction from p3d files works well)but
that wave cannot be played(I use Wavelab it say it can't reproduce the file but it's a normal wave).
I repeat I extracted other waves from prototype and they work but the files I specified don't.
(I think those radp files are encoded differently from the others)
any ideas?

Andrew
## Post #12
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2009-09-09T14:30:32+00:00
- Post Title: Prototype

Thanks for the tools!! 

Is there any known shortcuts in dos that I can use to convert all .radp to .wav's? going through every file manually is a pain.
## Post #13
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2011-03-08T09:24:13+00:00
- Post Title: Prototype

do you help to find "wav2radp.exe" ?
## Post #14
- Username: WrappedInBlack
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Apr 27, 2012 5:51 am
- Post datetime: 2012-04-30T21:52:43+00:00
- Post Title: Prototype

Sooo.... if any of you guys still use this site can you post up a converter for p3d files? It says the other post was removed and I need a converter for Prototype 2.
## Post #15
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-04T21:20:51+00:00
- Post Title: Prototype

Ok, so we added P3D (RADP) support to vgmstream ages ago (when I ripped all three (PS3, 360, PC) back in 09). x360 version uses XMA (use VGMToolbox with ToWav and XMASH), and PS3 is Interleaved MP3 (not supported by anything at the moment). Should work for both Prototype games.
## Post #16
- Username: WrappedInBlack
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Apr 27, 2012 5:51 am
- Post datetime: 2012-05-05T12:11:33+00:00
- Post Title: Re: Prototype

> Reply from bxaimc
>
> Ok, so we added P3D (RADP) support to vgmstream ages ago (when I ripped all three (PS3, 360, PC) back in 09). x360 version uses XMA (use VGMToolbox with ToWav and XMASH), and PS3 is Interleaved MP3 (not supported by anything at the moment). Should work for both Prototype games.
The [Prototype 2] p3d files don't work with it, or maybe I did something wrong.
## Post #17
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-07T03:33:55+00:00
- Post Title: Re: Prototype

Take a closer look at my post. Only RADP P3D is supported by vgmstream.
Everything else requires an extra step such as converting.
## Post #18
- Username: WrappedInBlack
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Apr 27, 2012 5:51 am
- Post datetime: 2012-05-08T21:18:27+00:00
- Post Title: Re: Prototype

> Reply from bxaimc
>
> Take a closer look at my post. Only RADP P3D is supported by vgmstream.
Everything else requires an extra step such as converting.

So how do I convert the Xbox ones? If I use Towav first then it doesn't work and if I use Xmash first it doesn't work.
## Post #19
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-09T04:09:03+00:00
- Post Title: Re: Prototype

Play around with VGMToolbox's byte remover, advanced cutter, or VFS extractor. A small challenge but experience gained.
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-09-03T18:07:02+00:00
- Post Title: Re: Prototype

Actually, the p3d files from Prototype II don't play... And yes, radp2wav.exe doesn't convert the files properly (at least stereo doesn't work like it should)
## Post #21
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-09T14:57:00+00:00
- Post Title: Re: Prototype

next step after radp maybie tool update
## Post #22
- Username: kangmin
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Jun 17, 2012 4:38 pm
- Post datetime: 2012-12-11T05:06:16+00:00
- Post Title: Re: Prototype

any updates here? still can't manage to extract the audio in the .p3d files T_T please help me .. the game's sfx just gives me eargasm ) need it badly T_T someone?
## Post #23
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2013-01-17T10:23:55+00:00
- Post Title: Re: Prototype

this tool can convert .p3d to radp

[http://www.sendspace.com/file/vulvj2](http://www.sendspace.com/file/vulvj2)

but after that's ? for this time no news
## Post #24
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-01-18T19:42:48+00:00
- Post Title: Re: Prototype

Is there any way to rip the models with animations?
## Post #25
- Username: kiyoppon15
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 25, 2022 10:14 pm
- Post datetime: 2022-03-25T14:25:53+00:00
- Post Title: Re: Prototype

> Reply from duncanmackirik ↑Thu Aug 27, 2009 10:06 pm at Thu Aug 27, 2009 10:06 pm
>
> 
The contents of this post was deleted because of possible forum rules violation.

heya, I know this is so so late cuz it's been years but do you still have the tool? I would like to download it because I want to try to rip boss mercer's sound from the prototype 2 game. or anyone who still have the tool. Thanks
## Post #26
- Username: kiyoppon15
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 25, 2022 10:14 pm
- Post datetime: 2022-03-25T14:27:40+00:00
- Post Title: Re: Prototype

> Reply from Pepsee ↑Sun Jan 19, 2020 3:42 am at Sun Jan 19, 2020 3:42 am
>
> 
Is there any way to rip the models with animations?

well, I think you can now 
try to see the videos in this channel: [https://www.youtube.com/channel/UC4dgg5 ... 92jukDskw/](https://www.youtube.com/channel/UC4dgg5MpkhxuLN92jukDskw/)
or you can join their discord and ask more help
