## Post #1
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-08-01T21:15:17+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

here's what i know:
in the darkness 2, some is raw wave data, some is placeholder, a like the cue file system unreal uses, (comes out when imported raw as a quick sequence of tones) and some is compressed in some manner. most probably adpcm or other audio compression, and imports as garbled static. none of these files have any headers i can see.
in warframe, everything is compressed or data cues. this makes getting any audio from it currently impossible.
in star trek, i'm told its the same as warframe, if you need samples from any game pm me. warframe is also free 2 play, so anyone on the internet can get it. I'm still not sure about the legality of uploading its unpacked files, so pm me for any samples.
## Post #2
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2013-09-25T00:35:15+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

How did this thread get buried?

I too am curious about this unplayable audio (specifically from Darkness 2). Can't anyone help me and Pepper?

I can also upload samples if need be through PM.
## Post #3
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-09-26T18:38:52+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

quick update regarding warframe and startrek, some audio now works, if you use the newer extractor specifically for warframe. but still, certain audio is compressed and headerless. in warframe all the reloading sfx are messed up while most of the shooting ones come out fine as big/little endian raw 16bit.

There are still these files that refuse to decode as raw data, which makes me think they are some kind of adpcm.
## Post #4
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2013-11-23T21:15:33+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

Just bumping this to say I'm also interested. Particularly in Warframe now that the full game has been released. 
...damn headerless WAVs, which are not really WAVs.
## Post #5
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2013-12-19T16:45:12+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

Here's a string from Warframe:

> SC_PCM, SC_WMA2, SC_WMA3, SC_XMA2, SC_ATRAC3, SC_ADPCM, SC_ATRAC9
Audio probably has to be in one of those formats. Top contenders are PCM, ADPCM, and WMA2/3. Supposedly ADPCM could be IMA, or a custom implementation, or maybe MSADPCM without the adaptation table (since it's the same for all MSADPCM files).
## Post #6
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-19T23:28:22+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

> Reply from GMMan
>
> Here's a string from Warframe:
SC_PCM, SC_WMA2, SC_WMA3, SC_XMA2, SC_ATRAC3, SC_ADPCM, SC_ATRAC9
Audio probably has to be in one of those formats. Top contenders are PCM, ADPCM, and WMA2/3. Supposedly ADPCM could be IMA, or a custom implementation, or maybe MSADPCM without the adaptation table (since it's the same for all MSADPCM files).

Looks like they plan xbox one/ps4 ports. atrac and xma are console brand specific (and they've been doing a big push for free2play in next gen), pcm is the type we can just import as raw data, i bet it's adpcm for these non decoders. I just couldn't get it sound proper with a generic header.
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2013-12-23T08:21:27+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

any idea how to extract the Star Trek audio from pc?
## Post #8
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-12-23T22:49:21+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

> Reply from Devilot
>
> any idea how to extract the Star Trek audio from pc?
reinstalling it atm. going to take a second crack at it now that there's a good extractor for warframe.

some work, as raw 44100 khz little end wavs, alot don't and are staticy mess.
## Post #9
- Username: hoodlum47
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Jan 30, 2011 6:01 am
- Post datetime: 2014-01-23T19:57:12+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

Wow, this is proving to be a tough nut to crack for everyone involved.

I particularly am working on the voice clips from Darkness 2. Going off of GMMan's notes in his "Evolution Engine Cache Extractor" thread, the "H" variant files of misc_en.cache (which is where the voices are kept) don't look like headers at all, they look to me like a list of the localisations available for each individual voice clip. To me (even though I'm no expert) it looks like there's definitely a coalition between the "Binary" variant files and the "File" variant files, It's probably a different story for the different data types throughout the caches I'm sure.
## Post #10
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2015-09-30T17:10:05+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

Any progress made on Darkness II? Have done what most already discovered on the little end, but the remaining are yet to be decoded properly.
## Post #11
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-10-01T12:12:07+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

In darkness 2 files are adpcm. I can restore headers for some files and play them, but not for all.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-03T10:13:23+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

I did some research on Darkness II.

There are total of 12830 files:

496 raw PCM (mostly music)
3715 MS ADPCM (mostly sound fx)
8619 WMA2 (mostly dialogue voices)

All three formats are well known and must be easily extracted. You just need to combine the info from H files with the body from F files.

Where can I find that tool for warframe? Maybe they already did it?
## Post #13
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2015-10-03T17:03:30+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

Only one I know of is from [blog/?p=1081](http://forum.xentax.com/blog/?p=1081)
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-15T16:00:42+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

I'm starting with the tool for this engine now. There are 3 folders with data, and the only way to do this it seems to select all 3 folders, and make something like a batch convert for all files available.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-17T20:36:49+00:00
- Post Title: Darkness 2/Warframe/Star Trek Compressed audio (headerless)

I've found all the flags and properties to build headers for all 3 kind of files. Now only need to write a tool. Expect it to be soon.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-12-18T19:38:44+00:00
- Post Title: Re: Darkness 2/Warframe/Star Trek Compressed audio (headerle

First version of the tool released, you can test it:

[viewtopic.php?f=17&t=13701](http://forum.xentax.com/viewtopic.php?f=17&t=13701)
