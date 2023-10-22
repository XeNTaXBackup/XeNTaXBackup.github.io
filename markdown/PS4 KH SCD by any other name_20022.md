## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-14T13:23:13+00:00
- Post Title: PS4 KH SCD by any other name?

Hi everyone, I'm having some trouble with understanding how/where audio is stored in certain files got off PS4 PKG of Kingdom Hearts 1.5+2.5.

When looking through them via HxD, they clearly display either to be containers for SCD, or to be SCD by different name. 

There is also a 3D model, .mdls, which does store some audio files.

I have no idea, however, how to get these files out. PSound doesn't work anymore, which was the tool I used for the PS2 games,

Samples per each type are [here](https://www.mediafire.com/file/86p0fwlglfjjzoy/Recom+1.5.rar/file).

I'd appreciate help, please.
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-14T14:07:27+00:00
- Post Title: PS4 KH SCD by any other name?

UPDATE: VSV successfully opened. 
Feel free to ignore the .vsv file.
## Post #3
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-14T20:37:40+00:00
- Post Title: PS4 KH SCD by any other name?

Update 2: it has come to my attention that, despite the names, the audio inside the files may not be SCD. I'd greatly appreciate any tool that can detect also PS2 audio, since PSound doesn't work. It could be VAG audio.
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-14T23:36:25+00:00
- Post Title: PS4 KH SCD by any other name?

Update 3: ReCom battle voices found.
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-04T09:55:28+00:00
- Post Title: PS4 KH SCD by any other name?

So, just a small report: PSound apparently can find PS2 audio files, but not the ones specifically made for the PS4. Any way to scan through them?
## Post #6
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-04T16:19:34+00:00
- Post Title: PS4 KH SCD by any other name?

A few observations from those files in the "1.5" folder:

All of the following files open ok for me with PSound (v2.0) - some have a VAG header, some don't, but all seem to be standard Playstation 4-bit audio:

aw_006.vset - 7 sounds
aw_goofy.csv - 15 sounds
music157.dat - 33 sounds (all musical instrument sounds, which also seems to include associated midi-style song data to play them)
pc_036.dat - 3 sounds
xw_tz_5000 - 2 sounds

xa_al_0030.mdls - can't find any sounds in this file

It's possible there is other data in the files apart from the audio.  SCD seems to be a general file extension which isn't related to the type of content in the file, from what I can tell.
## Post #7
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-04T21:57:09+00:00
- Post Title: PS4 KH SCD by any other name?

> Reply from DKDave ↑Wed Jun 05, 2019 12:19 am at Wed Jun 05, 2019 12:19 am
>
> 
A few observations from those files in the "1.5" folder:

All of the following files open ok for me with PSound (v2.0) - some have a VAG header, some don't, but all seem to be standard Playstation 4-bit audio:

aw_006.vset - 7 sounds
aw_goofy.csv - 15 sounds
music157.dat - 33 sounds (all musical instrument sounds, which also seems to include associated midi-style song data to play them)
pc_036.dat - 3 sounds
xw_tz_5000 - 2 sounds

xa_al_0030.mdls - can't find any sounds in this file

It's possible there is other data in the files apart from the audio.  SCD seems to be a general file extension which isn't related to the type of content in the file, from what I can tell.

Oh yeah most of the files are like, 3d models or animations. So you're saying that what I'm finding is the only audio that there is?
## Post #8
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-04T22:16:12+00:00
- Post Title: PS4 KH SCD by any other name?

Yes, those are the only sounds in those KH files.

There are quite a lot of voice audio files in the game - maybe about 2,000 in total.  It doesn't seem like the audio format has changed from the original PS2 version, so you should be able to find them all in various archives with PSound, assuming they're not compressed.
## Post #9
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-04T22:30:54+00:00
- Post Title: PS4 KH SCD by any other name?

> Reply from DKDave ↑Wed Jun 05, 2019 6:16 am at Wed Jun 05, 2019 6:16 am
>
> 
Yes, those are the only sounds in those KH files.

There are quite a lot of voice audio files in the game - maybe about 2,000 in total.  It doesn't seem like the audio format has changed from the original PS2 version, so you should be able to find them all in various archives with PSound, assuming they're not compressed.

Thanks. In a way, it is comforting. I'm more disappointed about ReCom audio, since "cutscene" audio is actually embedded in the cutscene... not possible to get it out.
## Post #10
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-04T22:52:58+00:00
- Post Title: PS4 KH SCD by any other name?

No problem.  Do you have an example of a Re:CoM cutscene?  I could take a look at it, see if I can make anything of it.  Anything's possible!
## Post #11
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-05T07:36:23+00:00
- Post Title: PS4 KH SCD by any other name?

> Reply from DKDave ↑Wed Jun 05, 2019 6:52 am at Wed Jun 05, 2019 6:52 am
>
> 
No problem.  Do you have an example of a Re:CoM cutscene?  I could take a look at it, see if I can make anything of it.  Anything's possible!

I can send you something, definitely. What is the file extension of cutscenes?
## Post #12
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-05T15:40:08+00:00
- Post Title: PS4 KH SCD by any other name?

I'm not sure.  I know someone who has the disc, so I'll get it and have a look as soon as I can.
## Post #13
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-05T15:50:15+00:00
- Post Title: PS4 KH SCD by any other name?

> Reply from DKDave ↑Wed Jun 05, 2019 11:40 pm at Wed Jun 05, 2019 11:40 pm
>
> 
I'm not sure.  I know someone who has the disc, so I'll get it and have a look as soon as I can.

I've got most files out, if that helps.
## Post #14
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-05T16:01:06+00:00
- Post Title: PS4 KH SCD by any other name?

Yes, if you could post a list of the file names and sizes that might be useful.
## Post #15
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-05T18:25:55+00:00
- Post Title: PS4 KH SCD by any other name?

There's a folder called "stream" with such a file example: ST0100. This one sounds moderately promising.
[ST0100.zip](https://xentaxbackup.github.io/file/16325_ST0100.zip)
## Post #16
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-05T19:32:47+00:00
- Post Title: Re: PS4 KH SCD by any other name?

There's definitely some background music in that .SVM file.  Do you have a few more examples?  I may be able to work out the format and how to extract them.
## Post #17
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-06T07:26:06+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Thu Jun 06, 2019 3:32 am at Thu Jun 06, 2019 3:32 am
>
> 
There's definitely some background music in that .SVM file.  Do you have a few more examples?  I may be able to work out the format and how to extract them.

oh yes, of that and more - including battle voices. Which one would you prefer?
## Post #18
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-06T15:54:50+00:00
- Post Title: Re: PS4 KH SCD by any other name?

Your .SVM file had some audio, but it seems more like ambient background rather than cutscene audio.  Is it specifically the cutscene voice audio in Chain of Memories you need?

The cutscenes in the PS2 version seem to have exactly the same audio, and I can rip those ones as they're contained in .PSS video files.  I assume the PS4 has similar versions of these files, but they'll probably be much larger due to being higher quality video.

As an example, attached is the audio from one of the PS2 cutscenes  You can play it with Foobar/vgmstream if you keep the attached .txth file in the same folder.

[https://mega.nz/#!WuJBwChQ!qwf2e5Ja5e_X ... w0-qYyfVDo](https://mega.nz/#!WuJBwChQ!qwf2e5Ja5e_XDiNGcp-KcMGsJL-JHVR6iw0-qYyfVDo)
## Post #19
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-06T22:41:51+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Thu Jun 06, 2019 11:54 pm at Thu Jun 06, 2019 11:54 pm
>
> 
Your .SVM file had some audio, but it seems more like ambient background rather than cutscene audio.  Is it specifically the cutscene voice audio in Chain of Memories you need?

The cutscenes in the PS2 version seem to have exactly the same audio, and I can rip those ones as they're contained in .PSS video files.  I assume the PS4 has similar versions of these files, but they'll probably be much larger due to being higher quality video.

As an example, attached is the audio from one of the PS2 cutscenes  You can play it with Foobar/vgmstream if you keep the attached .txth file in the same folder.

https://mega.nz/#!WuJBwChQ!qwf2e5Ja5e_X ... w0-qYyfVDo

Not the cutscene audio, if it's not possible to detach it from the background music, which is evidently not possible to do.
I'm looking also for cutscene audio but I'm more concerned about whether Square, for some reason, kept the PS2 audio then added PS4 SCD audio, lord help me why.

Many thanks for your help!
## Post #20
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-07T16:36:04+00:00
- Post Title: Re: PS4 KH SCD by any other name?

Unless someone knows different, I think they've used exactly the same audio data for the PS4 version and just updated the graphics.  If that's the case, then you'll only get the voices mixed in with the background music, which is the majority (all?) of the dialogue in Re:CoM.

There's such a mixture of different file extensions all containing various VAG format sounds, with or without headers.  There doesn't appear to be any dialogue other than in the cutscenes that I can see.

So, the .VSV files appear to be background music for gameplay scenes, .VSM files appear to be little musical themes for when you complete a level, and the .SND files appear to be the battle sounds.  If your PS4 has .PSS files, then they will be the cutscenes.
## Post #21
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-10T07:49:02+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Sat Jun 08, 2019 12:36 am at Sat Jun 08, 2019 12:36 am
>
> 
Unless someone knows different, I think they've used exactly the same audio data for the PS4 version and just updated the graphics.  If that's the case, then you'll only get the voices mixed in with the background music, which is the majority (all?) of the dialogue in Re:CoM.

There's such a mixture of different file extensions all containing various VAG format sounds, with or without headers.  There doesn't appear to be any dialogue other than in the cutscenes that I can see.

So, the .VSV files appear to be background music for gameplay scenes, .VSM files appear to be little musical themes for when you complete a level, and the .SND files appear to be the battle sounds.  If your PS4 has .PSS files, then they will be the cutscenes.

How do you get the audio off the SND?

I cannot find and PSS file, this is all I can find in MAP folders.
[0002.zip](https://xentaxbackup.github.io/file/16335_0002.zip)
## Post #22
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-10T16:52:55+00:00
- Post Title: Re: PS4 KH SCD by any other name?

I just used PSound on your SND file to see what was there, and it found 3 sounds in old-style PSX format.  No filenames are stored for these.  I suspect there may be other sounds in the file in a different format, but I can't find anything specific from trying to play the data with various codecs.

Those files from the MAP folders don't appear to contain any audio either.

I suspect that your PS4 disc may be structured similar to the PS2 version.  On the PS2 disc of KH:CoM there's a hidden index to all of the data on the rest of the disc, so I was able to extract the files and then extract the cutscene audio.  I still need to get my hands on a PS4 disc to check if it has the same setup.  I believe the PS4 disc is about 40 GB, so that's a lot of data that's probably not visible in the normal file system.

They don't make it easy!
## Post #23
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-11T10:22:00+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Tue Jun 11, 2019 12:52 am at Tue Jun 11, 2019 12:52 am
>
> 
I just used PSound on your SND file to see what was there, and it found 3 sounds in old-style PSX format.  No filenames are stored for these.  I suspect there may be other sounds in the file in a different format, but I can't find anything specific from trying to play the data with various codecs.

Those files from the MAP folders don't appear to contain any audio either.

I suspect that your PS4 disc may be structured similar to the PS2 version.  On the PS2 disc of KH:CoM there's a hidden index to all of the data on the rest of the disc, so I was able to extract the files and then extract the cutscene audio.  I still need to get my hands on a PS4 disc to check if it has the same setup.  I believe the PS4 disc is about 40 GB, so that's a lot of data that's probably not visible in the normal file system.

They don't make it easy!

Ohh right, maybe I'd find the text file? any suggestion about that?

Many thanks for your help!
## Post #24
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-11T17:01:56+00:00
- Post Title: Re: PS4 KH SCD by any other name?

What I did with the PS2 version was to dump the first 20 MB or so of the disc sectors and then look at it in a hex editor, and I found a file table with filenames.  You can do a search for some of the following filenames to see if you find anything similar in the PS4 version:

001.pss
011.pss
012.pss

This index is usually straight after the 'normal' file system data, so it shouldn't be too hard to find.
## Post #25
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-13T22:23:12+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Wed Jun 12, 2019 1:01 am at Wed Jun 12, 2019 1:01 am
>
> 
What I did with the PS2 version was to dump the first 20 MB or so of the disc sectors and then look at it in a hex editor, and I found a file table with filenames.  You can do a search for some of the following filenames to see if you find anything similar in the PS4 version:

001.pss
011.pss
012.pss

This index is usually straight after the 'normal' file system data, so it shouldn't be too hard to find.

No PSS files but I found files with in-game text. Is this the same thing?
## Post #26
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-14T15:47:55+00:00
- Post Title: Re: PS4 KH SCD by any other name?

I don't think it's the same thing, unfortunately.  I think I really need to get my hands on the disc to have a proper look.  I might then have a better idea of getting all of the audio.
## Post #27
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-16T10:05:43+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Fri Jun 14, 2019 11:47 pm at Fri Jun 14, 2019 11:47 pm
>
> 
I don't think it's the same thing, unfortunately.  I think I really need to get my hands on the disc to have a proper look.  I might then have a better idea of getting all of the audio.

any way I can help, perhaps with the PKG?
## Post #28
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-17T15:44:32+00:00
- Post Title: Re: PS4 KH SCD by any other name?

Yes, the PKG file would be good - although it's probably about 40 GB, I would imagine!
## Post #29
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-06-25T08:16:32+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Mon Jun 17, 2019 11:44 pm at Mon Jun 17, 2019 11:44 pm
>
> 
Yes, the PKG file would be good - although it's probably about 40 GB, I would imagine!

Yes it is, even more so unpacked. Do you need links?
## Post #30
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-06-28T17:43:14+00:00
- Post Title: Re: PS4 KH SCD by any other name?

Yes, if you're allowed to.  I haven't been able to get the disc yet either.
## Post #31
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-07-05T07:11:47+00:00
- Post Title: Re: PS4 KH SCD by any other name?

> Reply from DKDave ↑Sat Jun 29, 2019 1:43 am at Sat Jun 29, 2019 1:43 am
>
> 
Yes, if you're allowed to.  I haven't been able to get the disc yet either.

I'm back, sorry for the delay. Please PVT me.
