## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-17T17:04:13+00:00
- Post Title: demultiplexing BIK videos

Ok, this is something that is long overdue I think. Since the bik format is supported by no standard programs, I'd like to see a possibility to demultiplex those videos into BIK video and BIK audio. It really bugs me that I only can decode the audio to uncompressed PCM and not leave it in its original format because it takes too much disk space AND I'd like to archive the original audio streams.
How do demux the videos isn't important (QuickBMS, some stand-alone tool etc.).
Does anyone know the specs and is able to program a demuxer?
Thanks for your help!
## Post #2
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-02-17T18:40:44+00:00
- Post Title: demultiplexing BIK videos

I don't know of tools to completely demultiplex BIKs into audio + video streams, but here's a little info that you might useful.
The latest BIK files tend to have more than 1 audio track in them (dialog, stereo & mono, front left & right audio channels, rear left & right audio channels, etc..). Open up Rad Video Tools and select one of the cutscenes, then click the "File info" button, you'll see how many audio tracks are in there (could be 2, 4 or more). And than to extract them all separately into WAVs we can use the "batch" option with "Convert a file" function.

On how to do it properly, I advise you to look into this: [http://infectionist.com/forum/viewtopic ... highlight=](http://infectionist.com/forum/viewtopic.php?t=2547&start=0&postdays=0&postorder=asc&highlight=) 
It gets to the topic of bik files starting with post #6.
(I hope it's ok to link to another forum here).
The guy over there showed me the way how to extract multiple audio tracks from BIKs.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-02-17T20:45:18+00:00
- Post Title: demultiplexing BIK videos

Yep, that doesn't help. Nothing new here...
## Post #4
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-06-29T18:10:48+00:00
- Post Title: demultiplexing BIK videos

[VGMToolbox r879](https://sourceforge.net/projects/vgmtoolbox/) now supports demultiplexing Bink BIK files.

At this time, RAD Video Tools (binkplay.exe) does not seem to support files containing only one audio stream (and no video stream). Also, when no video stream is present, the "last" audio stream does not seem to play (try experimenting with "Advanced play" to observe this behavior).  I think these are both symptoms of the same issue.

Use the RAD Video Tools "Convert a file" tool (binkconv.exe) to output the audio to a WAV file. It seems to function properly for all audio streams.

I have begun testing if adding a "dummy" audio stream to work around this behavior will fix binkplay.exe playback, but it will take some time and may not even work.

Many thanks to Timo for testing, etc...
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2014-10-23T18:16:43+00:00
- Post Title: demultiplexing BIK videos

Sorry, I must necropost here...
What about the new bk2 format? It's an updated version of bik that isn't supported yet.
## Post #6
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2015-05-30T03:30:08+00:00
- Post Title: demultiplexing BIK videos

I've added Bink2 support to [VGMToolbox r972](http://sourceforge.net/projects/vgmtoolbox/).  I haven't had a big amount of samples to test with, but it seems to work with both single and multi-track audio files.  Thanks to AlphaTwentyThree for the initial round of testing.

If anyone discovers files that do not demux correctly, please let me know, as I'd like to make it as compatible as possible with all Bink2 variants.
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2015-05-30T05:53:50+00:00
- Post Title: demultiplexing BIK videos

A little impatient, are we? 
I'll run some more tests later!
## Post #8
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-09-05T17:38:01+00:00
- Post Title: demultiplexing BIK videos

you can easily convert .bik to png sequence via ffmpeg or convert it
## Post #9
- Username: planedec50
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 08, 2015 1:12 am
- Post datetime: 2015-09-06T12:14:19+00:00
- Post Title: demultiplexing BIK videos

vladik they are trying to seperate audio from the bik stream not convert to video
## Post #10
- Username: vladik4kides
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jun 18, 2015 12:36 am
- Post datetime: 2015-09-20T09:23:17+00:00
- Post Title: demultiplexing BIK videos

> Reply from planedec50
>
> vladik they are trying to seperate audio from the bik stream not convert to video
ohh kkk
