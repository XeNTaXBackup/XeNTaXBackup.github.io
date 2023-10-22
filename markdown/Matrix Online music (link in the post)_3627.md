## Post #1
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-03T14:12:52+00:00
- Post Title: Matrix Online music (link in the post)

(UPDATE : PARTIAL SOLUTION in post Thu Aug 06, 2009 5:50 pm)

Well, the music of this game looks like a bit complicated and sliced up. 
please help, how can we put this together to a single music file?

additional info: the music files are also in a strange .wav format as:

-they are sliced up to pieces, almost all piece ending with fade out
-many but not all accompanied by a .sgt file (that probably controls where the fading starts??)
-winamp wont play them, only windows media player

here is one music , one of the main themes:

[http://vegpage.net63.net/music/music.zip](http://vegpage.net63.net/music/music.zip)
(12 megabyte)

please help, how can we put this together to a single music file?

(UPDATE : PARTIAL SOLUTION in post Thu Aug 06, 2009 5:50 pm)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-03T15:35:43+00:00
- Post Title: Matrix Online music (link in the post)

File is down.
## Post #3
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-03T18:33:17+00:00
- Post Title: Matrix Online music (link in the post)

fixed  sorry
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-03T20:37:47+00:00
- Post Title: Matrix Online music (link in the post)

Is this all the music in the game?

About the sequences damn not again, i saw this also in red faction guerilla, it requires cutting of the endings right at the exact loop point where the msuic is suppose to transsition into the next segment.

very time consuming.
## Post #5
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-03T20:54:56+00:00
- Post Title: Matrix Online music (link in the post)

there are more music, but they are all in like this sliced up form

is there any chance that those .sgt files have info in them, to help automatising the cutting task?
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-03T22:03:25+00:00
- Post Title: Matrix Online music (link in the post)

Nope no infos about the fade start. but im not entirely sure. Another way is to use audacity and kinda stack up the tracks sequenctually. like when the first track is about to fadeout, put the other segment under the fadestart point and that will transistion right into the snext segment, obscurign the fadeout.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-03T22:27:39+00:00
- Post Title: Matrix Online music (link in the post)

It's a riff-wave-mp3, you can convert with ffmpeg, in minds it's a wave "container" with mp3 codec inside, you can reconvert with dbpoweramp too
[http://ffmpeg.arrozcru.org/wiki/index.php?title=Links](http://ffmpeg.arrozcru.org/wiki/index.php?title=Links)
and
[http://www.dbpoweramp.com](http://www.dbpoweramp.com)

for ffmpeg use

```

```


see?

```
Duration: 00:00:09.12, bitrate: 127 kb/s
Stream #0.0: Audio: mp3, 44100 Hz, stereo, s16, 128 kb/s

```


You can reconvert to wav-mp3 again with ffmpeg using .wav instead .mp3, like:

```

```

 

PS: This post must be in audio section, right?
## Post #8
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-03T23:06:06+00:00
- Post Title: Matrix Online music (link in the post)

Thank you for your help, but what is your goal with all these converting?
We want to merge them, not convert... At least I don't understand how
converting can help the merging.

There are .sgt files that belong to game file research if these are to help the
merging, this is also what we'd like to find out.
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-08-04T06:14:28+00:00
- Post Title: Matrix Online music (link in the post)

I read this..

> Well, the music of this game looks like a bit complicated.
>
> the music files in a strange .wav format as:
>
> -winamp wont play them, only windows media player
Now we/i know what codec it's used and how...about merging i'm looking this.
## Post #10
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-04T11:45:27+00:00
- Post Title: Matrix Online music (link in the post)

yeah, you are right, that wasn't the actual question, that was like a foreword, like an additional detail. 
sorry about that confusion. 

what we really need is, to know if it possible to determine the start of fading from the .sgt files
(or are the .sgt files in any way helping in the merging?)
please help if you can
## Post #11
- Username: Edvinke
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 11, 2007 5:02 pm
- Post datetime: 2009-08-06T16:50:34+00:00
- Post Title: Matrix Online music (link in the post)

Ok, here is an update:
(Courtesy of BakuraRyou, thank you!)

1.
For a bit glitchy and timing error versions, here are all the songs from MxO:
[http://www.mxoarchive.net/music.html](http://www.mxoarchive.net/music.html)

2. Now lets try to make the proper ones:
It turns out that the .sgt files are DirectMusic Producer Segments Type files,
which can be opened by DirectMusic Producer:
[http://www.microsoft.com/downloads/deta ... laylang=en](http://www.microsoft.com/downloads/details.aspx?FamilyID=07F29CE2-1C03-4AEF-B5B0-CBDAF07AF08D&displaylang=en)

you highlight all the consecutive wavs and sgt-s and drop into DM Producer, and turn on the small clock button,
and make sure the "snap to" is turned on, when you hover your mouse to the thicker vertical lines,
now you will have the exact times where the fading starts, displayed in the bottom right corner:



When the interval between tracks remains the same, all the tracks are referenced in the one .sgt file, 
but when the interval changes a new .sgt file is used. Using DirectMusic as a guide, I assembled them in Audacity thusly:



here I think the remainders shouldn't be left in the track, they should be cut out, as I don't remember in the
original songs the loud fade out effect to be present. (the same problem is with the mxoarchive tracks)

Now there is only 1 problem left, the segments DON'T START at 0:00, they have a short silence
at the beginning.

Please, if you know how to deduce the STARTING time of the segments from the sgt-s, then HELP!!!
(I think these are custom sgt-s as the producer itself do not play the tracks as they were in the game
ie. loud fade out effect is present)
