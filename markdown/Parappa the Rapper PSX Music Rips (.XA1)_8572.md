## Post #1
- Username: HellFire2345
- Rank: Banned
- Number of posts: 13
- Joined date: Fri Dec 16, 2011 7:59 am
- Post datetime: 2012-03-17T02:15:29+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

I'd like to rip the music from Parappa the Rapper (The game is all about music), and I've already figured out how to get the sound effects from it, but I'm still trying to find the music. They're in what I'm assuming STAGE(stagenumber).XA1 files, considering the PSX reads XA sounds. I've tried opening them with average XA Players, but they don't read it correctly. Any ideas?

[http://dl.dropbox.com/u/66564653/STAGE2.XA1](http://dl.dropbox.com/u/66564653/STAGE2.XA1) (here's one of them)
## Post #2
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-03-17T05:26:00+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

jPSXdec is your solution. [http://kenai.com/projects/jpsxdec/pages/Home](http://kenai.com/projects/jpsxdec/pages/Home)
It is the most up-to-date player/ripper of audio/video/picture data from PSX images.

It will save XA1 as WAV, just make sure to scan the whole Iso, not just separate files, otherwise it won't recognize them.

Looks like for this game, each XA1 file contains several variations of the same track, STAGE2.XA1 for example had 6.

Here, all 6 of them converted to WAV: <link removed due forum rules violation>
## Post #3
- Username: Metroid1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 12, 2012 9:25 pm
- Post datetime: 2012-04-12T13:38:04+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

> Reply from MiLØ
>
> jPSXdec is your solution. http://kenai.com/projects/jpsxdec/pages/Home
It is the most up-to-date player/ripper of audio/video/picture data from PSX images.

It will save XA1 as WAV, just make sure to scan the whole Iso, not just separate files, otherwise it won't recognize them.

Looks like for this game, each XA1 file contains several variations of the same track, STAGE2.XA1 for example had 6.

Here, all 6 of them converted to WAV: http://www.mediafire.com/?3sr1c669c16q342
How do you do it? I've tried to extract the music from a PSX game, but all I get is sounds and voices in every video clip... I could also extract videos and images, but no trace of music. I can't seem to find a single music file at all using that program. Are they like hidden or something...? (And I know there's music in the game)

Would be nice of you if you could just make a mini-tutorial (in text) just how you did with the Parappa
## Post #4
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-04-20T03:06:46+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

Sure, ok so we luanch jPSXdec > Open And Analyze Disc Image > [it will scan for audio/video/picture data]

Now we see a file tree with 10 folders. Open the 2nd from the top (S9) by clicking the [+] sign to the left of it. 

Click [+] next to STAGE9.XA1

And inside of it we have:

STAGE9.XA1[0]
STAGE9.XA1[1]
STAGE9.XA1[2]
STAGE9.XA1[3]

Each one of those is a music track that lasts 2min 22sec. You can play them by switching (on a right hand side) from 'Save' tab to 'Play' and hitting the 'Play' button at the bottom.

And you can save each track as .WAV

For that make sure to put a check mark (on a left) in front of each of those tracks on a file tree. Go to 'Save' tab and hit 'Save All Selected' > 'Start'.

So just like these 4 tracks were inside STAGE9.XA1 the rest of the tracks are in their folders/stage.xa files accordingly.

For example S7 folder has 6 tracks inside STAGE7.XA1, S6 folder has 6 tracks inside STAGE6.XA1... etc

Hope this helps.
## Post #5
- Username: Metroid1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 12, 2012 9:25 pm
- Post datetime: 2012-04-20T20:05:13+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

> Reply from MiLØ
>
> Sure, ok so we luanch jPSXdec > Open And Analyze Disc Image > [it will scan for audio/video/picture data]

Now we see a file tree with 10 folders. Open the 2nd from the top (S9) by clicking the [+] sign to the left of it. 

Click [+] next to STAGE9.XA1

And inside of it we have:

STAGE9.XA1[0]
STAGE9.XA1[1]
STAGE9.XA1[2]
STAGE9.XA1[3]

Each one of those is a music track that lasts 2min 22sec. You can play them by switching (on a right hand side) from 'Save' tab to 'Play' and hitting the 'Play' button at the bottom.

And you can save each track as .WAV

For that make sure to put a check mark (on a left) in front of each of those tracks on a file tree. Go to 'Save' tab and hit 'Save All Selected' > 'Start'.

So just like these 4 tracks were inside STAGE9.XA1 the rest of the tracks are in their folders/stage.xa files accordingly.

For example S7 folder has 6 tracks inside STAGE7.XA1, S6 folder has 6 tracks inside STAGE6.XA1... etc

Hope this helps.

Here's how it looks when I open a PSX game. The sounds for the cutscenes is in dat10, which is the only XA1 files I could find. Guess the program can't help me...

Thanks for the tutorial, MiLØ.
## Post #6
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2012-05-08T20:25:03+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

Ya know....we have an CD-XA extractor in VGMToolbox 

Just drag and drop everything onto it.
## Post #7
- Username: BobbySteed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 31, 2014 10:48 am
- Post datetime: 2014-08-31T02:50:55+00:00
- Post Title: Parappa the Rapper PSX Music Rips (.XA1)

Both VGMToolbox CD-XA extractor and jPSXdec work but I can't find PaRappa's vocals using either. Anyone know where they are?
