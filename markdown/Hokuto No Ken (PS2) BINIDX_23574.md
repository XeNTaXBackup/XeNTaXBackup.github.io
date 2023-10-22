## Post #1
- Username: AyanamiRei0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 17, 2020 6:36 pm
- Post datetime: 2021-03-11T00:02:08+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

Hello there, I've been looking into extracting this game but unfortunately it's using compressed files like Arcsys releases on newer consoles.
Any help would be appreciated thanks!

Here's the sample files too.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1XHMbc5US227QxB7I3RLDlabGBz-SuXUf?usp=sharing)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-11T12:38:11+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

You mean PS2 game with title "Hokuto no Ken: Shinpan no Sōsōsei Kengō Retsuden" which is known also as Fist of the North Star, right?
And it is the main archive from that game?

And what are those Arcsys releases you were talking about?
## Post #3
- Username: AyanamiRei0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 17, 2020 6:36 pm
- Post datetime: 2021-03-11T15:11:37+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

Yeah that's the full name and yes that's those are the main archives in the game going from the size and with the compression PS3 releases of Persona 4 Arena and other games made or published by arcsys use AR Segs archives I believe that's what I meant by newer releases.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-11T15:33:59+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

Ok, so I was able to investigate your sample and here is the result
[http://wiki.xentax.com/index.php/Hokuto_no_Ken_BIN_IDX](http://wiki.xentax.com/index.php/Hokuto_no_Ken_BIN_IDX)

I have also created extractor for this archive
[https://github.com/bartlomiejduda/Tools ... DX_Tool.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Hokuto%20No%20Ken/Hokuto_no_ken_BIN_IDX_Tool.py)

It seems that files are not compressed or at least not all of them, bacause extracted VAG audio files can be played without any issues.
## Post #5
- Username: AyanamiRei0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 17, 2020 6:36 pm
- Post datetime: 2021-03-11T17:19:01+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

Sadly it appears the games music and other sound effects are within all those files and the python script doesn't seem to work them either and theres some dat files without any header info too.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-11T20:29:39+00:00
- Post Title: Hokuto No Ken (PS2) BIN/IDX

File format of main archive has been fully figured out as you can see on the wiki.
But to rip sound or do other stuff, you need to understand format of the files stored inside main archive.

It would be easier to do that with filenames for sure, but this type of archive doesn't store filenames,
so you could probably do some debugging to figure out what are those files for.
It is hard and time consuming, but if you are ready for challenge, you could start learning with these tutorials [viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
