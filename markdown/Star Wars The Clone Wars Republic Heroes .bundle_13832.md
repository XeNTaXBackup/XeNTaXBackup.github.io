## Post #1
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-16T19:46:10+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

So I was originally needing someone to extract files from the Nintendo DS game, but I managed to do it myself.

I have the file I need to get into, cw_hh_2.bundle

I have no doubt that all of the games audio files are within this file. The only problem is I am using Windows, and after research the only way to get into a .bundle file is using the Finder program on a Mac computer?

I was wondering if anyone could help me with this, or if there is some sort of way to get all of the files out of this .bundle file without the need of a Mac computer.

I have uploaded the .bundle file here:
[http://www.mediafire.com/download/cen7k ... h_2.bundle](http://www.mediafire.com/download/cen7kx592p4b5tb/cw_hh_2.bundle)

If anyone can help me extract all the audio files from this I would sure appreciate it.
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-16T20:56:03+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

This file has no information about the files in it. So there must be some other file with resources directory.

Anyway, by just scanning it, it's possible to write a tool or script that will extract 1000's of IFF files, that are some ADPCM audio files as I can see. Do you have a decoder for these audios?
## Post #3
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-16T21:53:23+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

> Reply from daemon1
>
> This file has no information about the files in it. So there must be some other file with resources directory.

Anyway, by just scanning it, it's possible to write a tool or script that will extract 1000's of IFF files, that are some ADPCM audio files as I can see. Do you have a decoder for these audios?

This .bundle file does have a .toc file and from research apparently this has information on the asset files or something.
[http://www.mediafire.com/download/2al5e ... w_hh_2.toc](http://www.mediafire.com/download/2al5ebaa8u2ly7t/cw_hh_2.toc)

I don't know if this helps at all, I have no idea how to decode it, I just was able to unpack the .nds game file with dslazy program.
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-17T07:42:17+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

yes with this file we can split the bundle into individual files.
many of them will be audio files, all encoded with IMA ADPCM, with a very low freq of 8000 hz

like this one [http://www104.zippyshare.com/v/AHMnM22p/file.html](http://www104.zippyshare.com/v/AHMnM22p/file.html)

there are other versions of the game with much better audio
are you sure you need to do this?
## Post #5
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-17T15:46:53+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

> Reply from daemon1
>
> yes with this file we can split the bundle into individual files.
many of them will be audio files, all encoded with IMA ADPCM, with a very low freq of 8000 hz

like this one http://www104.zippyshare.com/v/AHMnM22p/file.html

there are other versions of the game with much better audio
are you sure you need to do this?

The voice I actually want is a droid voice, so the low quality adds a nice effect to it. Yeah I do need to do this, I need all possible audio.
## Post #6
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-24T15:12:31+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

> Reply from daemon1
>
> yes with this file we can split the bundle into individual files.
many of them will be audio files, all encoded with IMA ADPCM, with a very low freq of 8000 hz

like this one http://www104.zippyshare.com/v/AHMnM22p/file.html

there are other versions of the game with much better audio
are you sure you need to do this?

Any update? I really need the audio..
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-24T16:13:24+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

dont have time for research now, so here's a quick solution for you

this tool will extract IFF files from your bundle, just drop the bundle file onto it

you'll get about 3500 sound files

to convert those, you can use vgmtoolbox function "create GENH" with settings:

4 bit IMA ADPCM
header skip 0x28
channel = 1
freq = 8000 (or 11025, 22050) depending on file name
no loops

this will give you files playable with vgmstream

Or maybe you can find better way converting them.
[StarWars_Republic_Heroes.rar](https://xentaxbackup.github.io/file/10360_StarWars_Republic_Heroes.rar)
## Post #8
- Username: Kylor
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jan 09, 2016 2:59 am
- Post datetime: 2016-01-25T19:36:00+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

> Reply from daemon1
>
> dont have time for research now, so here's a quick solution for you

this tool will extract IFF files from your bundle, just drop the bundle file onto it

you'll get about 3500 sound files

to convert those, you can use vgmtoolbox function "create GENH" with settings:

4 bit IMA ADPCM
header skip 0x28
channel = 1
freq = 8000 (or 11025, 22050) depending on file name
no loops

this will give you files playable with vgmstream

Or maybe you can find better way converting them.

Downloaded the exe file, and dropped the bundle file onto it, the command prompt opened then it said the exe wasn't working:



I'm on Windows 8 x64
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-01-26T04:34:56+00:00
- Post Title: Star Wars The Clone Wars Republic Heroes .bundle

toc file must also be in the same folder
