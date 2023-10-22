## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-10-28T14:08:58+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Simple question, not so simple answer maybe:
Is there a way to join mono channels of MP3 files without re-encoding? If it's possible, I'll write a QuickBMS script.
Thanks for your help.

P.S.: I'm specifically searching for a way to join the mono channels from Deus Ex: Human Revolution.
## Post #2
- Username: RENIKRILL
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Feb 11, 2009 7:54 pm
- Post datetime: 2013-11-06T05:13:14+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Certainly is possible. SoX can help you out: [http://sourceforge.net/projects/sox/](http://sourceforge.net/projects/sox/) 
From the CLI, use the -M command

ex: sox.exe -M input_left.mp3 input_right.mp3 output.mp3
(where "input_left" is your left channel, and "input_right" is your right. Just to clarify   )

Hope this helps buddy.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2013-11-06T11:12:58+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Thanks a lot!!!
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-24T14:27:39+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Sorry to necro-post, but I've just now found the time to try the program. Trying to merge two mono files I get the error message:

"Unable to load MAD decoder library (libmad)"

How can I solve this?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-24T14:34:19+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Solved the problem, the files are downloadable here: [https://docs.google.com/file/d/0BxRalAl ... edit?pli=1](https://docs.google.com/file/d/0BxRalAlWlsgjclFzOTVKLTBGUnM/edit?pli=1)

HOWEVER, there's a new problem: I can't get sox to merge the channels without re-encoding - and I don't see any option to do so! Can anybody help me out? Is the program really able to do this?
## Post #6
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-24T21:51:34+00:00
- Post Title: MP3: mono to stereo without re-encoding?

I don't think it is possible to convert two mono mp3s into a joint-stereo one without re-encoding. You need the sum and difference of the audio data for joint-stereo and the only way I can think of to get these is by decoding the source streams (followed, obviously, by re-encoding the muxed stream). You might be able to convert to a multichannel MP3 with two channels by fixing the frame header flags and combining the data from each frame (or interleave the frames), but that's not trivial (it might not even be possible).

I haven't (yet) found any mp3 file which uses the multichannel type encoding for stereo files, and so I don't even know if existing decoders handle these correctly...

-Darkstar
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-24T22:46:11+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Of course joint-stereo is not possible but what about genuine stereo? Aren't the two channels on MP3 processed independently? Sorry for sounding like a dork...
## Post #8
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-25T14:39:13+00:00
- Post Title: MP3: mono to stereo without re-encoding?

As I said, I've never seen an actual (non-joint-)stereo mp3 file. [Here](http://cutebugs.net/files/mpeg-drafts/11172-3.pdf)'s a draft of the Layer III bitstream spec, maybe you (or someone else) finds the answer you need in there
## Post #9
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-01-25T15:28:04+00:00
- Post Title: MP3: mono to stereo without re-encoding?

Something like this?

> Create a stereo output from two mono inputs:
>
> Code: Select allffmpeg -i left.mp3 -i right.mp3 -ac 2 output.wav
>
> or with the amerge audio filter:
>
> Code: Select allffmpeg -i left.mp3 -i right.mp3 -filter_complex amerge output.mka
[https://trac.ffmpeg.org/wiki/AudioChann ... monostereo](https://trac.ffmpeg.org/wiki/AudioChannelManipulation#a2monostereo)
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-01-25T15:44:01+00:00
- Post Title: MP3: mono to stereo without re-encoding?

without re-encoding! That includes decoding as well...

Seems there's no actual possibility. :-\
